---
title: Resilienza della piattaforma Azure
description: Architettura di app .NET cloud native per Azure | Resilienza dell'infrastruttura cloud con Azure
ms.date: 06/30/2019
ms.openlocfilehash: 5d8ddc65ccdf4bb305be62e5caca30eab49f87e2
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182979"
---
# <a name="azure-platform-resiliency"></a><span data-ttu-id="9a6fe-103">Resilienza della piattaforma Azure</span><span class="sxs-lookup"><span data-stu-id="9a6fe-103">Azure platform resiliency</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="9a6fe-104">La creazione di un'applicazione affidabile nel cloud è diversa dallo sviluppo tradizionale di applicazioni locali.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-104">Building a reliable application in the cloud is different from traditional on-premises application development.</span></span> <span data-ttu-id="9a6fe-105">Mentre in passato è stato acquistato hardware di fascia superiore per la scalabilità verticale, in un ambiente cloud viene scalato in orizzontale. Invece di tentare di impedire errori, l'obiettivo è ridurre al minimo gli effetti e assicurare la stabilità del sistema.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-105">While historically you purchased higher-end hardware to scale up, in a cloud environment you scale out. Instead of trying to prevent failures, the goal is to minimize their effects and keep the system stable.</span></span>

<span data-ttu-id="9a6fe-106">Detto questo, le applicazioni cloud affidabili visualizzano caratteristiche distinte:</span><span class="sxs-lookup"><span data-stu-id="9a6fe-106">That said, reliable cloud applications display distinct characteristics:</span></span>

- <span data-ttu-id="9a6fe-107">Sono resilienti, si ripristinano normalmente dai problemi e continuano a funzionare.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-107">They're resilient, recover gracefully from problems, and continue to function.</span></span>
- <span data-ttu-id="9a6fe-108">Sono a disponibilità elevata e vengono eseguiti come progettato in uno stato integro senza tempi di inattività significativi.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-108">They're highly available (HA) and run as designed in a healthy state with no significant downtime.</span></span>

<span data-ttu-id="9a6fe-109">Comprendere il modo in cui queste caratteristiche interagiscono e il modo in cui influiscono sui costi è essenziale per la creazione di un'applicazione cloud nativa affidabile.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-109">Understanding how these characteristics work together - and how they affect cost - is essential to building a reliable cloud-native application.</span></span> <span data-ttu-id="9a6fe-110">Verranno ora esaminati i modi in cui è possibile creare resilienza e disponibilità nelle applicazioni native del cloud sfruttando le funzionalità del cloud di Azure.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-110">We'll next look at ways that you can build resiliency and availability into your cloud-native applications leveraging features from the Azure cloud.</span></span>

## <a name="design-with-redundancy"></a><span data-ttu-id="9a6fe-111">Progettazione con ridondanza</span><span class="sxs-lookup"><span data-stu-id="9a6fe-111">Design with redundancy</span></span>

<span data-ttu-id="9a6fe-112">Gli errori variano nell'ambito dell'effetto.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-112">Failures vary in scope of impact.</span></span> <span data-ttu-id="9a6fe-113">Un errore hardware, ad esempio un disco guasto, può interessare un singolo nodo in un cluster.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-113">A hardware failure, such as a failed disk, can affect a single node in a cluster.</span></span> <span data-ttu-id="9a6fe-114">Uno switch di rete con errore potrebbe influire su un intero rack server.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-114">A failed network switch could affect an entire server rack.</span></span> <span data-ttu-id="9a6fe-115">Errori meno comuni, ad esempio la perdita di energia, potrebbero causare l'interruzione di un intero data center.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-115">Less common failures, such as loss of power, could disrupt a whole datacenter.</span></span> <span data-ttu-id="9a6fe-116">Raramente, un'intera area diventa non disponibile.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-116">Rarely, an entire region becomes unavailable.</span></span>

