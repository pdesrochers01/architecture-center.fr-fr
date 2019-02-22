---
title: 'Framework d’adoption du cloud : Base de référence de la sécurité des processus de conformité à la stratégie'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
ms.service: architecture-center
ms.subservice: enterprise-cloud-adoption
ms.custom: governance
ms.date: 02/11/2019
description: Base de référence de la sécurité des processus de conformité à la stratégie
author: BrianBlanchard
ms.openlocfilehash: 8f115436d7021fe725118dcc0dfd64167c4cbfa1
ms.sourcegitcommit: 273e690c0cfabbc3822089c7d8bc743ef41d2b6e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55901078"
---
# <a name="security-baseline-policy-compliance-processes"></a><span data-ttu-id="37fac-103">Base de référence de la sécurité des processus de conformité à la stratégie</span><span class="sxs-lookup"><span data-stu-id="37fac-103">Security Baseline policy compliance processes</span></span>

<span data-ttu-id="37fac-104">Cet article décrit les processus d’adhésion à la stratégie, qui gouvernent la [base de référence de la sécurité](./overview.md).</span><span class="sxs-lookup"><span data-stu-id="37fac-104">This article discusses an approach to policy adherence processes that govern [Security Baseline](./overview.md).</span></span> <span data-ttu-id="37fac-105">Pour être efficace, une gouvernance de sécurité du cloud implique plusieurs processus manuels récurrents qui visent à détecter les vulnérabilités et à imposer des stratégies d’atténuation de ces risques de sécurité.</span><span class="sxs-lookup"><span data-stu-id="37fac-105">Effective governance of cloud security starts with recurring manual processes designed to detect vulnerabilities and impose policies to mitigate those security risks.</span></span> <span data-ttu-id="37fac-106">De fait, l’équipe de gouvernance cloud et les équipes informatiques des parties prenantes intéressées sont régulièrement sollicitées afin de passer en revue et mettre à jour la stratégie et veiller au respect de cette dernière.</span><span class="sxs-lookup"><span data-stu-id="37fac-106">This requires regular involvement of the Cloud Governance team and interested business and IT stakeholders to review and update policy and ensure policy compliance.</span></span> <span data-ttu-id="37fac-107">En outre, de nombreux processus de supervision et d’application continues peuvent être automatisés ou complétés par des outils afin de réduire la charge de gouvernance et accélérer la réponse en cas de manquement à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="37fac-107">In addition, many ongoing monitoring and enforcement processes can be automated or supplemented with tooling to reduce the overhead of governance and allow for faster response to policy deviation.</span></span>

## <a name="planning-review-and-reporting-processes"></a><span data-ttu-id="37fac-108">Processus de planification, de révision et de génération de rapports</span><span class="sxs-lookup"><span data-stu-id="37fac-108">Planning, review, and reporting processes</span></span>

<span data-ttu-id="37fac-109">Les outils de base de référence de la sécurité du cloud ne peuvent pas surpasser les processus et stratégies qu’ils appuient.</span><span class="sxs-lookup"><span data-stu-id="37fac-109">The best Security Baseline tools in the cloud are only as good as the processes and policies that they support.</span></span> <span data-ttu-id="37fac-110">Les éléments suivants représentent un ensemble d’exemples de processus généralement impliqués dans la discipline Base de référence de la sécurité.</span><span class="sxs-lookup"><span data-stu-id="37fac-110">The following is a set of example processes commonly involved in the Security Baseline discipline.</span></span> <span data-ttu-id="37fac-111">Ces exemples constituent des points de départ pour planifier les processus qui vous permettront de mettre à jour la stratégie de sécurité à mesure que l’entreprise évolue et selon les commentaires des équipes informatiques chargés d’implémenter les mesures de gouvernance.</span><span class="sxs-lookup"><span data-stu-id="37fac-111">Use these examples as a starting point when planning the processes that will allow you to continue to update security policy based on business change and feedback from the security and IT teams tasked with turning governance guidance into action.</span></span>

