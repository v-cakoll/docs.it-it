---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 48e56b79f47e84122ddd4d7f55d50044510bfa66
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149059"
---
# <a name="ltclientviagt"></a><span data-ttu-id="2baec-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="2baec-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="2baec-103">Specifica l'URI per il quale creare il canale del trasporto.</span><span class="sxs-lookup"><span data-stu-id="2baec-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="2baec-104">Per altre informazioni, vedere <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="2baec-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="2baec-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2baec-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="2baec-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="2baec-106">\<behaviors></span></span>  
<span data-ttu-id="2baec-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2baec-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="2baec-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="2baec-108">\<behavior></span></span>  
<span data-ttu-id="2baec-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="2baec-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2baec-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2baec-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2baec-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2baec-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2baec-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2baec-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2baec-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="2baec-113">Attributes</span></span>  
  
|<span data-ttu-id="2baec-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="2baec-114">Attribute</span></span>|<span data-ttu-id="2baec-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2baec-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="2baec-116">Stringa che specifica un Uri che indica la route che deve essere presa da un messaggio.</span><span class="sxs-lookup"><span data-stu-id="2baec-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2baec-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2baec-117">Child Elements</span></span>  
 <span data-ttu-id="2baec-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="2baec-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2baec-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2baec-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2baec-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="2baec-120">Element</span></span>|<span data-ttu-id="2baec-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2baec-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2baec-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2baec-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2baec-123">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2baec-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2baec-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2baec-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
