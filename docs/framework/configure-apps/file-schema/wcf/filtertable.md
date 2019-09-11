---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855187"
---
# <a name="filtertable"></a><span data-ttu-id="c2bd5-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="c2bd5-101">\<filterTable></span></span>
<span data-ttu-id="c2bd5-102">Rappresenta una tabella di routing contenente un elenco di filtri in base ai quali valutare i messaggi e l'endpoint client a cui indirizzare i messaggi se il filtro restituisce true.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
<span data-ttu-id="c2bd5-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c2bd5-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c2bd5-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c2bd5-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c2bd5-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di routing**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="c2bd5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="c2bd5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> filterTables**](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="c2bd5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="c2bd5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> filterTable**</span><span class="sxs-lookup"><span data-stu-id="c2bd5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2bd5-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2bd5-108">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
     name="String">
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2bd5-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c2bd5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c2bd5-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2bd5-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="c2bd5-111">Attributes</span></span>  
  
|<span data-ttu-id="c2bd5-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2bd5-112">Element</span></span>|<span data-ttu-id="c2bd5-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2bd5-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2bd5-114">name</span><span class="sxs-lookup"><span data-stu-id="c2bd5-114">name</span></span>|<span data-ttu-id="c2bd5-115">Stringa contenente il nome univoco di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2bd5-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c2bd5-116">Child Elements</span></span>  
  
|<span data-ttu-id="c2bd5-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2bd5-117">Element</span></span>|<span data-ttu-id="c2bd5-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2bd5-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2bd5-119">\<filters></span><span class="sxs-lookup"><span data-stu-id="c2bd5-119">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="c2bd5-120">Mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c2bd5-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c2bd5-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c2bd5-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2bd5-122">Element</span></span>|<span data-ttu-id="c2bd5-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2bd5-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2bd5-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="c2bd5-124">\<routing></span></span>](routing.md)|<span data-ttu-id="c2bd5-125">Sezione di configurazione contenente tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2bd5-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2bd5-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
