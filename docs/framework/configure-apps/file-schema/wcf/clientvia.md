---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 6218bb3f205f2825eb3f10fabf834cfd0396ac87
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltclientviagt"></a><span data-ttu-id="d020e-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="d020e-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="d020e-103">Specifica l'URI per il quale creare il canale del trasporto.</span><span class="sxs-lookup"><span data-stu-id="d020e-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="d020e-104">Per altre informazioni, vedere <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="d020e-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="d020e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d020e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d020e-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="d020e-106">\<behaviors></span></span>  
<span data-ttu-id="d020e-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d020e-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="d020e-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="d020e-108">\<behavior></span></span>  
<span data-ttu-id="d020e-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="d020e-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d020e-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d020e-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d020e-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d020e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d020e-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d020e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d020e-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="d020e-113">Attributes</span></span>  
  
|<span data-ttu-id="d020e-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="d020e-114">Attribute</span></span>|<span data-ttu-id="d020e-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d020e-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="d020e-116">Stringa che specifica un Uri che indica la route che deve essere presa da un messaggio.</span><span class="sxs-lookup"><span data-stu-id="d020e-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d020e-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d020e-117">Child Elements</span></span>  
 <span data-ttu-id="d020e-118">Nessuno</span><span class="sxs-lookup"><span data-stu-id="d020e-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d020e-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d020e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d020e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="d020e-120">Element</span></span>|<span data-ttu-id="d020e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d020e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d020e-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d020e-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d020e-123">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="d020e-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d020e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d020e-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
