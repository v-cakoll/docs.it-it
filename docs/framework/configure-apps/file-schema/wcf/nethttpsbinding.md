---
title: '&lt;netHttpsBinding&gt;'
ms.date: 03/30/2017
ms.assetid: ff122116-6042-4792-9f21-275b4f97a105
ms.openlocfilehash: fb279321cccc325700ac18697d484da20c685c9d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltnethttpsbindinggt"></a><span data-ttu-id="171d0-102">&lt;netHttpsBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="171d0-102">&lt;netHttpsBinding&gt;</span></span>
<span data-ttu-id="171d0-103">Rappresenta un'associazione che un servizio Windows Communication Foundation (WCF) è possibile utilizzare per configurare ed esporre endpoint che sono in grado di comunicare tramite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="171d0-103">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTPS.</span></span> <span data-ttu-id="171d0-104">Nel caso di un contratto duplex, verrà usato Web Sockets. In caso contrario, verrà usato HTTPS.</span><span class="sxs-lookup"><span data-stu-id="171d0-104">When used with a duplex contract, Web Sockets will be used, otherwise HTTPS will be used.</span></span>  
  
 <span data-ttu-id="171d0-105">Elemento radice</span><span class="sxs-lookup"><span data-stu-id="171d0-105">Root Element</span></span>  
<span data-ttu-id="171d0-106">Elemento successivo</span><span class="sxs-lookup"><span data-stu-id="171d0-106">Next Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="171d0-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="171d0-107">Syntax</span></span>  

