---
title: Supporto per le query
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: db3580d0a29353aac027bddd8f040d3085d674af
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665295"
---
# <a name="support-for-queries"></a><span data-ttu-id="c0da0-102">Supporto per le query</span><span class="sxs-lookup"><span data-stu-id="c0da0-102">Support for Queries</span></span>
<span data-ttu-id="c0da0-103">L'archivio di istanze del flusso di lavoro SQL registra un set di proprietà note nell'archivio.</span><span class="sxs-lookup"><span data-stu-id="c0da0-103">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="c0da0-104">Gli utenti possono eseguire query per le istanze basate su queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="c0da0-104">Users can query for instances based on these properties.</span></span> <span data-ttu-id="c0da0-105">Nell'elenco seguente sono contenute alcune di queste proprietà note:</span><span class="sxs-lookup"><span data-stu-id="c0da0-105">The following list contains some of these well-known properties:</span></span>  
  
- <span data-ttu-id="c0da0-106">**Nome del sito.**</span><span class="sxs-lookup"><span data-stu-id="c0da0-106">**Site Name.**</span></span> <span data-ttu-id="c0da0-107">Nome del sito Web che contiene il servizio.</span><span class="sxs-lookup"><span data-stu-id="c0da0-107">Name of the Web site that contains the service.</span></span>  
  
- <span data-ttu-id="c0da0-108">**Percorso relativo dell'applicazione.**</span><span class="sxs-lookup"><span data-stu-id="c0da0-108">**Relative Application Path.**</span></span> <span data-ttu-id="c0da0-109">Percorso dell'applicazione relativo al sito Web.</span><span class="sxs-lookup"><span data-stu-id="c0da0-109">Path of the application relative to the Web site.</span></span>  
  
- <span data-ttu-id="c0da0-110">**Percorso relativo del servizio.**</span><span class="sxs-lookup"><span data-stu-id="c0da0-110">**Relative Service Path.**</span></span> <span data-ttu-id="c0da0-111">Percorso del servizio relativo all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c0da0-111">Path of the service relative to the application.</span></span>  
  
- <span data-ttu-id="c0da0-112">**Nome del servizio.**</span><span class="sxs-lookup"><span data-stu-id="c0da0-112">**Service Name.**</span></span> <span data-ttu-id="c0da0-113">Nome del servizio.</span><span class="sxs-lookup"><span data-stu-id="c0da0-113">Name of the service.</span></span>  
  
- <span data-ttu-id="c0da0-114">**Servizio Namespace.**</span><span class="sxs-lookup"><span data-stu-id="c0da0-114">**Service Namespace.**</span></span> <span data-ttu-id="c0da0-115">Nome dello spazio dei nomi utilizzato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="c0da0-115">Name of the namespace that the service uses.</span></span>  
  
- <span data-ttu-id="c0da0-116">**Computer corrente.**</span><span class="sxs-lookup"><span data-stu-id="c0da0-116">**Current Machine.**</span></span>  
  
- <span data-ttu-id="c0da0-117">**Ultimo macchina**.</span><span class="sxs-lookup"><span data-stu-id="c0da0-117">**Last Machine**.</span></span> <span data-ttu-id="c0da0-118">Computer su cui l'istanza del servizio flusso di lavoro è stata eseguita l'ultima volta.</span><span class="sxs-lookup"><span data-stu-id="c0da0-118">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0da0-119">Per gli scenari indipendenti che usano l'host del servizio del flusso di lavoro vengono popolate solo le ultime quattro proprietà.</span><span class="sxs-lookup"><span data-stu-id="c0da0-119">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="c0da0-120">Per gli scenari dell'applicazione flusso di lavoro, viene popolata solo l'ultima proprietà.</span><span class="sxs-lookup"><span data-stu-id="c0da0-120">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="c0da0-121">L'esecuzione del flusso di lavoro fornisce valori per le prime tre proprietà.</span><span class="sxs-lookup"><span data-stu-id="c0da0-121">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="c0da0-122">L'host del servizio del flusso di lavoro fornisce il valore per il **Suspend Reason** proprietà.</span><span class="sxs-lookup"><span data-stu-id="c0da0-122">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="c0da0-123">La Store di istanza del flusso di lavoro SQL stesso fornisce valori per il **Last Updated Machine** proprietà.</span><span class="sxs-lookup"><span data-stu-id="c0da0-123">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="c0da0-124">La funzionalità di archivio di istanze del flusso di lavoro SQL consente anche di specificare le proprietà personalizzate per cui si desidera archiviare i valori nel database di persistenza e che si desidera usare nelle query.</span><span class="sxs-lookup"><span data-stu-id="c0da0-124">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="c0da0-125">Per altre informazioni sulle promozioni personalizzate, vedere [Store estendibilità](store-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="c0da0-125">For more information about custom promotions, see [Store Extensibility](store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="c0da0-126">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="c0da0-126">Views</span></span>  
 <span data-ttu-id="c0da0-127">L'archivio di istanze contiene le visualizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c0da0-127">The instance store contains the following views.</span></span> <span data-ttu-id="c0da0-128">Visualizzare [Schema di Database di persistenza](persistence-database-schema.md) per altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="c0da0-128">See [Persistence Database Schema](persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="c0da0-129">Visualizzazione Instances</span><span class="sxs-lookup"><span data-stu-id="c0da0-129">The Instances View</span></span>  
 <span data-ttu-id="c0da0-130">La visualizzazione Instances contiene i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0da0-130">The Instances view contains the following fields:</span></span>  
  
