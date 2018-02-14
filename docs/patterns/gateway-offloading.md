---
title: "Modèle de déchargement de passerelle"
description: "Déchargez des fonctionnalités de service partagé ou spécialisé sur un proxy de passerelle."
author: dragon119
ms.date: 06/23/2017
ms.openlocfilehash: 6b3e4541aae77349ca91c18c788ddb508912361d
ms.sourcegitcommit: b0482d49aab0526be386837702e7724c61232c60
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2017
---
# <a name="gateway-offloading-pattern"></a><span data-ttu-id="8f34b-103">Modèle de déchargement de passerelle</span><span class="sxs-lookup"><span data-stu-id="8f34b-103">Gateway Offloading pattern</span></span>

<span data-ttu-id="8f34b-104">Déchargez des fonctionnalités de service partagé ou spécialisé sur un proxy de passerelle.</span><span class="sxs-lookup"><span data-stu-id="8f34b-104">Offload shared or specialized service functionality to a gateway proxy.</span></span> <span data-ttu-id="8f34b-105">Ce modèle peut simplifier le développement d’applications en déplaçant les fonctionnalités de service partagé, comme l’utilisation des certificats SSL, d’autres parties de l’application vers la passerelle.</span><span class="sxs-lookup"><span data-stu-id="8f34b-105">This pattern can simplify application development by moving shared service functionality, such as the use of SSL certificates, from other parts of the application into the gateway.</span></span>

## <a name="context-and-problem"></a><span data-ttu-id="8f34b-106">Contexte et problème</span><span class="sxs-lookup"><span data-stu-id="8f34b-106">Context and problem</span></span>

<span data-ttu-id="8f34b-107">Certaines fonctionnalités sont couramment utilisées dans plusieurs services et elles doivent être configurées, gérées et maintenues.</span><span class="sxs-lookup"><span data-stu-id="8f34b-107">Some features are commonly used across multiple services, and these features require configuration, management, and maintenance.</span></span> <span data-ttu-id="8f34b-108">Un service partagé ou spécialisé qui est distribué avec chaque déploiement d’application augmente la surcharge administrative et accroît la probabilité qu’une erreur de déploiement se produise.</span><span class="sxs-lookup"><span data-stu-id="8f34b-108">A shared or specialized service that is distributed with every application deployment increases the administrative overhead and increases the likelihood of deployment error.</span></span> <span data-ttu-id="8f34b-109">Les mises à jour d’une fonctionnalité partagée doivent être déployées sur tous les services qui partagent cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="8f34b-109">Any updates to a shared feature must be deployed across all services that share that feature.</span></span>

<span data-ttu-id="8f34b-110">Gérer correctement des problèmes de sécurité (validation de jeton, chiffrement, gestion de certificats SSL) et d’autres tâches complexes peut exiger que les membres de l’équipe soient extrêmement spécialisés.</span><span class="sxs-lookup"><span data-stu-id="8f34b-110">Properly handling security issues (token validation, encryption, SSL certificate management) and other complex tasks can require team members to have highly specialized skills.</span></span> <span data-ttu-id="8f34b-111">Par exemple, un certificat requis par une application doit être configuré et déployé sur toutes les instances de l’application.</span><span class="sxs-lookup"><span data-stu-id="8f34b-111">For example, a certificate needed by an application must be configured and deployed on all application instances.</span></span> <span data-ttu-id="8f34b-112">Avec chaque nouveau déploiement, le certificat doit être géré pour garantir qu’il n’expire pas.</span><span class="sxs-lookup"><span data-stu-id="8f34b-112">With each new deployment, the certificate must be managed to ensure that it does not expire.</span></span> <span data-ttu-id="8f34b-113">Les certificats courants sur le point d’expirer doivent être mis à jour, testés et vérifiés sur chaque déploiement d’application.</span><span class="sxs-lookup"><span data-stu-id="8f34b-113">Any common certificate that is due to expire must be updated, tested, and verified on every application deployment.</span></span>

<span data-ttu-id="8f34b-114">D’autres services courants comme l’authentification, l’autorisation, la journalisation, la surveillance ou la [limitation](./throttling.md) peuvent être difficiles à implémenter et à gérer dans un grand nombre de déploiements.</span><span class="sxs-lookup"><span data-stu-id="8f34b-114">Other common services such as authentication, authorization, logging, monitoring, or [throttling](./throttling.md) can be difficult to implement and manage across a large number of deployments.</span></span> <span data-ttu-id="8f34b-115">Il peut être préférable de consolider ce type de fonctionnalité, afin de réduire la surcharge et les risques d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="8f34b-115">It may be better to consolidate this type of functionality, in order to reduce overhead and the chance of errors.</span></span>

## <a name="solution"></a><span data-ttu-id="8f34b-116">Solution</span><span class="sxs-lookup"><span data-stu-id="8f34b-116">Solution</span></span>

