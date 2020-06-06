---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: a1c2ee68fb039e24e1462148cb52daf1bb57f8ed
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398104"
---
# \<clientVia>
<span data-ttu-id="5c719-101">Specifica l'URI per il quale creare il canale del trasporto.</span><span class="sxs-lookup"><span data-stu-id="5c719-101">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="5c719-102">Per altre informazioni, vedere <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5c719-102">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**  
  
## <a name="syntax"></a><span data-ttu-id="5c719-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c719-103">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c719-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5c719-104">Attributes and Elements</span></span>  
 <span data-ttu-id="5c719-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5c719-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c719-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="5c719-106">Attributes</span></span>  
  
|<span data-ttu-id="5c719-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="5c719-107">Attribute</span></span>|<span data-ttu-id="5c719-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c719-108">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="5c719-109">Stringa che specifica un Uri che indica la route che deve essere presa da un messaggio.</span><span class="sxs-lookup"><span data-stu-id="5c719-109">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c719-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5c719-110">Child Elements</span></span>  
 <span data-ttu-id="5c719-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="5c719-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c719-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5c719-112">Parent Elements</span></span>  
  
|<span data-ttu-id="5c719-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c719-113">Element</span></span>|<span data-ttu-id="5c719-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c719-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5c719-115">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5c719-115">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c719-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c719-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
