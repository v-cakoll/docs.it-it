---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 6491411d8cfe5c7a5a944f3b1cd728c9f0a4b852
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641213"
---
# <a name="ltclientviagt"></a><span data-ttu-id="7533a-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="7533a-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="7533a-103">Specifica l'URI per il quale creare il canale del trasporto.</span><span class="sxs-lookup"><span data-stu-id="7533a-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="7533a-104">Per altre informazioni, vedere <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="7533a-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="7533a-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7533a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="7533a-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="7533a-106">\<behaviors></span></span>  
<span data-ttu-id="7533a-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="7533a-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="7533a-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7533a-108">\<behavior></span></span>  
<span data-ttu-id="7533a-109">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="7533a-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7533a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7533a-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7533a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7533a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7533a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7533a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7533a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="7533a-113">Attributes</span></span>  
  
|<span data-ttu-id="7533a-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="7533a-114">Attribute</span></span>|<span data-ttu-id="7533a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7533a-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="7533a-116">Stringa che specifica un Uri che indica la route che deve essere presa da un messaggio.</span><span class="sxs-lookup"><span data-stu-id="7533a-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7533a-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7533a-117">Child Elements</span></span>  
 <span data-ttu-id="7533a-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="7533a-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7533a-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7533a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7533a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="7533a-120">Element</span></span>|<span data-ttu-id="7533a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7533a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7533a-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7533a-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7533a-123">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="7533a-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7533a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7533a-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
