---
title: <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: b0d81ca0-87c5-4090-8baa-e390fd3656d2
ms.openlocfilehash: 815ee3993a2f2b2819210b225c0cb0b3d3fd8b87
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84201019"
---
# \<netHttpBinding>
<span data-ttu-id="96a1d-101">Rappresenta un'associazione che può essere utilizzata da un servizio Windows Communication Foundation (WCF) per configurare ed esporre endpoint in grado di comunicare tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="96a1d-101">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTP.</span></span> <span data-ttu-id="96a1d-102">Nel caso di un contratto duplex, verrà usato Web Sockets. In caso contrario, verrà usato HTTP.</span><span class="sxs-lookup"><span data-stu-id="96a1d-102">When used with a duplex contract, Web Sockets will be used, otherwise HTTP will be used.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="96a1d-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96a1d-103">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="96a1d-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="96a1d-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96a1d-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="96a1d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="96a1d-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="96a1d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96a1d-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="96a1d-107">Attributes</span></span>  
  
|<span data-ttu-id="96a1d-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="96a1d-108">Attribute</span></span>|<span data-ttu-id="96a1d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96a1d-109">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="96a1d-110">Valore booleano che indica se il client accetta cookie e li propaga alle richieste future.</span><span class="sxs-lookup"><span data-stu-id="96a1d-110">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="96a1d-111">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="96a1d-111">The default is `false`.</span></span><br /><br /> <span data-ttu-id="96a1d-112">È possibile usare questa proprietà quando si interagisce con servizi Web ASMX che usano cookie.</span><span class="sxs-lookup"><span data-stu-id="96a1d-112">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="96a1d-113">In questo modo i cookie restituiti dal server vengono copiati automaticamente in tutte le richieste client future per quel servizio.</span><span class="sxs-lookup"><span data-stu-id="96a1d-113">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="96a1d-114">Valore booleano che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="96a1d-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="96a1d-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="96a1d-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="96a1d-116">Una risorsa Internet è locale se dispone di un indirizzo locale.</span><span class="sxs-lookup"><span data-stu-id="96a1d-116">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="96a1d-117">Un indirizzo locale è quello che si trova nello stesso computer, nella rete LAN o Intranet locale ed è identificato, sintatticamente, dalla mancanza di un punto (.) come negli URI `http://webserver/` e `http://localhost/` .</span><span class="sxs-lookup"><span data-stu-id="96a1d-117">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs `http://webserver/` and `http://localhost/`.</span></span><br /><br /> <span data-ttu-id="96a1d-118">L'impostazione di questo attributo determina se gli endpoint configurati con BasicHttpBinding usano il server proxy quando accedono alle risorse locali.</span><span class="sxs-lookup"><span data-stu-id="96a1d-118">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="96a1d-119">Se questo attributo è `true`, le richieste alle risorse Internet locali non usano il server proxy.</span><span class="sxs-lookup"><span data-stu-id="96a1d-119">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="96a1d-120">Quando l'attributo è impostato su `true`, usare il nome host invece di localhost se si desidera che i client passino da un proxy per comunicare con servizi nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="96a1d-120">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="96a1d-121">Se questo attributo è `false`, tutte le richieste Internet vengono effettuate tramite il server proxy.</span><span class="sxs-lookup"><span data-stu-id="96a1d-121">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="96a1d-122">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="96a1d-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="96a1d-123">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="96a1d-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="96a1d-124">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="96a1d-124">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="96a1d-125">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="96a1d-125">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="96a1d-126">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="96a1d-126">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="96a1d-127">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="96a1d-127">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="96a1d-128">Valore intero che specifica la quantità massima di memoria allocata al gestore dei buffer dei messaggi che riceve i messaggi dal canale.</span><span class="sxs-lookup"><span data-stu-id="96a1d-128">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="96a1d-129">Il valore predefinito è 524.288 (0x80000) byte.</span><span class="sxs-lookup"><span data-stu-id="96a1d-129">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="96a1d-130">Il gestore dei buffer usa un pool di buffer per ridurre al minimo il costo legato all'utilizzo dei buffer.</span><span class="sxs-lookup"><span data-stu-id="96a1d-130">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="96a1d-131">I buffer sono necessari per elaborare i messaggi provenienti dal servizio quando arrivano dal canale.</span><span class="sxs-lookup"><span data-stu-id="96a1d-131">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="96a1d-132">Se la memoria nel pool di buffer non è sufficiente per elaborare il carico dei messaggi, il gestore dei buffer deve allocare altra memoria dall'heap CLR, aumentando l'overhead della procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="96a1d-132">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="96a1d-133">Se la quantità di memoria aggiuntiva allocata in questo modo è notevolmente elevata, ciò significa che le dimensioni del pool di buffer sono troppo ridotte e che per migliorare le prestazioni è possibile allocare più risorse a tale pool mediante l'aumento del limite specificato da questo attributo.</span><span class="sxs-lookup"><span data-stu-id="96a1d-133">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="96a1d-134">Un valore intero che specifica la dimensione massima, in byte, di un buffer che memorizza i messaggi mentre vengono elaborati per un endpoint configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="96a1d-134">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="96a1d-135">L'impostazione predefinita è 65.536 byte.</span><span class="sxs-lookup"><span data-stu-id="96a1d-135">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="96a1d-136">Numero intero positivo che definisce la dimensione massima del messaggio, incluse le intestazioni, che può essere ricevuto in canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="96a1d-136">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="96a1d-137">Il mittente riceve un errore SOAP se il messaggio è troppo grande per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="96a1d-137">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="96a1d-138">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="96a1d-138">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="96a1d-139">Il valore predefinito è 65.536 byte.</span><span class="sxs-lookup"><span data-stu-id="96a1d-139">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="96a1d-140">Definisce il codificatore usato per codificare il messaggio SOAP.</span><span class="sxs-lookup"><span data-stu-id="96a1d-140">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="96a1d-141">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="96a1d-141">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="96a1d-142">-Text: usa un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="96a1d-142">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="96a1d-143">-MTOM: usare un codificatore Message Transmission Organization Mechanism 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="96a1d-143">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="96a1d-144">L'impostazione predefinita è Text.</span><span class="sxs-lookup"><span data-stu-id="96a1d-144">The default is Text.</span></span> <span data-ttu-id="96a1d-145">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="96a1d-145">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="96a1d-146">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="96a1d-146">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="96a1d-147">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="96a1d-147">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="96a1d-148">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="96a1d-148">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="96a1d-149">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="96a1d-149">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="96a1d-150">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="96a1d-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="96a1d-151">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="96a1d-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="96a1d-152">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="96a1d-152">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="96a1d-153">URI che contiene l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="96a1d-153">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="96a1d-154">Se `useSystemWebProxy` è impostato su `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="96a1d-154">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="96a1d-155">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="96a1d-155">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="96a1d-156">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="96a1d-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="96a1d-157">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="96a1d-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="96a1d-158">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="96a1d-158">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="96a1d-159">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="96a1d-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="96a1d-160">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="96a1d-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="96a1d-161">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="96a1d-161">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="96a1d-162">Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="96a1d-162">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="96a1d-163">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="96a1d-163">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="96a1d-164">-BigEndianUnicode: codifica BigEndian Unicode.</span><span class="sxs-lookup"><span data-stu-id="96a1d-164">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="96a1d-165">-Unicode: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="96a1d-165">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="96a1d-166">-UTF8: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="96a1d-166">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="96a1d-167">Il valore predefinito è UTF8.</span><span class="sxs-lookup"><span data-stu-id="96a1d-167">The default is UTF8.</span></span> <span data-ttu-id="96a1d-168">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="96a1d-168">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="96a1d-169">Valore <xref:System.ServiceModel.TransferMode> valido che specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso in una richiesta o una risposta.</span><span class="sxs-lookup"><span data-stu-id="96a1d-169">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="96a1d-170">Valore booleano che specifica se il proxy HTTP configurato automaticamente del sistema deve essere usato, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="96a1d-170">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="96a1d-171">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="96a1d-171">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="96a1d-172">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="96a1d-172">Child Elements</span></span>  
  
|<span data-ttu-id="96a1d-173">Elemento</span><span class="sxs-lookup"><span data-stu-id="96a1d-173">Element</span></span>|<span data-ttu-id="96a1d-174">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96a1d-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|<span data-ttu-id="96a1d-175">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="96a1d-175">Defines the security settings for the binding.</span></span> <span data-ttu-id="96a1d-176">L'elemento è di tipo <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="96a1d-176">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="96a1d-177">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="96a1d-177">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="96a1d-178">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="96a1d-178">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="96a1d-179">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="96a1d-179">Parent Elements</span></span>  
  
|<span data-ttu-id="96a1d-180">Elemento</span><span class="sxs-lookup"><span data-stu-id="96a1d-180">Element</span></span>|<span data-ttu-id="96a1d-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96a1d-181">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="96a1d-182">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="96a1d-182">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96a1d-183">Commenti</span><span class="sxs-lookup"><span data-stu-id="96a1d-183">Remarks</span></span>  
 <span data-ttu-id="96a1d-184">NetHttpBinding usa HTTP come trasporto per l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="96a1d-184">The NetHttpBinding uses HTTP as the transport for sending messages.</span></span> <span data-ttu-id="96a1d-185">Nel caso di un contratto duplex, verrà usato Web Sockets.</span><span class="sxs-lookup"><span data-stu-id="96a1d-185">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="96a1d-186">Se si usa un contratto richiesta-risposta, NetHttpBinding si comporta come BasicHttpBinding con un codificatore binario.</span><span class="sxs-lookup"><span data-stu-id="96a1d-186">When used with a request-reply contract NetHttpBinding will behave like a BasicHttpBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="96a1d-187">Per impostazione predefinita, la sicurezza è disattivata, ma è possibile aggiungerla impostando l'attributo mode dell' [\<security>](security-of-basichttpbinding.md) elemento figlio su un valore diverso da `None` .</span><span class="sxs-lookup"><span data-stu-id="96a1d-187">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="96a1d-188">Per impostazione predefinita usa una codifica dei messaggi "Text" e una codifica del testo UTF-8.</span><span class="sxs-lookup"><span data-stu-id="96a1d-188">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96a1d-189">Esempio</span><span class="sxs-lookup"><span data-stu-id="96a1d-189">Example</span></span>  
 <span data-ttu-id="96a1d-190">Nell'esempio seguente è dimostrato l'uso di <xref:System.ServiceModel.NetHttpBinding> che fornisce la comunicazione HTTP e la interoperabilità massima con servizi Web di prima e seconda generazione.</span><span class="sxs-lookup"><span data-stu-id="96a1d-190">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTP communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="96a1d-191">L'associazione è specificata nei file di configurazione per il client e il servizio.</span><span class="sxs-lookup"><span data-stu-id="96a1d-191">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="96a1d-192">Il tipo di associazione specificato usando l'attributo `binding` dell'elemento `<endpoint>`.</span><span class="sxs-lookup"><span data-stu-id="96a1d-192">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="96a1d-193">Se si desidera configurare l'associazione di base e modificare alcune delle relative impostazioni, è necessario definire una configurazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="96a1d-193">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="96a1d-194">L'endpoint deve fare riferimento alla configurazione di associazione tramite il nome usando l'attributo `bindingConfiguration` dell'elemento `<endpoint>`, come è illustrato nel seguente codice di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="96a1d-194">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="96a1d-195">Esempio</span><span class="sxs-lookup"><span data-stu-id="96a1d-195">Example</span></span>  
 <span data-ttu-id="96a1d-196">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="96a1d-196">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="96a1d-197">La funzionalità dell'esempio precedente può essere eseguita rimuovendo il bindingConfiguration dall'indirizzo endpoint e il nome dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="96a1d-197">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name from the binding.</span></span>  
  
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
  
 <span data-ttu-id="96a1d-198">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="96a1d-198">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a1d-199">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="96a1d-199">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="96a1d-200">Binding</span><span class="sxs-lookup"><span data-stu-id="96a1d-200">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="96a1d-201">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="96a1d-201">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="96a1d-202">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="96a1d-202">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
