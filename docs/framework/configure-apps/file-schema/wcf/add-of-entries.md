---
title: <add> di <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 690fd07159e07b7e037f7330b31fdcba423e80f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920133"
---
# <a name="add-of-entries"></a><span data-ttu-id="58bb0-102">\<aggiungere > di \<voci ></span><span class="sxs-lookup"><span data-stu-id="58bb0-102">\<add> of \<entries></span></span>
<span data-ttu-id="58bb0-103">Rappresenta una voce di routing che esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="58bb0-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="58bb0-104">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="58bb0-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="58bb0-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="58bb0-105">\<system.serviceModel></span></span>  
<span data-ttu-id="58bb0-106">\<routing></span><span class="sxs-lookup"><span data-stu-id="58bb0-106">\<routing></span></span>  
<span data-ttu-id="58bb0-107">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="58bb0-107">\<filterTables></span></span>  
<span data-ttu-id="58bb0-108">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="58bb0-108">\<filterTable></span></span>  
<span data-ttu-id="58bb0-109">\<voci ></span><span class="sxs-lookup"><span data-stu-id="58bb0-109">\<entries></span></span>  
<span data-ttu-id="58bb0-110">\<add></span><span class="sxs-lookup"><span data-stu-id="58bb0-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58bb0-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58bb0-111">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58bb0-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="58bb0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="58bb0-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="58bb0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58bb0-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="58bb0-114">Attributes</span></span>  
  
|<span data-ttu-id="58bb0-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="58bb0-115">Attribute</span></span>|<span data-ttu-id="58bb0-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58bb0-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58bb0-117">backupList</span><span class="sxs-lookup"><span data-stu-id="58bb0-117">backupList</span></span>|<span data-ttu-id="58bb0-118">Stringa che specifica un riferimento a un elenco di backup di endpoint.</span><span class="sxs-lookup"><span data-stu-id="58bb0-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="58bb0-119">endpoint</span><span class="sxs-lookup"><span data-stu-id="58bb0-119">endpoint</span></span>|<span data-ttu-id="58bb0-120">Stringa che specifica un riferimento a un endpoint client che riceverà i messaggi corrispondenti al filtro specificato dall'attributo `filterName`.</span><span class="sxs-lookup"><span data-stu-id="58bb0-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="58bb0-121">filterName</span><span class="sxs-lookup"><span data-stu-id="58bb0-121">filterName</span></span>|<span data-ttu-id="58bb0-122">Stringa che specifica un riferimento a un elemento di filtro.</span><span class="sxs-lookup"><span data-stu-id="58bb0-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="58bb0-123">priorità</span><span class="sxs-lookup"><span data-stu-id="58bb0-123">priority</span></span>|<span data-ttu-id="58bb0-124">Integer che specifica la priorità di questa voce.</span><span class="sxs-lookup"><span data-stu-id="58bb0-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="58bb0-125">Le voci nella tabella di routing verranno valutate in base alla priorità, con 0 come priorità più bassa.</span><span class="sxs-lookup"><span data-stu-id="58bb0-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="58bb0-126">Tutte le voci per una priorità specifica vengono valutate simultaneamente. Se non viene trovata alcuna voce corrispondente per la priorità corrente, verrà valutato il livello di priorità successivo.</span><span class="sxs-lookup"><span data-stu-id="58bb0-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="58bb0-127">Questo valore è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58bb0-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58bb0-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="58bb0-128">Child Elements</span></span>  
 <span data-ttu-id="58bb0-129">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="58bb0-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58bb0-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="58bb0-130">Parent Elements</span></span>  
  
|<span data-ttu-id="58bb0-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="58bb0-131">Element</span></span>|<span data-ttu-id="58bb0-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58bb0-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58bb0-133">\<routing></span><span class="sxs-lookup"><span data-stu-id="58bb0-133">\<routing></span></span>](routing.md)|<span data-ttu-id="58bb0-134">Sezione di configurazione contenente voci di mapping di routing.</span><span class="sxs-lookup"><span data-stu-id="58bb0-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58bb0-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58bb0-135">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