<span data-ttu-id="37fac-112">**Évaluation des risques et planification initiales** : Dans le cadre de l’adoption initiale de la discipline de base de référence de la sécurité, identifiez vos principaux risques métier et tolérances liés à la sécurité du cloud.</span><span class="sxs-lookup"><span data-stu-id="37fac-112">**Initial risk assessment and planning**: As part of your initial adoption of the Security Baseline discipline, identify your core business risks and tolerances related to cloud security.</span></span> <span data-ttu-id="37fac-113">Utilisez ces informations pour débattre des techniques spécifiques avec les membres de vos équipes informatiques et de sécurité, puis développer un ensemble de stratégies de sécurité de base pour atténuer ces risques et ainsi établir votre stratégie de gouvernance initiale.</span><span class="sxs-lookup"><span data-stu-id="37fac-113">Use this information to discuss specific technical risks with members of your IT and security teams and develop a baseline set of security policies for mitigating these risks to establish your initial governance strategy.</span></span>

<span data-ttu-id="37fac-114">**Planification de déploiement** : Avant le déploiement de n’importe quelle charge de travail ou ressource, effectuez une révision de la sécurité afin d’identifier tout nouveau risque et de vous assurer que toutes les exigences de la stratégie d’accès et de sécurité des données sont respectées.</span><span class="sxs-lookup"><span data-stu-id="37fac-114">**Deployment planning**: Prior to deployment of any workload or asset, perform a security review to identify any new risks and ensure all access and data security policy requirements are met.</span></span>

<span data-ttu-id="37fac-115">**Test de déploiement** : Dans le cadre du processus de déploiement de n’importe quelle charge de travail ou ressource, l’équipe de gouvernance du cloud, en collaboration avec les équipes de sécurité de votre entreprise, sera responsable du passage en revue du déploiement pour valider la conformité à la stratégie de sécurité.</span><span class="sxs-lookup"><span data-stu-id="37fac-115">**Deployment testing**: As part of the deployment process for any workload or asset, the Cloud Governance team, in cooperation with your corporate security teams, will be responsible for reviewing the deployment to validate security policy compliance.</span></span>

<span data-ttu-id="37fac-116">**Planification annuelle :** Tous les ans, effectuez une révision de haut niveau de la stratégie de base de référence de la sécurité des ressources.</span><span class="sxs-lookup"><span data-stu-id="37fac-116">**Annual planning**: On an annual basis, perform a high-level review of Security Baseline strategy.</span></span> <span data-ttu-id="37fac-117">Étudiez les priorités de l’entreprise pour l’avenir et les stratégies d’adoption du cloud mises à jour afin d’identifier l’augmentation des risques potentiels ou d’autres besoins en sécurité émergents.</span><span class="sxs-lookup"><span data-stu-id="37fac-117">Explore future corporate priorities and updated cloud adoption strategies to identify potential risk increase and other emerging security needs.</span></span> <span data-ttu-id="37fac-118">Utilisez ce temps de révision annuelle pour examiner les dernières meilleures pratiques liées aux bases de référence de la sécurité et intégrez-les dans vos stratégies et processus de révision.</span><span class="sxs-lookup"><span data-stu-id="37fac-118">Also use this time to review the latest Security Baseline best practices and integrate these into your policies and review processes.</span></span>

<span data-ttu-id="37fac-119">**Planification et révision trimestrielles** : Tous les trimestres, effectuez une révision des données d’audit de sécurité et des rapports d’incident afin d’identifier les modifications requises dans la stratégie de sécurité.</span><span class="sxs-lookup"><span data-stu-id="37fac-119">**Quarterly review and planning**: On a quarterly basis perform a review of security audit data and incident reports to identify any changes required in security policy.</span></span> <span data-ttu-id="37fac-120">Dans le cadre de ce processus, passez en revue les ressources de cybersécurité afin d’anticiper de manière proactive les nouvelles menaces et mettre à jour la stratégie, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="37fac-120">As part of this process, review the current cybersecurity landscape to proactively anticipate emerging threats, and update policy as appropriate.</span></span> <span data-ttu-id="37fac-121">Une fois l’examen terminé, assurez-vous de la conformité des mesures de conception à la stratégie mise à jour.</span><span class="sxs-lookup"><span data-stu-id="37fac-121">After the review is complete, align design guidance with updated policy.</span></span>

