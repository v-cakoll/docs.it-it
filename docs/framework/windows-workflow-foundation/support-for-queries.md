---
title: Supporto per le query
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: 30695fcd791a0d69c31a897068d69838c80c3957
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641515"
---
# <a name="support-for-queries"></a><span data-ttu-id="40d6a-102">Supporto per le query</span><span class="sxs-lookup"><span data-stu-id="40d6a-102">Support for Queries</span></span>
<span data-ttu-id="40d6a-103">L'archivio di istanze del flusso di lavoro SQL registra un set di proprietà note nell'archivio.</span><span class="sxs-lookup"><span data-stu-id="40d6a-103">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="40d6a-104">Gli utenti possono eseguire query per le istanze basate su queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="40d6a-104">Users can query for instances based on these properties.</span></span> <span data-ttu-id="40d6a-105">Nell'elenco seguente sono contenute alcune di queste proprietà note:</span><span class="sxs-lookup"><span data-stu-id="40d6a-105">The following list contains some of these well-known properties:</span></span>  
  
- <span data-ttu-id="40d6a-106">**Nome del sito.**</span><span class="sxs-lookup"><span data-stu-id="40d6a-106">**Site Name.**</span></span> <span data-ttu-id="40d6a-107">Nome del sito Web che contiene il servizio.</span><span class="sxs-lookup"><span data-stu-id="40d6a-107">Name of the Web site that contains the service.</span></span>  
  
- <span data-ttu-id="40d6a-108">**Percorso relativo dell'applicazione.**</span><span class="sxs-lookup"><span data-stu-id="40d6a-108">**Relative Application Path.**</span></span> <span data-ttu-id="40d6a-109">Percorso dell'applicazione relativo al sito Web.</span><span class="sxs-lookup"><span data-stu-id="40d6a-109">Path of the application relative to the Web site.</span></span>  
  
- <span data-ttu-id="40d6a-110">**Percorso relativo del servizio.**</span><span class="sxs-lookup"><span data-stu-id="40d6a-110">**Relative Service Path.**</span></span> <span data-ttu-id="40d6a-111">Percorso del servizio relativo all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="40d6a-111">Path of the service relative to the application.</span></span>  
  
- <span data-ttu-id="40d6a-112">**Nome del servizio.**</span><span class="sxs-lookup"><span data-stu-id="40d6a-112">**Service Name.**</span></span> <span data-ttu-id="40d6a-113">Nome del servizio.</span><span class="sxs-lookup"><span data-stu-id="40d6a-113">Name of the service.</span></span>  
  
- <span data-ttu-id="40d6a-114">**Servizio Namespace.**</span><span class="sxs-lookup"><span data-stu-id="40d6a-114">**Service Namespace.**</span></span> <span data-ttu-id="40d6a-115">Nome dello spazio dei nomi utilizzato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="40d6a-115">Name of the namespace that the service uses.</span></span>  
  
- <span data-ttu-id="40d6a-116">**Computer corrente.**</span><span class="sxs-lookup"><span data-stu-id="40d6a-116">**Current Machine.**</span></span>  
  
- <span data-ttu-id="40d6a-117">**Ultimo macchina**.</span><span class="sxs-lookup"><span data-stu-id="40d6a-117">**Last Machine**.</span></span> <span data-ttu-id="40d6a-118">Computer su cui l'istanza del servizio flusso di lavoro è stata eseguita l'ultima volta.</span><span class="sxs-lookup"><span data-stu-id="40d6a-118">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40d6a-119">Per gli scenari indipendenti che usano l'host del servizio del flusso di lavoro vengono popolate solo le ultime quattro proprietà.</span><span class="sxs-lookup"><span data-stu-id="40d6a-119">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="40d6a-120">Per gli scenari dell'applicazione flusso di lavoro, viene popolata solo l'ultima proprietà.</span><span class="sxs-lookup"><span data-stu-id="40d6a-120">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="40d6a-121">L'esecuzione del flusso di lavoro fornisce valori per le prime tre proprietà.</span><span class="sxs-lookup"><span data-stu-id="40d6a-121">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="40d6a-122">L'host del servizio del flusso di lavoro fornisce il valore per il **Suspend Reason** proprietà.</span><span class="sxs-lookup"><span data-stu-id="40d6a-122">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="40d6a-123">La Store di istanza del flusso di lavoro SQL stesso fornisce valori per il **Last Updated Machine** proprietà.</span><span class="sxs-lookup"><span data-stu-id="40d6a-123">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="40d6a-124">La funzionalità di archivio di istanze del flusso di lavoro SQL consente anche di specificare le proprietà personalizzate per cui si desidera archiviare i valori nel database di persistenza e che si desidera usare nelle query.</span><span class="sxs-lookup"><span data-stu-id="40d6a-124">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="40d6a-125">Per altre informazioni sulle promozioni personalizzate, vedere [Store estendibilità](store-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="40d6a-125">For more information about custom promotions, see [Store Extensibility](store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="40d6a-126">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="40d6a-126">Views</span></span>  
 <span data-ttu-id="40d6a-127">L'archivio di istanze contiene le visualizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="40d6a-127">The instance store contains the following views.</span></span> <span data-ttu-id="40d6a-128">Visualizzare [Schema di Database di persistenza](persistence-database-schema.md) per altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="40d6a-128">See [Persistence Database Schema](persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="40d6a-129">Visualizzazione Instances</span><span class="sxs-lookup"><span data-stu-id="40d6a-129">The Instances View</span></span>  
 <span data-ttu-id="40d6a-130">La visualizzazione Instances contiene i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="40d6a-130">The Instances view contains the following fields:</span></span>  
  
