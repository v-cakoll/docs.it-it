---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: ffe2538fa2c3cb680285cfaa68c975c0f9d4b1bd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855286"
---
# \<entries>
<span data-ttu-id="b668f-101">Voce di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="b668f-101">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**  
  
## <a name="syntax"></a><span data-ttu-id="b668f-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b668f-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b668f-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b668f-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b668f-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b668f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b668f-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="b668f-105">Attributes</span></span>  
 <span data-ttu-id="b668f-106">No.</span><span class="sxs-lookup"><span data-stu-id="b668f-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b668f-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b668f-107">Child Elements</span></span>  
  
|<span data-ttu-id="b668f-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="b668f-108">Element</span></span>|<span data-ttu-id="b668f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b668f-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="b668f-110">Esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b668f-110">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="b668f-111">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="b668f-111">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b668f-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b668f-112">Parent Elements</span></span>  
  
|<span data-ttu-id="b668f-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="b668f-113">Element</span></span>|<span data-ttu-id="b668f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b668f-114">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="b668f-115">Sezione di configurazione contenente una tabella di routing.</span><span class="sxs-lookup"><span data-stu-id="b668f-115">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b668f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b668f-116">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
