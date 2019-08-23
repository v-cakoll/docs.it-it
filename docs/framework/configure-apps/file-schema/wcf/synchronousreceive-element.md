---
title: Elemento <synchronousReceive>
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: fa14d4606303b2d67cf5ef845d428bb086680204
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938962"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="b1c0b-102">\<elemento > synchronousReceive</span><span class="sxs-lookup"><span data-stu-id="b1c0b-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="b1c0b-103">Questo elemento di configurazione viene usato per specificare il comportamento in fase di esecuzione per la ricezione di messaggi in un servizio o in un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="b1c0b-104">Non prevede attributi o elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="b1c0b-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b1c0b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="b1c0b-106">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="b1c0b-106">\<behaviors></span></span>  
<span data-ttu-id="b1c0b-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="b1c0b-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="b1c0b-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="b1c0b-108">\<behavior></span></span>  
<span data-ttu-id="b1c0b-109">\<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="b1c0b-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1c0b-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1c0b-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1c0b-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b1c0b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b1c0b-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1c0b-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="b1c0b-113">Attributes</span></span>  
 <span data-ttu-id="b1c0b-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b1c0b-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b1c0b-115">Child Elements</span></span>  
 <span data-ttu-id="b1c0b-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b1c0b-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b1c0b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b1c0b-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1c0b-118">Element</span></span>|<span data-ttu-id="b1c0b-119">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b1c0b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1c0b-120">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b1c0b-120">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b1c0b-121">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1c0b-122">Note</span><span class="sxs-lookup"><span data-stu-id="b1c0b-122">Remarks</span></span>  
 <span data-ttu-id="b1c0b-123">Usare questo comportamento per fornire al listener del canale l'istruzione di usare la ricezione sincrona anziché l'impostazione predefinita, ovvero la modalità asincrona.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="b1c0b-124">Windows Communication Foundation (WCF) rilascia un nuovo thread per la distribuzione per ogni canale accettato.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="b1c0b-125">Se esistono molti canali, sussiste la possibilità di esaurire i thread.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1c0b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1c0b-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
