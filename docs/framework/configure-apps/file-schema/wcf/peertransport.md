---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 8962a0c018442ed590b62e53ea8323d80e334df7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55290095"
---
# <a name="peertransport"></a><span data-ttu-id="35447-101">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="35447-101">\<peerTransport></span></span>
<span data-ttu-id="35447-102">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="35447-102">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="35447-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="35447-103">\<system.serviceModel></span></span>  
<span data-ttu-id="35447-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="35447-104">\<bindings></span></span>  
<span data-ttu-id="35447-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="35447-105">\<customBinding></span></span>  
<span data-ttu-id="35447-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="35447-106">\<binding></span></span>  
<span data-ttu-id="35447-107">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="35447-107">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35447-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35447-108">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35447-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="35447-109">Attributes and Elements</span></span>  
 <span data-ttu-id="35447-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="35447-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35447-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="35447-111">Attributes</span></span>  
  
|<span data-ttu-id="35447-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="35447-112">Attribute</span></span>|<span data-ttu-id="35447-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35447-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35447-114">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="35447-114">listenIpAddress</span></span>|<span data-ttu-id="35447-115">Stringa che specifica l'indirizzo IP usato dal nodo peer per l'ascolto dei messaggi TCP.</span><span class="sxs-lookup"><span data-stu-id="35447-115">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="35447-116">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="35447-116">The default is `null`.</span></span>|  
|<span data-ttu-id="35447-117">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="35447-117">maxBufferPoolSize</span></span>|<span data-ttu-id="35447-118">Numero intero positivo che specifica la dimensione massima del pool di buffer.</span><span class="sxs-lookup"><span data-stu-id="35447-118">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="35447-119">Il valore predefinito è 524288.</span><span class="sxs-lookup"><span data-stu-id="35447-119">The default is 524288.</span></span><br /><br /> <span data-ttu-id="35447-120">Molte parti di WCF usano buffer.</span><span class="sxs-lookup"><span data-stu-id="35447-120">Many parts of WCF use buffers.</span></span> <span data-ttu-id="35447-121">La creazione e l'eliminazione dei buffer a ogni relativo uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="35447-121">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="35447-122">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="35447-122">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="35447-123">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione dei buffer.</span><span class="sxs-lookup"><span data-stu-id="35447-123">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="35447-124">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="35447-124">maxReceivedMessageSize</span></span>|<span data-ttu-id="35447-125">Numero intero positivo che definisce la dimensione massima in byte dei messaggi, comprese le intestazioni.</span><span class="sxs-lookup"><span data-stu-id="35447-125">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="35447-126">Il mittente di un messaggio riceve un errore SOAP se il messaggio è troppo grande per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="35447-126">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="35447-127">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="35447-127">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="35447-128">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="35447-128">The default is 65536.</span></span>|  
|<span data-ttu-id="35447-129">porta</span><span class="sxs-lookup"><span data-stu-id="35447-129">port</span></span>|<span data-ttu-id="35447-130">Numero intero che specifica la porta dell'interfaccia di rete usata dall'associazione per elaborare i messaggi TCP del canale peer.</span><span class="sxs-lookup"><span data-stu-id="35447-130">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="35447-131">Il valore deve essere compreso tra <xref:System.Net.IPEndPoint.MinPort> e <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="35447-131">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="35447-132">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="35447-132">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35447-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="35447-133">Child Elements</span></span>  
  
|<span data-ttu-id="35447-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="35447-134">Element</span></span>|<span data-ttu-id="35447-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35447-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35447-136">\<security></span><span class="sxs-lookup"><span data-stu-id="35447-136">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="35447-137">Definisce le impostazioni di sicurezza per questo trasporto.</span><span class="sxs-lookup"><span data-stu-id="35447-137">Defines the security settings for this transport.</span></span> <span data-ttu-id="35447-138">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="35447-138">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="35447-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="35447-139">Parent Elements</span></span>  
  
|<span data-ttu-id="35447-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="35447-140">Element</span></span>|<span data-ttu-id="35447-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="35447-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35447-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="35447-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="35447-143">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="35447-143">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35447-144">Note</span><span class="sxs-lookup"><span data-stu-id="35447-144">Remarks</span></span>  
 <span data-ttu-id="35447-145">Questo trasporto non può essere usato con contratti che includono operazioni request/reply.</span><span class="sxs-lookup"><span data-stu-id="35447-145">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35447-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35447-146">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="35447-147">Trasporti</span><span class="sxs-lookup"><span data-stu-id="35447-147">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="35447-148">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="35447-148">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="35447-149">Associazioni</span><span class="sxs-lookup"><span data-stu-id="35447-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="35447-150">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="35447-150">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="35447-151">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="35447-151">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="35447-152">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="35447-152">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
