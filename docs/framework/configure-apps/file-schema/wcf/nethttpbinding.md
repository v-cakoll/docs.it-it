---
title: '&lt;netHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: b0d81ca0-87c5-4090-8baa-e390fd3656d2
ms.openlocfilehash: f6d3085ce999caad7e605341ecdb6d7099da3590
ms.sourcegitcommit: e8dc507cfdaad504fc9d4c83d28d24569dcef91c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/03/2018
ms.locfileid: "32751922"
---
# <a name="ltnethttpbindinggt"></a><span data-ttu-id="54894-102">&lt;netHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="54894-102">&lt;netHttpBinding&gt;</span></span>
<span data-ttu-id="54894-103">Rappresenta un'associazione che un servizio Windows Communication Foundation (WCF) è possibile usare per configurare ed esporre endpoint che sono in grado di comunicare tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="54894-103">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTP.</span></span> <span data-ttu-id="54894-104">Nel caso di un contratto duplex, verrà usato Web Sockets. In caso contrario, verrà usato HTTP.</span><span class="sxs-lookup"><span data-stu-id="54894-104">When used with a duplex contract, Web Sockets will be used, otherwise HTTP will be used.</span></span>  
  
 <span data-ttu-id="54894-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="54894-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="54894-106">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="54894-106">\<bindings></span></span>  
<span data-ttu-id="54894-107">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="54894-107">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54894-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54894-108">Syntax</span></span>  

