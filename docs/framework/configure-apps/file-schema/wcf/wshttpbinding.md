---
title: <wsHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: a71ad2a2279eabbcf917df58d7bedec0e728f9e5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140387"
---
# \<wsHttpBinding>
<span data-ttu-id="5ddab-101">Definisce un'associazione protetta, affidabile, interoperabile adatta per contratti di servizio non duplex.</span><span class="sxs-lookup"><span data-stu-id="5ddab-101">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="5ddab-102">L'associazione implementa le specifiche seguenti: WS-ReliableMessaging per l'affidabilità e WS-Security per la sicurezza e l'autenticazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="5ddab-102">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="5ddab-103">Il trasporto è HTTP e la codifica dei messaggi è Text/XML.</span><span class="sxs-lookup"><span data-stu-id="5ddab-103">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="5ddab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5ddab-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ddab-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5ddab-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5ddab-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5ddab-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ddab-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="5ddab-107">Attributes</span></span>  
  
|<span data-ttu-id="5ddab-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="5ddab-108">Attribute</span></span>|<span data-ttu-id="5ddab-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ddab-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ddab-110">allowCookies</span><span class="sxs-lookup"><span data-stu-id="5ddab-110">allowCookies</span></span>|<span data-ttu-id="5ddab-111">Valore booleano che indica se il client accetta cookie e li propaga alle richieste future.</span><span class="sxs-lookup"><span data-stu-id="5ddab-111">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="5ddab-112">Il valore predefinito è false.</span><span class="sxs-lookup"><span data-stu-id="5ddab-112">The default is false.</span></span><br /><br /> <span data-ttu-id="5ddab-113">È possibile usare questa proprietà quando si interagisce con servizi Web ASMX che usano cookie.</span><span class="sxs-lookup"><span data-stu-id="5ddab-113">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="5ddab-114">In questo modo i cookie restituiti dal server vengono copiati automaticamente in tutte le richieste client future per quel servizio.</span><span class="sxs-lookup"><span data-stu-id="5ddab-114">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="5ddab-115">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="5ddab-115">bypassProxyOnLocal</span></span>|<span data-ttu-id="5ddab-116">Valore booleano che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="5ddab-116">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="5ddab-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="5ddab-117">The default is `false`.</span></span>|  
|<span data-ttu-id="5ddab-118">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="5ddab-118">closeTimeout</span></span>|<span data-ttu-id="5ddab-119">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="5ddab-119">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="5ddab-120">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5ddab-120">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5ddab-121">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5ddab-121">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="5ddab-122">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="5ddab-122">hostnameComparisonMode</span></span>|<span data-ttu-id="5ddab-123">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="5ddab-123">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="5ddab-124">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="5ddab-124">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="5ddab-125">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="5ddab-125">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="5ddab-126">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="5ddab-126">maxBufferPoolSize</span></span>|<span data-ttu-id="5ddab-127">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="5ddab-127">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="5ddab-128">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="5ddab-128">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="5ddab-129">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="5ddab-129">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="5ddab-130">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="5ddab-130">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="5ddab-131">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="5ddab-131">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="5ddab-132">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="5ddab-132">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="5ddab-133">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="5ddab-133">maxReceivedMessageSize</span></span>|<span data-ttu-id="5ddab-134">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="5ddab-134">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="5ddab-135">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="5ddab-135">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="5ddab-136">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="5ddab-136">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="5ddab-137">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="5ddab-137">The default is 65536.</span></span>|  
|<span data-ttu-id="5ddab-138">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="5ddab-138">messageEncoding</span></span>|<span data-ttu-id="5ddab-139">Definisce il codificatore usato per codificare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="5ddab-139">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="5ddab-140">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ddab-140">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5ddab-141">-Text: usa un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="5ddab-141">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="5ddab-142">-MTOM: usare un codificatore Message Transmission Organization Mechanism 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="5ddab-142">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="5ddab-143">-Il valore predefinito è testo.</span><span class="sxs-lookup"><span data-stu-id="5ddab-143">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="5ddab-144">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="5ddab-144">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="5ddab-145">name</span><span class="sxs-lookup"><span data-stu-id="5ddab-145">name</span></span>|<span data-ttu-id="5ddab-146">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="5ddab-146">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="5ddab-147">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="5ddab-147">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="5ddab-148">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="5ddab-148">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5ddab-149">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="5ddab-149">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="5ddab-150">openTimeout</span><span class="sxs-lookup"><span data-stu-id="5ddab-150">openTimeout</span></span>|<span data-ttu-id="5ddab-151">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="5ddab-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="5ddab-152">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5ddab-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5ddab-153">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5ddab-153">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="5ddab-154">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="5ddab-154">proxyAddress</span></span>|<span data-ttu-id="5ddab-155">URI che specifica l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="5ddab-155">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="5ddab-156">Se `useSystemWebProxy` è `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="5ddab-156">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="5ddab-157">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="5ddab-157">The default is `null`.</span></span>|  
|<span data-ttu-id="5ddab-158">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="5ddab-158">receiveTimeout</span></span>|<span data-ttu-id="5ddab-159">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="5ddab-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="5ddab-160">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5ddab-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5ddab-161">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5ddab-161">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="5ddab-162">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="5ddab-162">sendTimeout</span></span>|<span data-ttu-id="5ddab-163">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="5ddab-163">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="5ddab-164">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="5ddab-164">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5ddab-165">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="5ddab-165">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="5ddab-166">textEncoding</span><span class="sxs-lookup"><span data-stu-id="5ddab-166">textEncoding</span></span>|<span data-ttu-id="5ddab-167">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="5ddab-167">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="5ddab-168">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ddab-168">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5ddab-169">-UnicodeFffeTextEncoding: codifica BigEndian Unicode.</span><span class="sxs-lookup"><span data-stu-id="5ddab-169">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="5ddab-170">-Utf16TextEncoding: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="5ddab-170">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="5ddab-171">-Utf8TextEncoding: codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="5ddab-171">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="5ddab-172">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="5ddab-172">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="5ddab-173">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="5ddab-173">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="5ddab-174">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="5ddab-174">transactionFlow</span></span>|<span data-ttu-id="5ddab-175">Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="5ddab-175">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="5ddab-176">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="5ddab-176">The default is `false`.</span></span>|  
|<span data-ttu-id="5ddab-177">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="5ddab-177">useDefaultWebProxy</span></span>|<span data-ttu-id="5ddab-178">Valore booleano che specifica se viene usato il proxy HTTP di sistema configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5ddab-178">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="5ddab-179">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="5ddab-179">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ddab-180">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5ddab-180">Child Elements</span></span>  
  
|<span data-ttu-id="5ddab-181">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ddab-181">Element</span></span>|<span data-ttu-id="5ddab-182">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ddab-182">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="5ddab-183">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="5ddab-183">Defines the security settings for the binding.</span></span> <span data-ttu-id="5ddab-184">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="5ddab-184">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="5ddab-185">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="5ddab-185">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5ddab-186">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="5ddab-186">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="5ddab-187">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="5ddab-187">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ddab-188">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5ddab-188">Parent Elements</span></span>  
  
|<span data-ttu-id="5ddab-189">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ddab-189">Element</span></span>|<span data-ttu-id="5ddab-190">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ddab-190">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="5ddab-191">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="5ddab-191">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ddab-192">Commenti</span><span class="sxs-lookup"><span data-stu-id="5ddab-192">Remarks</span></span>  
 <span data-ttu-id="5ddab-193">`WSHttpBinding` è simile a `BasicHttpBinding` ma fornisce più funzionalità del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="5ddab-193">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="5ddab-194">Usa il trasporto HTTP e fornisce sicurezza dei messaggi, in modo analogo a BasicHttpBinding, ma offre inoltre funzionalità per transazioni, messaggistica affidabile e WS-Addressing, attivate per impostazione predefinita o disponibili tramite l'impostazione di un singolo controllo.</span><span class="sxs-lookup"><span data-stu-id="5ddab-194">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ddab-195">Esempio</span><span class="sxs-lookup"><span data-stu-id="5ddab-195">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ddab-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ddab-196">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement>
- [<span data-ttu-id="5ddab-197">Binding</span><span class="sxs-lookup"><span data-stu-id="5ddab-197">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5ddab-198">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="5ddab-198">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5ddab-199">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="5ddab-199">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
