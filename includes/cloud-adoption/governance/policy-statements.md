<!-- TEMPLATE FILE - DO NOT ADD METADATA -->

## <a name="policy-statements"></a><span data-ttu-id="722b6-101">Policy statements</span><span class="sxs-lookup"><span data-stu-id="722b6-101">Policy statements</span></span>

<span data-ttu-id="722b6-102">Les instructions stratégiques suivantes établissent les exigences visant à atténuer les risques définis.</span><span class="sxs-lookup"><span data-stu-id="722b6-102">The following policy statements establish the requirements needed to mitigate the defined risks.</span></span> <span data-ttu-id="722b6-103">Ces stratégies définissent les exigences fonctionnelles pour le produit minimum viable de la gouvernance.</span><span class="sxs-lookup"><span data-stu-id="722b6-103">These policies define the functional requirements for the governance MVP.</span></span> <span data-ttu-id="722b6-104">Chacune d’entre elle sera représentée dans l’implémentation du produit minimum viable de la gouvernance.</span><span class="sxs-lookup"><span data-stu-id="722b6-104">Each will be represented in the implementation of the governance MVP.</span></span>

<span data-ttu-id="722b6-105">Accélération du déploiement :</span><span class="sxs-lookup"><span data-stu-id="722b6-105">Deployment Acceleration:</span></span>

- <span data-ttu-id="722b6-106">Toutes les ressources doivent être regroupées et libellées en fonction de stratégies définies.</span><span class="sxs-lookup"><span data-stu-id="722b6-106">All assets must be grouped and tagged according to defined grouping and tagging strategies.</span></span>
- <span data-ttu-id="722b6-107">Toutes les ressources doivent utiliser un modèle de déploiement approuvé.</span><span class="sxs-lookup"><span data-stu-id="722b6-107">All assets must use an approved deployment model.</span></span>
- <span data-ttu-id="722b6-108">Une fois que les fondements de la gouvernance sont établis pour un fournisseur de cloud, tous les outils de déploiement doivent être compatibles avec les outils définis par l’équipe de gouvernance.</span><span class="sxs-lookup"><span data-stu-id="722b6-108">Once a governance foundation has been established for a cloud provider, any deployment tooling must be compatible with the tools defined by the governance team.</span></span>

<span data-ttu-id="722b6-109">Base de référence des identités :</span><span class="sxs-lookup"><span data-stu-id="722b6-109">Identity Baseline:</span></span>

- <span data-ttu-id="722b6-110">Toutes les ressources déployées dans le cloud doivent être contrôlées à l’aide d’identités et de rôles approuvés par les stratégies de gouvernance en vigueur.</span><span class="sxs-lookup"><span data-stu-id="722b6-110">All assets deployed to the cloud should be controlled using identities and roles approved by current governance policies.</span></span>
- <span data-ttu-id="722b6-111">Tous les groupes de l’infrastructure Active Directory locale qui disposent de privilèges élevés doivent être mappés vers un rôle RBAC approuvé.</span><span class="sxs-lookup"><span data-stu-id="722b6-111">All groups in the on-premises Active Directory infrastructure that have elevated privileges should be mapped to an approved RBAC role.</span></span>

<span data-ttu-id="722b6-112">Base de référence de la sécurité :</span><span class="sxs-lookup"><span data-stu-id="722b6-112">Security Baseline:</span></span>

- <span data-ttu-id="722b6-113">Toutes les ressources déployées dans le cloud doivent entrer dans la classification approuvée des données.</span><span class="sxs-lookup"><span data-stu-id="722b6-113">Any asset deployed to the cloud must have an approved data classification.</span></span>
- <span data-ttu-id="722b6-114">Les ressources identifiées avec un niveau de données protégé ne peuvent pas être déployées sur le cloud tant que les exigences de sécurité et de gouvernance suffisantes ne sont pas approuvées et implémentées.</span><span class="sxs-lookup"><span data-stu-id="722b6-114">No assets identified with a protected level of data may be deployed to the cloud, until sufficient requirements for security and governance can be approved and implemented.</span></span>
- <span data-ttu-id="722b6-115">Tant que les exigences de sécurité réseau minimales ne sont pas validées et régies, les environnements cloud sont considérés comme des zones démilitarisées et doivent répondre aux mêmes exigences de connexion que d’autres centres de données ou réseaux internes.</span><span class="sxs-lookup"><span data-stu-id="722b6-115">Until minimum network security requirements can be validated and governed, cloud environments are seen as a demilitarized zone and should meet similar connection requirements to other data centers or internal networks.</span></span>

