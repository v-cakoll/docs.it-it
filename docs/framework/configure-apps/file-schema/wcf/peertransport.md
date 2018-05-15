---
title: '&lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: df192c6a602aa073f48fab4229b4be3fbeb2349d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltpeertransportgt"></a><span data-ttu-id="ba594-102">&lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="ba594-102">&lt;peerTransport&gt;</span></span>
<span data-ttu-id="ba594-103">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ba594-103">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="ba594-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ba594-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ba594-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="ba594-105">\<bindings></span></span>  
<span data-ttu-id="ba594-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ba594-106">\<customBinding></span></span>  
<span data-ttu-id="ba594-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="ba594-107">\<binding></span></span>  
<span data-ttu-id="ba594-108">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="ba594-108">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba594-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba594-109">Syntax</span></span>  
  
```xml  
<peerTransport   
    listenIpAddress="String"  
    maxBufferPoolSize="Integer"  
    maxReceivedMessageSize="Integer"  
    port="Integer"  
        <security>  
    </security>  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba594-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ba594-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ba594-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ba594-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba594-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="ba594-112">Attributes</span></span>  
  
|<span data-ttu-id="ba594-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="ba594-113">Attribute</span></span>|<span data-ttu-id="ba594-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba594-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba594-115">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="ba594-115">listenIpAddress</span></span>|<span data-ttu-id="ba594-116">Stringa che specifica l'indirizzo IP usato dal nodo peer per l'ascolto dei messaggi TCP.</span><span class="sxs-lookup"><span data-stu-id="ba594-116">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="ba594-117">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="ba594-117">The default is `null`.</span></span>|  
|<span data-ttu-id="ba594-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="ba594-118">maxBufferPoolSize</span></span>|<span data-ttu-id="ba594-119">Numero intero positivo che specifica la dimensione massima del pool di buffer.</span><span class="sxs-lookup"><span data-stu-id="ba594-119">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="ba594-120">Il valore predefinito è 524288.</span><span class="sxs-lookup"><span data-stu-id="ba594-120">The default is 524288.</span></span><br /><br /> <span data-ttu-id="ba594-121">Molte parti di WCF usano buffer.</span><span class="sxs-lookup"><span data-stu-id="ba594-121">Many parts of WCF use buffers.</span></span> <span data-ttu-id="ba594-122">La creazione e l'eliminazione dei buffer a ogni relativo uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="ba594-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="ba594-123">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="ba594-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="ba594-124">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione dei buffer.</span><span class="sxs-lookup"><span data-stu-id="ba594-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="ba594-125">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="ba594-125">maxReceivedMessageSize</span></span>|<span data-ttu-id="ba594-126">Numero intero positivo che definisce la dimensione massima in byte dei messaggi, comprese le intestazioni.</span><span class="sxs-lookup"><span data-stu-id="ba594-126">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="ba594-127">Il mittente di un messaggio riceve un errore SOAP se il messaggio è troppo grande per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="ba594-127">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="ba594-128">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="ba594-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="ba594-129">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="ba594-129">The default is 65536.</span></span>|  
|<span data-ttu-id="ba594-130">porta</span><span class="sxs-lookup"><span data-stu-id="ba594-130">port</span></span>|<span data-ttu-id="ba594-131">Numero intero che specifica la porta dell'interfaccia di rete usata dall'associazione per elaborare i messaggi TCP del canale peer.</span><span class="sxs-lookup"><span data-stu-id="ba594-131">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="ba594-132">Il valore deve essere compreso tra <xref:System.Net.IPEndPoint.MinPort> e <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="ba594-132">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="ba594-133">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="ba594-133">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba594-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ba594-134">Child Elements</span></span>  
  
|<span data-ttu-id="ba594-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba594-135">Element</span></span>|<span data-ttu-id="ba594-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba594-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba594-137">\<security></span><span class="sxs-lookup"><span data-stu-id="ba594-137">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="ba594-138">Definisce le impostazioni di sicurezza per questo trasporto.</span><span class="sxs-lookup"><span data-stu-id="ba594-138">Defines the security settings for this transport.</span></span> <span data-ttu-id="ba594-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="ba594-139">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba594-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ba594-140">Parent Elements</span></span>  
  
|<span data-ttu-id="ba594-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba594-141">Element</span></span>|<span data-ttu-id="ba594-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba594-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba594-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="ba594-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="ba594-144">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ba594-144">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba594-145">Note</span><span class="sxs-lookup"><span data-stu-id="ba594-145">Remarks</span></span>  
 <span data-ttu-id="ba594-146">Questo trasporto non può essere usato con contratti che includono operazioni request/reply.</span><span class="sxs-lookup"><span data-stu-id="ba594-146">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba594-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba594-147">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportElement>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="ba594-148">Trasporti</span><span class="sxs-lookup"><span data-stu-id="ba594-148">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="ba594-149">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="ba594-149">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="ba594-150">Associazioni</span><span class="sxs-lookup"><span data-stu-id="ba594-150">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ba594-151">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="ba594-151">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="ba594-152">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ba594-152">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="ba594-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ba594-153">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
