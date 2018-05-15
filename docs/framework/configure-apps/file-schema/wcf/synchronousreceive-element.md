---
title: Elemento &lt;synchronousReceive&gt;
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: af1ca2ee1fe3c03c33f05e0c30c7b843b3720a36
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="03257-102">Elemento &lt;synchronousReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="03257-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="03257-103">Questo elemento di configurazione viene usato per specificare il comportamento in fase di esecuzione per la ricezione di messaggi in un servizio o in un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="03257-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="03257-104">Non prevede attributi o elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="03257-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="03257-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="03257-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="03257-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="03257-106">\<behaviors></span></span>  
<span data-ttu-id="03257-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="03257-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="03257-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="03257-108">\<behavior></span></span>  
<span data-ttu-id="03257-109">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="03257-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03257-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03257-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03257-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="03257-111">Attributes and Elements</span></span>  
 <span data-ttu-id="03257-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="03257-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03257-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="03257-113">Attributes</span></span>  
 <span data-ttu-id="03257-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="03257-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03257-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="03257-115">Child Elements</span></span>  
 <span data-ttu-id="03257-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="03257-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03257-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="03257-117">Parent Elements</span></span>  
  
|<span data-ttu-id="03257-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="03257-118">Element</span></span>|<span data-ttu-id="03257-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03257-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03257-120">\<behavior></span><span class="sxs-lookup"><span data-stu-id="03257-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="03257-121">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="03257-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03257-122">Note</span><span class="sxs-lookup"><span data-stu-id="03257-122">Remarks</span></span>  
 <span data-ttu-id="03257-123">Usare questo comportamento per fornire al listener del canale l'istruzione di usare la ricezione sincrona anziché l'impostazione predefinita, ovvero la modalità asincrona.</span><span class="sxs-lookup"><span data-stu-id="03257-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="03257-124">Windows Communication Foundation (WCF) genera un nuovo thread per la distribuzione per ogni canale accettato.</span><span class="sxs-lookup"><span data-stu-id="03257-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="03257-125">Se esistono molti canali, sussiste la possibilità di esaurire i thread.</span><span class="sxs-lookup"><span data-stu-id="03257-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03257-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03257-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