```xml  
<netHttpBinding>  
   <binding   
       allowCookies="Boolean"  
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
       useDefaultWebProxy="Boolean"  
       <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">  
           <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"  
                  proxyCredentialType="None/Basic/Digest/Ntlm/Windows"  
                                    realm="string" />  
           <message   
                 algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                            clientCredentialType="UserName/Certificate"/>  
       </security>  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"             maxNameTableCharCount="Integer"                maxStringContentLength="Integer" />  
   </binding>  
</netHttpBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="54894-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="54894-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54894-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="54894-110">Attributes and Elements</span></span>  
 <span data-ttu-id="54894-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="54894-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54894-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="54894-112">Attributes</span></span>  
  
|<span data-ttu-id="54894-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="54894-113">Attribute</span></span>|<span data-ttu-id="54894-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54894-114">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="54894-115">Valore booleano che indica se il client accetta cookie e li propaga alle richieste future.</span><span class="sxs-lookup"><span data-stu-id="54894-115">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="54894-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="54894-116">The default is `false`.</span></span><br /><br /> <span data-ttu-id="54894-117">È possibile usare questa proprietà quando si interagisce con servizi Web ASMX che usano cookie.</span><span class="sxs-lookup"><span data-stu-id="54894-117">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="54894-118">In questo modo i cookie restituiti dal server vengono copiati automaticamente in tutte le richieste client future per quel servizio.</span><span class="sxs-lookup"><span data-stu-id="54894-118">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="54894-119">Valore booleano che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="54894-119">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="54894-120">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="54894-120">The default is `false`.</span></span><br /><br /> <span data-ttu-id="54894-121">Una risorsa Internet è locale se dispone di un indirizzo locale.</span><span class="sxs-lookup"><span data-stu-id="54894-121">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="54894-122">Un indirizzo locale è situato nello stesso computer, la LAN o intranet locale ed è identificato nella sintassi dalla mancanza di un punto (.) come gli URI "http://webserver/"e"http://localhost/".</span><span class="sxs-lookup"><span data-stu-id="54894-122">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="54894-123">L'impostazione di questo attributo determina se gli endpoint configurati con BasicHttpBinding usano il server proxy quando accedono alle risorse locali.</span><span class="sxs-lookup"><span data-stu-id="54894-123">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="54894-124">Se questo attributo è `true`, le richieste alle risorse Internet locali non usano il server proxy.</span><span class="sxs-lookup"><span data-stu-id="54894-124">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="54894-125">Quando l'attributo è impostato su `true`, usare il nome host invece di localhost se si desidera che i client passino da un proxy per comunicare con servizi nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="54894-125">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="54894-126">Se questo attributo è `false`, tutte le richieste Internet vengono effettuate tramite il server proxy.</span><span class="sxs-lookup"><span data-stu-id="54894-126">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="54894-127">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="54894-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="54894-128">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="54894-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="54894-129">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="54894-129">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="54894-130">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="54894-130">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="54894-131">L'attributo è di tipo `System.ServiceModel.HostnameComparisonMode`, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="54894-131">This attribute is of type `System.ServiceModel.HostnameComparisonMode`, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="54894-132">Il valore predefinito è `StrongWildcard`>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="54894-132">The default value is `StrongWildcard`>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="54894-133">Valore intero che specifica la quantità massima di memoria allocata al gestore dei buffer dei messaggi che riceve i messaggi dal canale.</span><span class="sxs-lookup"><span data-stu-id="54894-133">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="54894-134">Il valore predefinito è 524.288 (0x80000) byte.</span><span class="sxs-lookup"><span data-stu-id="54894-134">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="54894-135">Il gestore dei buffer usa un pool di buffer per ridurre al minimo il costo legato all'utilizzo dei buffer.</span><span class="sxs-lookup"><span data-stu-id="54894-135">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="54894-136">I buffer sono necessari per elaborare i messaggi provenienti dal servizio quando arrivano dal canale.</span><span class="sxs-lookup"><span data-stu-id="54894-136">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="54894-137">Se la memoria nel pool di buffer non è sufficiente per elaborare il carico dei messaggi, il gestore dei buffer deve allocare altra memoria dall'heap CLR, aumentando l'overhead della procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="54894-137">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="54894-138">Se la quantità di memoria aggiuntiva allocata in questo modo è notevolmente elevata, ciò significa che le dimensioni del pool di buffer sono troppo ridotte e che per migliorare le prestazioni è possibile allocare più risorse a tale pool mediante l'aumento del limite specificato da questo attributo.</span><span class="sxs-lookup"><span data-stu-id="54894-138">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="54894-139">Un valore intero che specifica la dimensione massima, in byte, di un buffer che memorizza i messaggi mentre vengono elaborati per un endpoint configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="54894-139">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="54894-140">L'impostazione predefinita è 65.536 byte.</span><span class="sxs-lookup"><span data-stu-id="54894-140">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="54894-141">Numero intero positivo che definisce la dimensione massima del messaggio, incluse le intestazioni, che può essere ricevuto in canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="54894-141">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="54894-142">Il mittente riceve un errore SOAP se il messaggio è troppo grande per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="54894-142">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="54894-143">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="54894-143">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="54894-144">L'impostazione predefinita è 65.536 byte.</span><span class="sxs-lookup"><span data-stu-id="54894-144">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="54894-145">Definisce il codificatore usato per codificare il messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="54894-145">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="54894-146">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="54894-146">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="54894-147">-Text: Usa un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="54894-147">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="54894-148">-Mtom: Usa un codificatore Message Transmission organizzazione Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="54894-148">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="54894-149">L'impostazione predefinita è Text.</span><span class="sxs-lookup"><span data-stu-id="54894-149">The default is Text.</span></span> <span data-ttu-id="54894-150">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="54894-150">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="54894-151">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="54894-151">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="54894-152">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="54894-152">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="54894-153">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="54894-153">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="54894-154">In aggiunta, il nome è univoco fra associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="54894-154">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="54894-155">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="54894-155">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="54894-156">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="54894-156">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`namespace`|<span data-ttu-id="54894-157">Specifica lo spazio dei nomi XML dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="54894-157">Specifies the XML namespace of the binding.</span></span> <span data-ttu-id="54894-158">Il valore predefinito è "http://tempuri.org/Bindings".</span><span class="sxs-lookup"><span data-stu-id="54894-158">The default value is "http://tempuri.org/Bindings".</span></span> <span data-ttu-id="54894-159">Ciascuna associazione è provvista di un attributo `name` e `namespace` che insieme la identificano in modo univoco nei metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="54894-159">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span>|  
|`openTimeout`|<span data-ttu-id="54894-160">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="54894-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="54894-161">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="54894-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="54894-162">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="54894-162">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="54894-163">URI che contiene l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="54894-163">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="54894-164">Se `useSystemWebProxy` è impostato su `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="54894-164">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="54894-165">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="54894-165">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="54894-166">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="54894-166">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="54894-167">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="54894-167">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="54894-168">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="54894-168">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="54894-169">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="54894-169">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="54894-170">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="54894-170">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="54894-171">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="54894-171">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="54894-172">Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="54894-172">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="54894-173">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="54894-173">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="54894-174">-BigEndianUnicode: Codifica Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="54894-174">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="54894-175">-Unicode: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="54894-175">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="54894-176">-UTF8: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="54894-176">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="54894-177">L'impostazione predefinita è UTF8.</span><span class="sxs-lookup"><span data-stu-id="54894-177">The default is UTF8.</span></span> <span data-ttu-id="54894-178">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="54894-178">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="54894-179">Valore <xref:System.ServiceModel.TransferMode> valido che specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso in una richiesta o una risposta.</span><span class="sxs-lookup"><span data-stu-id="54894-179">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="54894-180">Valore booleano che specifica se il proxy HTTP configurato automaticamente del sistema deve essere usato, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="54894-180">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="54894-181">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="54894-181">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="54894-182">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="54894-182">Child Elements</span></span>  
  