```xml
<netHttpsBinding>  
  <binding allowCookies="Boolean"  
           bypassProxyOnLocal="Boolean"  
           closeTimeout="TimeSpan"   
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
           maxBufferPoolSize="Integer"  
           maxBufferSize="Integer"  
           maxReceivedMessageSize="Integer"  
           messageEncoding="Binary/Text/Mtom"  
           name="string"   
           openTimeout="TimeSpan"   
           proxyAddress="URI"  
           receiveTimeout="TimeSpan"  
           sendTimeout="TimeSpan"  
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
           useDefaultWebProxy="Boolean">
    <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">  
      <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"  
                 proxyCredentialType="None/Basic/Digest/Ntlm/Windows"  
                 realm="string" />  
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" 
               clientCredentialType="UserName/Certificate"/>  
    </security>  
    <readerQuotas maxArrayLength="Integer" 
                  maxBytesPerRead="Integer" 
                  maxDepth="Integer" 
                  maxNameTableCharCount="Integer" 
                  maxStringContentLength="Integer" />  
  </binding>  
</netHttpsBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="171d0-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="171d0-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="171d0-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="171d0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="171d0-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="171d0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="171d0-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="171d0-111">Attributes</span></span>  
  
|<span data-ttu-id="171d0-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="171d0-112">Attribute</span></span>|<span data-ttu-id="171d0-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="171d0-113">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="171d0-114">Valore booleano che indica se il client accetta cookie e li propaga alle richieste future.</span><span class="sxs-lookup"><span data-stu-id="171d0-114">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="171d0-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="171d0-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="171d0-116">È possibile usare questa proprietà quando si interagisce con servizi Web ASMX che usano cookie.</span><span class="sxs-lookup"><span data-stu-id="171d0-116">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="171d0-117">In questo modo i cookie restituiti dal server vengono copiati automaticamente in tutte le richieste client future per quel servizio.</span><span class="sxs-lookup"><span data-stu-id="171d0-117">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="171d0-118">Valore booleano che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="171d0-118">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="171d0-119">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="171d0-119">The default is `false`.</span></span><br /><br /> <span data-ttu-id="171d0-120">Una risorsa Internet è locale se dispone di un indirizzo locale.</span><span class="sxs-lookup"><span data-stu-id="171d0-120">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="171d0-121">Un indirizzo locale è situato nello stesso computer, la LAN o intranet locale ed è identificato nella sintassi dalla mancanza di un punto (.) come URI "http://webserver/"e"http://localhost/".</span><span class="sxs-lookup"><span data-stu-id="171d0-121">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="171d0-122">L'impostazione di questo attributo determina se gli endpoint configurati con BasicHttpBinding usano il server proxy quando accedono alle risorse locali.</span><span class="sxs-lookup"><span data-stu-id="171d0-122">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="171d0-123">Se questo attributo è `true`, le richieste alle risorse Internet locali non usano il server proxy.</span><span class="sxs-lookup"><span data-stu-id="171d0-123">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="171d0-124">Quando l'attributo è impostato su `true`, usare il nome host invece di localhost se si desidera che i client passino da un proxy per comunicare con servizi nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="171d0-124">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="171d0-125">Se questo attributo è `false`, tutte le richieste Internet vengono effettuate tramite il server proxy.</span><span class="sxs-lookup"><span data-stu-id="171d0-125">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="171d0-126">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="171d0-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="171d0-127">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="171d0-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="171d0-128">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="171d0-128">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="171d0-129">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="171d0-129">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="171d0-130">L'attributo è di tipo `HostnameComparisonMode`, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="171d0-130">This attribute is of type `HostnameComparisonMode`, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="171d0-131">Il valore predefinito è `StrongWildcard`, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="171d0-131">The default value is `StrongWildcard`, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="171d0-132">Valore intero che specifica la quantità massima di memoria allocata al gestore dei buffer dei messaggi che riceve i messaggi dal canale.</span><span class="sxs-lookup"><span data-stu-id="171d0-132">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="171d0-133">Il valore predefinito è 524.288 (0x80000) byte.</span><span class="sxs-lookup"><span data-stu-id="171d0-133">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="171d0-134">Il gestore dei buffer usa un pool di buffer per ridurre al minimo il costo legato all'utilizzo dei buffer.</span><span class="sxs-lookup"><span data-stu-id="171d0-134">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="171d0-135">I buffer sono necessari per elaborare i messaggi provenienti dal servizio quando arrivano dal canale.</span><span class="sxs-lookup"><span data-stu-id="171d0-135">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="171d0-136">Se la memoria nel pool di buffer non è sufficiente per elaborare il carico dei messaggi, il gestore dei buffer deve allocare altra memoria dall'heap CLR, aumentando l'overhead della procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="171d0-136">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="171d0-137">Se la quantità di memoria aggiuntiva allocata in questo modo è notevolmente elevata, ciò significa che le dimensioni del pool di buffer sono troppo ridotte e che per migliorare le prestazioni è possibile allocare più risorse a tale pool mediante l'aumento del limite specificato da questo attributo.</span><span class="sxs-lookup"><span data-stu-id="171d0-137">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="171d0-138">Un valore intero che specifica la dimensione massima, in byte, di un buffer che memorizza i messaggi mentre vengono elaborati per un endpoint configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="171d0-138">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="171d0-139">L'impostazione predefinita è 65.536 byte.</span><span class="sxs-lookup"><span data-stu-id="171d0-139">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="171d0-140">Numero intero positivo che definisce la dimensione massima del messaggio, incluse le intestazioni, che può essere ricevuto in canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="171d0-140">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="171d0-141">Il mittente riceve un errore SOAP se il messaggio è troppo grande per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="171d0-141">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="171d0-142">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="171d0-142">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="171d0-143">L'impostazione predefinita è 65.536 byte.</span><span class="sxs-lookup"><span data-stu-id="171d0-143">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="171d0-144">Definisce il codificatore usato per codificare il messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="171d0-144">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="171d0-145">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="171d0-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="171d0-146">-Text: Usa un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="171d0-146">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="171d0-147">-Mtom: Usa un codificatore Message Transmission Organization meccanismo 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="171d0-147">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="171d0-148">L'impostazione predefinita è Text.</span><span class="sxs-lookup"><span data-stu-id="171d0-148">The default is Text.</span></span> <span data-ttu-id="171d0-149">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="171d0-149">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="171d0-150">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="171d0-150">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="171d0-151">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="171d0-151">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="171d0-152">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="171d0-152">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="171d0-153">In aggiunta, il nome è univoco fra associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="171d0-153">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="171d0-154">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="171d0-154">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="171d0-155">Per ulteriori informazioni sulla configurazione predefinita e senza nome associazioni e comportamenti, vedere [configurazione semplificata](../../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="171d0-155">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`namespace`|<span data-ttu-id="171d0-156">Specifica lo spazio dei nomi XML dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="171d0-156">Specifies the XML namespace of the binding.</span></span> <span data-ttu-id="171d0-157">Il valore predefinito è "http://tempuri.org/Bindings".</span><span class="sxs-lookup"><span data-stu-id="171d0-157">The default value is "http://tempuri.org/Bindings".</span></span> <span data-ttu-id="171d0-158">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="171d0-158">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span>|  
|`openTimeout`|<span data-ttu-id="171d0-159">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="171d0-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="171d0-160">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="171d0-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="171d0-161">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="171d0-161">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="171d0-162">URI che contiene l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="171d0-162">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="171d0-163">Se `useSystemWebProxy` è impostato su `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="171d0-163">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="171d0-164">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="171d0-164">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="171d0-165">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="171d0-165">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="171d0-166">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="171d0-166">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="171d0-167">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="171d0-167">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="171d0-168">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="171d0-168">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="171d0-169">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="171d0-169">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="171d0-170">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="171d0-170">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="171d0-171">Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="171d0-171">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="171d0-172">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="171d0-172">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="171d0-173">-BigEndianUnicode: Codifica Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="171d0-173">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="171d0-174">-Unicode: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="171d0-174">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="171d0-175">-UTF8: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="171d0-175">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="171d0-176">L'impostazione predefinita è UTF8.</span><span class="sxs-lookup"><span data-stu-id="171d0-176">The default is UTF8.</span></span> <span data-ttu-id="171d0-177">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="171d0-177">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="171d0-178">Valore <xref:System.ServiceModel.TransferMode> valido che specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso in una richiesta o una risposta.</span><span class="sxs-lookup"><span data-stu-id="171d0-178">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="171d0-179">Valore booleano che specifica se il proxy HTTP configurato automaticamente del sistema deve essere usato, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="171d0-179">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="171d0-180">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="171d0-180">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="171d0-181">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="171d0-181">Child Elements</span></span>  
  
