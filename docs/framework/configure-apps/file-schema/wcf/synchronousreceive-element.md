---
title: Elemento <synchronousReceive>
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: b3f4860be6b7edac776a1c30611271b2eb36968e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399503"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="4e8e6-102">\<elemento > synchronousReceive</span><span class="sxs-lookup"><span data-stu-id="4e8e6-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="4e8e6-103">Questo elemento di configurazione viene usato per specificare il comportamento in fase di esecuzione per la ricezione di messaggi in un servizio o in un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="4e8e6-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="4e8e6-104">Non prevede attributi o elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="4e8e6-104">It does not have any attributes or child elements.</span></span>  
  
<span data-ttu-id="4e8e6-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4e8e6-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4e8e6-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4e8e6-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4e8e6-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4e8e6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4e8e6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4e8e6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="4e8e6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4e8e6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="4e8e6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> synchronousReceive**</span><span class="sxs-lookup"><span data-stu-id="4e8e6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e8e6-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e8e6-111">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e8e6-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4e8e6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4e8e6-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4e8e6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e8e6-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="4e8e6-114">Attributes</span></span>  
 <span data-ttu-id="4e8e6-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4e8e6-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4e8e6-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4e8e6-116">Child Elements</span></span>  
 <span data-ttu-id="4e8e6-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4e8e6-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e8e6-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4e8e6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4e8e6-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4e8e6-119">Element</span></span>|<span data-ttu-id="4e8e6-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4e8e6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e8e6-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4e8e6-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="4e8e6-122">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="4e8e6-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e8e6-123">Note</span><span class="sxs-lookup"><span data-stu-id="4e8e6-123">Remarks</span></span>  
 <span data-ttu-id="4e8e6-124">Usare questo comportamento per fornire al listener del canale l'istruzione di usare la ricezione sincrona anziché l'impostazione predefinita, ovvero la modalità asincrona.</span><span class="sxs-lookup"><span data-stu-id="4e8e6-124">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="4e8e6-125">Windows Communication Foundation (WCF) rilascia un nuovo thread per la distribuzione per ogni canale accettato.</span><span class="sxs-lookup"><span data-stu-id="4e8e6-125">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="4e8e6-126">Se esistono molti canali, sussiste la possibilità di esaurire i thread.</span><span class="sxs-lookup"><span data-stu-id="4e8e6-126">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e8e6-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e8e6-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
