---
title: Elemento &lt;synchronousReceive&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b630f5ad2fbf5e3f20667e0bd1b7ae711992dc18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="f5792-102">Elemento &lt;synchronousReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="f5792-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="f5792-103">Questo elemento di configurazione viene usato per specificare il comportamento in fase di esecuzione per la ricezione di messaggi in un servizio o in un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="f5792-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="f5792-104">Non prevede attributi o elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="f5792-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="f5792-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f5792-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="f5792-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="f5792-106">\<behaviors></span></span>  
<span data-ttu-id="f5792-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f5792-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="f5792-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="f5792-108">\<behavior></span></span>  
<span data-ttu-id="f5792-109">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="f5792-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5792-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5792-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5792-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f5792-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f5792-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f5792-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5792-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="f5792-113">Attributes</span></span>  
 <span data-ttu-id="f5792-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f5792-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f5792-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f5792-115">Child Elements</span></span>  
 <span data-ttu-id="f5792-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f5792-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5792-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f5792-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f5792-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5792-118">Element</span></span>|<span data-ttu-id="f5792-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5792-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5792-120">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="f5792-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f5792-121">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f5792-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5792-122">Note</span><span class="sxs-lookup"><span data-stu-id="f5792-122">Remarks</span></span>  
 <span data-ttu-id="f5792-123">Usare questo comportamento per fornire al listener del canale l'istruzione di usare la ricezione sincrona anziché l'impostazione predefinita, ovvero la modalità asincrona.</span><span class="sxs-lookup"><span data-stu-id="f5792-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="f5792-124">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] viene emesso un nuovo thread per la distribuzione per ogni canale accettato.</span><span class="sxs-lookup"><span data-stu-id="f5792-124">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="f5792-125">Se esistono molti canali, sussiste la possibilità di esaurire i thread.</span><span class="sxs-lookup"><span data-stu-id="f5792-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5792-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5792-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
