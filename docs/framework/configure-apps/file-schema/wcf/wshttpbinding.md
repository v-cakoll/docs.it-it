---
title: <wsHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: 83cad6af4d00f04cd53e5e4b064fe768647956d1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277758"
---
# <a name="wshttpbinding"></a><span data-ttu-id="29648-101">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="29648-101">\<wsHttpBinding></span></span>
<span data-ttu-id="29648-102">Definisce un'associazione protetta, affidabile, interoperabile adatta per contratti di servizio non duplex.</span><span class="sxs-lookup"><span data-stu-id="29648-102">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="29648-103">L'associazione implementa le specifiche seguenti: WS-ReliableMessaging per affidabilità e WS-Security per l'autenticazione e sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="29648-103">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="29648-104">Il trasporto è HTTP e la codifica dei messaggi è Text/XML.</span><span class="sxs-lookup"><span data-stu-id="29648-104">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
 <span data-ttu-id="29648-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="29648-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="29648-106">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="29648-106">\<bindings></span></span>  
<span data-ttu-id="29648-107">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="29648-107">\<wsHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29648-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29648-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29648-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="29648-109">Attributes and Elements</span></span>  
 <span data-ttu-id="29648-110">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="29648-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29648-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="29648-111">Attributes</span></span>  
  
|<span data-ttu-id="29648-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="29648-112">Attribute</span></span>|<span data-ttu-id="29648-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29648-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29648-114">allowCookies</span><span class="sxs-lookup"><span data-stu-id="29648-114">allowCookies</span></span>|<span data-ttu-id="29648-115">Valore booleano che indica se il client accetta cookie e li propaga alle richieste future.</span><span class="sxs-lookup"><span data-stu-id="29648-115">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="29648-116">Il valore predefinito è false.</span><span class="sxs-lookup"><span data-stu-id="29648-116">The default is false.</span></span><br /><br /> <span data-ttu-id="29648-117">È possibile usare questa proprietà quando si interagisce con servizi Web ASMX che usano cookie.</span><span class="sxs-lookup"><span data-stu-id="29648-117">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="29648-118">In questo modo i cookie restituiti dal server vengono copiati automaticamente in tutte le richieste client future per quel servizio.</span><span class="sxs-lookup"><span data-stu-id="29648-118">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="29648-119">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="29648-119">bypassProxyOnLocal</span></span>|<span data-ttu-id="29648-120">Valore booleano che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="29648-120">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="29648-121">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="29648-121">The default is `false`.</span></span>|  
|<span data-ttu-id="29648-122">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="29648-122">closeTimeout</span></span>|<span data-ttu-id="29648-123">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="29648-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="29648-124">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="29648-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="29648-125">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="29648-125">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="29648-126">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="29648-126">hostnameComparisonMode</span></span>|<span data-ttu-id="29648-127">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="29648-127">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="29648-128">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="29648-128">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="29648-129">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="29648-129">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="29648-130">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="29648-130">maxBufferPoolSize</span></span>|<span data-ttu-id="29648-131">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="29648-131">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="29648-132">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="29648-132">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="29648-133">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="29648-133">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="29648-134">La creazione e l'eliminazione dei buffer a ogni relativo uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="29648-134">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="29648-135">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="29648-135">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="29648-136">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione dei buffer.</span><span class="sxs-lookup"><span data-stu-id="29648-136">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="29648-137">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="29648-137">maxReceivedMessageSize</span></span>|<span data-ttu-id="29648-138">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="29648-138">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="29648-139">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="29648-139">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="29648-140">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="29648-140">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="29648-141">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="29648-141">The default is 65536.</span></span>|  
|<span data-ttu-id="29648-142">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="29648-142">messageEncoding</span></span>|<span data-ttu-id="29648-143">Definisce il codificatore usato per codificare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="29648-143">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="29648-144">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="29648-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="29648-145">-Text: Usare un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="29648-145">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="29648-146">-Mtom: Usa un codificatore Message Transmission organizzazione Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="29648-146">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="29648-147">-Il valore predefinito è testo.</span><span class="sxs-lookup"><span data-stu-id="29648-147">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="29648-148">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="29648-148">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="29648-149">name</span><span class="sxs-lookup"><span data-stu-id="29648-149">name</span></span>|<span data-ttu-id="29648-150">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="29648-150">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="29648-151">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="29648-151">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="29648-152">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="29648-152">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="29648-153">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="29648-153">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="29648-154">openTimeout</span><span class="sxs-lookup"><span data-stu-id="29648-154">openTimeout</span></span>|<span data-ttu-id="29648-155">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="29648-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="29648-156">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="29648-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="29648-157">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="29648-157">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="29648-158">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="29648-158">proxyAddress</span></span>|<span data-ttu-id="29648-159">URI che specifica l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="29648-159">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="29648-160">Se `useSystemWebProxy` è `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="29648-160">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="29648-161">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="29648-161">The default is `null`.</span></span>|  
|<span data-ttu-id="29648-162">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="29648-162">receiveTimeout</span></span>|<span data-ttu-id="29648-163">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="29648-163">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="29648-164">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="29648-164">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="29648-165">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="29648-165">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="29648-166">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="29648-166">sendTimeout</span></span>|<span data-ttu-id="29648-167">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="29648-167">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="29648-168">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="29648-168">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="29648-169">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="29648-169">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="29648-170">textEncoding</span><span class="sxs-lookup"><span data-stu-id="29648-170">textEncoding</span></span>|<span data-ttu-id="29648-171">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="29648-171">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="29648-172">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="29648-172">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="29648-173">-UnicodeFffeTextEncoding: Codifica Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="29648-173">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="29648-174">-   Utf16TextEncoding: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="29648-174">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="29648-175">-   Utf8TextEncoding: codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="29648-175">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="29648-176">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="29648-176">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="29648-177">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="29648-177">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="29648-178">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="29648-178">transactionFlow</span></span>|<span data-ttu-id="29648-179">Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="29648-179">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="29648-180">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="29648-180">The default is `false`.</span></span>|  
|<span data-ttu-id="29648-181">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="29648-181">useDefaultWebProxy</span></span>|<span data-ttu-id="29648-182">Valore booleano che specifica se viene usato il proxy HTTP di sistema configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="29648-182">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="29648-183">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="29648-183">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29648-184">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="29648-184">Child Elements</span></span>  
  
