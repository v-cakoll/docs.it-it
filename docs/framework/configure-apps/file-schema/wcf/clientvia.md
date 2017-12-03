---
title: '&lt;clientVia&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3782eb9cbe793fef450c8b1c58456a1d4f7b0b94
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltclientviagt"></a><span data-ttu-id="5f52b-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="5f52b-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="5f52b-103">Specifica l'URI per il quale creare il canale del trasporto.</span><span class="sxs-lookup"><span data-stu-id="5f52b-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="5f52b-104">Per altre informazioni, vedere <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5f52b-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="5f52b-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5f52b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5f52b-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="5f52b-106">\<behaviors></span></span>  
<span data-ttu-id="5f52b-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5f52b-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="5f52b-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="5f52b-108">\<behavior></span></span>  
<span data-ttu-id="5f52b-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="5f52b-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f52b-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f52b-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f52b-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5f52b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5f52b-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5f52b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f52b-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="5f52b-113">Attributes</span></span>  
  
|<span data-ttu-id="5f52b-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="5f52b-114">Attribute</span></span>|<span data-ttu-id="5f52b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f52b-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="5f52b-116">Stringa che specifica un Uri che indica la route che deve essere presa da un messaggio.</span><span class="sxs-lookup"><span data-stu-id="5f52b-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f52b-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5f52b-117">Child Elements</span></span>  
 <span data-ttu-id="5f52b-118">None</span><span class="sxs-lookup"><span data-stu-id="5f52b-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5f52b-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5f52b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5f52b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f52b-120">Element</span></span>|<span data-ttu-id="5f52b-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f52b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f52b-122">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="5f52b-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5f52b-123">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5f52b-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f52b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f52b-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