|<span data-ttu-id="54894-183">Elemento</span><span class="sxs-lookup"><span data-stu-id="54894-183">Element</span></span>|<span data-ttu-id="54894-184">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54894-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54894-185">\<security></span><span class="sxs-lookup"><span data-stu-id="54894-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="54894-186">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="54894-186">Defines the security settings for the binding.</span></span> <span data-ttu-id="54894-187">L'elemento è di tipo `NetHttpSecurityElement`.</span><span class="sxs-lookup"><span data-stu-id="54894-187">This element is of type `NetHttpSecurityElement`.</span></span>|  
|[<span data-ttu-id="54894-188">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="54894-188">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="54894-189">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="54894-189">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="54894-190">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="54894-190">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54894-191">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="54894-191">Parent Elements</span></span>  
  
|<span data-ttu-id="54894-192">Elemento</span><span class="sxs-lookup"><span data-stu-id="54894-192">Element</span></span>|<span data-ttu-id="54894-193">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54894-193">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54894-194">\<bindings></span><span class="sxs-lookup"><span data-stu-id="54894-194">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="54894-195">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="54894-195">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54894-196">Note</span><span class="sxs-lookup"><span data-stu-id="54894-196">Remarks</span></span>  
 <span data-ttu-id="54894-197">NetHttpBinding usa HTTP come trasporto per l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="54894-197">The NetHttpBinding uses HTTP as the transport for sending messages.</span></span> <span data-ttu-id="54894-198">Nel caso di un contratto duplex, verrà usato Web Sockets.</span><span class="sxs-lookup"><span data-stu-id="54894-198">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="54894-199">Se si usa un contratto richiesta-risposta, NetHttpBinding si comporta come BasicHttpBinding con un codificatore binario.</span><span class="sxs-lookup"><span data-stu-id="54894-199">When used with a request-reply contract NetHttpBinding will behave like a BasicHttpBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="54894-200">La protezione è disattivata per impostazione predefinita, ma è possibile aggiungerla impostando l'attributo mode del [ \<sicurezza >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) elemento figlio da un valore diverso da `None`.</span><span class="sxs-lookup"><span data-stu-id="54894-200">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="54894-201">Per impostazione predefinita usa una codifica dei messaggi "Text" e una codifica del testo UTF-8.</span><span class="sxs-lookup"><span data-stu-id="54894-201">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54894-202">Esempio</span><span class="sxs-lookup"><span data-stu-id="54894-202">Example</span></span>  
 <span data-ttu-id="54894-203">Nell'esempio seguente è dimostrato l'uso di <xref:System.ServiceModel.NetHttpBinding> che fornisce la comunicazione HTTP e la interoperabilità massima con servizi Web di prima e seconda generazione.</span><span class="sxs-lookup"><span data-stu-id="54894-203">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTP communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="54894-204">L'associazione è specificata nei file di configurazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="54894-204">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="54894-205">Il tipo di associazione specificato usando l'attributo `binding` dell'elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="54894-205">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="54894-206">Se si desidera configurare l'associazione di base   e modificare alcune delle relative impostazioni, è necessario definire una configurazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="54894-206">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="54894-207">L'endpoint deve fare riferimento alla configurazione di associazione tramite il nome usando l'attributo `bindingConfiguration` dell'elemento `<endpoint>`, come è illustrato nel seguente codice di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="54894-207">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="netHttpBinding"  
             bindingConfiguration="Binding1"   
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <netHttpBinding>  
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
               useDefaultWebProxy="true" >  
              <security mode="None" />  
         </binding>  
     </netHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="example"></a><span data-ttu-id="54894-208">Esempio</span><span class="sxs-lookup"><span data-stu-id="54894-208">Example</span></span>  
 <span data-ttu-id="54894-209">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="54894-209">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="54894-210">La funzionalità dall'esempio precedente può essere ottenuta rimuovendo bindingConfiguration dall'indirizzo endpoint e il nome dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="54894-210">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name frm the binding.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="netHttpBinding"  
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <netHttpBinding>  
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
     </netHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="54894-211">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="54894-211">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54894-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54894-212">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="54894-213">Associazioni</span><span class="sxs-lookup"><span data-stu-id="54894-213">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="54894-214">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="54894-214">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="54894-215">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="54894-215">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="54894-216">\<binding></span><span class="sxs-lookup"><span data-stu-id="54894-216">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
