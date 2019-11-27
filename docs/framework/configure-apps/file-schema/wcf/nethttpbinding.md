---
title: <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: b0d81ca0-87c5-4090-8baa-e390fd3656d2
ms.openlocfilehash: 537cbd03e55615bcda2a0ab8e41a171e22a94344
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430866"
---
# <a name="nethttpbinding"></a><span data-ttu-id="7111d-101">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="7111d-101">\<netHttpBinding></span></span>
<span data-ttu-id="7111d-102">Rappresenta un'associazione che può essere utilizzata da un servizio Windows Communication Foundation (WCF) per configurare ed esporre endpoint in grado di comunicare tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="7111d-102">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTP.</span></span> <span data-ttu-id="7111d-103">Nel caso di un contratto duplex, verrà usato Web Sockets. In caso contrario, verrà usato HTTP.</span><span class="sxs-lookup"><span data-stu-id="7111d-103">When used with a duplex contract, Web Sockets will be used, otherwise HTTP will be used.</span></span>  
  
<span data-ttu-id="7111d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7111d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7111d-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7111d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7111d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<></span><span class="sxs-lookup"><span data-stu-id="7111d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="7111d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<NetHttpBinding** ></span><span class="sxs-lookup"><span data-stu-id="7111d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7111d-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7111d-108">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Binary/Text/Mtom"
           name="String"
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
               clientCredentialType="UserName/Certificate" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="7111d-109">Digitare</span><span class="sxs-lookup"><span data-stu-id="7111d-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7111d-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7111d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7111d-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7111d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7111d-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7111d-112">Attributes</span></span>  
  
