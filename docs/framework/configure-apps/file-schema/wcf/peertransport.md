---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 99fb013e052329ae4b99c4db89565ace8935c456
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736512"
---
# \<peerTransport>
<span data-ttu-id="77d48-101">Definisce un trasporto peer per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="77d48-101">Defines a peer transport for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="77d48-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77d48-102">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77d48-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="77d48-103">Attributes and Elements</span></span>  
 <span data-ttu-id="77d48-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="77d48-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77d48-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="77d48-105">Attributes</span></span>  
  
|<span data-ttu-id="77d48-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="77d48-106">Attribute</span></span>|<span data-ttu-id="77d48-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77d48-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77d48-108">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="77d48-108">listenIpAddress</span></span>|<span data-ttu-id="77d48-109">Stringa che specifica l'indirizzo IP usato dal nodo peer per l'ascolto dei messaggi TCP.</span><span class="sxs-lookup"><span data-stu-id="77d48-109">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="77d48-110">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="77d48-110">The default is `null`.</span></span>|  
|<span data-ttu-id="77d48-111">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="77d48-111">maxBufferPoolSize</span></span>|<span data-ttu-id="77d48-112">Numero intero positivo che specifica la dimensione massima del pool di buffer.</span><span class="sxs-lookup"><span data-stu-id="77d48-112">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="77d48-113">Il valore predefinito è 524288.</span><span class="sxs-lookup"><span data-stu-id="77d48-113">The default is 524288.</span></span><br /><br /> <span data-ttu-id="77d48-114">Molte parti di WCF usano buffer.</span><span class="sxs-lookup"><span data-stu-id="77d48-114">Many parts of WCF use buffers.</span></span> <span data-ttu-id="77d48-115">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="77d48-115">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="77d48-116">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="77d48-116">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="77d48-117">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="77d48-117">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="77d48-118">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="77d48-118">maxReceivedMessageSize</span></span>|<span data-ttu-id="77d48-119">Numero intero positivo che definisce la dimensione massima in byte dei messaggi, comprese le intestazioni.</span><span class="sxs-lookup"><span data-stu-id="77d48-119">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="77d48-120">Il mittente di un messaggio riceve un errore SOAP se il messaggio è troppo grande per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="77d48-120">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="77d48-121">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="77d48-121">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="77d48-122">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="77d48-122">The default is 65536.</span></span>|  
|<span data-ttu-id="77d48-123">port</span><span class="sxs-lookup"><span data-stu-id="77d48-123">port</span></span>|<span data-ttu-id="77d48-124">Numero intero che specifica la porta dell'interfaccia di rete usata dall'associazione per elaborare i messaggi TCP del canale peer.</span><span class="sxs-lookup"><span data-stu-id="77d48-124">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="77d48-125">Il valore deve essere compreso tra <xref:System.Net.IPEndPoint.MinPort> e <xref:System.Net.IPEndPoint.MaxPort>.</span><span class="sxs-lookup"><span data-stu-id="77d48-125">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="77d48-126">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="77d48-126">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77d48-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="77d48-127">Child Elements</span></span>  
  
|<span data-ttu-id="77d48-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="77d48-128">Element</span></span>|<span data-ttu-id="77d48-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77d48-129">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="77d48-130">Definisce le impostazioni di sicurezza per questo trasporto.</span><span class="sxs-lookup"><span data-stu-id="77d48-130">Defines the security settings for this transport.</span></span> <span data-ttu-id="77d48-131">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="77d48-131">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="77d48-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="77d48-132">Parent Elements</span></span>  
  
|<span data-ttu-id="77d48-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="77d48-133">Element</span></span>|<span data-ttu-id="77d48-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77d48-134">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="77d48-135">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="77d48-135">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77d48-136">Commenti</span><span class="sxs-lookup"><span data-stu-id="77d48-136">Remarks</span></span>  
 <span data-ttu-id="77d48-137">Questo trasporto non può essere usato con contratti che includono operazioni request/reply.</span><span class="sxs-lookup"><span data-stu-id="77d48-137">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77d48-138">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="77d48-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="77d48-139">Trasporti</span><span class="sxs-lookup"><span data-stu-id="77d48-139">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="77d48-140">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="77d48-140">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="77d48-141">Binding</span><span class="sxs-lookup"><span data-stu-id="77d48-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="77d48-142">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="77d48-142">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="77d48-143">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="77d48-143">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