<span data-ttu-id="8f34b-117">Déchargez certaines fonctionnalités sur une passerelle d’API, particulièrement les questions transversales comme la gestion des certificats, l’authentification, la terminaison SSL, la surveillance, la traduction de protocole ou la limitation.</span><span class="sxs-lookup"><span data-stu-id="8f34b-117">Offload some features into an API gateway, particularly cross-cutting concerns such as certificate management, authentication, SSL termination, monitoring, protocol translation, or throttling.</span></span> 

<span data-ttu-id="8f34b-118">Le schéma suivant montre une passerelle d’API qui termine les connexions SSL entrantes.</span><span class="sxs-lookup"><span data-stu-id="8f34b-118">The following diagram shows an API gateway that terminates inbound SSL connections.</span></span> <span data-ttu-id="8f34b-119">Il demande des données pour le compte du demandeur d’origine à partir d’un serveur HTTP en amont de la passerelle d’API.</span><span class="sxs-lookup"><span data-stu-id="8f34b-119">It requests data on behalf of the original requestor from any HTTP server upstream of the API gateway.</span></span>

 ![](./_images/gateway-offload.png)
 
<span data-ttu-id="8f34b-120">Ce modèle présente les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="8f34b-120">Benefits of this pattern include:</span></span>

- <span data-ttu-id="8f34b-121">Simplifiez le développement de services en supprimant le besoin de distribution et de maintien des ressources de prise en charge, comme les certificats de serveur web et la configuration des sites web sécurisés.</span><span class="sxs-lookup"><span data-stu-id="8f34b-121">Simplify the development of services by removing the need to distribute and maintain supporting resources, such as web server certificates and configuration for secure websites.</span></span> <span data-ttu-id="8f34b-122">Une configuration plus simple permet une gestion et une extensibilité plus aisées, à l’instar des mises à niveau des services.</span><span class="sxs-lookup"><span data-stu-id="8f34b-122">Simpler configuration results in easier management and scalability and makes service upgrades simpler.</span></span>

- <span data-ttu-id="8f34b-123">Offrez aux équipes dédiées la possibilité d’implémenter des fonctionnalités qui nécessitent une expertise particulière telle que la sécurité.</span><span class="sxs-lookup"><span data-stu-id="8f34b-123">Allow dedicated teams to implement features that require specialized expertise, such as security.</span></span> <span data-ttu-id="8f34b-124">Cela permet à votre équipe métier de se concentrer sur les fonctionnalités de l’application et de laisser les experts traiter les problèmes propres à leur domaine.</span><span class="sxs-lookup"><span data-stu-id="8f34b-124">This allows your core team to focus on the application functionality, leaving these specialized but cross-cutting concerns to the relevant experts.</span></span>

- <span data-ttu-id="8f34b-125">Offrez une certaine cohérence pour la surveillance et la journalisation des requêtes et des réponses.</span><span class="sxs-lookup"><span data-stu-id="8f34b-125">Provide some consistency for request and response logging and monitoring.</span></span> <span data-ttu-id="8f34b-126">Même si un service n’est pas correctement instrumenté, la passerelle peut être configurée pour assurer un niveau minimal de surveillance et de journalisation.</span><span class="sxs-lookup"><span data-stu-id="8f34b-126">Even if a service is not correctly instrumented, the gateway can be configured to ensure a minimum level of monitoring and logging.</span></span>

## <a name="issues-and-considerations"></a><span data-ttu-id="8f34b-127">Problèmes et considérations</span><span class="sxs-lookup"><span data-stu-id="8f34b-127">Issues and considerations</span></span>

- <span data-ttu-id="8f34b-128">Vérifiez que la passerelle d’API est hautement disponible et résistante à l’échec.</span><span class="sxs-lookup"><span data-stu-id="8f34b-128">Ensure the API gateway is highly available and resilient to failure.</span></span> <span data-ttu-id="8f34b-129">Évitez les points de défaillance uniques en exécutant plusieurs instances de votre passerelle d’API.</span><span class="sxs-lookup"><span data-stu-id="8f34b-129">Avoid single points of failure by running multiple instances of your API gateway.</span></span> 
- <span data-ttu-id="8f34b-130">Assurez-vous que la passerelle est conçue pour répondre aux besoins en termes de capacité et de mise à l’échelle de votre application et de vos points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="8f34b-130">Ensure the gateway is designed for the capacity and scaling requirements of your application and endpoints.</span></span> <span data-ttu-id="8f34b-131">Vérifiez que la passerelle ne se transforme pas en goulot d’étranglement pour l’application et qu’elle est suffisamment évolutive.</span><span class="sxs-lookup"><span data-stu-id="8f34b-131">Make sure the gateway does not become a bottleneck for the application and is sufficiently scalable.</span></span>
- <span data-ttu-id="8f34b-132">Déchargez uniquement les fonctionnalités qui sont utilisées par l’intégralité de l’application, telles que la sécurité ou le transfert de données.</span><span class="sxs-lookup"><span data-stu-id="8f34b-132">Only offload features that are used by the entire application, such as security or data transfer.</span></span>
- <span data-ttu-id="8f34b-133">La logique métier ne doit jamais être déchargée vers la passerelle d’API.</span><span class="sxs-lookup"><span data-stu-id="8f34b-133">Business logic should never be offloaded to the API gateway.</span></span> 
- <span data-ttu-id="8f34b-134">Si vous avez besoin de suivre des transactions, envisagez de générer des ID de corrélation à des fins de journalisation.</span><span class="sxs-lookup"><span data-stu-id="8f34b-134">If you need to track transactions, consider generating correlation IDs for logging purposes.</span></span>