|<span data-ttu-id="7111d-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7111d-113">Attribute</span></span>|<span data-ttu-id="7111d-114">description</span><span class="sxs-lookup"><span data-stu-id="7111d-114">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="7111d-115">Valore booleano che indica se il client accetta cookie e li propaga alle richieste future.</span><span class="sxs-lookup"><span data-stu-id="7111d-115">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="7111d-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="7111d-116">The default is `false`.</span></span><br /><br /> <span data-ttu-id="7111d-117">È possibile usare questa proprietà quando si interagisce con servizi Web ASMX che usano cookie.</span><span class="sxs-lookup"><span data-stu-id="7111d-117">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="7111d-118">In questo modo i cookie restituiti dal server vengono copiati automaticamente in tutte le richieste client future per quel servizio.</span><span class="sxs-lookup"><span data-stu-id="7111d-118">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="7111d-119">Valore booleano che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="7111d-119">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="7111d-120">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="7111d-120">The default is `false`.</span></span><br /><br /> <span data-ttu-id="7111d-121">Una risorsa Internet è locale se dispone di un indirizzo locale.</span><span class="sxs-lookup"><span data-stu-id="7111d-121">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="7111d-122">Un indirizzo locale è quello che si trova nello stesso computer, nella rete LAN o Intranet locale ed è identificato, sintatticamente, dalla mancanza di un punto (.) come negli URI "http://webserver/" e "http://localhost/".</span><span class="sxs-lookup"><span data-stu-id="7111d-122">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="7111d-123">L'impostazione di questo attributo determina se gli endpoint configurati con BasicHttpBinding usano il server proxy quando accedono alle risorse locali.</span><span class="sxs-lookup"><span data-stu-id="7111d-123">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="7111d-124">Se questo attributo è `true`, le richieste alle risorse Internet locali non usano il server proxy.</span><span class="sxs-lookup"><span data-stu-id="7111d-124">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="7111d-125">Quando l'attributo è impostato su `true`, usare il nome host invece di localhost se si desidera che i client passino da un proxy per comunicare con servizi nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="7111d-125">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="7111d-126">Se questo attributo è `false`, tutte le richieste Internet vengono effettuate tramite il server proxy.</span><span class="sxs-lookup"><span data-stu-id="7111d-126">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="7111d-127">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="7111d-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="7111d-128">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7111d-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7111d-129">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7111d-129">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="7111d-130">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="7111d-130">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="7111d-131">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="7111d-131">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="7111d-132">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="7111d-132">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="7111d-133">Valore intero che specifica la quantità massima di memoria allocata al gestore dei buffer dei messaggi che riceve i messaggi dal canale.</span><span class="sxs-lookup"><span data-stu-id="7111d-133">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="7111d-134">Il valore predefinito è 524.288 (0x80000) byte.</span><span class="sxs-lookup"><span data-stu-id="7111d-134">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="7111d-135">Il gestore dei buffer usa un pool di buffer per ridurre al minimo il costo legato all'utilizzo dei buffer.</span><span class="sxs-lookup"><span data-stu-id="7111d-135">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="7111d-136">I buffer sono necessari per elaborare i messaggi provenienti dal servizio quando arrivano dal canale.</span><span class="sxs-lookup"><span data-stu-id="7111d-136">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="7111d-137">Se la memoria nel pool di buffer non è sufficiente per elaborare il carico dei messaggi, il gestore dei buffer deve allocare altra memoria dall'heap CLR, aumentando l'overhead della procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7111d-137">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="7111d-138">Se la quantità di memoria aggiuntiva allocata in questo modo è notevolmente elevata, ciò significa che le dimensioni del pool di buffer sono troppo ridotte e che per migliorare le prestazioni è possibile allocare più risorse a tale pool mediante l'aumento del limite specificato da questo attributo.</span><span class="sxs-lookup"><span data-stu-id="7111d-138">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="7111d-139">Un valore intero che specifica la dimensione massima, in byte, di un buffer che memorizza i messaggi mentre vengono elaborati per un endpoint configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="7111d-139">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="7111d-140">L'impostazione predefinita è 65.536 byte.</span><span class="sxs-lookup"><span data-stu-id="7111d-140">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="7111d-141">Numero intero positivo che definisce la dimensione massima del messaggio, incluse le intestazioni, che può essere ricevuto in canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="7111d-141">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="7111d-142">Il mittente riceve un errore SOAP se il messaggio è troppo grande per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="7111d-142">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="7111d-143">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="7111d-143">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="7111d-144">L'impostazione predefinita è 65.536 byte.</span><span class="sxs-lookup"><span data-stu-id="7111d-144">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="7111d-145">Definisce il codificatore usato per codificare il messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="7111d-145">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="7111d-146">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="7111d-146">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7111d-147">-Text: usa un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="7111d-147">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="7111d-148">-MTOM: usare un codificatore Message Transmission Organization Mechanism 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="7111d-148">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="7111d-149">L'impostazione predefinita è Text.</span><span class="sxs-lookup"><span data-stu-id="7111d-149">The default is Text.</span></span> <span data-ttu-id="7111d-150">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="7111d-150">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="7111d-151">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="7111d-151">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="7111d-152">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="7111d-152">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="7111d-153">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="7111d-153">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7111d-154">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7111d-154">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="7111d-155">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="7111d-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="7111d-156">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7111d-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7111d-157">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7111d-157">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="7111d-158">URI che contiene l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="7111d-158">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="7111d-159">Se `useSystemWebProxy` è impostato su `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="7111d-159">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="7111d-160">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="7111d-160">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="7111d-161">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="7111d-161">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="7111d-162">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7111d-162">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7111d-163">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="7111d-163">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="7111d-164">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="7111d-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="7111d-165">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="7111d-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7111d-166">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7111d-166">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="7111d-167">Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="7111d-167">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="7111d-168">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="7111d-168">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7111d-169">-BigEndianUnicode: codifica BigEndian Unicode.</span><span class="sxs-lookup"><span data-stu-id="7111d-169">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="7111d-170">-Unicode: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="7111d-170">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="7111d-171">-UTF8: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="7111d-171">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="7111d-172">L'impostazione predefinita è UTF8.</span><span class="sxs-lookup"><span data-stu-id="7111d-172">The default is UTF8.</span></span> <span data-ttu-id="7111d-173">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="7111d-173">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="7111d-174">Valore <xref:System.ServiceModel.TransferMode> valido che specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso in una richiesta o una risposta.</span><span class="sxs-lookup"><span data-stu-id="7111d-174">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="7111d-175">Valore booleano che specifica se il proxy HTTP configurato automaticamente del sistema deve essere usato, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="7111d-175">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="7111d-176">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="7111d-176">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="7111d-177">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7111d-177">Child Elements</span></span>  
  