|<span data-ttu-id="171d0-182">Elemento</span><span class="sxs-lookup"><span data-stu-id="171d0-182">Element</span></span>|<span data-ttu-id="171d0-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="171d0-183">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="171d0-184">\<security></span><span class="sxs-lookup"><span data-stu-id="171d0-184">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="171d0-185">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="171d0-185">Defines the security settings for the binding.</span></span> <span data-ttu-id="171d0-186">L'elemento è di tipo <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="171d0-186">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span></span> |  
|[<span data-ttu-id="171d0-187">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="171d0-187">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="171d0-188">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="171d0-188">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="171d0-189">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="171d0-189">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="171d0-190">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="171d0-190">Parent Elements</span></span>  
  
|<span data-ttu-id="171d0-191">Elemento</span><span class="sxs-lookup"><span data-stu-id="171d0-191">Element</span></span>|<span data-ttu-id="171d0-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="171d0-192">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="171d0-193">\<bindings></span><span class="sxs-lookup"><span data-stu-id="171d0-193">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="171d0-194">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="171d0-194">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="171d0-195">Note</span><span class="sxs-lookup"><span data-stu-id="171d0-195">Remarks</span></span>  
 <span data-ttu-id="171d0-196">NetHttpsBinding usa HTTPS come trasporto per l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="171d0-196">The NetHttpsBinding uses HTTPS as the transport for sending messages.</span></span> <span data-ttu-id="171d0-197">Nel caso di un contratto duplex, verrà usato Web Sockets.</span><span class="sxs-lookup"><span data-stu-id="171d0-197">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="171d0-198">Se si usa un contratto richiesta-risposta, NetHttpsBinding si comporta come BasicHttpsBinding con un codificatore binario.</span><span class="sxs-lookup"><span data-stu-id="171d0-198">When used with a request-reply contract NetHttpsBinding will behave like a BasicHttpsBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="171d0-199">La protezione è disattivata per impostazione predefinita, ma è possibile aggiungerla impostando l'attributo mode del [ \<sicurezza >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) elemento figlio di un valore diverso da `None`.</span><span class="sxs-lookup"><span data-stu-id="171d0-199">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="171d0-200">Per impostazione predefinita usa una codifica dei messaggi "Text" e una codifica del testo UTF-8.</span><span class="sxs-lookup"><span data-stu-id="171d0-200">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="171d0-201">Esempio</span><span class="sxs-lookup"><span data-stu-id="171d0-201">Example</span></span>  
 <span data-ttu-id="171d0-202">Nell'esempio seguente è dimostrato l'uso di <xref:System.ServiceModel.NetHttpBinding> che fornisce la comunicazione HTTPS e la massima interoperabilità con servizi Web di prima e seconda generazione.</span><span class="sxs-lookup"><span data-stu-id="171d0-202">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTPS communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="171d0-203">L'associazione è specificata nei file di configurazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="171d0-203">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="171d0-204">Il tipo di associazione specificato usando l'attributo `binding` dell'elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="171d0-204">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="171d0-205">Se si desidera configurare l'associazione di base   e modificare alcune delle relative impostazioni, è necessario definire una configurazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="171d0-205">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="171d0-206">L'endpoint deve fare riferimento alla configurazione di associazione tramite il nome usando l'attributo `bindingConfiguration` dell'elemento `<endpoint>`, come è illustrato nel seguente codice di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="171d0-206">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <endpoint address=""  
                binding="netHttpsBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
    <netHttpsBinding>  
      <binding name="Binding1"   
               hostNameComparisonMode="StrongWildcard" 
               receiveTimeout="00:10:00" 
               sendTimeout="00:10:00" 
               openTimeout="00:10:00" 
               closeTimeout="00:10:00" 
               maxReceivedMessageSize="65536" 
               maxBufferSize="65536" 
               maxBufferPoolSize="524288" 
               transferMode="Buffered" 
               messageEncoding="Binary" 
               textEncoding="utf-8" 
               bypassProxyOnLocal="false" 
               useDefaultWebProxy="true">  
        <security mode="None" />  
      </binding>  
    </netHttpsBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="example"></a><span data-ttu-id="171d0-207">Esempio</span><span class="sxs-lookup"><span data-stu-id="171d0-207">Example</span></span>  
 <span data-ttu-id="171d0-208">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="171d0-208">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="171d0-209">La funzionalità dall'esempio precedente può essere ottenuta rimuovendo bindingConfiguration dall'indirizzo endpoint e il nome dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="171d0-209">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name frm the binding.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="netHttpsBinding"  
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <netHttpsBinding>  
        <binding   
               hostNameComparisonMode="StrongWildcard"   
               receiveTimeout="00:10:00"  
               sendTimeout="00:10:00"  
               openTimeout="00:10:00"  
               closeTimeout="00:10:00"  
               maxReceivedMessageSize="65536"   
               maxBufferSize="65536"   
               maxBufferPoolSize="524288"   
               transferMode="Buffered"   
               messageEncoding="Binary"   
               textEncoding="utf-8"  
               bypassProxyOnLocal="false"  
               useDefaultWebProxy="true" >  
              <security mode="None" />  
         </binding>  
     </netHttpsBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="171d0-210">Per ulteriori informazioni sulla configurazione predefinita e senza nome associazioni e comportamenti, vedere [configurazione semplificata](../../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="171d0-210">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="171d0-211">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="171d0-211">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="171d0-212">Associazioni</span><span class="sxs-lookup"><span data-stu-id="171d0-212">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="171d0-213">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="171d0-213">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="171d0-214">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="171d0-214">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="171d0-215">\<binding></span><span class="sxs-lookup"><span data-stu-id="171d0-215">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