## <a name="when-to-use-this-pattern"></a><span data-ttu-id="8f34b-135">Quand utiliser ce modèle</span><span class="sxs-lookup"><span data-stu-id="8f34b-135">When to use this pattern</span></span>

<span data-ttu-id="8f34b-136">Utilisez ce modèle dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="8f34b-136">Use this pattern when:</span></span>

- <span data-ttu-id="8f34b-137">Un déploiement d’application qui a un problème partagé comme les certificats SSL ou le chiffrement.</span><span class="sxs-lookup"><span data-stu-id="8f34b-137">An application deployment has a shared concern such as SSL certificates or encryption.</span></span>
- <span data-ttu-id="8f34b-138">Une fonctionnalité commune à plusieurs déploiements d’application qui peuvent avoir différents besoins en matière de ressources, comme des ressources de mémoire, une capacité de stockage ou des connexions réseau.</span><span class="sxs-lookup"><span data-stu-id="8f34b-138">A feature that is common across application deployments that may have different resource requirements, such as memory resources, storage capacity or network connections.</span></span>
- <span data-ttu-id="8f34b-139">Vous souhaitez confier la responsabilité des problèmes comme la sécurité réseau, la limitation ou d’autres soucis de limites réseau à une équipe plus spécialisée.</span><span class="sxs-lookup"><span data-stu-id="8f34b-139">You wish to move the responsibility for issues such as network security, throttling, or other network boundary concerns to a more specialized team.</span></span>

<span data-ttu-id="8f34b-140">Ce modèle peut ne pas convenir s’il introduit le couplage entre les services.</span><span class="sxs-lookup"><span data-stu-id="8f34b-140">This pattern may not be suitable if it introduces coupling across services.</span></span>

## <a name="example"></a><span data-ttu-id="8f34b-141">Exemple</span><span class="sxs-lookup"><span data-stu-id="8f34b-141">Example</span></span>

<span data-ttu-id="8f34b-142">Avec Nginx en tant qu’appliance de déchargement SSL, la configuration suivante termine une connexion SSL entrante et la distribue à l’un des trois serveurs HTTP en amont.</span><span class="sxs-lookup"><span data-stu-id="8f34b-142">Using Nginx as the SSL offload appliance, the following configuration terminates an inbound SSL connection and distributes the connection to one of three upstream HTTP servers.</span></span>

```
upstream iis {
        server  10.3.0.10    max_fails=3    fail_timeout=15s;
        server  10.3.0.20    max_fails=3    fail_timeout=15s;
        server  10.3.0.30    max_fails=3    fail_timeout=15s;
}

server {
        listen 443;
        ssl on;
        ssl_certificate /etc/nginx/ssl/domain.cer;
        ssl_certificate_key /etc/nginx/ssl/domain.key;

        location / {
                set $targ iis;
                proxy_pass http://$targ;
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
                proxy_set_header X-Forwarded-Proto https;
proxy_set_header X-Real-IP $remote_addr;
                proxy_set_header Host $host;
        }
}
```

## <a name="related-guidance"></a><span data-ttu-id="8f34b-143">Aide connexe</span><span class="sxs-lookup"><span data-stu-id="8f34b-143">Related guidance</span></span>

- <span data-ttu-id="8f34b-144">[Backends for Frontends pattern](./backends-for-frontends.md) (Modèle de services principaux destinés aux frontaux)</span><span class="sxs-lookup"><span data-stu-id="8f34b-144">[Backends for Frontends pattern](./backends-for-frontends.md)</span></span>
- <span data-ttu-id="8f34b-145">[Gateway Aggregation pattern](./gateway-aggregation.md) (Modèle d’agrégation de passerelle)</span><span class="sxs-lookup"><span data-stu-id="8f34b-145">[Gateway Aggregation pattern](./gateway-aggregation.md)</span></span>
- [<span data-ttu-id="8f34b-146">Modèle de routage de passerelle</span><span class="sxs-lookup"><span data-stu-id="8f34b-146">Gateway Routing pattern</span></span>](./gateway-routing.md)