|<span data-ttu-id="29648-185">Elemento</span><span class="sxs-lookup"><span data-stu-id="29648-185">Element</span></span>|<span data-ttu-id="29648-186">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29648-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29648-187">\<security></span><span class="sxs-lookup"><span data-stu-id="29648-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="29648-188">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="29648-188">Defines the security settings for the binding.</span></span> <span data-ttu-id="29648-189">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="29648-189">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="29648-190">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="29648-190">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="29648-191">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="29648-191">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="29648-192">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="29648-192">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="29648-193">reliableSession</span><span class="sxs-lookup"><span data-stu-id="29648-193">reliableSession</span></span>](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="29648-194">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="29648-194">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="29648-195">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="29648-195">Parent Elements</span></span>  
  
|<span data-ttu-id="29648-196">Elemento</span><span class="sxs-lookup"><span data-stu-id="29648-196">Element</span></span>|<span data-ttu-id="29648-197">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29648-197">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29648-198">\<bindings></span><span class="sxs-lookup"><span data-stu-id="29648-198">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="29648-199">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="29648-199">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29648-200">Note</span><span class="sxs-lookup"><span data-stu-id="29648-200">Remarks</span></span>  
 <span data-ttu-id="29648-201">`WSHttpBinding` è simile a `BasicHttpBinding` ma fornisce più funzionalità del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="29648-201">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="29648-202">Usa il trasporto HTTP e fornisce sicurezza dei messaggi, in modo analogo a BasicHttpBinding, ma offre inoltre funzionalità per transazioni, messaggistica affidabile e WS-Addressing, attivate per impostazione predefinita o disponibili tramite l'impostazione di un singolo controllo.</span><span class="sxs-lookup"><span data-stu-id="29648-202">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29648-203">Esempio</span><span class="sxs-lookup"><span data-stu-id="29648-203">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="29648-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29648-204">See also</span></span>
- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement>
- [<span data-ttu-id="29648-205">Associazioni</span><span class="sxs-lookup"><span data-stu-id="29648-205">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="29648-206">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="29648-206">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="29648-207">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="29648-207">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="29648-208">\<binding></span><span class="sxs-lookup"><span data-stu-id="29648-208">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
