---
title: <wsHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: a71ad2a2279eabbcf917df58d7bedec0e728f9e5
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140387"
---
# <a name="wshttpbinding"></a><span data-ttu-id="debf6-101">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="debf6-101">\<wsHttpBinding></span></span>
<span data-ttu-id="debf6-102">Definisce un'associazione protetta, affidabile, interoperabile adatta per contratti di servizio non duplex.</span><span class="sxs-lookup"><span data-stu-id="debf6-102">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="debf6-103">L'associazione implementa le specifiche seguenti: WS-ReliableMessaging per l'affidabilità e WS-Security per la sicurezza e l'autenticazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="debf6-103">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="debf6-104">Il trasporto è HTTP e la codifica dei messaggi è Text/XML.</span><span class="sxs-lookup"><span data-stu-id="debf6-104">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
<span data-ttu-id="debf6-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="debf6-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="debf6-106">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="debf6-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="debf6-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="debf6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="debf6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<wsHttpBinding>**</span><span class="sxs-lookup"><span data-stu-id="debf6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="debf6-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="debf6-109">Syntax</span></span>  
  
```xml  
<wsHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="Message/None/Transport/TransportWithCredential">
      <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 realm="string" />
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="debf6-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="debf6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="debf6-111">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="debf6-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="debf6-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="debf6-112">Attributes</span></span>  
  
|<span data-ttu-id="debf6-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="debf6-113">Attribute</span></span>|<span data-ttu-id="debf6-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="debf6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="debf6-115">allowCookies</span><span class="sxs-lookup"><span data-stu-id="debf6-115">allowCookies</span></span>|<span data-ttu-id="debf6-116">Valore booleano che indica se il client accetta cookie e li propaga alle richieste future.</span><span class="sxs-lookup"><span data-stu-id="debf6-116">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="debf6-117">Il valore predefinito è false.</span><span class="sxs-lookup"><span data-stu-id="debf6-117">The default is false.</span></span><br /><br /> <span data-ttu-id="debf6-118">È possibile usare questa proprietà quando si interagisce con servizi Web ASMX che usano cookie.</span><span class="sxs-lookup"><span data-stu-id="debf6-118">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="debf6-119">In questo modo i cookie restituiti dal server vengono copiati automaticamente in tutte le richieste client future per quel servizio.</span><span class="sxs-lookup"><span data-stu-id="debf6-119">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="debf6-120">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="debf6-120">bypassProxyOnLocal</span></span>|<span data-ttu-id="debf6-121">Valore booleano che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="debf6-121">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="debf6-122">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="debf6-122">The default is `false`.</span></span>|  
|<span data-ttu-id="debf6-123">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="debf6-123">closeTimeout</span></span>|<span data-ttu-id="debf6-124">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="debf6-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="debf6-125">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="debf6-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="debf6-126">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="debf6-126">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="debf6-127">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="debf6-127">hostnameComparisonMode</span></span>|<span data-ttu-id="debf6-128">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="debf6-128">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="debf6-129">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="debf6-129">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="debf6-130">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="debf6-130">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="debf6-131">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="debf6-131">maxBufferPoolSize</span></span>|<span data-ttu-id="debf6-132">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="debf6-132">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="debf6-133">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="debf6-133">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="debf6-134">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="debf6-134">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="debf6-135">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="debf6-135">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="debf6-136">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="debf6-136">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="debf6-137">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="debf6-137">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="debf6-138">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="debf6-138">maxReceivedMessageSize</span></span>|<span data-ttu-id="debf6-139">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="debf6-139">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="debf6-140">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="debf6-140">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="debf6-141">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="debf6-141">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="debf6-142">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="debf6-142">The default is 65536.</span></span>|  
|<span data-ttu-id="debf6-143">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="debf6-143">messageEncoding</span></span>|<span data-ttu-id="debf6-144">Definisce il codificatore usato per codificare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="debf6-144">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="debf6-145">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="debf6-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="debf6-146">-   Text: Use a text message encoder.</span><span class="sxs-lookup"><span data-stu-id="debf6-146">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="debf6-147">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span><span class="sxs-lookup"><span data-stu-id="debf6-147">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="debf6-148">-   The default is Text.</span><span class="sxs-lookup"><span data-stu-id="debf6-148">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="debf6-149">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="debf6-149">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="debf6-150">name</span><span class="sxs-lookup"><span data-stu-id="debf6-150">name</span></span>|<span data-ttu-id="debf6-151">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="debf6-151">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="debf6-152">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="debf6-152">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="debf6-153">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="debf6-153">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="debf6-154">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="debf6-154">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="debf6-155">openTimeout</span><span class="sxs-lookup"><span data-stu-id="debf6-155">openTimeout</span></span>|<span data-ttu-id="debf6-156">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="debf6-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="debf6-157">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="debf6-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="debf6-158">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="debf6-158">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="debf6-159">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="debf6-159">proxyAddress</span></span>|<span data-ttu-id="debf6-160">URI che specifica l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="debf6-160">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="debf6-161">Se `useSystemWebProxy` è `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="debf6-161">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="debf6-162">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="debf6-162">The default is `null`.</span></span>|  
|<span data-ttu-id="debf6-163">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="debf6-163">receiveTimeout</span></span>|<span data-ttu-id="debf6-164">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="debf6-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="debf6-165">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="debf6-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="debf6-166">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="debf6-166">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="debf6-167">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="debf6-167">sendTimeout</span></span>|<span data-ttu-id="debf6-168">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="debf6-168">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="debf6-169">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="debf6-169">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="debf6-170">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="debf6-170">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="debf6-171">textEncoding</span><span class="sxs-lookup"><span data-stu-id="debf6-171">textEncoding</span></span>|<span data-ttu-id="debf6-172">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="debf6-172">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="debf6-173">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="debf6-173">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="debf6-174">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span><span class="sxs-lookup"><span data-stu-id="debf6-174">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="debf6-175">-   Utf16TextEncoding: 16-bit encoding.</span><span class="sxs-lookup"><span data-stu-id="debf6-175">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="debf6-176">-   Utf8TextEncoding: 8-bit encoding.</span><span class="sxs-lookup"><span data-stu-id="debf6-176">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="debf6-177">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="debf6-177">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="debf6-178">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="debf6-178">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="debf6-179">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="debf6-179">transactionFlow</span></span>|<span data-ttu-id="debf6-180">Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="debf6-180">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="debf6-181">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="debf6-181">The default is `false`.</span></span>|  
|<span data-ttu-id="debf6-182">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="debf6-182">useDefaultWebProxy</span></span>|<span data-ttu-id="debf6-183">Valore booleano che specifica se viene usato il proxy HTTP di sistema configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="debf6-183">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="debf6-184">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="debf6-184">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="debf6-185">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="debf6-185">Child Elements</span></span>  
  
