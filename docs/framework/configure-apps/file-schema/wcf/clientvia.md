---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: a1c2ee68fb039e24e1462148cb52daf1bb57f8ed
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398104"
---
# <a name="clientvia"></a><span data-ttu-id="27c0b-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="27c0b-101">\<clientVia></span></span>
<span data-ttu-id="27c0b-102">Specifica l'URI per il quale creare il canale del trasporto.</span><span class="sxs-lookup"><span data-stu-id="27c0b-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="27c0b-103">Per altre informazioni, vedere <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="27c0b-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
<span data-ttu-id="27c0b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="27c0b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="27c0b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="27c0b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="27c0b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="27c0b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="27c0b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="27c0b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="27c0b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="27c0b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="27c0b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> clientVia**</span><span class="sxs-lookup"><span data-stu-id="27c0b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27c0b-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27c0b-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27c0b-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="27c0b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="27c0b-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="27c0b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27c0b-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="27c0b-113">Attributes</span></span>  
  
|<span data-ttu-id="27c0b-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="27c0b-114">Attribute</span></span>|<span data-ttu-id="27c0b-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="27c0b-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="27c0b-116">Stringa che specifica un Uri che indica la route che deve essere presa da un messaggio.</span><span class="sxs-lookup"><span data-stu-id="27c0b-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27c0b-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="27c0b-117">Child Elements</span></span>  
 <span data-ttu-id="27c0b-118">Nessuna</span><span class="sxs-lookup"><span data-stu-id="27c0b-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27c0b-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="27c0b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="27c0b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="27c0b-120">Element</span></span>|<span data-ttu-id="27c0b-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="27c0b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27c0b-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="27c0b-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="27c0b-123">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="27c0b-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27c0b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27c0b-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
