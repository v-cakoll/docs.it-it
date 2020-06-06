---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c68479737cefe542a10a404a8b31a4820a430ffb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855207"
---
# \<filterTables>
<span data-ttu-id="f7da2-101">Rappresenta una sezione di configurazione per la definizione di tabelle di routing contenenti i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="f7da2-101">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**  
  
## <a name="syntax"></a><span data-ttu-id="f7da2-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7da2-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7da2-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f7da2-103">Attributes and Elements</span></span>  
 <span data-ttu-id="f7da2-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f7da2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7da2-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="f7da2-105">Attributes</span></span>  
 <span data-ttu-id="f7da2-106">No.</span><span class="sxs-lookup"><span data-stu-id="f7da2-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f7da2-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f7da2-107">Child Elements</span></span>  
  
|<span data-ttu-id="f7da2-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7da2-108">Element</span></span>|<span data-ttu-id="f7da2-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7da2-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="f7da2-110">Tabella di routing contenente i mapping tra i filtri di routing e gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="f7da2-110">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f7da2-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f7da2-111">Parent Elements</span></span>  
  
|<span data-ttu-id="f7da2-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7da2-112">Element</span></span>|<span data-ttu-id="f7da2-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7da2-113">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="f7da2-114">Sezione di configurazione contenente filtri e tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="f7da2-114">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7da2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7da2-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
