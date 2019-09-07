---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: d896953a7ed31fdaf5f357a8721c7d085d50bc56
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400062"
---
# <a name="peertransport"></a><span data-ttu-id="2a8e8-101">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="2a8e8-101">\<peerTransport></span></span>
<span data-ttu-id="2a8e8-102">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-102">Defines a peer transport for a custom binding.</span></span>  
  
<span data-ttu-id="2a8e8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2a8e8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2a8e8-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2a8e8-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2a8e8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2a8e8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2a8e8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="2a8e8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="2a8e8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="2a8e8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2a8e8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> peerTransport**</span><span class="sxs-lookup"><span data-stu-id="2a8e8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerTransport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a8e8-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a8e8-109">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a8e8-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2a8e8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2a8e8-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a8e8-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="2a8e8-112">Attributes</span></span>  
  
|<span data-ttu-id="2a8e8-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="2a8e8-113">Attribute</span></span>|<span data-ttu-id="2a8e8-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a8e8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a8e8-115">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="2a8e8-115">listenIpAddress</span></span>|<span data-ttu-id="2a8e8-116">Stringa che specifica l'indirizzo IP usato dal nodo peer per l'ascolto dei messaggi TCP.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-116">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="2a8e8-117">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-117">The default is `null`.</span></span>|  
|<span data-ttu-id="2a8e8-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="2a8e8-118">maxBufferPoolSize</span></span>|<span data-ttu-id="2a8e8-119">Numero intero positivo che specifica la dimensione massima del pool di buffer.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-119">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="2a8e8-120">Il valore predefinito è 524288.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-120">The default is 524288.</span></span><br /><br /> <span data-ttu-id="2a8e8-121">Molte parti di WCF usano buffer.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-121">Many parts of WCF use buffers.</span></span> <span data-ttu-id="2a8e8-122">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="2a8e8-123">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="2a8e8-124">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="2a8e8-125">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="2a8e8-125">maxReceivedMessageSize</span></span>|<span data-ttu-id="2a8e8-126">Numero intero positivo che definisce la dimensione massima in byte dei messaggi, comprese le intestazioni.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-126">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="2a8e8-127">Il mittente di un messaggio riceve un errore SOAP se il messaggio è troppo grande per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-127">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="2a8e8-128">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="2a8e8-129">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-129">The default is 65536.</span></span>|  
|<span data-ttu-id="2a8e8-130">port</span><span class="sxs-lookup"><span data-stu-id="2a8e8-130">port</span></span>|<span data-ttu-id="2a8e8-131">Numero intero che specifica la porta dell'interfaccia di rete usata dall'associazione per elaborare i messaggi TCP del canale peer.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-131">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="2a8e8-132">Il valore deve essere compreso tra <xref:System.Net.IPEndPoint.MinPort> e <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-132">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="2a8e8-133">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-133">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a8e8-134">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2a8e8-134">Child Elements</span></span>  
  
|<span data-ttu-id="2a8e8-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="2a8e8-135">Element</span></span>|<span data-ttu-id="2a8e8-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a8e8-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a8e8-137">\<security></span><span class="sxs-lookup"><span data-stu-id="2a8e8-137">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="2a8e8-138">Definisce le impostazioni di sicurezza per questo trasporto.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-138">Defines the security settings for this transport.</span></span> <span data-ttu-id="2a8e8-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-139">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a8e8-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2a8e8-140">Parent Elements</span></span>  
  
|<span data-ttu-id="2a8e8-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="2a8e8-141">Element</span></span>|<span data-ttu-id="2a8e8-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a8e8-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a8e8-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="2a8e8-143">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="2a8e8-144">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-144">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a8e8-145">Note</span><span class="sxs-lookup"><span data-stu-id="2a8e8-145">Remarks</span></span>  
 <span data-ttu-id="2a8e8-146">Questo trasporto non può essere usato con contratti che includono operazioni request/reply.</span><span class="sxs-lookup"><span data-stu-id="2a8e8-146">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a8e8-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a8e8-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2a8e8-148">Trasporti</span><span class="sxs-lookup"><span data-stu-id="2a8e8-148">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="2a8e8-149">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="2a8e8-149">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="2a8e8-150">Associazioni</span><span class="sxs-lookup"><span data-stu-id="2a8e8-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2a8e8-151">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="2a8e8-151">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2a8e8-152">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="2a8e8-152">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2a8e8-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2a8e8-153">\<customBinding></span></span>](custombinding.md)
