---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c68479737cefe542a10a404a8b31a4820a430ffb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855207"
---
# <a name="filtertables"></a><span data-ttu-id="6996f-101">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="6996f-101">\<filterTables></span></span>
<span data-ttu-id="6996f-102">Rappresenta una sezione di configurazione per la definizione di tabelle di routing contenenti i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="6996f-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
<span data-ttu-id="6996f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6996f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6996f-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6996f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6996f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di routing**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="6996f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="6996f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> filterTables**</span><span class="sxs-lookup"><span data-stu-id="6996f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6996f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6996f-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6996f-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6996f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6996f-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6996f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6996f-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="6996f-110">Attributes</span></span>  
 <span data-ttu-id="6996f-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6996f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6996f-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6996f-112">Child Elements</span></span>  
  
|<span data-ttu-id="6996f-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="6996f-113">Element</span></span>|<span data-ttu-id="6996f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6996f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6996f-115">\<filters></span><span class="sxs-lookup"><span data-stu-id="6996f-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="6996f-116">Tabella di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="6996f-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6996f-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6996f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6996f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="6996f-118">Element</span></span>|<span data-ttu-id="6996f-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6996f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6996f-120">\<routing></span><span class="sxs-lookup"><span data-stu-id="6996f-120">\<routing></span></span>](routing.md)|<span data-ttu-id="6996f-121">Sezione di configurazione contenente filtri e tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="6996f-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6996f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6996f-122">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