1. <span data-ttu-id="40d6a-131">**Id**</span><span class="sxs-lookup"><span data-stu-id="40d6a-131">**Id**</span></span>  
  
2. <span data-ttu-id="40d6a-132">**PendingTimer**</span><span class="sxs-lookup"><span data-stu-id="40d6a-132">**PendingTimer**</span></span>  
  
3. <span data-ttu-id="40d6a-133">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="40d6a-133">**CreationTime**</span></span>  
  
4. <span data-ttu-id="40d6a-134">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="40d6a-134">**LastUpdatedTime**</span></span>  
  
5. <span data-ttu-id="40d6a-135">**ServiceDeploymentId**</span><span class="sxs-lookup"><span data-stu-id="40d6a-135">**ServiceDeploymentId**</span></span>  
  
6. <span data-ttu-id="40d6a-136">**SuspensionExceptionName**</span><span class="sxs-lookup"><span data-stu-id="40d6a-136">**SuspensionExceptionName**</span></span>  
  
7. <span data-ttu-id="40d6a-137">**SuspensionReason**</span><span class="sxs-lookup"><span data-stu-id="40d6a-137">**SuspensionReason**</span></span>  
  
8. <span data-ttu-id="40d6a-138">**ActiveBookmarks**</span><span class="sxs-lookup"><span data-stu-id="40d6a-138">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="40d6a-139">**CurrentMachine**</span><span class="sxs-lookup"><span data-stu-id="40d6a-139">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="40d6a-140">**LastMachine**</span><span class="sxs-lookup"><span data-stu-id="40d6a-140">**LastMachine**</span></span>  
  
11. <span data-ttu-id="40d6a-141">**ExecutionStatus**</span><span class="sxs-lookup"><span data-stu-id="40d6a-141">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="40d6a-142">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="40d6a-142">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="40d6a-143">**IsSuspended**</span><span class="sxs-lookup"><span data-stu-id="40d6a-143">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="40d6a-144">**IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="40d6a-144">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="40d6a-145">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="40d6a-145">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="40d6a-146">**ReadWritePrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="40d6a-146">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="40d6a-147">**WriteOnlyPrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="40d6a-147">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="40d6a-148">**ReadWriteComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="40d6a-148">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="40d6a-149">**WriteOnlyComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="40d6a-149">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="40d6a-150">Visualizzazione ServiceDeployments</span><span class="sxs-lookup"><span data-stu-id="40d6a-150">The ServiceDeployments view</span></span>  
 <span data-ttu-id="40d6a-151">La visualizzazione ServiceDeployments contiene i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="40d6a-151">The ServiceDeployments view contains the following fields:</span></span>  
  
1. <span data-ttu-id="40d6a-152">**SiteName**</span><span class="sxs-lookup"><span data-stu-id="40d6a-152">**SiteName**</span></span>  
  
2. <span data-ttu-id="40d6a-153">**RelativeServicePath**</span><span class="sxs-lookup"><span data-stu-id="40d6a-153">**RelativeServicePath**</span></span>  
  
3. <span data-ttu-id="40d6a-154">**RelativeApplicationPath**</span><span class="sxs-lookup"><span data-stu-id="40d6a-154">**RelativeApplicationPath**</span></span>  
  
4. <span data-ttu-id="40d6a-155">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="40d6a-155">**ServiceName**</span></span>  
  
5. <span data-ttu-id="40d6a-156">**ServiceNamespace**</span><span class="sxs-lookup"><span data-stu-id="40d6a-156">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="40d6a-157">Visualizzazione InstancePromotedProperties</span><span class="sxs-lookup"><span data-stu-id="40d6a-157">The InstancePromotedProperties view</span></span>  
 <span data-ttu-id="40d6a-158">La visualizzazione InstancePromotedProperties contiene i campi seguenti.</span><span class="sxs-lookup"><span data-stu-id="40d6a-158">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="40d6a-159">Per informazioni dettagliate sulle proprietà innalzate di livello, vedere la [Store estendibilità](store-extensibility.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="40d6a-159">For details on promoted properties, see the [Store Extensibility](store-extensibility.md) topic.</span></span>  
  
1. <span data-ttu-id="40d6a-160">**InstanceId**</span><span class="sxs-lookup"><span data-stu-id="40d6a-160">**InstanceId**</span></span>  
  
2. <span data-ttu-id="40d6a-161">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="40d6a-161">**EncodingOption**</span></span>  
  
3. <span data-ttu-id="40d6a-162">**PromotionName**</span><span class="sxs-lookup"><span data-stu-id="40d6a-162">**PromotionName**</span></span>  
  
4. <span data-ttu-id="40d6a-163">**Valore #** (un intervallo di campi da **Value1** al **Value64**).</span><span class="sxs-lookup"><span data-stu-id="40d6a-163">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
