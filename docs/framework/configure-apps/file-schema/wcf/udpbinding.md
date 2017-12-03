---
title: '&lt;udpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 26ed0c9dd2c895d4a01536a5715c6235ff65df7b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltudpbindinggt"></a><span data-ttu-id="30ed0-102">&lt;udpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="30ed0-102">&lt;udpBinding&gt;</span></span>
<span data-ttu-id="30ed0-103">Elemento di configurazione usato per configurare <xref:System.ServiceModel.UdpBinding>.</span><span class="sxs-lookup"><span data-stu-id="30ed0-103">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
 <span data-ttu-id="30ed0-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="30ed0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="30ed0-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="30ed0-105">\<bindings></span></span>  
<span data-ttu-id="30ed0-106">\<udpBinding ></span><span class="sxs-lookup"><span data-stu-id="30ed0-106">\<udpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30ed0-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30ed0-107">Syntax</span></span>  
  
```xml  
<udpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       duplicateMessageHistoryLength="Integer"  
       maxBufferPoolSize="Integer"  
       maxBufferSize="Integer"       maxPendingMessagesTotalSize="Integer"  
       maxReceivedMessageSize="Integer"       maxRetransmitCount="Integer"  
       multicastInterfaceId="Integer"  
              name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan"  
       textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
       timeToLive="TimeSpan">  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"             maxNameTableCharCount="Integer"                maxStringContentLength="Integer" />  
   </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30ed0-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="30ed0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="30ed0-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="30ed0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30ed0-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="30ed0-110">Attributes</span></span>  
  
|<span data-ttu-id="30ed0-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="30ed0-111">Attribute</span></span>|<span data-ttu-id="30ed0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30ed0-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="30ed0-113">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="30ed0-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="30ed0-114">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="30ed0-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="30ed0-115">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="30ed0-115">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="30ed0-116">Valore integer che specifica la lunghezza della cronologia dei messaggi duplicati.</span><span class="sxs-lookup"><span data-stu-id="30ed0-116">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="30ed0-117">Valore intero che specifica la quantità massima di memoria allocata al gestore dei buffer dei messaggi che riceve i messaggi dal canale.</span><span class="sxs-lookup"><span data-stu-id="30ed0-117">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="30ed0-118">Il valore predefinito è 524.288 (0x80000) byte.</span><span class="sxs-lookup"><span data-stu-id="30ed0-118">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="30ed0-119">Un valore intero che specifica la dimensione massima, in byte, di un buffer che memorizza i messaggi mentre vengono elaborati per un endpoint configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="30ed0-119">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="30ed0-120">L'impostazione predefinita è 65.536 byte.</span><span class="sxs-lookup"><span data-stu-id="30ed0-120">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="30ed0-121">Valore integer che specifica il numero massimo di messaggi ricevuti ma non ancora rimossi dalla coda di input per una singola istanza di canale.</span><span class="sxs-lookup"><span data-stu-id="30ed0-121">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="30ed0-122">Numero intero positivo che definisce la dimensione massima del messaggio, incluse le intestazioni, che può essere ricevuto in canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="30ed0-122">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="30ed0-123">Il mittente riceve un errore SOAP se il messaggio è troppo grande per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="30ed0-123">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="30ed0-124">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="30ed0-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="30ed0-125">L'impostazione predefinita è 65.536 byte.</span><span class="sxs-lookup"><span data-stu-id="30ed0-125">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="30ed0-126">Valore integer che specifica il numero massimo di messaggi da ritrasmettere.</span><span class="sxs-lookup"><span data-stu-id="30ed0-126">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="30ed0-127">Valore integer che specifica l'ID multicast dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="30ed0-127">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="30ed0-128">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="30ed0-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="30ed0-129">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="30ed0-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="30ed0-130">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="30ed0-130">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="30ed0-131">In aggiunta, il nome è univoco fra associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="30ed0-131">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="30ed0-132">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="30ed0-132">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="30ed0-133">Per ulteriori informazioni sulla configurazione predefinita e senza nome associazioni e comportamenti, vedere [configurazione semplificata](../../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="30ed0-133">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="30ed0-134">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="30ed0-134">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="30ed0-135">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="30ed0-135">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="30ed0-136">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="30ed0-136">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="30ed0-137">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="30ed0-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="30ed0-138">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="30ed0-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="30ed0-139">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="30ed0-139">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="30ed0-140">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="30ed0-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="30ed0-141">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="30ed0-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="30ed0-142">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="30ed0-142">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="30ed0-143">Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="30ed0-143">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="30ed0-144">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="30ed0-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="30ed0-145">-BigEndianUnicode: Codifica Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="30ed0-145">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="30ed0-146">-Unicode: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="30ed0-146">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="30ed0-147">-UTF8: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="30ed0-147">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="30ed0-148">L'impostazione predefinita è UTF8.</span><span class="sxs-lookup"><span data-stu-id="30ed0-148">The default is UTF8.</span></span> <span data-ttu-id="30ed0-149">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="30ed0-149">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="30ed0-150">Valore timespan che specifica durata (TTL, Time To Live) dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="30ed0-150">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30ed0-151">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="30ed0-151">Child Elements</span></span>  
  
|<span data-ttu-id="30ed0-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="30ed0-152">Element</span></span>|<span data-ttu-id="30ed0-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30ed0-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30ed0-154">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="30ed0-154">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="30ed0-155">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="30ed0-155">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="30ed0-156">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="30ed0-156">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="30ed0-157">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="30ed0-157">Parent Elements</span></span>  
  
|<span data-ttu-id="30ed0-158">Elemento</span><span class="sxs-lookup"><span data-stu-id="30ed0-158">Element</span></span>|<span data-ttu-id="30ed0-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30ed0-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30ed0-160">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="30ed0-160">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="30ed0-161">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="30ed0-161">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30ed0-162">Note</span><span class="sxs-lookup"><span data-stu-id="30ed0-162">Remarks</span></span>  
 <span data-ttu-id="30ed0-163">UdpBinding consente ai servizi WCF di comunicare tramite trasporto UDP.</span><span class="sxs-lookup"><span data-stu-id="30ed0-163">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="30ed0-164">Consente infatti di scambi di messaggi "fire and forget" in cui un client invia un messaggio a un servizio e non prevede alcuna risposta.</span><span class="sxs-lookup"><span data-stu-id="30ed0-164">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30ed0-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="30ed0-165">Example</span></span>  
 <span data-ttu-id="30ed0-166">L'esempio seguente illustra come configurare <xref:System.ServiceModel.UdpBinding> usando l'elemento <`udpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="30ed0-166">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
```xml  
<udpBinding>  
        <binding  closeTimeout="00:10:00"  
                   duplicateMessageHistoryLength="100"  
                   maxBufferPoolSize="100"  
                   maxPendingMessagesTotalSize="100000"  
                   maxReceivedMessageSize="65536"  
                    maxRetransmitCount="10"  
                   multicastInterfaceId="00000"  
                   name="myUdpBinding"  
                   openTimeout="00:10:00"  
                   receiveTimeout="00:10:00"  
                   sendTimeout="00:10:00"  
                   textEncoding="utf-8"  
                   timeToLive="00:10:00"  
          <readerQuotas/>   
        </binding>  
      </udpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="30ed0-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30ed0-167">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="30ed0-168">Associazioni</span><span class="sxs-lookup"><span data-stu-id="30ed0-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="30ed0-169">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="30ed0-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="30ed0-170">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="30ed0-170">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="30ed0-171">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="30ed0-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