<span data-ttu-id="37fac-122">Ce processus de planification constitue également un moment idéal pour évaluer les lacunes des membres de votre équipe de gouvernance cloud en lien avec les risques, nouveaux ou évolutifs, associés à la sécurité.</span><span class="sxs-lookup"><span data-stu-id="37fac-122">This planning process is also a good time to evaluate the current membership of your Cloud Governance team for knowledge gaps related to new or evolving policy and risks related to security.</span></span> <span data-ttu-id="37fac-123">Invitez le personnel informatique concerné à participer aux révisions et à la planification en tant que conseillers techniques temporaires ou membres permanents de votre équipe.</span><span class="sxs-lookup"><span data-stu-id="37fac-123">Invite relevant IT staff to participate in reviews and planning as either temporary technical advisors or permanent members of your team.</span></span>

<span data-ttu-id="37fac-124">**Apprentissage et formation** : Deux fois par mois, offrez des sessions de formation pour vous assurer que le personnel informatique et les développeurs connaissent les dernières exigences en matière de sécurité.</span><span class="sxs-lookup"><span data-stu-id="37fac-124">**Education and Training**: On a bi-monthly basis, offer training sessions to make sure IT staff and developers are up-to-date on the latest security policy requirements.</span></span> <span data-ttu-id="37fac-125">Dans le cadre de ce processus, relisez et mettez à jour toute la documentation, les guides et les autres ressources de formation pour vous assurer qu’ils correspondent aux dernières instructions stratégiques de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="37fac-125">As part of this process review and update any documentation, guidance, or other training assets to ensure they are in sync with the latest corporate policy statements.</span></span>

<span data-ttu-id="37fac-126">**Révisions d’audit et création de rapports mensuelles** : Tous les mois, effectuez un audit sur tous les déploiements cloud afin de garantir leur alignement continu sur la stratégie de sécurité.</span><span class="sxs-lookup"><span data-stu-id="37fac-126">**Monthly audit and reporting reviews**: On a monthly basis, perform an audit on all cloud deployments to assure their continued alignment with security policy.</span></span> <span data-ttu-id="37fac-127">Examinez les activités de sécurité avec le personnel informatique, puis identifiez les problèmes de conformité qui n’ont pas encore été pris en charge par le processus d’application et de supervision continues.</span><span class="sxs-lookup"><span data-stu-id="37fac-127">Review security related activities with IT staff and identify any compliance issues not already handled as part of the ongoing monitoring and enforcement process.</span></span> <span data-ttu-id="37fac-128">Cet examen produit un rapport pour l’équipe de la stratégie cloud et chaque équipe d’adoption du cloud afin de communiquer sur l’adhésion générale des parties prenantes à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="37fac-128">The result of this review is a report for the Cloud Strategy team and each cloud adoption team to communicate overall adherence to policy.</span></span> <span data-ttu-id="37fac-129">Le rapport est également conservé à des fins d’audit et juridiques.</span><span class="sxs-lookup"><span data-stu-id="37fac-129">The report is also stored for auditing and legal purposes.</span></span>

## <a name="ongoing-monitoring-processes"></a><span data-ttu-id="37fac-130">Processus de supervision continue</span><span class="sxs-lookup"><span data-stu-id="37fac-130">Ongoing monitoring processes</span></span>

<span data-ttu-id="37fac-131">Votre stratégie de gouvernance de sécurité réussit si l’état actuel et passé de votre infrastructure cloud est clairement identifiable.</span><span class="sxs-lookup"><span data-stu-id="37fac-131">Determining if your security governance strategy is successful depends on visibility into the current and past state of your cloud infrastructure.</span></span> <span data-ttu-id="37fac-132">Si vous ne pouvez pas analyser les mesures et données pertinentes au sujet de l’intégrité et de l’activité de vos ressources cloud, vous ne pourrez pas identifier les changements de risques ni détecter les violations de vos tolérances aux risques.</span><span class="sxs-lookup"><span data-stu-id="37fac-132">Without the ability to analyze the relevant metrics and data of your cloud resources security health and activity, you cannot identify changes in your risks or detect violations of your risk tolerances.</span></span> <span data-ttu-id="37fac-133">Les processus de gouvernance continus décrits ci-dessus exigent que vous fournissiez des données de qualité afin d’être capable de modifier la stratégie pour protéger votre infrastructure au mieux face à l’évolution des menaces et des exigences en matière de sécurité.</span><span class="sxs-lookup"><span data-stu-id="37fac-133">The ongoing governance processes discussed above require quality data to ensure policy can be modified to better protect your infrastructure against changing threats and security requirements.</span></span>

