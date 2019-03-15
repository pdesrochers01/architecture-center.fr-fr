---
title: 'Framework d’adoption du cloud : Guide de décision sur la journalisation et création de rapports'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
ms.service: architecture-center
ms.subservice: enterprise-cloud-adoption
ms.custom: governance
ms.date: 02/11/2019
description: 'Découvrez les principaux services pour les migrations Azure : journalisation, création de rapports et supervision.'
author: rotycenh
ms.openlocfilehash: 36552488872622ec59e2fcf4816da4184c3d4fbf
ms.sourcegitcommit: 273e690c0cfabbc3822089c7d8bc743ef41d2b6e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55900942"
---
# <a name="logging-and-reporting-decision-guide"></a><span data-ttu-id="fbd66-103">Guide de décision sur la journalisation et création de rapports</span><span class="sxs-lookup"><span data-stu-id="fbd66-103">Logging and reporting decision guide</span></span>

<span data-ttu-id="fbd66-104">Toutes les organisations ont besoin de mécanismes leur permettant d’avertir les équipes informatiques en cas de problèmes de performances, de temps de fonctionnement et de sécurité avant qu’ils ne s’aggravent.</span><span class="sxs-lookup"><span data-stu-id="fbd66-104">All organizations need mechanisms for notifying IT teams of performance, uptime, and security issues before they become serious problems.</span></span> <span data-ttu-id="fbd66-105">Une stratégie de supervision efficace vous permet d’analyser les performances individuelles des composants qui constituent vos charges de travail et votre infrastructure réseau.</span><span class="sxs-lookup"><span data-stu-id="fbd66-105">A successful monitoring strategy allows you to understand how the individual components that make up your workloads and networking infrastructure are performing.</span></span> <span data-ttu-id="fbd66-106">Dans le cas d’une migration de cloud public, il est essentiel d’intégrer la journalisation et la création de rapports à vos systèmes de supervision existants, et d’informer le personnel informatique approprié des événements et métriques importants. De cette manière, vous vous assurez que votre organisation atteint ses objectifs de conformité en termes de temps de fonctionnement, de sécurité et de stratégies.</span><span class="sxs-lookup"><span data-stu-id="fbd66-106">Within the context of a public cloud migration, integrating logging and reporting with any of your existing monitoring systems, while surfacing important events and metrics to the appropriate IT staff, is critical in ensuring your organization is meeting uptime, security, and policy compliance goals.</span></span>

![Traçage des options de journalisation, de création de rapports et de supervision de la moins complexe à la plus complexe, dans l’ordre des liens ci-dessous](../../_images/discovery-guides/discovery-guide-logs-and-reporting.png)

