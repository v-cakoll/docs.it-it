---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: ffe2538fa2c3cb680285cfaa68c975c0f9d4b1bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855286"
---
# <a name="entries"></a><span data-ttu-id="2c007-101">\<voci ></span><span class="sxs-lookup"><span data-stu-id="2c007-101">\<entries></span></span>
<span data-ttu-id="2c007-102">Voce di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="2c007-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
<span data-ttu-id="2c007-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2c007-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2c007-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2c007-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2c007-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di routing**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="2c007-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="2c007-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> filterTables**](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="2c007-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="2c007-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> filterTable**](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="2c007-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="2c007-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<voci >**</span><span class="sxs-lookup"><span data-stu-id="2c007-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c007-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c007-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c007-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2c007-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2c007-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2c007-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c007-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="2c007-112">Attributes</span></span>  
 <span data-ttu-id="2c007-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2c007-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2c007-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2c007-114">Child Elements</span></span>  
  
|<span data-ttu-id="2c007-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c007-115">Element</span></span>|<span data-ttu-id="2c007-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2c007-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c007-117">\<filters></span><span class="sxs-lookup"><span data-stu-id="2c007-117">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="2c007-118">Esegue il mapping di un filtro a un endpoint client definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2c007-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="2c007-119">I messaggi che corrispondono a questo filtro verranno inviati a questa destinazione.</span><span class="sxs-lookup"><span data-stu-id="2c007-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c007-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2c007-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2c007-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c007-121">Element</span></span>|<span data-ttu-id="2c007-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c007-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c007-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="2c007-123">\<routing></span></span>](routing.md)|<span data-ttu-id="2c007-124">Sezione di configurazione contenente una tabella di routing.</span><span class="sxs-lookup"><span data-stu-id="2c007-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c007-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c007-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