<span data-ttu-id="37fac-134">Assurez-vous que vos équipes de sécurité et informatiques ont mis en place des systèmes de supervision automatisés pour votre infrastructure cloud recueillant les données de journaux pertinentes dont vous avez besoin pour évaluer les risques.</span><span class="sxs-lookup"><span data-stu-id="37fac-134">Ensure that your security and IT teams have implemented automated monitoring systems for your cloud infrastructure that capture the relevant logs data you need to evaluate risk.</span></span> <span data-ttu-id="37fac-135">Soyez proactif dans le cadre de la surveillance de ces systèmes afin d’assurer la détection et l’atténuation rapides des violations potentielles des stratégies, et assurez-vous que votre stratégie de supervision est conforme aux besoins en matière de sécurité.</span><span class="sxs-lookup"><span data-stu-id="37fac-135">Be proactive in monitoring these systems to ensure prompt detection and mitigation of potential policy violation, and ensure your monitoring strategy is in line with security needs.</span></span>

## <a name="violation-triggers-and-enforcement-actions"></a><span data-ttu-id="37fac-136">Déclencheurs relatifs aux violations et actions de mise en conformité</span><span class="sxs-lookup"><span data-stu-id="37fac-136">Violation triggers and enforcement actions</span></span>

<span data-ttu-id="37fac-137">Comme le non-respect des règles de sécurité peut entraîner des erreurs critiques et une divulgation de données, ainsi que des risques d’interruption de service, l’équipe de gouvernance du cloud doit disposer d’une visibilité totale sur les violations graves des stratégies.</span><span class="sxs-lookup"><span data-stu-id="37fac-137">Because security noncompliance can lead to critical and data exposure and service disruption risks, the Cloud Governance team should have visibility into serious policy violations.</span></span> <span data-ttu-id="37fac-138">Veillez à ce que le personnel informatique dispose de chemins d’escalade clairs pour signaler les problèmes de sécurité aux membres de l’équipe de gouvernance les mieux placés pour identifier et vérifier que les problèmes de stratégie sont atténués.</span><span class="sxs-lookup"><span data-stu-id="37fac-138">Ensure IT staff have clear escalation paths for reporting security issues to the governance team members best suited to identify and verify that policy issues are mitigated.</span></span>  

<span data-ttu-id="37fac-139">Lorsque des violations sont détectées, vous devez prendre des actions conformes à la stratégie dès que possible.</span><span class="sxs-lookup"><span data-stu-id="37fac-139">When violations are detected, you should take actions to realign with policy as soon as possible.</span></span> <span data-ttu-id="37fac-140">Votre équipe informatique peut automatiser la plupart des déclencheurs relatifs aux violations à l’aide des outils présentés dans la [chaîne d’outils Base de référence de la sécurité pour Azure](toolchain.md).</span><span class="sxs-lookup"><span data-stu-id="37fac-140">Your IT team can automate most violation triggers using the tools outlined in the [Security Baseline toolchain for Azure](toolchain.md).</span></span>

<span data-ttu-id="37fac-141">Les déclencheurs et mesures d’application ci-après fournissent des exemples auxquels vous pouvez vous référer lorsque vous planifiez d’utiliser les données de supervision pour résoudre les violations des stratégies :</span><span class="sxs-lookup"><span data-stu-id="37fac-141">The following triggers and enforcement actions provide examples you can reference when planning how to use monitoring data to resolve policy violations:</span></span>

