---
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 743eaa281fef233ddc2e8af5cee890bd10ce0963
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941183"
---
# <a name="udpbinding"></a><span data-ttu-id="103eb-101">\<udpBinding></span><span class="sxs-lookup"><span data-stu-id="103eb-101">\<udpBinding></span></span>
<span data-ttu-id="103eb-102">Elemento di configurazione usato per configurare <xref:System.ServiceModel.UdpBinding>.</span><span class="sxs-lookup"><span data-stu-id="103eb-102">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
 <span data-ttu-id="103eb-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="103eb-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="103eb-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="103eb-104">\<bindings></span></span>  
<span data-ttu-id="103eb-105">\<udpBinding></span><span class="sxs-lookup"><span data-stu-id="103eb-105">\<udpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="103eb-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="103eb-106">Syntax</span></span>  
  
```xml  
<udpBinding>
  <binding closeTimeout="TimeSpan"
           duplicateMessageHistoryLength="Integer"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxPendingMessagesTotalSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetransmitCount="Integer"
           multicastInterfaceId="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           timeToLive="TimeSpan">
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="103eb-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="103eb-107">Attributes and Elements</span></span>  
 <span data-ttu-id="103eb-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="103eb-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="103eb-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="103eb-109">Attributes</span></span>  
  
|<span data-ttu-id="103eb-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="103eb-110">Attribute</span></span>|<span data-ttu-id="103eb-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="103eb-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="103eb-112">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="103eb-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="103eb-113">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="103eb-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="103eb-114">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="103eb-114">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="103eb-115">Valore integer che specifica la lunghezza della cronologia dei messaggi duplicati.</span><span class="sxs-lookup"><span data-stu-id="103eb-115">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="103eb-116">Valore intero che specifica la quantità massima di memoria allocata al gestore dei buffer dei messaggi che riceve i messaggi dal canale.</span><span class="sxs-lookup"><span data-stu-id="103eb-116">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="103eb-117">Il valore predefinito è 524.288 (0x80000) byte.</span><span class="sxs-lookup"><span data-stu-id="103eb-117">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="103eb-118">Un valore intero che specifica la dimensione massima, in byte, di un buffer che memorizza i messaggi mentre vengono elaborati per un endpoint configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="103eb-118">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="103eb-119">L'impostazione predefinita è 65.536 byte.</span><span class="sxs-lookup"><span data-stu-id="103eb-119">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="103eb-120">Valore integer che specifica il numero massimo di messaggi ricevuti ma non ancora rimossi dalla coda di input per una singola istanza di canale.</span><span class="sxs-lookup"><span data-stu-id="103eb-120">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="103eb-121">Numero intero positivo che definisce la dimensione massima del messaggio, incluse le intestazioni, che può essere ricevuto in canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="103eb-121">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="103eb-122">Il mittente riceve un errore SOAP se il messaggio è troppo grande per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="103eb-122">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="103eb-123">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="103eb-123">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="103eb-124">L'impostazione predefinita è 65.536 byte.</span><span class="sxs-lookup"><span data-stu-id="103eb-124">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="103eb-125">Valore integer che specifica il numero massimo di messaggi da ritrasmettere.</span><span class="sxs-lookup"><span data-stu-id="103eb-125">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="103eb-126">Valore integer che specifica l'ID multicast dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="103eb-126">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="103eb-127">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="103eb-127">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="103eb-128">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="103eb-128">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="103eb-129">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="103eb-129">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="103eb-130">In aggiunta, il nome è univoco fra associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="103eb-130">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="103eb-131">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="103eb-131">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="103eb-132">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="103eb-132">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="103eb-133">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="103eb-133">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="103eb-134">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="103eb-134">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="103eb-135">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="103eb-135">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="103eb-136">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="103eb-136">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="103eb-137">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="103eb-137">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="103eb-138">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="103eb-138">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="103eb-139">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="103eb-139">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="103eb-140">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="103eb-140">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="103eb-141">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="103eb-141">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="103eb-142">Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="103eb-142">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="103eb-143">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="103eb-143">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="103eb-144">BigEndianUnicode Codifica BigEndian Unicode.</span><span class="sxs-lookup"><span data-stu-id="103eb-144">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="103eb-145">Unicode codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="103eb-145">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="103eb-146">UTF8 codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="103eb-146">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="103eb-147">L'impostazione predefinita è UTF8.</span><span class="sxs-lookup"><span data-stu-id="103eb-147">The default is UTF8.</span></span> <span data-ttu-id="103eb-148">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="103eb-148">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="103eb-149">Valore timespan che specifica durata (TTL, Time To Live) dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="103eb-149">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="103eb-150">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="103eb-150">Child Elements</span></span>  
  
|<span data-ttu-id="103eb-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="103eb-151">Element</span></span>|<span data-ttu-id="103eb-152">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="103eb-152">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="103eb-153">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="103eb-153">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="103eb-154">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="103eb-154">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="103eb-155">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="103eb-155">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="103eb-156">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="103eb-156">Parent Elements</span></span>  
  
|<span data-ttu-id="103eb-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="103eb-157">Element</span></span>|<span data-ttu-id="103eb-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="103eb-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="103eb-159">\<bindings></span><span class="sxs-lookup"><span data-stu-id="103eb-159">\<bindings></span></span>](bindings.md)|<span data-ttu-id="103eb-160">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="103eb-160">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="103eb-161">Note</span><span class="sxs-lookup"><span data-stu-id="103eb-161">Remarks</span></span>  
 <span data-ttu-id="103eb-162">UdpBinding consente ai servizi WCF di comunicare tramite trasporto UDP.</span><span class="sxs-lookup"><span data-stu-id="103eb-162">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="103eb-163">Consente lo scambio di messaggi "Fire and Forget" in cui un client invia un messaggio a un servizio e non prevede alcuna risposta.</span><span class="sxs-lookup"><span data-stu-id="103eb-163">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="103eb-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="103eb-164">Example</span></span>  
 <span data-ttu-id="103eb-165">Nell'esempio seguente viene illustrato come configurare <xref:System.ServiceModel.UdpBinding> usando l'elemento <`udpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="103eb-165">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
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
            timeToLive="00:10:00">
    <readerQuotas />
  </binding>
</udpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="103eb-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="103eb-166">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="103eb-167">Associazioni</span><span class="sxs-lookup"><span data-stu-id="103eb-167">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="103eb-168">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="103eb-168">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="103eb-169">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="103eb-169">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="103eb-170">\<binding></span><span class="sxs-lookup"><span data-stu-id="103eb-170">\<binding></span></span>](../../../misc/binding.md)
