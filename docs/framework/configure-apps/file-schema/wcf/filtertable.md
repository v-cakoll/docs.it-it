---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855187"
---
# \<filterTable>
<span data-ttu-id="bd85f-101">Rappresenta una tabella di routing contenente un elenco di filtri in base ai quali valutare i messaggi e l'endpoint client al quale indirizzare i messaggi se il filtro restituisce true.</span><span class="sxs-lookup"><span data-stu-id="bd85f-101">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a><span data-ttu-id="bd85f-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd85f-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd85f-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bd85f-103">Attributes and Elements</span></span>  
 <span data-ttu-id="bd85f-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bd85f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd85f-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="bd85f-105">Attributes</span></span>  
  
|<span data-ttu-id="bd85f-106">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd85f-106">Element</span></span>|<span data-ttu-id="bd85f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd85f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd85f-108">name</span><span class="sxs-lookup"><span data-stu-id="bd85f-108">name</span></span>|<span data-ttu-id="bd85f-109">Stringa contenente il nome univoco di questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bd85f-109">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd85f-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bd85f-110">Child Elements</span></span>  
  
|<span data-ttu-id="bd85f-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd85f-111">Element</span></span>|<span data-ttu-id="bd85f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd85f-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="bd85f-113">Mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="bd85f-113">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd85f-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bd85f-114">Parent Elements</span></span>  
  
|<span data-ttu-id="bd85f-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd85f-115">Element</span></span>|<span data-ttu-id="bd85f-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd85f-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="bd85f-117">Sezione di configurazione contenente tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="bd85f-117">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd85f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd85f-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
