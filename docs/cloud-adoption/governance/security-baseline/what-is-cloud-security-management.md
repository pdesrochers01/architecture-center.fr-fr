---
title: 'Framework d’adoption du cloud : Qu’est-ce que la base de référence de la sécurité'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
ms.service: architecture-center
ms.subservice: enterprise-cloud-adoption
ms.custom: governance
ms.date: 10/10/2018
description: Qu’est-ce que la base de référence de la sécurité ?
author: BrianBlanchard
ms.openlocfilehash: cb6e3372fd76486e5c4467ef822163eac0499573
ms.sourcegitcommit: 273e690c0cfabbc3822089c7d8bc743ef41d2b6e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55900930"
---
<!-- markdownlint-disable MD026 -->

# <a name="what-is-the-cloud-security-baseline"></a><span data-ttu-id="d57c4-103">Qu’est-ce que la base de référence de la sécurité ?</span><span class="sxs-lookup"><span data-stu-id="d57c4-103">What is the Cloud Security Baseline?</span></span>

<span data-ttu-id="d57c4-104">Cet article introductif présente la base de référence de la sécurité de manière générale. Cette notion repose sur les [cinq disciplines de la gouvernance cloud](../governance-disciplines.md) et permet d’établir un cadre de gouvernance.</span><span class="sxs-lookup"><span data-stu-id="d57c4-104">This is an introductory article on the general topic of Cloud Security Baseline which builds on the [Five Disciplines of Cloud Governance](../governance-disciplines.md) to establish a governance framework.</span></span> <span data-ttu-id="d57c4-105">Des informations plus détaillées sur la sécurité du cloud sont disponibles dans le [cloud approuvé d’Azure](https://azure.microsoft.com/overview/trusted-cloud/).</span><span class="sxs-lookup"><span data-stu-id="d57c4-105">More detailed information about Cloud Security is available from [Azure's Trusted Cloud](https://azure.microsoft.com/overview/trusted-cloud/).</span></span> <span data-ttu-id="d57c4-106">Des approches pour améliorer l’état de sécurité de vos organisations sont disponibles dans le [catalogue des services de sécurité cloud](https://www.microsoft.com/security/information-protection).</span><span class="sxs-lookup"><span data-stu-id="d57c4-106">Approaches to improving your organizations security posture can be found in the [Cloud Security Service Catalog](https://www.microsoft.com/security/information-protection)</span></span>

> [!NOTE]
> <span data-ttu-id="d57c4-107">Cet article n’a pas été conçu pour fournir le contexte nécessaire au lecteur pour qu’il puisse implémenter une stratégie de sécurité.</span><span class="sxs-lookup"><span data-stu-id="d57c4-107">This article is not expected to provide enough context to allow the reader to implement a security strategy.</span></span> <span data-ttu-id="d57c4-108">Il cherche uniquement à familiariser le lecteur au sujet.</span><span class="sxs-lookup"><span data-stu-id="d57c4-108">It is for general awareness only.</span></span>

## <a name="cloud-security"></a><span data-ttu-id="d57c4-109">Sécurité cloud</span><span class="sxs-lookup"><span data-stu-id="d57c4-109">Cloud security</span></span>

<span data-ttu-id="d57c4-110">La sécurité cloud est une extension des pratiques traditionnelles destinées à protéger les informations.</span><span class="sxs-lookup"><span data-stu-id="d57c4-110">Cloud security is an extension of traditional information security practices.</span></span> <span data-ttu-id="d57c4-111">La sécurité informatique traditionnelle englobe les stratégies et contrôles permettant de surveiller la sécurité des ordinateurs, la sécurité du réseau, la protection des données, l’utilisation des informations, etc.</span><span class="sxs-lookup"><span data-stu-id="d57c4-111">Traditional IT security would include policies and controls governing computer security, network security, data protection, information usage, and so forth.</span></span> <span data-ttu-id="d57c4-112">Ces mêmes stratégies et contrôles sont nécessaires dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="d57c4-112">These same policies and controls are needed in the cloud.</span></span> <span data-ttu-id="d57c4-113">Pendant la transformation cloud, il est impératif que le chef de la sécurité des systèmes soit activement impliqué et qu’il comprenne le paysage cloud, afin de s’assurer que les stratégies informatiques héritées sont mappées à des niveaux de contrôle corrects dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="d57c4-113">During any Cloud Transformation, it is imperative that the CISO be actively involved and understand the cloud landscape, to ensure legacy IT policies map to proper levels of control in the cloud.</span></span>

<span data-ttu-id="d57c4-114">Toute stratégie de sécurité cloud doit au moins prendre en compte les points suivants :</span><span class="sxs-lookup"><span data-stu-id="d57c4-114">At minimum, any cloud security strategy should consider the following topics:</span></span>

* <span data-ttu-id="d57c4-115">Classification des données : Une classification correcte des données est nécessaire pour comprendre toutes les sources de données privées, protégées ou hautement confidentielles.</span><span class="sxs-lookup"><span data-stu-id="d57c4-115">Classify data: Proper data classification to understand any data sources that are private, protected, or highly confidential.</span></span> <span data-ttu-id="d57c4-116">Elle vous aide à gérer les risques pendant la planification.</span><span class="sxs-lookup"><span data-stu-id="d57c4-116">This will help manage risk during planning.</span></span>
* <span data-ttu-id="d57c4-117">Planification d’un scénario de cloud hybride : Comprendre comment les réseaux locaux hérités se connecteront au cloud aide le chef de la sécurité des systèmes à identifier et réduire les risques.</span><span class="sxs-lookup"><span data-stu-id="d57c4-117">Plan for a hybrid cloud scenario: Understanding how legacy, on-premise networks will connect to the cloud will help the CISO identify and mitigate risks.</span></span>
* <span data-ttu-id="d57c4-118">Planification des attaques et des erreurs : Durant les premiers mois d’une transformation, l’équipe apprendra tout en faisant des erreurs.</span><span class="sxs-lookup"><span data-stu-id="d57c4-118">Plan for attacks and mistakes: In the first few months of a transformation, mistakes will be made as the team learns.</span></span> <span data-ttu-id="d57c4-119">Commencez par des déploiements avec peu de risques et hautement restreints pour apprendre en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="d57c4-119">Start with low risk and highly restricted deployments to learn securely.</span></span>
* <span data-ttu-id="d57c4-120">Hiérarchisation de la confidentialité : Pendant la transformation, toute l’équipe doit mettre la vie privée des clients et des employés au cœur de ses préoccupations.</span><span class="sxs-lookup"><span data-stu-id="d57c4-120">Prioritize privacy: Throughout any transformation, the entire team should keep customer and employee privacy top of mind.</span></span> <span data-ttu-id="d57c4-121">Dans le cloud, vos données sont protégées. Toutefois, l’équipe doit faire particulièrement attention lorsqu’elle s’occupe de données sensibles.</span><span class="sxs-lookup"><span data-stu-id="d57c4-121">Your data is safe in the cloud, but the team should be aware and extra cautious when dealing with sensitive data.</span></span>

## <a name="protecting-data-and-privacy"></a><span data-ttu-id="d57c4-122">Protection des données et de la confidentialité</span><span class="sxs-lookup"><span data-stu-id="d57c4-122">Protecting data and privacy</span></span>

<span data-ttu-id="d57c4-123">Pour les organisations du monde entier, &mdash;que ce soit des gouvernements, des organismes à but non lucratif ou des entreprises&mdash;, le cloud computing est désormais un composant essentiel de leur stratégie informatique continuelle.</span><span class="sxs-lookup"><span data-stu-id="d57c4-123">For organizations throughout the world &mdash; whether governments, nonprofits, or businesses &mdash; cloud computing has become a key part of their ongoing IT strategy.</span></span> <span data-ttu-id="d57c4-124">Les services cloud permettent aux organisations de toutes tailles de bénéficier d’un stockage de données quasiment illimité, tout en leur évitant d’avoir à acheter, entretenir et mettre à jour leurs propres réseaux et systèmes informatiques.</span><span class="sxs-lookup"><span data-stu-id="d57c4-124">Cloud services give organizations of all sizes access to virtually unlimited data storage while freeing them from the need to purchase, maintain, and update their own networks and computer systems.</span></span> <span data-ttu-id="d57c4-125">Microsoft et d’autres fournisseurs de cloud offrent une infrastructure informatique, une plateforme et un service SaaS (software as a service), qui permettent aux clients de faire évoluer à la hausse ou à la baisse rapidement, et de ne payer que pour la puissance informatique et le stockage qu’ils utilisent.</span><span class="sxs-lookup"><span data-stu-id="d57c4-125">Microsoft and other cloud providers offer IT infrastructure, platform, and software as a service (SaaS), enabling customers to quickly scale up or down as needed and only paying for the computing power and storage they use.</span></span>

<span data-ttu-id="d57c4-126">Toutefois, si les organisations continuent de profiter des avantages des services cloud (plus de choix, d’agilité et de flexibilité, stimulation de l’efficacité, et réduction des coûts informatiques), elles doivent également se rendre compte que l’introduction des services cloud nuit à la confidentialité, la sécurité et la conformité.</span><span class="sxs-lookup"><span data-stu-id="d57c4-126">However, as organizations continue to take advantage of the benefits of cloud services, such as increased choice, agility, and flexibility while boosting efficiency and lowering IT cost, they must consider how the introduction of cloud services affects their privacy, security, and compliance posture.</span></span> <span data-ttu-id="d57c4-127">Microsoft s’est efforcé de proposer des offres cloud non seulement évolutives, fiables et gérables, mais également capables d’assurer la protection et l’utilisation des données client de manière transparente.</span><span class="sxs-lookup"><span data-stu-id="d57c4-127">Microsoft has worked to make their cloud offerings not only scalable, reliable, and manageable, but also to ensure our customers data is protected and used in a transparent manner.</span></span>

<span data-ttu-id="d57c4-128">La sécurité est un composant essentiel dans la protection robuste des données, pour tous les environnements informatiques en ligne.</span><span class="sxs-lookup"><span data-stu-id="d57c4-128">Security is an essential component of strong data safeguards in all online computing environments.</span></span> <span data-ttu-id="d57c4-129">Toutefois, la sécurité à elle toute seule n’est pas suffisante.</span><span class="sxs-lookup"><span data-stu-id="d57c4-129">But security alone is not sufficient.</span></span> <span data-ttu-id="d57c4-130">La volonté des clients et des entreprises à utiliser un produit de cloud computing en particulier dépend également de la capacité du client ou de l’entreprise à croire que la confidentialité de leurs informations sera préservée par ce produit, et que leurs données seront uniquement utilisées conformément à leurs attentes.</span><span class="sxs-lookup"><span data-stu-id="d57c4-130">Consumers’ and businesses’ willingness to use a particular cloud computing product also depends on their ability to trust that the privacy of their information will be protected, and that their data will only be used in a manner consistent with customer expectations.</span></span> <span data-ttu-id="d57c4-131">Apprenez-en davantage sur l’approche de Microsoft en matière de [protection des données et confidentialité dans le cloud ](https://go.microsoft.com/fwlink/?LinkId=808242&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="d57c4-131">Learn more about Microsoft's approach to [Protecting data and privacy in the cloud](https://go.microsoft.com/fwlink/?LinkId=808242&clcid=0x409)</span></span>

## <a name="risk-mitigation"></a><span data-ttu-id="d57c4-132">Atténuation des risques</span><span class="sxs-lookup"><span data-stu-id="d57c4-132">Risk mitigation</span></span>

<span data-ttu-id="d57c4-133">Les deux risques principaux dans un centre de données peuvent provenir de deux sources différentes : le vieillissement des systèmes et les erreurs humaines.</span><span class="sxs-lookup"><span data-stu-id="d57c4-133">The two greatest risks in any datacenter can be grouped into two sources: Aging systems and Human error.</span></span> <span data-ttu-id="d57c4-134">Lors de la définition d’une stratégie de sécurité informatique, le minimum est de se protéger contre ces deux risques.</span><span class="sxs-lookup"><span data-stu-id="d57c4-134">Protecting against these two risks is a minimum when defining an IT security strategy.</span></span> <span data-ttu-id="d57c4-135">Et c’est exactement la même chose dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="d57c4-135">The same is true in the cloud.</span></span> <span data-ttu-id="d57c4-136">Voici quelques exemples de contrôles que vous pouvez mettre en place pour atténuer les risques et renforcer votre stratégie de sécurité cloud.</span><span class="sxs-lookup"><span data-stu-id="d57c4-136">The following are a few examples of controls that can be put in place to mitigate risks and strengthen your Cloud Security strategy.</span></span>

* <span data-ttu-id="d57c4-137">Systèmes hérités : Beaucoup de composants dans les centres de données locaux sont des logiciels, du matériel et des processus antérieurs aux risques de sécurité actuels.</span><span class="sxs-lookup"><span data-stu-id="d57c4-137">Legacy Systems: Many components in on-premises datacenter solutions consist of software, hardware, and processes that predate current security risks.</span></span> <span data-ttu-id="d57c4-138">Si possible, corrigez, remplacez ou retirez ces systèmes lors d’une transformation cloud.</span><span class="sxs-lookup"><span data-stu-id="d57c4-138">When possible, remediate, replace, or retire these systems during a Cloud Transformation.</span></span> <span data-ttu-id="d57c4-139">Bien sûr, ce n’est pas toujours possible.</span><span class="sxs-lookup"><span data-stu-id="d57c4-139">Of course, that's not always feasible.</span></span> <span data-ttu-id="d57c4-140">Si les systèmes hérités restent en production dans une solution hybride, il est important que ces systèmes soient inventoriés et pris en compte lors de la conception d’un centre de données virtuel.</span><span class="sxs-lookup"><span data-stu-id="d57c4-140">If any legacy systems will remain in production in a hybrid solution, it is important that those systems have been inventoried and understood during Virtual Datacenter design.</span></span> <span data-ttu-id="d57c4-141">Ainsi, l’équipe de conception peut éliminer ou contrôler l’accès à ces systèmes à partir du cloud.</span><span class="sxs-lookup"><span data-stu-id="d57c4-141">Doing so allows the design team to eliminate or control access to those systems from the cloud.</span></span>
* <span data-ttu-id="d57c4-142">Contrôles et processus de sécurité informatique : Au minimum, les équipes de conception cloud doivent être informées des processus et contrôles de sécurité informatique existants, afin de les transférer dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="d57c4-142">IT Security processes and controls: At minimum, Cloud design teams should be refreshed on existing IT security processes and controls to carry those forward into the cloud.</span></span> <span data-ttu-id="d57c4-143">Dans un scénario idéal, un membre de l’équipe de sécurité informatique est formé en cyber-sécurité, et fait également partie (en tant que membre) des équipes de conception et d’implémentation.</span><span class="sxs-lookup"><span data-stu-id="d57c4-143">In an ideal scenario, a member of the IT security team would be trained in cybersecurity and dedicated as a member of the design and implementation teams.</span></span>
* <span data-ttu-id="d57c4-144">Supervision et audit : Lors de la conception des processus et des outils de gouvernance, assurez-vous que les solutions de supervision et d’audit prennent en compte les risques et les violations de sécurité.</span><span class="sxs-lookup"><span data-stu-id="d57c4-144">Monitoring and Auditing: When designing governance processes and tooling, ensure that monitoring and auditing solutions include security risks or violations.</span></span>

> [!NOTE]
> <span data-ttu-id="d57c4-145">Divulgation de la dette technique : Ce sujet ne dispose pas de prochaines étapes exploitables.</span><span class="sxs-lookup"><span data-stu-id="d57c4-145">Technical Debt disclosure: This topic lacks actionable next steps.</span></span> <span data-ttu-id="d57c4-146">D’autres articles aborderont ce sujet plus tard.</span><span class="sxs-lookup"><span data-stu-id="d57c4-146">Addition articles will expand on this topic over time.</span></span> <span data-ttu-id="d57c4-147">Des informations plus détaillées sur la sécurité du cloud sont disponibles dans le [cloud approuvé d’Azure](https://azure.microsoft.com/overview/trusted-cloud/).</span><span class="sxs-lookup"><span data-stu-id="d57c4-147">More detailed information about Cloud Security is available from [Azure's Trusted Cloud](https://azure.microsoft.com/overview/trusted-cloud/).</span></span> <span data-ttu-id="d57c4-148">Des approches pour améliorer l’état de sécurité de vos organisations sont disponibles dans le [catalogue des services de sécurité cloud](https://www.microsoft.com/security/information-protection).</span><span class="sxs-lookup"><span data-stu-id="d57c4-148">Approaches to improving your organizations security posture can be found in the [Cloud Security Service Catalog](https://www.microsoft.com/security/information-protection)</span></span>