1. <span data-ttu-id="c0da0-131">**Id**</span><span class="sxs-lookup"><span data-stu-id="c0da0-131">**Id**</span></span>  
  
2. <span data-ttu-id="c0da0-132">**PendingTimer**</span><span class="sxs-lookup"><span data-stu-id="c0da0-132">**PendingTimer**</span></span>  
  
3. <span data-ttu-id="c0da0-133">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="c0da0-133">**CreationTime**</span></span>  
  
4. <span data-ttu-id="c0da0-134">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="c0da0-134">**LastUpdatedTime**</span></span>  
  
5. <span data-ttu-id="c0da0-135">**ServiceDeploymentId**</span><span class="sxs-lookup"><span data-stu-id="c0da0-135">**ServiceDeploymentId**</span></span>  
  
6. <span data-ttu-id="c0da0-136">**SuspensionExceptionName**</span><span class="sxs-lookup"><span data-stu-id="c0da0-136">**SuspensionExceptionName**</span></span>  
  
7. <span data-ttu-id="c0da0-137">**SuspensionReason**</span><span class="sxs-lookup"><span data-stu-id="c0da0-137">**SuspensionReason**</span></span>  
  
8. <span data-ttu-id="c0da0-138">**ActiveBookmarks**</span><span class="sxs-lookup"><span data-stu-id="c0da0-138">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="c0da0-139">**CurrentMachine**</span><span class="sxs-lookup"><span data-stu-id="c0da0-139">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="c0da0-140">**LastMachine**</span><span class="sxs-lookup"><span data-stu-id="c0da0-140">**LastMachine**</span></span>  
  
11. <span data-ttu-id="c0da0-141">**ExecutionStatus**</span><span class="sxs-lookup"><span data-stu-id="c0da0-141">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="c0da0-142">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="c0da0-142">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="c0da0-143">**IsSuspended**</span><span class="sxs-lookup"><span data-stu-id="c0da0-143">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="c0da0-144">**IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="c0da0-144">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="c0da0-145">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="c0da0-145">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="c0da0-146">**ReadWritePrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="c0da0-146">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="c0da0-147">**WriteOnlyPrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="c0da0-147">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="c0da0-148">**ReadWriteComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="c0da0-148">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="c0da0-149">**WriteOnlyComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="c0da0-149">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="c0da0-150">Visualizzazione ServiceDeployments</span><span class="sxs-lookup"><span data-stu-id="c0da0-150">The ServiceDeployments view</span></span>  
 <span data-ttu-id="c0da0-151">La visualizzazione ServiceDeployments contiene i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0da0-151">The ServiceDeployments view contains the following fields:</span></span>  
  
1. <span data-ttu-id="c0da0-152">**SiteName**</span><span class="sxs-lookup"><span data-stu-id="c0da0-152">**SiteName**</span></span>  
  
2. <span data-ttu-id="c0da0-153">**RelativeServicePath**</span><span class="sxs-lookup"><span data-stu-id="c0da0-153">**RelativeServicePath**</span></span>  
  
3. <span data-ttu-id="c0da0-154">**RelativeApplicationPath**</span><span class="sxs-lookup"><span data-stu-id="c0da0-154">**RelativeApplicationPath**</span></span>  
  
4. <span data-ttu-id="c0da0-155">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="c0da0-155">**ServiceName**</span></span>  
  
5. <span data-ttu-id="c0da0-156">**ServiceNamespace**</span><span class="sxs-lookup"><span data-stu-id="c0da0-156">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="c0da0-157">Visualizzazione InstancePromotedProperties</span><span class="sxs-lookup"><span data-stu-id="c0da0-157">The InstancePromotedProperties view</span></span>  
 <span data-ttu-id="c0da0-158">La visualizzazione InstancePromotedProperties contiene i campi seguenti.</span><span class="sxs-lookup"><span data-stu-id="c0da0-158">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="c0da0-159">Per informazioni dettagliate sulle proprietà innalzate di livello, vedere la [Store estendibilità](store-extensibility.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="c0da0-159">For details on promoted properties, see the [Store Extensibility](store-extensibility.md) topic.</span></span>  
  
1. <span data-ttu-id="c0da0-160">**InstanceId**</span><span class="sxs-lookup"><span data-stu-id="c0da0-160">**InstanceId**</span></span>  
  
2. <span data-ttu-id="c0da0-161">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="c0da0-161">**EncodingOption**</span></span>  
  
3. <span data-ttu-id="c0da0-162">**PromotionName**</span><span class="sxs-lookup"><span data-stu-id="c0da0-162">**PromotionName**</span></span>  
  
4. <span data-ttu-id="c0da0-163">**Valore #** (un intervallo di campi da **Value1** al **Value64**).</span><span class="sxs-lookup"><span data-stu-id="c0da0-163">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