- <span data-ttu-id="37fac-142">Augmentation du nombre d’attaques détectées : Si une ressource subit une augmentation de 25 % du nombre d’attaques par force brute ou DDoS, discutez avec le personnel du service de sécurité informatique et le propriétaire de la charge de travail pour déterminer les solutions.</span><span class="sxs-lookup"><span data-stu-id="37fac-142">Increase in attacks detected: If any resource experiences a 25% increase in brute force or DDoS attacks, discuss with IT security staff and workload owner to determine remedies.</span></span> <span data-ttu-id="37fac-143">Suivez la résolution des problèmes et actualisez votre assistance si une révision de la stratégie est nécessaire pour prévenir d’autres incidents.</span><span class="sxs-lookup"><span data-stu-id="37fac-143">Track issue and update guidance if policy revision is necessary to prevent future incidents.</span></span>
- <span data-ttu-id="37fac-144">Données non classifiées détectées : L’accès externe sera refusé à n’importe quelle source de données dont l’impact sur la confidentialité, la sécurité ou les activités n’aura pas été correctement classifié. Cet accès sera rétabli lorsque le propriétaire des données aura appliqué la classification et le niveau de protection des données appropriés.</span><span class="sxs-lookup"><span data-stu-id="37fac-144">Unclassified data detected: Any data source without an appropriate privacy, security, or business impact classification will have external access denied until the classification is applied by the data owner and the appropriate level of data protection applied.</span></span>
- <span data-ttu-id="37fac-145">Problème d’intégrité de la sécurité détecté : Désactivez l’accès à toutes les machines virtuelles vulnérables, ou auxquelles des logiciels malveillants ont pu accéder, jusqu’à ce que des correctifs ou logiciels de sécurité appropriés soient installés.</span><span class="sxs-lookup"><span data-stu-id="37fac-145">Security health issue detected: Disable access to any virtual machines (VMs) that have known access or malware vulnerabilities identified until appropriate patches or security software can be installed.</span></span> <span data-ttu-id="37fac-146">Mettez à jour les conseils stratégiques à prendre en compte pour chaque nouvelle menace détectée.</span><span class="sxs-lookup"><span data-stu-id="37fac-146">Update policy guidance to account for any newly detected threats.</span></span>
- <span data-ttu-id="37fac-147">Vulnérabilité du réseau détectée : L’accès à toute ressource non explicitement autorisée par les stratégies d’accès au réseau doit alerter le personnel informatique et de sécurité, ainsi que le propriétaire de la charge de travail concernée.</span><span class="sxs-lookup"><span data-stu-id="37fac-147">Network vulnerability detected: Access to any resource not explicitly allowed by the network access policies should trigger an alert to IT security staff and the relevant workload owner.</span></span> <span data-ttu-id="37fac-148">Suivez la résolution des problèmes et actualisez votre assistance si une révision de la stratégie est nécessaire pour réduire les risques d’autres incidents.</span><span class="sxs-lookup"><span data-stu-id="37fac-148">Track issue and update guidance if policy revision is necessary to mitigate future incidents.</span></span>

## <a name="next-steps"></a><span data-ttu-id="37fac-149">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="37fac-149">Next steps</span></span>

<span data-ttu-id="37fac-150">À l’aide du [modèle de gestion cloud](./template.md), documentez les processus et les déclencheurs qui correspondent au plan d’adoption du cloud actuel.</span><span class="sxs-lookup"><span data-stu-id="37fac-150">Using the [Cloud Management template](./template.md), document the processes and triggers that align to the current cloud adoption plan.</span></span>

<span data-ttu-id="37fac-151">Pour obtenir des conseils sur l’exécution des stratégies de gestion cloud en harmonie avec les plans d’adoption, consultez l’article sur l’amélioration de la discipline.</span><span class="sxs-lookup"><span data-stu-id="37fac-151">For guidance on executing cloud management policies in alignment with adoption plans, see the article on discipline improvement.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="37fac-152">Amélioration de la discipline Base de référence de la sécurité</span><span class="sxs-lookup"><span data-stu-id="37fac-152">Security Baseline discipline improvement</span></span>](./discipline-improvement.md)