|<span data-ttu-id="7111d-178">Elemento</span><span class="sxs-lookup"><span data-stu-id="7111d-178">Element</span></span>|<span data-ttu-id="7111d-179">description</span><span class="sxs-lookup"><span data-stu-id="7111d-179">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7111d-180">> di sicurezza \<</span><span class="sxs-lookup"><span data-stu-id="7111d-180">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="7111d-181">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="7111d-181">Defines the security settings for the binding.</span></span> <span data-ttu-id="7111d-182">L'elemento è di tipo <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="7111d-182">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="7111d-183">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7111d-183">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="7111d-184">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="7111d-184">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="7111d-185">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="7111d-185">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7111d-186">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7111d-186">Parent Elements</span></span>  
  
|<span data-ttu-id="7111d-187">Elemento</span><span class="sxs-lookup"><span data-stu-id="7111d-187">Element</span></span>|<span data-ttu-id="7111d-188">description</span><span class="sxs-lookup"><span data-stu-id="7111d-188">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7111d-189">associazioni di \<></span><span class="sxs-lookup"><span data-stu-id="7111d-189">\<bindings></span></span>](bindings.md)|<span data-ttu-id="7111d-190">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="7111d-190">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7111d-191">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7111d-191">Remarks</span></span>  
 <span data-ttu-id="7111d-192">NetHttpBinding usa HTTP come trasporto per l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="7111d-192">The NetHttpBinding uses HTTP as the transport for sending messages.</span></span> <span data-ttu-id="7111d-193">Nel caso di un contratto duplex, verrà usato Web Sockets.</span><span class="sxs-lookup"><span data-stu-id="7111d-193">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="7111d-194">Se si usa un contratto richiesta-risposta, NetHttpBinding si comporta come BasicHttpBinding con un codificatore binario.</span><span class="sxs-lookup"><span data-stu-id="7111d-194">When used with a request-reply contract NetHttpBinding will behave like a BasicHttpBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="7111d-195">Per impostazione predefinita, la sicurezza è disattivata, ma è possibile aggiungerla impostando l'attributo mode dell'elemento figlio [\<security >](security-of-basichttpbinding.md) su un valore diverso da `None`.</span><span class="sxs-lookup"><span data-stu-id="7111d-195">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="7111d-196">Per impostazione predefinita usa una codifica dei messaggi "Text" e una codifica del testo UTF-8.</span><span class="sxs-lookup"><span data-stu-id="7111d-196">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7111d-197">Esempio</span><span class="sxs-lookup"><span data-stu-id="7111d-197">Example</span></span>  
 <span data-ttu-id="7111d-198">Nell'esempio seguente è dimostrato l'uso di <xref:System.ServiceModel.NetHttpBinding> che fornisce la comunicazione HTTP e la interoperabilità massima con servizi Web di prima e seconda generazione.</span><span class="sxs-lookup"><span data-stu-id="7111d-198">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTP communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="7111d-199">L'associazione è specificata nei file di configurazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="7111d-199">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="7111d-200">Il tipo di associazione specificato usando l'attributo `binding` dell'elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="7111d-200">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="7111d-201">Se si desidera configurare l'associazione di base e modificare alcune delle relative impostazioni, è necessario definire una configurazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="7111d-201">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="7111d-202">L'endpoint deve fare riferimento alla configurazione di associazione tramite il nome usando l'attributo `bindingConfiguration` dell'elemento `<endpoint>`, come è illustrato nel seguente codice di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="7111d-202">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
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
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="example"></a><span data-ttu-id="7111d-203">Esempio</span><span class="sxs-lookup"><span data-stu-id="7111d-203">Example</span></span>  
 <span data-ttu-id="7111d-204">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="7111d-204">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7111d-205">La funzionalità dell'esempio precedente può essere eseguita rimuovendo il bindingConfiguration dall'indirizzo endpoint e il nome dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="7111d-205">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name from the binding.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <binding hostNameComparisonMode="StrongWildcard"
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
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
 <span data-ttu-id="7111d-206">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7111d-206">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7111d-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7111d-207">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="7111d-208">Associazioni</span><span class="sxs-lookup"><span data-stu-id="7111d-208">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7111d-209">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="7111d-209">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7111d-210">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="7111d-210">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7111d-211">Binding \<></span><span class="sxs-lookup"><span data-stu-id="7111d-211">\<binding></span></span>](bindings.md)