<span data-ttu-id="722b6-116">Gestion des coûts :</span><span class="sxs-lookup"><span data-stu-id="722b6-116">Cost Management:</span></span>

- <span data-ttu-id="722b6-117">À des fins de suivi, toutes les ressources doivent être associées à un propriétaire d’application dans l’une des fonctions métier principales.</span><span class="sxs-lookup"><span data-stu-id="722b6-117">For tracking purposes, all assets must be assigned to an application owner within one of the core business functions.</span></span>
- <span data-ttu-id="722b6-118">En cas de préoccupations relatives aux coûts, des exigences de gouvernance supplémentaires sont établies avec le service financier.</span><span class="sxs-lookup"><span data-stu-id="722b6-118">When cost concerns arise, additional governance requirements will be established with the Finance team.</span></span>

<span data-ttu-id="722b6-119">Cohérence des ressources :</span><span class="sxs-lookup"><span data-stu-id="722b6-119">Resource Consistency:</span></span>

- <span data-ttu-id="722b6-120">Étant donné qu’aucune charge de travail critique n’est déployée à ce stade, il n’existe aucune exigence à respecter par rapport à un contrat de niveau de service, aux performances ou à la continuité d’activité et reprise d’activité.</span><span class="sxs-lookup"><span data-stu-id="722b6-120">Because no mission-critical workloads are deployed at this stage, there are no SLA, performance, or BCDR requirements to be governed.</span></span>
- <span data-ttu-id="722b6-121">Lorsque des charges de travail critiques sont déployées, des exigences de gouvernance supplémentaires sont établies avec le service des opérations informatiques.</span><span class="sxs-lookup"><span data-stu-id="722b6-121">When mission-critical workloads are deployed, additional governance requirements will be established with IT operations.</span></span>

## <a name="processes"></a><span data-ttu-id="722b6-122">Processus</span><span class="sxs-lookup"><span data-stu-id="722b6-122">Processes</span></span>

<span data-ttu-id="722b6-123">Aucun budget n’a été alloué à la surveillance et à l’application continues de ces stratégies de gouvernance.</span><span class="sxs-lookup"><span data-stu-id="722b6-123">No budget has been allocated for ongoing monitoring and enforcement of these governance policies.</span></span> <span data-ttu-id="722b6-124">C’est pourquoi l’équipe de gouvernance cloud dispose de quelques solutions ponctuelles afin de veiller au bon respect des instructions stratégiques.</span><span class="sxs-lookup"><span data-stu-id="722b6-124">Because of that, the Cloud Governance team has some ad hoc ways to monitor adherence to policy statements.</span></span>

- <span data-ttu-id="722b6-125">**Formation :** L’équipe de gouvernance coud consacre du temps à former les équipes d’adoption du cloud aux parcours de gouvernance qui sous-tendent ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="722b6-125">**Education**: The Cloud Governance team is investing time to educate the cloud adoption teams on the governance journeys that support these policies.</span></span>
- <span data-ttu-id="722b6-126">Révisions du **déploiement** : Avant de déployer une ressource, l’équipe de gouvernance cloud examine le parcours de gouvernance aux côtés de l’équipe d’adoption du cloud.</span><span class="sxs-lookup"><span data-stu-id="722b6-126">**Deployment** reviews: Before deploying any asset, the Cloud Governance team will review the governance journey with the cloud adoption teams.</span></span>