<span data-ttu-id="fbd66-108">Passer à : [Planification de votre infrastructure de supervision](#planning-your-monitoring-infrastructure) | [Cloud natif](#cloud-native) | [Extension locale](#on-premises-extension) | [Agrégation de passerelle](#gateway-aggregation) | [Supervision hybride (locale)](#hybrid-monitoring-on-premises) | [Supervision hybride (basée sur le cloud)](#hybrid-monitoring-cloud-based) | [Multi-cloud](#multi-cloud) | [En savoir plus](#learn-more)</span><span class="sxs-lookup"><span data-stu-id="fbd66-108">Jump to: [Planning your monitoring infrastructure](#planning-your-monitoring-infrastructure) | [Cloud native](#cloud-native) | [On-premises extension](#on-premises-extension) | [Gateway aggregation](#gateway-aggregation) | [Hybrid monitoring (on-premises)](#hybrid-monitoring-on-premises) | [Hybrid monitoring (cloud-based)](#hybrid-monitoring-cloud-based) | [Multi-cloud](#multi-cloud) | [Learn more](#learn-more)</span></span>

<span data-ttu-id="fbd66-109">Le point d’inflexion lors de la définition d’une stratégie d’identité cloud se base principalement sur les investissements que votre organisation a déjà faits dans les processus opérationnels et, dans une certaine mesure, sur les exigences à prendre en charge dans une stratégie multi-cloud.</span><span class="sxs-lookup"><span data-stu-id="fbd66-109">The inflection point when determining a cloud identity strategy is based primarily on existing investments your organization has made in operational processes, and to some degree any requirements you have to support a multi-cloud strategy.</span></span>

<span data-ttu-id="fbd66-110">Il existe plusieurs façons de journaliser et de créer des rapports sur les activités dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="fbd66-110">There are multiple ways to log and report on activities in the cloud.</span></span> <span data-ttu-id="fbd66-111">Le cloud natif et la journalisation centralisée sont deux options SaaS (software as a service) courantes, qui se fondent sur la conception de l’abonnement et le nombre d’abonnements.</span><span class="sxs-lookup"><span data-stu-id="fbd66-111">Cloud native and centralized logging are two common software as a service (SaaS) options that are driven by the subscription design and the number of subscriptions.</span></span>

## <a name="planning-your-monitoring-infrastructure"></a><span data-ttu-id="fbd66-112">Planification de l’infrastructure de supervision</span><span class="sxs-lookup"><span data-stu-id="fbd66-112">Planning your monitoring infrastructure</span></span>

<span data-ttu-id="fbd66-113">Lors de la planification de votre déploiement, vous devez penser à l’emplacement où seront stockées vos données de journalisation, et à la manière dont vous intégrerez les rapports et les services de supervision basés sur le cloud à vos processus et outils existants.</span><span class="sxs-lookup"><span data-stu-id="fbd66-113">When planning your deployment, you need to consider where logging data is stored and how you will integrate cloud-based reporting and monitoring services with your existing processes and tools.</span></span>

| <span data-ttu-id="fbd66-114">Question</span><span class="sxs-lookup"><span data-stu-id="fbd66-114">Question</span></span> | <span data-ttu-id="fbd66-115">Cloud natif</span><span class="sxs-lookup"><span data-stu-id="fbd66-115">Cloud native</span></span> | <span data-ttu-id="fbd66-116">Extension locale</span><span class="sxs-lookup"><span data-stu-id="fbd66-116">On-premises extension</span></span> | <span data-ttu-id="fbd66-117">Supervision hybride</span><span class="sxs-lookup"><span data-stu-id="fbd66-117">Hybrid monitoring</span></span> | <span data-ttu-id="fbd66-118">Agrégation de passerelle</span><span class="sxs-lookup"><span data-stu-id="fbd66-118">Gateway aggregation</span></span> |
|-----|-----|-----|-----|-----|
| <span data-ttu-id="fbd66-119">Vous disposez déjà d’une infrastructure de supervision locale ?</span><span class="sxs-lookup"><span data-stu-id="fbd66-119">Do you have an existing on-premises monitoring infrastructure?</span></span> | <span data-ttu-id="fbd66-120">Non </span><span class="sxs-lookup"><span data-stu-id="fbd66-120">No</span></span> | <span data-ttu-id="fbd66-121">OUI</span><span class="sxs-lookup"><span data-stu-id="fbd66-121">Yes</span></span> | <span data-ttu-id="fbd66-122">OUI</span><span class="sxs-lookup"><span data-stu-id="fbd66-122">Yes</span></span> |  <span data-ttu-id="fbd66-123">Non </span><span class="sxs-lookup"><span data-stu-id="fbd66-123">No</span></span> |
| <span data-ttu-id="fbd66-124">Avez-vous des exigences qui empêchent le stockage des données de journal dans des emplacements de stockage externes ?</span><span class="sxs-lookup"><span data-stu-id="fbd66-124">Do you have requirements preventing storage of log data on external storage locations?</span></span> | <span data-ttu-id="fbd66-125">Non </span><span class="sxs-lookup"><span data-stu-id="fbd66-125">No</span></span> | <span data-ttu-id="fbd66-126">OUI</span><span class="sxs-lookup"><span data-stu-id="fbd66-126">Yes</span></span> | <span data-ttu-id="fbd66-127">Non </span><span class="sxs-lookup"><span data-stu-id="fbd66-127">No</span></span> | <span data-ttu-id="fbd66-128">Non </span><span class="sxs-lookup"><span data-stu-id="fbd66-128">No</span></span> |
| <span data-ttu-id="fbd66-129">Avez-vous besoin d’intégrer la supervision cloud à des systèmes locaux ?</span><span class="sxs-lookup"><span data-stu-id="fbd66-129">Do you need to integrate cloud monitoring with on-premises systems?</span></span> | <span data-ttu-id="fbd66-130">Non </span><span class="sxs-lookup"><span data-stu-id="fbd66-130">No</span></span> | <span data-ttu-id="fbd66-131">Non </span><span class="sxs-lookup"><span data-stu-id="fbd66-131">No</span></span> | <span data-ttu-id="fbd66-132">OUI</span><span class="sxs-lookup"><span data-stu-id="fbd66-132">Yes</span></span> | <span data-ttu-id="fbd66-133">Non </span><span class="sxs-lookup"><span data-stu-id="fbd66-133">No</span></span> |
<span data-ttu-id="fbd66-134">Avez-vous besoin de traiter ou filtrer les données de télémétrie avant de les envoyer à vos systèmes de supervision ?</span><span class="sxs-lookup"><span data-stu-id="fbd66-134">Do you need to process or filter telemetry data before submitting it to your monitoring systems?</span></span> | <span data-ttu-id="fbd66-135">Non </span><span class="sxs-lookup"><span data-stu-id="fbd66-135">No</span></span> | <span data-ttu-id="fbd66-136">Non </span><span class="sxs-lookup"><span data-stu-id="fbd66-136">No</span></span> | <span data-ttu-id="fbd66-137">Non </span><span class="sxs-lookup"><span data-stu-id="fbd66-137">No</span></span> | <span data-ttu-id="fbd66-138">OUI</span><span class="sxs-lookup"><span data-stu-id="fbd66-138">Yes</span></span> |

### <a name="cloud-native"></a><span data-ttu-id="fbd66-139">Cloud natif</span><span class="sxs-lookup"><span data-stu-id="fbd66-139">Cloud native</span></span>

<span data-ttu-id="fbd66-140">Si votre organisation ne dispose pas à l’heure actuelle de systèmes de création de rapports et de journalisation établis, ou si votre déploiement cloud planifié n’a pas besoin d’être intégré à des systèmes de supervision locaux existants ou externes, le plus simple est d’opter pour une solution SaaS cloud native.</span><span class="sxs-lookup"><span data-stu-id="fbd66-140">If your organization currently lacks established logging and reporting systems, or if your planned cloud deployment does not need to be integrated with existing on-premises or other external monitoring systems, a cloud native SaaS solution is the simplest choice.</span></span>

<span data-ttu-id="fbd66-141">Dans ce scénario, les données de journal sont enregistrées et stockées dans le même environnement cloud que votre charge de travail, tandis que les outils de journalisation et création de rapports qui traitent les informations et les mettent en évidence auprès du personnel informatique font partie de la plateforme cloud.</span><span class="sxs-lookup"><span data-stu-id="fbd66-141">In this scenario, log data is recorded and stored in the same cloud environment as your workload, while the logging and reporting tools that process and surface information to IT staff are offered as part of the cloud platform.</span></span>

<span data-ttu-id="fbd66-142">Les solutions de journalisation cloud natives peuvent être implémentées ad hoc par abonnement ou par charge de travail pour les déploiements plus petits ou expérimentaux. Par ailleurs, elles sont organisées de manière centralisée afin de superviser les données de journal de l’ensemble de votre parc cloud.</span><span class="sxs-lookup"><span data-stu-id="fbd66-142">Cloud native logging solutions can be implemented ad hoc per subscription or workload for smaller or experimental deployments and are organized in a centralized manner to monitor log data across your entire cloud estate.</span></span>

<span data-ttu-id="fbd66-143">**Postulats concernant le caractère natif dans le cloud**.</span><span class="sxs-lookup"><span data-stu-id="fbd66-143">**Cloud native assumptions**.</span></span> <span data-ttu-id="fbd66-144">Les postulats suivants sont admis lorsque l’on utilise un système de création de rapports et de journalisation cloud natif :</span><span class="sxs-lookup"><span data-stu-id="fbd66-144">Using a cloud native logging and reporting system assumes the following:</span></span>

- <span data-ttu-id="fbd66-145">Vous n’avez pas besoin d’intégrer les données de journal de vos charges de travail cloud dans vos systèmes locaux existants.</span><span class="sxs-lookup"><span data-stu-id="fbd66-145">You do not need to integrate the log data from you cloud workloads into existing on-premises systems.</span></span>
- <span data-ttu-id="fbd66-146">Vous n’utilisez pas vos systèmes de création de rapports basés sur le cloud pour superviser les systèmes locaux.</span><span class="sxs-lookup"><span data-stu-id="fbd66-146">You will not be using your cloud-based reporting systems to monitor on-premises systems.</span></span>

### <a name="on-premises-extension"></a><span data-ttu-id="fbd66-147">Extension locale</span><span class="sxs-lookup"><span data-stu-id="fbd66-147">On-premises extension</span></span>

<span data-ttu-id="fbd66-148">Si vous devez intégrer la télémétrie cloud à des systèmes locaux incompatibles avec la création de rapports et la journalisation hybrides, ou si vous devez prendre en charge la migration d’applications et de services en minimisant le plus possible le redéveloppement, vous devrez déployer des agents de supervision sur les machines virtuelles. Ainsi, les données de journal seront envoyées directement à vos systèmes locaux, au lieu d’être stockées dans l’environnement cloud.</span><span class="sxs-lookup"><span data-stu-id="fbd66-148">In scenarios where you need to integrate cloud telemetry with on-premises systems that do not support hybrid logging and reporting, or support the migration of applications and services with a minimum amount of redevelopment, you will need to deploy monitoring agents to VMs that will send log data directly to your on-premises systems, rather than storing it in the cloud environment.</span></span>

<span data-ttu-id="fbd66-149">Pour que cette approche soit possible, vos ressources cloud doivent être en mesure de communiquer directement avec vos systèmes locaux via une [mise en réseau hybride](../software-defined-network/hybrid.md) et des [services de domaine hébergés sur le cloud](../identity/overview.md#cloud-hosted-domain-services).</span><span class="sxs-lookup"><span data-stu-id="fbd66-149">In order to support this approach, your cloud resources will need to be able to communicate directly with your on-premises systems through a combination of [hybrid networking](../software-defined-network/hybrid.md) and [cloud hosted domain services](../identity/overview.md#cloud-hosted-domain-services).</span></span> <span data-ttu-id="fbd66-150">Une fois cela mis en place, le réseau virtuel cloud fonctionne comme une extension de l’environnement local.</span><span class="sxs-lookup"><span data-stu-id="fbd66-150">With this in place, the cloud virtual network functions as a network extension of the on-premises environment.</span></span> <span data-ttu-id="fbd66-151">Par conséquent, vos charges de travail hébergées sur le cloud peuvent communiquer directement avec votre système de création de rapports et de journalisation local.</span><span class="sxs-lookup"><span data-stu-id="fbd66-151">Therefore, cloud hosted workloads can communicate directly with your on-premises logging and reporting system.</span></span>

<span data-ttu-id="fbd66-152">Cette approche s’appuie sur les investissements que vous avez déjà faits dans les outils de supervision, et modifie de manière limitée les applications et services déployés sur le cloud.</span><span class="sxs-lookup"><span data-stu-id="fbd66-152">This approach capitalizes on your existing investment in monitoring tooling with limited modification to any cloud-deployed applications or services.</span></span> <span data-ttu-id="fbd66-153">Cette approche est souvent la plus rapide pour prendre en charge la supervision lors d’une migration lift-and-shift.</span><span class="sxs-lookup"><span data-stu-id="fbd66-153">This is often the fastest approach to support monitoring during a lift-and-shift migration.</span></span> <span data-ttu-id="fbd66-154">En revanche, elle ne permet pas de capturer les données de journal produites par les ressources PaaS et SaaS basées sur le cloud. De même, elle omet tous les journaux liés aux machines virtuelles et générés par la plateforme cloud en elle-même, comme l’état des machines virtuelles.</span><span class="sxs-lookup"><span data-stu-id="fbd66-154">However, it won’t capture log data produced by cloud-based PaaS and SaaS resources, and it will omit any VM-related logs generated by the cloud platform itself such as VM status.</span></span> <span data-ttu-id="fbd66-155">Par conséquent, ce modèle doit servir de solution temporaire en attendant qu’une solution de supervision hybride plus complète soit implémentée.</span><span class="sxs-lookup"><span data-stu-id="fbd66-155">As a result, this pattern should be a temporary solution until a more comprehensive hybrid monitoring solution is implemented.</span></span>

<span data-ttu-id="fbd66-156">Postulats concernant le caractère local :</span><span class="sxs-lookup"><span data-stu-id="fbd66-156">On-premises only assumptions:</span></span>

- <span data-ttu-id="fbd66-157">Vous devez conserver vos données de journal uniquement dans votre environnement local, que ce soit en raison d’exigences techniques ou d’exigences stratégiques ou réglementaires.</span><span class="sxs-lookup"><span data-stu-id="fbd66-157">You need to maintain log data only in your on-premises environment only, either in support of technical requirements or due to regulatory or policy requirements.</span></span>
- <span data-ttu-id="fbd66-158">Vos systèmes locaux ne prennent pas en charge les solutions de journalisation et création de rapports hybrides ni les solutions d’agrégation de passerelle.</span><span class="sxs-lookup"><span data-stu-id="fbd66-158">Your on-premises systems do not support hybrid logging and reporting or gateway aggregation solutions.</span></span>
- <span data-ttu-id="fbd66-159">Vos applications basées sur le cloud peuvent envoyer la télémétrie directement à vos systèmes de journalisation et agents de supervision locaux. Ces derniers effectuent un envoi local, qui peut être déployé sur les machines virtuelles de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="fbd66-159">Your cloud-based applications can submit telemetry directly to your on-premises logging systems or monitoring agents that submit to on-premises can be deployed to workload VMs.</span></span>
- <span data-ttu-id="fbd66-160">Vos charges de travail ne sont pas dépendantes de services PaaS ou SaaS, qui requièrent une journalisation et une création de rapports basées sur le cloud.</span><span class="sxs-lookup"><span data-stu-id="fbd66-160">Your workloads are not dependent on PaaS or SaaS services that require cloud-based logging and reporting.</span></span>

### <a name="gateway-aggregation"></a><span data-ttu-id="fbd66-161">Agrégation de passerelle</span><span class="sxs-lookup"><span data-stu-id="fbd66-161">Gateway aggregation</span></span>

<span data-ttu-id="fbd66-162">Si la quantité de données de télémétrie basées sur le cloud est très volumineuse ou si les systèmes de supervision locaux existants ont besoin de modifier les données de journal avant de pouvoir les traiter, un service d’[agrégation de passerelle](../../../patterns/gateway-aggregation.md) de données journal peut être requis.</span><span class="sxs-lookup"><span data-stu-id="fbd66-162">For scenarios where the amount of cloud-based telemetry data is very large or existing on-premises monitoring systems need log data modified before it can be processed, a log data [gateway aggregation](../../../patterns/gateway-aggregation.md) service may be required.</span></span>

<span data-ttu-id="fbd66-163">Un service de passerelle est déployé sur votre fournisseur de cloud.</span><span class="sxs-lookup"><span data-stu-id="fbd66-163">A gateway service is deployed to your cloud provider.</span></span> <span data-ttu-id="fbd66-164">Ensuite, les applications et les services appropriés sont configurés de manière à ce qu’ils envoient les données de télémétrie à la passerelle au lieu du système de journalisation par défaut.</span><span class="sxs-lookup"><span data-stu-id="fbd66-164">Then, relevant applications and services are configured to submit telemetry data to the gateway instead of a default logging system.</span></span> <span data-ttu-id="fbd66-165">Suite à cela, la passerelle peut traiter les données : elle agrège des données, les combine et les formate selon les besoins avant de les envoyer à votre système de supervision qui les ingère et les analyse.</span><span class="sxs-lookup"><span data-stu-id="fbd66-165">The gateway can then process the data: aggregating, combining, or otherwise formatting it before then submitting it to your monitoring service for ingestion and analysis.</span></span>

<span data-ttu-id="fbd66-166">En outre, une passerelle peut être utilisée pour agréger et prétraiter des liaisons de données de télémétrie pour les systèmes cloud natifs et hybrides.</span><span class="sxs-lookup"><span data-stu-id="fbd66-166">Also, a gateway can be used to aggregate and preprocess telemetry data bound for cloud-native or hybrid systems.</span></span>

<span data-ttu-id="fbd66-167">Postulats concernant l’agrégation de passerelle :</span><span class="sxs-lookup"><span data-stu-id="fbd66-167">Gateway aggregation assumptions:</span></span>

- <span data-ttu-id="fbd66-168">Vous vous attendez à des niveaux très élevés de données de télémétrie depuis vos services et applications basés sur le cloud.</span><span class="sxs-lookup"><span data-stu-id="fbd66-168">You expect very high levels of telemetry data from your cloud-based applications or services.</span></span>
- <span data-ttu-id="fbd66-169">Vous devez formater ou optimiser vos données de télémétrie avant de les envoyer à vos systèmes de supervision.</span><span class="sxs-lookup"><span data-stu-id="fbd66-169">You need to format or otherwise optimize telemetry data before submitting it to your monitoring systems.</span></span>
- <span data-ttu-id="fbd66-170">Vos systèmes de supervision disposent d’API ou d’autres mécanismes disponibles pour ingérer les données de journal après leur traitement par la passerelle.</span><span class="sxs-lookup"><span data-stu-id="fbd66-170">Your monitoring systems have APIs or other mechanisms available to ingest log data after processing by the gateway.</span></span>

### <a name="hybrid-monitoring-on-premises"></a><span data-ttu-id="fbd66-171">Supervision hybride (locale)</span><span class="sxs-lookup"><span data-stu-id="fbd66-171">Hybrid monitoring (on-premises)</span></span>

<span data-ttu-id="fbd66-172">Une solution de supervision hybride combine les données de journal de vos ressources locales et cloud. De cette manière, elle peut vous fournir une vue intégrée de l’état opérationnel de votre parc informatique.</span><span class="sxs-lookup"><span data-stu-id="fbd66-172">A hybrid monitoring solution combines log data from both your on-premises and cloud resources to provide an integrated view into your IT estate's operational status.</span></span>

<span data-ttu-id="fbd66-173">Si vous avez déjà investi dans des systèmes de supervision locaux qu’il serait difficile ou coûteux de remplacer, vous pouvez intégrer la télémétrie de vos charges de travail cloud à vos solutions de supervision locales existantes.</span><span class="sxs-lookup"><span data-stu-id="fbd66-173">If you have an existing investment in on-premises monitoring systems that would be difficult or costly to replace, you may need to integrate the telemetry from your cloud workloads into preexisting on-premises monitoring solutions.</span></span> <span data-ttu-id="fbd66-174">Dans un système de supervision local hybride, les données de télémétrie locales continuent d’utiliser le système de supervision local existant.</span><span class="sxs-lookup"><span data-stu-id="fbd66-174">In a hybrid on-premises monitoring system, on-premises telemetry data continues to use the existing on-premises monitoring system.</span></span> <span data-ttu-id="fbd66-175">Les données de télémétrie basées sur le cloud peuvent être directement envoyées au système de supervision cloud ou elles peuvent être stockées dans le cloud avec vos charges de travail. Ensuite, elles sont compilées et ingérées par le système local à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="fbd66-175">Cloud-based telemetry data is either sent to the cloud monitoring system directly, or the data is stored on the cloud alongside your workloads and then compiled and ingested into the on-premises system at regular intervals.</span></span>

<span data-ttu-id="fbd66-176">**Postulats concernant la supervision hybride locale**.</span><span class="sxs-lookup"><span data-stu-id="fbd66-176">**On-premises hybrid monitoring assumptions**.</span></span> <span data-ttu-id="fbd66-177">Les postulats suivants sont admis lorsque l’on utilise un système de création de rapports et de journalisation local pour la supervision hybride :</span><span class="sxs-lookup"><span data-stu-id="fbd66-177">Using an on-premises logging and reporting system for hybrid monitoring assumes the following:</span></span>

- <span data-ttu-id="fbd66-178">Vous devez utiliser des systèmes de création de rapports locaux existants pour superviser les charges de travail cloud.</span><span class="sxs-lookup"><span data-stu-id="fbd66-178">You need to use existing on-premises reporting systems to monitor cloud workloads.</span></span>
- <span data-ttu-id="fbd66-179">Vous devez rester propriétaire des données de journal locales.</span><span class="sxs-lookup"><span data-stu-id="fbd66-179">You need to maintain ownership of log data on-premises.</span></span>
- <span data-ttu-id="fbd66-180">Vos systèmes de gestion locaux disposent d’API ou d’autres mécanismes disponibles pour ingérer les données de journal venant de systèmes basés sur le cloud.</span><span class="sxs-lookup"><span data-stu-id="fbd66-180">Your on-premises management systems have APIs or other mechanisms available to ingest log data from cloud-based systems.</span></span>

> [!TIP]
> <span data-ttu-id="fbd66-181">En prenant en compte la nature itérative de la migration cloud, il est probable de passer d’une supervision cloud native et locale à une approche hybride partielle.</span><span class="sxs-lookup"><span data-stu-id="fbd66-181">As part of the iterative nature of cloud migration, transitioning from distinct cloud-native and on-premises monitoring to a partial hybrid approach is likely.</span></span> <span data-ttu-id="fbd66-182">Veillez à ce que les modifications de votre architecture de supervision soient alignées sur vos processus opérationnels et informatiques globaux.</span><span class="sxs-lookup"><span data-stu-id="fbd66-182">Make sure to keep changes to your monitoring architecture in line with your overall IT and operational processes.</span></span>

### <a name="hybrid-monitoring-cloud-based"></a><span data-ttu-id="fbd66-183">Supervision hybride (basée sur le cloud)</span><span class="sxs-lookup"><span data-stu-id="fbd66-183">Hybrid monitoring (cloud-based)</span></span>

<span data-ttu-id="fbd66-184">Si vous n’avez pas un besoin essentiel de maintenir un système de supervision local, ou si vous voulez remplacer les systèmes de supervision locaux par une solution SaaS, vous pouvez également choisir d’intégrer des données de journal locales à un système de supervision centralisé basé sur le cloud.</span><span class="sxs-lookup"><span data-stu-id="fbd66-184">If you do not have a compelling need to maintain an on-premises monitoring system, or you want to replace on-premises monitoring systems with a SaaS solution, you can also choose to integrate on-premises log data with a centralized cloud-based monitoring system.</span></span>

<span data-ttu-id="fbd66-185">Ce scénario est une mise en miroir de l’approche centrée locale : les charges de travail utilisent leur mécanisme de journalisation cloud par défaut, tandis que les applications et services locaux soit envoient le répertoire de télémétrie au système de journalisation basé sur le cloud, soit agrègent les données pour qu’elles soient ingérées par le système cloud à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="fbd66-185">Mirroring the on-premises centered approach, in this scenario cloud workloads would use their default cloud logging mechanism, and on-premises applications and services would either send telemetry directory to the cloud-based logging system, or aggregate that data for ingestion into the cloud system at regular intervals.</span></span> <span data-ttu-id="fbd66-186">Le système de supervision basé sur le cloud vous sert ensuite de système principal de création de rapports et de supervision pour l’ensemble de votre parc informatique.</span><span class="sxs-lookup"><span data-stu-id="fbd66-186">The cloud-based monitoring system would then serve as your primary monitoring and reporting system for your entire IT estate.</span></span>

<span data-ttu-id="fbd66-187">Postulats concernant la supervision hybride basée sur le cloud : Les postulats suivants sont admis lorsque l’on utilise un système de création de rapports et de journalisation basé sur le cloud pour la supervision hybride :</span><span class="sxs-lookup"><span data-stu-id="fbd66-187">Cloud-based hybrid monitoring assumptions: Using cloud-based logging and reporting systems for hybrid monitoring assumes the following:</span></span>

- <span data-ttu-id="fbd66-188">Vous n’êtes pas dépendant des systèmes de supervision locaux existants.</span><span class="sxs-lookup"><span data-stu-id="fbd66-188">You are not dependent upon existing on-premises monitoring systems.</span></span>
- <span data-ttu-id="fbd66-189">Vos charges de travail n’imposent pas d’exigences stratégiques ou réglementaires quant au stockage des données de journal en local.</span><span class="sxs-lookup"><span data-stu-id="fbd66-189">Your workloads do not have regulatory or policy requirements to store log data on-premises.</span></span>
- <span data-ttu-id="fbd66-190">Vos systèmes de supervision basés sur le cloud disposent d’API ou d’autres mécanismes disponibles pour ingérer les données de journal venant de services et d’applications locaux.</span><span class="sxs-lookup"><span data-stu-id="fbd66-190">Your cloud-based monitoring systems have APIs or other mechanisms available to ingest log data from on-premises applications and services.</span></span>

### <a name="multi-cloud"></a><span data-ttu-id="fbd66-191">Multi-cloud</span><span class="sxs-lookup"><span data-stu-id="fbd66-191">Multi-cloud</span></span>

<span data-ttu-id="fbd66-192">L’intégration des capacités de journalisation et de création de rapports sur l’ensemble d’une plateforme multi-cloud peut être compliquée.</span><span class="sxs-lookup"><span data-stu-id="fbd66-192">Integrating logging and reporting capabilities across a multiple-cloud platform can be complicated.</span></span> <span data-ttu-id="fbd66-193">Les services offerts d’une plateforme à une autre ne sont pas directement comparables, et les capacités de journalisation et de télémétrie fournies par ces services sont également différentes.</span><span class="sxs-lookup"><span data-stu-id="fbd66-193">Services offered between platforms are often not directly comparable, and logging and telemetry capabilities provided by these services differ as well.</span></span>
<span data-ttu-id="fbd66-194">La prise en charge de la journalisation multi-cloud requiert souvent d’avoir recours à des services de passerelle. Ces derniers traitent les données de journal et les convertissent en un format courant, avant de les envoyer à une solution de journalisation hybride.</span><span class="sxs-lookup"><span data-stu-id="fbd66-194">Multi-cloud logging support often requires the use of gateway services to process log data into a common format before submitting data to a hybrid logging solution.</span></span>

## <a name="learn-more"></a><span data-ttu-id="fbd66-195">En savoir plus</span><span class="sxs-lookup"><span data-stu-id="fbd66-195">Learn more</span></span>

<span data-ttu-id="fbd66-196">[Azure Monitor](/azure/azure-monitor/overview) est le service de supervision et de création de rapports par défaut pour Azure.</span><span class="sxs-lookup"><span data-stu-id="fbd66-196">[Azure Monitor](/azure/azure-monitor/overview) is the default reporting and monitoring service for Azure.</span></span> <span data-ttu-id="fbd66-197">Elle fournit :</span><span class="sxs-lookup"><span data-stu-id="fbd66-197">It provides:</span></span>

- <span data-ttu-id="fbd66-198">Une plateforme unifiée servant à collecter la télémétrie d’application, la télémétrie d’hôte (par exemple, les machines virtuelles), les métriques de conteneur, les métriques de plateforme Azure et les journaux des événements.</span><span class="sxs-lookup"><span data-stu-id="fbd66-198">A unified platform for collecting app telemetry, host telemetry (such as VMs), container metrics, Azure platform metrics, and event logs.</span></span>
- <span data-ttu-id="fbd66-199">Visualisation, requêtes, alertes et outils d’analyse.</span><span class="sxs-lookup"><span data-stu-id="fbd66-199">Visualization, queries, alerts, and analytical tools.</span></span> <span data-ttu-id="fbd66-200">Ce service peut fournir des insights sur les machines virtuelles, les systèmes d’exploitation invités, les réseaux virtuels et les événements d’application de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="fbd66-200">It can provide insights into virtual machines, guest operating systems, virtual networks, and workload application events.</span></span>
- <span data-ttu-id="fbd66-201">Les [API REST](/azure/monitoring-and-diagnostics/monitoring-rest-api-walkthrough) pour l’intégration à des services externes et pour l’automatisation des services de supervision et d’alerte</span><span class="sxs-lookup"><span data-stu-id="fbd66-201">[REST APIs](/azure/monitoring-and-diagnostics/monitoring-rest-api-walkthrough) for integration with external services and automation of monitoring and alerting services</span></span>
- <span data-ttu-id="fbd66-202">[Intégration](/azure/monitoring-and-diagnostics/monitoring-partners) avec de nombreux fournisseurs tiers connus.</span><span class="sxs-lookup"><span data-stu-id="fbd66-202">[Integration](/azure/monitoring-and-diagnostics/monitoring-partners) with many popular third-party vendors.</span></span>