|<span data-ttu-id="debf6-186">Elemento</span><span class="sxs-lookup"><span data-stu-id="debf6-186">Element</span></span>|<span data-ttu-id="debf6-187">Descrizione</span><span class="sxs-lookup"><span data-stu-id="debf6-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="debf6-188">\<security></span><span class="sxs-lookup"><span data-stu-id="debf6-188">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="debf6-189">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="debf6-189">Defines the security settings for the binding.</span></span> <span data-ttu-id="debf6-190">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="debf6-190">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="debf6-191">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="debf6-191">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="debf6-192">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="debf6-192">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="debf6-193">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="debf6-193">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="debf6-194">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="debf6-194">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="debf6-195">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="debf6-195">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="debf6-196">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="debf6-196">Parent Elements</span></span>  
  
|<span data-ttu-id="debf6-197">Elemento</span><span class="sxs-lookup"><span data-stu-id="debf6-197">Element</span></span>|<span data-ttu-id="debf6-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="debf6-198">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="debf6-199">\<bindings></span><span class="sxs-lookup"><span data-stu-id="debf6-199">\<bindings></span></span>](bindings.md)|<span data-ttu-id="debf6-200">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="debf6-200">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="debf6-201">Note</span><span class="sxs-lookup"><span data-stu-id="debf6-201">Remarks</span></span>  
 <span data-ttu-id="debf6-202">`WSHttpBinding` è simile a `BasicHttpBinding` ma fornisce più funzionalità del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="debf6-202">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="debf6-203">Usa il trasporto HTTP e fornisce sicurezza dei messaggi, in modo analogo a BasicHttpBinding, ma offre inoltre funzionalità per transazioni, messaggistica affidabile e WS-Addressing, attivate per impostazione predefinita o disponibili tramite l'impostazione di un singolo controllo.</span><span class="sxs-lookup"><span data-stu-id="debf6-203">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="debf6-204">Esempio</span><span class="sxs-lookup"><span data-stu-id="debf6-204">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="Transport">
            <transport clientCredentialType="Digest"
                       proxyCredentialType="None"
                       realm="someRealm" />
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     defaultProtectionLevel="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="debf6-205">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="debf6-205">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement>
- [<span data-ttu-id="debf6-206">Associazioni</span><span class="sxs-lookup"><span data-stu-id="debf6-206">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="debf6-207">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="debf6-207">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="debf6-208">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="debf6-208">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="debf6-209">\<binding></span><span class="sxs-lookup"><span data-stu-id="debf6-209">\<binding></span></span>](bindings.md)
