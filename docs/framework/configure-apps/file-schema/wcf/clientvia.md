---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b8864760c1700cd785922b922346204d194f56cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673628"
---
# <a name="clientvia"></a><span data-ttu-id="da746-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="da746-101">\<clientVia></span></span>
<span data-ttu-id="da746-102">Specifica l'URI per il quale creare il canale del trasporto.</span><span class="sxs-lookup"><span data-stu-id="da746-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="da746-103">Per altre informazioni, vedere <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="da746-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="da746-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="da746-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="da746-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="da746-105">\<behaviors></span></span>  
<span data-ttu-id="da746-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="da746-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="da746-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="da746-107">\<behavior></span></span>  
<span data-ttu-id="da746-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="da746-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da746-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da746-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da746-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="da746-110">Attributes and Elements</span></span>  
 <span data-ttu-id="da746-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="da746-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da746-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="da746-112">Attributes</span></span>  
  
|<span data-ttu-id="da746-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="da746-113">Attribute</span></span>|<span data-ttu-id="da746-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da746-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="da746-115">Stringa che specifica un Uri che indica la route che deve essere presa da un messaggio.</span><span class="sxs-lookup"><span data-stu-id="da746-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da746-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="da746-116">Child Elements</span></span>  
 <span data-ttu-id="da746-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="da746-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da746-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="da746-118">Parent Elements</span></span>  
  
|<span data-ttu-id="da746-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="da746-119">Element</span></span>|<span data-ttu-id="da746-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da746-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da746-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="da746-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="da746-122">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="da746-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da746-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da746-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