<span data-ttu-id="9a6fe-117">La [ridondanza](https://docs.microsoft.com/azure/architecture/guide/design-principles/redundancy) è un modo per garantire la resilienza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-117">[Redundancy](https://docs.microsoft.com/azure/architecture/guide/design-principles/redundancy) is one way to provide application resilience.</span></span> <span data-ttu-id="9a6fe-118">Il livello di ridondanza esatto necessario dipende dai requisiti aziendali e influirà sia sui costi che sulla complessità del sistema.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-118">The exact level of redundancy needed depends on your business requirements and will affect both cost and complexity of your system.</span></span> <span data-ttu-id="9a6fe-119">Ad esempio, una distribuzione in più aree è più costosa e più complessa da gestire rispetto a una distribuzione in una singola area.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-119">For example, a multi-region deployment is more expensive and more complex to manage than a single-region deployment.</span></span> <span data-ttu-id="9a6fe-120">Sono necessarie procedure operative per gestire il failover e il failback.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-120">You'll need operational procedures to manage failover and failback.</span></span> <span data-ttu-id="9a6fe-121">I costi e la complessità aggiuntivi possono essere giustificati per alcuni scenari aziendali e non per altri.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-121">The additional cost and complexity might be justified for some business scenarios and not others.</span></span>

<span data-ttu-id="9a6fe-122">Per la ridondanza degli architetti, è necessario identificare i percorsi critici nell'applicazione e quindi determinare se è presente una ridondanza in ogni punto del percorso.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-122">To architect redundancy, you need to identify the critical paths in your application, and then determine if there's redundancy at each point in the path?</span></span> <span data-ttu-id="9a6fe-123">Se un sottosistema ha esito negativo, verrà eseguito il failover dell'applicazione in un altro?</span><span class="sxs-lookup"><span data-stu-id="9a6fe-123">If a subsystem should fail, will the application fail over to something else?</span></span> <span data-ttu-id="9a6fe-124">Infine, è necessario conoscere in modo chiaro le funzionalità incorporate nella piattaforma cloud di Azure che è possibile sfruttare per soddisfare i requisiti di ridondanza.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-124">Finally, you need a clear understanding of those features built into the Azure cloud platform that you can leverage to meet your redundancy requirements.</span></span> <span data-ttu-id="9a6fe-125">Di seguito sono riportati alcuni suggerimenti per l'architettura della ridondanza:</span><span class="sxs-lookup"><span data-stu-id="9a6fe-125">Here are recommendations for architecting redundancy:</span></span>

- <span data-ttu-id="9a6fe-126">*Distribuire più istanze dei servizi.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-126">*Deploy multiple instances of services.*</span></span> <span data-ttu-id="9a6fe-127">Se l'applicazione dipende da una singola istanza di un servizio, viene creato un singolo punto di errore.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-127">If your application depends on a single instance of a service, it creates a single point of failure.</span></span> <span data-ttu-id="9a6fe-128">Il provisioning di più istanze migliora sia la resilienza che la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-128">Provisioning multiple instances improves both resiliency and scalability.</span></span> <span data-ttu-id="9a6fe-129">Quando si esegue l'hosting nel servizio Azure Kubernetes, è possibile configurare in modo dichiarativo istanze ridondanti (set di repliche) nel file manifesto Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-129">When hosting in Azure Kubernetes Service, you can declaratively configure redundant instances (replica sets) in the Kubernetes manifest file.</span></span> <span data-ttu-id="9a6fe-130">Il valore del numero di repliche può essere gestito a livello di codice, nel portale o tramite le funzionalità di scalabilità automatica, che verranno discusse in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-130">The replica count value can be managed programmatically, in the portal or through autoscaling features, which will be discussed later on.</span></span>

- <span data-ttu-id="9a6fe-131">*Uso di un servizio di bilanciamento del carico.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-131">*Leveraging a load balancer.*</span></span> <span data-ttu-id="9a6fe-132">Il bilanciamento del carico distribuisce le richieste dell'applicazione a istanze del servizio integre e rimuove automaticamente le istanze non integre dalla rotazione.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-132">Load-balancing distributes your application's requests to healthy service instances and automatically removes unhealthy instances from rotation.</span></span> <span data-ttu-id="9a6fe-133">Quando si esegue la distribuzione in Kubernetes, il bilanciamento del carico può essere specificato nel file manifesto Kubernetes nella sezione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-133">When deploying to Kubernetes, load balancing can be specified in the Kubernetes manifest file in the Services section.</span></span>

- <span data-ttu-id="9a6fe-134">*Pianificare la distribuzione in più aree.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-134">*Plan for multiregion deployment.*</span></span> <span data-ttu-id="9a6fe-135">Se l'applicazione viene distribuita in una singola area e l'area non è più disponibile, anche l'applicazione non sarà più disponibile.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-135">If your application is deployed to a single region, and the region becomes unavailable, your application will also become unavailable.</span></span> <span data-ttu-id="9a6fe-136">Questo può essere inaccettabile in base alle condizioni dei contratti di servizio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-136">This may be unacceptable under the terms of your application's service level agreements.</span></span> <span data-ttu-id="9a6fe-137">In alternativa, è consigliabile distribuire l'applicazione e i relativi servizi in più aree.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-137">Instead, consider deploying your application and its services across multiple regions.</span></span> <span data-ttu-id="9a6fe-138">Ad esempio, un cluster Azure Kubernetes Service (AKS) viene distribuito in una singola area.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-138">For example, an Azure Kubernetes Service (AKS) cluster is deployed to a single region.</span></span> <span data-ttu-id="9a6fe-139">Per proteggere il sistema da un errore a livello di area, è possibile distribuire l'applicazione in più cluster AKS in aree diverse e usare la funzionalità [aree abbinate](https://buildazure.com/2017/01/06/azure-region-pairs-explained/) per coordinare gli aggiornamenti della piattaforma e assegnare priorità ai tentativi di ripristino.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-139">To protect your system from a regional failure, you might deploy your application to multiple AKS clusters across different regions and use the [Paired Regions](https://buildazure.com/2017/01/06/azure-region-pairs-explained/) feature to coordinate platform updates and prioritize recovery efforts.</span></span>

- <span data-ttu-id="9a6fe-140">*Abilitare la [replica geografica](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication).*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-140">*Enable [geo-replication](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication).*</span></span> <span data-ttu-id="9a6fe-141">La replica geografica per servizi quali il database SQL di Azure e Cosmos DB creerà le repliche secondarie dei dati in più aree.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-141">Geo-replication for services such as Azure SQL Database and Cosmos DB will create secondary replicas of your data across multiple regions.</span></span> <span data-ttu-id="9a6fe-142">Mentre entrambi i servizi eseguiranno automaticamente la replica dei dati all'interno della stessa area, la replica geografica proteggerà l'utente da un'interruzione a livello di area consentendo di eseguire il failover in un'area secondaria.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-142">While both services will automatically replicate data within the same region, geo-replication protects you against a regional outage by enabling you to fail over to a secondary region.</span></span> <span data-ttu-id="9a6fe-143">Un'altra procedura consigliata per la replica geografica si concentra sull'archiviazione delle immagini del contenitore.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-143">Another best practice for geo-replication centers around storing container images.</span></span> <span data-ttu-id="9a6fe-144">Per distribuire un servizio in AKS, è necessario archiviare ed eseguire il pull dell'immagine da un repository.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-144">To deploy a service in AKS, you need to store and pull the image from a repository.</span></span> <span data-ttu-id="9a6fe-145">Azure Container Registry si integra con AKS ed è in grado di archiviare in modo sicuro le immagini del contenitore.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-145">Azure Container Registry integrates with AKS and can securely store container images.</span></span> <span data-ttu-id="9a6fe-146">Per migliorare le prestazioni e la disponibilità, prendere in considerazione la replica geografica delle immagini in un registro in ogni area in cui si dispone di un cluster AKS.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-146">To improve performance and availability, consider geo-replicating your images to a registry in each region where you have an AKS cluster.</span></span> <span data-ttu-id="9a6fe-147">Ogni cluster AKS estrae quindi le immagini del contenitore dal registro contenitori locale nella propria area, come illustrato nella figura 6-6:</span><span class="sxs-lookup"><span data-stu-id="9a6fe-147">Each AKS cluster then pulls container images from the local container registry in its region as shown in Figure 6-6:</span></span>

![Risorse replicate tra le aree](./media/replicated-resources.png)

<span data-ttu-id="9a6fe-149">**Figura 6-6**.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-149">**Figure 6-6**.</span></span> <span data-ttu-id="9a6fe-150">Risorse replicate tra le aree</span><span class="sxs-lookup"><span data-stu-id="9a6fe-150">Replicated resources across regions</span></span>

- <span data-ttu-id="9a6fe-151">*Implementare un servizio di bilanciamento del carico del traffico DNS.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-151">*Implement a DNS traffic load balancer.*</span></span> <span data-ttu-id="9a6fe-152">[Gestione traffico di Azure](https://docs.microsoft.com/azure/traffic-manager/traffic-manager-overview) offre disponibilità elevata per le applicazioni critiche tramite il bilanciamento del carico a livello di DNS.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-152">[Azure Traffic Manager](https://docs.microsoft.com/azure/traffic-manager/traffic-manager-overview) provides high-availability for critical applications by load-balancing at the DNS level.</span></span> <span data-ttu-id="9a6fe-153">Può instradare il traffico a aree diverse in base a geografia, tempo di risposta del cluster e anche integrità dell'endpoint dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-153">It can route traffic to different regions based on geography, cluster response time, and even application endpoint health.</span></span> <span data-ttu-id="9a6fe-154">Gestione traffico di Azure, ad esempio, può indirizzare i clienti al cluster AKS più vicino e all'istanza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-154">For example, Azure Traffic Manager can direct customers to the closest AKS cluster and application instance.</span></span> <span data-ttu-id="9a6fe-155">Se si dispone di più cluster AKS in aree diverse, usare gestione traffico per controllare il flusso del traffico verso le applicazioni in esecuzione in ogni cluster.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-155">If you have multiple AKS clusters in different regions, use Traffic Manager to control how traffic flows to the applications that run in each cluster.</span></span> <span data-ttu-id="9a6fe-156">Nella figura 6-7 è illustrato questo scenario.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-156">Figure 6-7 shows this scenario.</span></span>

![AKS e gestione traffico di Azure](./media/aks-traffic-manager.png)

<span data-ttu-id="9a6fe-158">**Figura 6-7**.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-158">**Figure 6-7**.</span></span> <span data-ttu-id="9a6fe-159">AKS e gestione traffico di Azure</span><span class="sxs-lookup"><span data-stu-id="9a6fe-159">AKS and Azure Traffic Manager</span></span>

## <a name="design-for-scalability"></a><span data-ttu-id="9a6fe-160">Progettazione per la scalabilità</span><span class="sxs-lookup"><span data-stu-id="9a6fe-160">Design for scalability</span></span>

<span data-ttu-id="9a6fe-161">Il cloud si sviluppa in scala.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-161">The cloud thrives on scaling.</span></span> <span data-ttu-id="9a6fe-162">La possibilità di aumentare o ridurre le risorse di sistema per risolvere un carico di sistema crescente/decrescente è un principio fondamentale del cloud di Azure.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-162">The ability to increase/decrease system resources to address increasing/decreasing system load is a key tenet of the Azure cloud.</span></span> <span data-ttu-id="9a6fe-163">Tuttavia, per ridimensionare in modo efficace un'applicazione, è necessario conoscere le funzionalità di scalabilità di ogni servizio di Azure incluso nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-163">But, to effectively scale an application, you need an understanding of the scaling features of each Azure service that you include in your application.</span></span>  <span data-ttu-id="9a6fe-164">Ecco alcuni suggerimenti per implementare efficacemente il ridimensionamento nel sistema.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-164">Here are recommendations for effectively implementing scaling in your system.</span></span>

- <span data-ttu-id="9a6fe-165">*Progettazione per la scalabilità.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-165">*Design for scaling.*</span></span> <span data-ttu-id="9a6fe-166">Un'applicazione deve essere progettata per la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-166">An application must be designed for scaling.</span></span> <span data-ttu-id="9a6fe-167">Per iniziare, i servizi devono essere senza stato, in modo che le richieste possano essere indirizzate a qualsiasi istanza.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-167">To start, services should be stateless so that requests can be routed to any instance.</span></span> <span data-ttu-id="9a6fe-168">La presenza di servizi senza stato significa anche che l'aggiunta o la rimozione di un'istanza non influisce negativamente sugli utenti correnti.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-168">Having stateless services also means that adding or removing an instance doesn't adversely impact current users.</span></span>

- <span data-ttu-id="9a6fe-169">*Carichi di lavoro della partizione*.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-169">*Partition workloads*.</span></span> <span data-ttu-id="9a6fe-170">La scomposizione dei domini in microservizi indipendenti e indipendenti permette a ogni servizio di ridimensionarsi in modo indipendente dagli altri.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-170">Decomposing domains into independent, self-contained microservices enable each service to scale independently of others.</span></span> <span data-ttu-id="9a6fe-171">In genere, i servizi avranno esigenze e requisiti di scalabilità diversi.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-171">Typically, services will have different scalability needs and requirements.</span></span> <span data-ttu-id="9a6fe-172">Il partizionamento consente di ridimensionare solo gli elementi che è necessario ridimensionare senza il costo superfluo di ridimensionare un'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-172">Partitioning enables you to scale only what needs to be scaled without the unnecessary cost of scaling an entire application.</span></span>

- <span data-ttu-id="9a6fe-173">*Ottimizza la scalabilità orizzontale.* Le applicazioni basate sul cloud favoriscono la scalabilità orizzontale delle risorse anziché la scalabilità verticale.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-173">*Favor scale-out.* Cloud-based applications favor scaling out resources as opposed to scaling up.</span></span> <span data-ttu-id="9a6fe-174">La scalabilità orizzontale (detta anche scalabilità orizzontale) comporta l'aggiunta di altre risorse del servizio a un sistema esistente per soddisfare e condividere un livello di prestazioni desiderato.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-174">Scaling out (also known as horizontal scaling) involves adding more service resources to an existing system to meet and share a desired level of performance.</span></span> <span data-ttu-id="9a6fe-175">La scalabilità verticale (anche nota come scalabilità verticale) comporta la sostituzione delle risorse esistenti con hardware più potente (più core di disco, memoria e elaborazione).</span><span class="sxs-lookup"><span data-stu-id="9a6fe-175">Scaling up (also known as vertical scaling) involves replacing existing resources with more powerful hardware (more disk, memory, and processing cores).</span></span> <span data-ttu-id="9a6fe-176">La scalabilità orizzontale può essere richiamata automaticamente con le funzionalità di scalabilità automatica disponibili in alcune risorse cloud di Azure.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-176">Scaling out can be invoked automatically with the autoscaling features available in some Azure cloud resources.</span></span> <span data-ttu-id="9a6fe-177">La scalabilità orizzontale in più risorse consente inoltre di aggiungere ridondanza al sistema globale.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-177">Scaling out across multiple resources also adds redundancy to the overall system.</span></span> <span data-ttu-id="9a6fe-178">Infine, la scalabilità verticale di una singola risorsa è in genere più costosa rispetto alla scalabilità orizzontale in molte risorse più piccole.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-178">Finally scaling up a single resource is typically more expensive than scaling out across many smaller resources.</span></span> <span data-ttu-id="9a6fe-179">La figura 6-8 illustra i due approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a6fe-179">Figure 6-8 shows the two approaches:</span></span>

![Scalabilità verticale rispetto a scalabilità orizzontale](./media/scale-up-scale-out.png)

<span data-ttu-id="9a6fe-181">**Figura 6-8.**</span><span class="sxs-lookup"><span data-stu-id="9a6fe-181">**Figure 6-8.**</span></span> <span data-ttu-id="9a6fe-182">Scalabilità verticale rispetto a scalabilità orizzontale</span><span class="sxs-lookup"><span data-stu-id="9a6fe-182">Scale up versus scale out</span></span>

- <span data-ttu-id="9a6fe-183">*Ridimensiona proporzionalmente.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-183">*Scale proportionally.*</span></span> <span data-ttu-id="9a6fe-184">Quando si ridimensiona un servizio, è opportuno pensare in termini di *set di risorse*.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-184">When scaling a service, think in terms of *resource sets*.</span></span> <span data-ttu-id="9a6fe-185">Se fosse necessario scalare in modo significativo un servizio specifico, quale impatto avrebbe sugli archivi dati back-end, le cache e i servizi dipendenti?</span><span class="sxs-lookup"><span data-stu-id="9a6fe-185">If you were to dramatically scale out a specific service, what impact would that have on back-end data stores, caches and dependent services?</span></span> <span data-ttu-id="9a6fe-186">Alcune risorse, ad esempio Cosmos DB possono scalare in modo proporzionale, mentre molte altre non possono.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-186">Some resources such as Cosmos DB can scale out proportionally, while many others can't.</span></span> <span data-ttu-id="9a6fe-187">Si desidera assicurarsi di non aumentare la scalabilità orizzontale di una risorsa fino a un punto in cui si esauriranno altre risorse associate.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-187">You want to ensure that you don't scale out a resource to a point where it will exhaust other associated resources.</span></span>

- <span data-ttu-id="9a6fe-188">*Evitare l'affinità.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-188">*Avoid affinity.*</span></span> <span data-ttu-id="9a6fe-189">Una procedura consigliata consiste nel garantire che un nodo non richieda affinità locale, spesso definita *sessione*permanente.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-189">A best practice is to ensure a node doesn't require local affinity, often referred to as a *sticky session*.</span></span> <span data-ttu-id="9a6fe-190">Una richiesta deve essere in grado di indirizzare a qualsiasi istanza.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-190">A request should be able to route to any instance.</span></span> <span data-ttu-id="9a6fe-191">Se è necessario salvare lo stato, è necessario salvarlo in una cache distribuita, ad esempio [cache Redis di Azure](https://azure.microsoft.com/services/cache/).</span><span class="sxs-lookup"><span data-stu-id="9a6fe-191">If you need to persist state, it should be saved to a distributed cache, such as [Azure Redis cache](https://azure.microsoft.com/services/cache/).</span></span>

- <span data-ttu-id="9a6fe-192">*Sfrutta i vantaggi delle funzionalità di scalabilità automatica della piattaforma.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-192">*Take advantage of platform autoscaling features.*</span></span> <span data-ttu-id="9a6fe-193">Usare le funzionalità di scalabilità automatica predefinite, laddove possibile, anziché meccanismi personalizzati o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-193">Use built-in autoscaling features whenever possible, rather than custom or third-party mechanisms.</span></span> <span data-ttu-id="9a6fe-194">Laddove possibile, usare le regole di scalabilità pianificate per garantire che le risorse siano disponibili senza un ritardo di avvio, ma aggiungere la scalabilità automatica reattiva alle regole in base alle esigenze, per gestire modifiche impreviste della richiesta.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-194">Where possible, use scheduled scaling rules to ensure that resources are available without a startup delay, but add reactive autoscaling to the rules as appropriate, to cope with unexpected changes in demand.</span></span> <span data-ttu-id="9a6fe-195">Per altre informazioni, vedere [linee guida per la scalabilità](https://docs.microsoft.com/azure/architecture/best-practices/auto-scaling)automatica.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-195">For more information, see [Autoscaling guidance](https://docs.microsoft.com/azure/architecture/best-practices/auto-scaling).</span></span>

 - <span data-ttu-id="9a6fe-196">*Scalabilità verticale in modo aggressivo.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-196">*Scale-up aggressively.*</span></span> <span data-ttu-id="9a6fe-197">Una procedura finale è la scalabilità verticale in modo che sia possibile raggiungere rapidamente i picchi di traffico immediatamente senza perdere il business.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-197">A final practice would be to scale up aggressively so that you can quickly meet immediate spikes in traffic without losing business.</span></span> <span data-ttu-id="9a6fe-198">E quindi ridurre le risorse non necessarie (ovvero rimuovere le risorse non necessarie) in modo conservativo per assicurare la stabilità del sistema.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-198">And, then scale down (that is, remove unneeded resources) conservatively to keep the system stable.</span></span> <span data-ttu-id="9a6fe-199">Un modo semplice per implementare questa operazione consiste nell'impostare il periodo di raffreddamento, ovvero il tempo di attesa tra le operazioni di ridimensionamento, fino a cinque minuti per l'aggiunta di risorse e fino a 15 minuti per la rimozione di istanze.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-199">A simple way to implement this is to set the cool down period, which is the time to wait between scaling operations, to five minutes for adding resources and up to 15 minutes for removing instances.</span></span>

## <a name="built-in-retry-in-services"></a><span data-ttu-id="9a6fe-200">Tentativi predefiniti nei servizi</span><span class="sxs-lookup"><span data-stu-id="9a6fe-200">Built-in retry in services</span></span>

<span data-ttu-id="9a6fe-201">È stata consigliata la procedura consigliata per implementare le operazioni di ripetizione a livello di codice in una sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-201">We encouraged the best practice of implementing programmatic retry operations in an earlier section.</span></span> <span data-ttu-id="9a6fe-202">Tenere presente che molti servizi di Azure e gli SDK client corrispondenti includono anche meccanismi di ripetizione dei tentativi.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-202">Keep in mind that many Azure services and their corresponding client SDKs also include retry mechanisms.</span></span> <span data-ttu-id="9a6fe-203">L'elenco seguente riepiloga le funzionalità di ripetizione dei tentativi nei molti servizi di Azure trattati in questo libro:</span><span class="sxs-lookup"><span data-stu-id="9a6fe-203">The following list summarizes retry features in the many of the Azure services that are discussed in this book:</span></span>

- <span data-ttu-id="9a6fe-204">*Azure Cosmos DB.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-204">*Azure Cosmos DB.*</span></span> <span data-ttu-id="9a6fe-205">La <xref:Microsoft.Azure.Documents.Client.DocumentClient> classe dell'API client ritira automaticamente i tentativi non riusciti.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-205">The <xref:Microsoft.Azure.Documents.Client.DocumentClient> class from the client API automatically retires failed attempts.</span></span> <span data-ttu-id="9a6fe-206">Il numero di tentativi e il tempo massimo di attesa sono configurabili.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-206">The number of retries and maximum wait time are configurable.</span></span> <span data-ttu-id="9a6fe-207">Le eccezioni generate dall'API client sono richieste che superano i criteri di ripetizione o gli errori non temporanei.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-207">Exceptions thrown by the client API are either requests that exceed the retry policy or non-transient errors.</span></span>

- <span data-ttu-id="9a6fe-208">*Cache Redis di Azure.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-208">*Azure Redis Cache.*</span></span> <span data-ttu-id="9a6fe-209">Il client Redis StackExchange usa una classe di gestione connessione che include tentativi per i tentativi non riusciti.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-209">The Redis StackExchange client uses a connection manager class that includes retries on failed attempts.</span></span> <span data-ttu-id="9a6fe-210">Il numero di tentativi, i criteri di ripetizione e il tempo di attesa specifici sono configurabili.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-210">The number of retries, specific retry policy and wait time are all configurable.</span></span>

- <span data-ttu-id="9a6fe-211">*Bus di servizio di Azure.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-211">*Azure Service Bus.*</span></span> <span data-ttu-id="9a6fe-212">Il client del bus di servizio espone una [classe RetryPolicy](xref:Microsoft.ServiceBus.RetryPolicy) che può essere configurata con un intervallo di back-off <xref:Microsoft.ServiceBus.RetryExponential.TerminationTimeBuffer>, un numero di tentativi e, che specifica il tempo massimo che un'operazione può assumere.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-212">The Service Bus client exposes a [RetryPolicy class](xref:Microsoft.ServiceBus.RetryPolicy) that can be configured with a back-off interval, retry count, and <xref:Microsoft.ServiceBus.RetryExponential.TerminationTimeBuffer>, which specifies the maximum time an operation can take.</span></span> <span data-ttu-id="9a6fe-213">I criteri predefiniti sono nove tentativi di ripetizione massimi con un periodo di backoff di 30 secondi tra i tentativi.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-213">The default policy is nine maximum retry attempts with a 30-second backoff period between attempts.</span></span>

- <span data-ttu-id="9a6fe-214">*Database SQL di Azure.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-214">*Azure SQL Database.*</span></span> <span data-ttu-id="9a6fe-215">Quando si usa la libreria [Entity Framework Core](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency) , viene fornito il supporto per i tentativi.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-215">Retry support is provided when using the [Entity Framework Core](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency) library.</span></span>

- <span data-ttu-id="9a6fe-216">*Archiviazione di Azure.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-216">*Azure Storage.*</span></span> <span data-ttu-id="9a6fe-217">La libreria client di archiviazione supporta le operazioni di ripetizione dei tentativi.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-217">The storage client library support retry operations.</span></span> <span data-ttu-id="9a6fe-218">Le strategie variano tra le tabelle, i BLOB e le code di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-218">The strategies vary across Azure storage tables, blobs, and queues.</span></span> <span data-ttu-id="9a6fe-219">Inoltre, i tentativi alternativi passano tra i percorsi di servizi di archiviazione primari e secondari quando è abilitata la funzionalità di ridondanza geografica.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-219">As well, alternate retries switch between primary and secondary storage services locations when the geo-redundancy feature is enabled.</span></span>

- <span data-ttu-id="9a6fe-220">*Hub eventi di Azure.*</span><span class="sxs-lookup"><span data-stu-id="9a6fe-220">*Azure Event Hubs.*</span></span> <span data-ttu-id="9a6fe-221">La libreria client dell'hub eventi presenta una proprietà RetryPolicy, che include una funzionalità backoff esponenziale configurabile.</span><span class="sxs-lookup"><span data-stu-id="9a6fe-221">The Event Hub client library features a RetryPolicy property, which includes a configurable exponential backoff feature.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9a6fe-222">[Precedente](application-resiliency-patterns.md)
>[Successivo](resilient-communications.md)</span><span class="sxs-lookup"><span data-stu-id="9a6fe-222">[Previous](application-resiliency-patterns.md)
[Next](resilient-communications.md)</span></span>