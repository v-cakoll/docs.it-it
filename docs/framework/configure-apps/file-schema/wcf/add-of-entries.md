---
title: <add> di <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 23b0a825ea593f85ade870d5b93367571eaa3ec0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850504"
---
# <a name="add-of-entries"></a><span data-ttu-id="a3d94-102">\<add> di \<entries></span><span class="sxs-lookup"><span data-stu-id="a3d94-102">\<add> of \<entries></span></span>
<span data-ttu-id="a3d94-103">Rappresenta una voce di routing che esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a3d94-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="a3d94-104">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="a3d94-104">Messages matching this filter will be sent to this destination.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="a3d94-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3d94-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3d94-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a3d94-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a3d94-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a3d94-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3d94-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="a3d94-108">Attributes</span></span>  
  
|<span data-ttu-id="a3d94-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="a3d94-109">Attribute</span></span>|<span data-ttu-id="a3d94-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3d94-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a3d94-111">backupList</span><span class="sxs-lookup"><span data-stu-id="a3d94-111">backupList</span></span>|<span data-ttu-id="a3d94-112">Stringa che specifica un riferimento a un elenco di backup di endpoint.</span><span class="sxs-lookup"><span data-stu-id="a3d94-112">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="a3d94-113">endpoint</span><span class="sxs-lookup"><span data-stu-id="a3d94-113">endpoint</span></span>|<span data-ttu-id="a3d94-114">Stringa che specifica un riferimento a un endpoint client che riceverà i messaggi corrispondenti al filtro specificato dall'attributo `filterName`.</span><span class="sxs-lookup"><span data-stu-id="a3d94-114">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="a3d94-115">filterName</span><span class="sxs-lookup"><span data-stu-id="a3d94-115">filterName</span></span>|<span data-ttu-id="a3d94-116">Stringa che specifica un riferimento a un elemento di filtro.</span><span class="sxs-lookup"><span data-stu-id="a3d94-116">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="a3d94-117">priority</span><span class="sxs-lookup"><span data-stu-id="a3d94-117">priority</span></span>|<span data-ttu-id="a3d94-118">Integer che specifica la priorità di questa voce.</span><span class="sxs-lookup"><span data-stu-id="a3d94-118">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="a3d94-119">Le voci nella tabella di routing verranno valutate in base alla priorità, con 0 come priorità più bassa.</span><span class="sxs-lookup"><span data-stu-id="a3d94-119">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="a3d94-120">Tutte le voci per una priorità specifica vengono valutate simultaneamente. Se non viene trovata alcuna voce corrispondente per la priorità corrente, verrà valutato il livello di priorità successivo.</span><span class="sxs-lookup"><span data-stu-id="a3d94-120">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="a3d94-121">Questo valore è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a3d94-121">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3d94-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a3d94-122">Child Elements</span></span>  
 <span data-ttu-id="a3d94-123">No.</span><span class="sxs-lookup"><span data-stu-id="a3d94-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3d94-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a3d94-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a3d94-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3d94-125">Element</span></span>|<span data-ttu-id="a3d94-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3d94-126">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="a3d94-127">Sezione di configurazione contenente voci di mapping di routing.</span><span class="sxs-lookup"><span data-stu-id="a3d94-127">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3d94-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3d94-128">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
