---
title: <add> di <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 23b0a825ea593f85ade870d5b93367571eaa3ec0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850504"
---
# <a name="add-of-entries"></a><span data-ttu-id="7f12e-102">\<aggiungere > di \<voci ></span><span class="sxs-lookup"><span data-stu-id="7f12e-102">\<add> of \<entries></span></span>
<span data-ttu-id="7f12e-103">Rappresenta una voce di routing che esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7f12e-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="7f12e-104">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="7f12e-104">Messages matching this filter will be sent to this destination.</span></span>  
  
<span data-ttu-id="7f12e-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7f12e-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7f12e-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di routing**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="7f12e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> filterTables**](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="7f12e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> filterTable**](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="7f12e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<voci >** ](entries.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)</span></span>\
<span data-ttu-id="7f12e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="7f12e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f12e-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f12e-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f12e-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7f12e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7f12e-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7f12e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f12e-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="7f12e-115">Attributes</span></span>  
  
|<span data-ttu-id="7f12e-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="7f12e-116">Attribute</span></span>|<span data-ttu-id="7f12e-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7f12e-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f12e-118">backupList</span><span class="sxs-lookup"><span data-stu-id="7f12e-118">backupList</span></span>|<span data-ttu-id="7f12e-119">Stringa che specifica un riferimento a un elenco di backup di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7f12e-119">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="7f12e-120">endpoint</span><span class="sxs-lookup"><span data-stu-id="7f12e-120">endpoint</span></span>|<span data-ttu-id="7f12e-121">Stringa che specifica un riferimento a un endpoint client che riceverà i messaggi corrispondenti al filtro specificato dall'attributo `filterName`.</span><span class="sxs-lookup"><span data-stu-id="7f12e-121">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="7f12e-122">filterName</span><span class="sxs-lookup"><span data-stu-id="7f12e-122">filterName</span></span>|<span data-ttu-id="7f12e-123">Stringa che specifica un riferimento a un elemento di filtro.</span><span class="sxs-lookup"><span data-stu-id="7f12e-123">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="7f12e-124">priorità</span><span class="sxs-lookup"><span data-stu-id="7f12e-124">priority</span></span>|<span data-ttu-id="7f12e-125">Integer che specifica la priorità di questa voce.</span><span class="sxs-lookup"><span data-stu-id="7f12e-125">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="7f12e-126">Le voci nella tabella di routing verranno valutate in base alla priorità, con 0 come priorità più bassa.</span><span class="sxs-lookup"><span data-stu-id="7f12e-126">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="7f12e-127">Tutte le voci per una priorità specifica vengono valutate simultaneamente. Se non viene trovata alcuna voce corrispondente per la priorità corrente, verrà valutato il livello di priorità successivo.</span><span class="sxs-lookup"><span data-stu-id="7f12e-127">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="7f12e-128">Questo valore è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f12e-128">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f12e-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7f12e-129">Child Elements</span></span>  
 <span data-ttu-id="7f12e-130">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7f12e-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f12e-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7f12e-131">Parent Elements</span></span>  
  
|<span data-ttu-id="7f12e-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f12e-132">Element</span></span>|<span data-ttu-id="7f12e-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f12e-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f12e-134">\<routing></span><span class="sxs-lookup"><span data-stu-id="7f12e-134">\<routing></span></span>](routing.md)|<span data-ttu-id="7f12e-135">Sezione di configurazione contenente voci di mapping di routing.</span><span class="sxs-lookup"><span data-stu-id="7f12e-135">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f12e-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f12e-136">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
