---
title: '&lt;ws2007HttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8586ecc9-bdaa-44d6-8d4d-7038e4ea1741
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c28b5f0304106fb2aa3e95e68ddb798b5a1fe0b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltws2007httpbindinggt"></a><span data-ttu-id="498a8-102">&lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="498a8-102">&lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="498a8-103">Definisce un'associazione interoperativa che fornisce il supporto per le versioni corrette degli elementi di associazione <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession> e <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A>.</span><span class="sxs-lookup"><span data-stu-id="498a8-103">Defines an interoperable binding that provides support for the correct versions of the <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession>, and <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> binding elements.</span></span>  
  
 <span data-ttu-id="498a8-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="498a8-104">\<system.serviceModel></span></span>  
<span data-ttu-id="498a8-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="498a8-105">\<bindings></span></span>  
<span data-ttu-id="498a8-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="498a8-106">\<ws2007HttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="498a8-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="498a8-107">Syntax</span></span>  
  
```xml  
<ws2007HttpBinding>  
    <binding   
        allowCookies="Boolean"  
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
                realm="string"   
                                />  
          <message clientCredentialType ="Certificate/IssuedToken/None/UserName/Windows"  
           negotiateServiceCredential="Boolean"  
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
           establishSecurityContext="Boolean"   
           negotiateServiceCredential="Boolean"/>  
        </security>  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />    </binding>  
</ws2007HttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="498a8-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="498a8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="498a8-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="498a8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="498a8-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="498a8-110">Attributes</span></span>  
  
|<span data-ttu-id="498a8-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="498a8-111">Attribute</span></span>|<span data-ttu-id="498a8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="498a8-112">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="498a8-113">Valore che indica se il client accetta cookie e li propaga alle richieste future.</span><span class="sxs-lookup"><span data-stu-id="498a8-113">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="498a8-114">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="498a8-114">The default is `false`.</span></span><br /><br /> <span data-ttu-id="498a8-115">È possibile usare questa proprietà quando si interagisce con servizi Web ASP.NET (ASMX) che usano cookie.</span><span class="sxs-lookup"><span data-stu-id="498a8-115">You can use this property when you interact with ASP.NET Web services (ASMX) that use cookies.</span></span> <span data-ttu-id="498a8-116">In questo modo i cookie restituiti dal server vengono copiati automaticamente in tutte le richieste client future per quel servizio.</span><span class="sxs-lookup"><span data-stu-id="498a8-116">This ensures that cookies that the server returns are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="498a8-117">Valore che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="498a8-117">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="498a8-118">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="498a8-118">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="498a8-119">Valore di <xref:System.TimeSpan> che specifica l'intervallo di tempo per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="498a8-119">A <xref:System.TimeSpan> value that specifies the time interval for a close operation to complete.</span></span> <span data-ttu-id="498a8-120">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="498a8-120">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="498a8-121">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="498a8-121">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="498a8-122">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="498a8-122">Specifies the HTTP hostname comparison mode used to parse Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="498a8-123">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="498a8-123">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="498a8-124">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="498a8-124">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="498a8-125">Dimensione massima del pool di buffer dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="498a8-125">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="498a8-126">Il valore predefinito è 524.288 byte (512 * 1.024).</span><span class="sxs-lookup"><span data-stu-id="498a8-126">The default is 524,288 bytes (512 × 1,024).</span></span> <span data-ttu-id="498a8-127">Molte parti di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] usano buffer.</span><span class="sxs-lookup"><span data-stu-id="498a8-127">Many parts of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] use buffers.</span></span> <span data-ttu-id="498a8-128">La creazione e l'eliminazione dei buffer a ogni utilizzo sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="498a8-128">Creating and destroying buffers each time they are used is expensive, as is garbage collection for buffers.</span></span> <span data-ttu-id="498a8-129">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, reinserirlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="498a8-129">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool when you are done.</span></span> <span data-ttu-id="498a8-130">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione dei buffer.</span><span class="sxs-lookup"><span data-stu-id="498a8-130">This avoids the overhead in creating and destroying buffers.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="498a8-131">Dimensione massima in byte del messaggio, incluse le intestazioni, che può essere ricevuta in un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="498a8-131">The maximum message size, in bytes, including headers, which a channel configured with this binding, can receive.</span></span> <span data-ttu-id="498a8-132">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="498a8-132">The sender of a message exceeding this limit receives a SOAP fault.</span></span> <span data-ttu-id="498a8-133">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="498a8-133">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="498a8-134">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="498a8-134">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="498a8-135">Definisce il codificatore usato per codificare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="498a8-135">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="498a8-136">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="498a8-136">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="498a8-137">-   `Text`: Viene usato un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="498a8-137">-   `Text`: Use a text message encoder.</span></span><br /><span data-ttu-id="498a8-138">-   `Mtom`: Usa un codificatore Message Transmission Organization meccanismo 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="498a8-138">-   `Mtom`: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="498a8-139">Il valore predefinito è `Text`.</span><span class="sxs-lookup"><span data-stu-id="498a8-139">The default is `Text`.</span></span><br /><br /> <span data-ttu-id="498a8-140">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="498a8-140">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="498a8-141">Nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="498a8-141">The configuration name of the binding.</span></span> <span data-ttu-id="498a8-142">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="498a8-142">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="498a8-143">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="498a8-143">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="498a8-144">Per ulteriori informazioni sulla configurazione predefinita e senza nome associazioni e comportamenti, vedere [configurazione semplificata](../../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="498a8-144">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="498a8-145">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="498a8-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="498a8-146">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="498a8-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="498a8-147">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="498a8-147">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="498a8-148">URI che specifica l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="498a8-148">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="498a8-149">Se `useSystemWebProxy` è `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="498a8-149">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="498a8-150">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="498a8-150">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="498a8-151">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="498a8-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="498a8-152">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="498a8-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="498a8-153">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="498a8-153">The default is 00:01:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="498a8-154">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="498a8-154">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="498a8-155">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="498a8-155">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="498a8-156">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="498a8-156">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="498a8-157">Specifica la codifica del set di caratteri da usare per la creazione di messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="498a8-157">Specifies the character set encoding to use for emitting messages on the binding.</span></span> <span data-ttu-id="498a8-158">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="498a8-158">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="498a8-159">-   `UnicodeFffeTextEncoding`: Unicode Big Endian codifica.</span><span class="sxs-lookup"><span data-stu-id="498a8-159">-   `UnicodeFffeTextEncoding`: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="498a8-160">-   `Utf16TextEncoding`: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="498a8-160">-   `Utf16TextEncoding`: 16-bit encoding.</span></span><br /><span data-ttu-id="498a8-161">-   `Utf8TextEncoding`: codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="498a8-161">-   `Utf8TextEncoding`: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="498a8-162">Il valore predefinito è `Utf8TextEncoding`.</span><span class="sxs-lookup"><span data-stu-id="498a8-162">The default is `Utf8TextEncoding`.</span></span><br /><br /> <span data-ttu-id="498a8-163">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="498a8-163">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="498a8-164">Valore che specifica se l'associazione supporta il flusso di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="498a8-164">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="498a8-165">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="498a8-165">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="498a8-166">Valore che specifica se viene usato il proxy HTTP di sistema configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="498a8-166">A value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="498a8-167">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="498a8-167">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="498a8-168">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="498a8-168">Child Elements</span></span>  
  
|<span data-ttu-id="498a8-169">Elemento</span><span class="sxs-lookup"><span data-stu-id="498a8-169">Element</span></span>|<span data-ttu-id="498a8-170">Descrizione</span><span class="sxs-lookup"><span data-stu-id="498a8-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="498a8-171">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="498a8-171">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="498a8-172">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="498a8-172">Defines the security settings for the binding.</span></span> <span data-ttu-id="498a8-173">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="498a8-173">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="498a8-174">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="498a8-174">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="498a8-175">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="498a8-175">Defines the constraints on the complexity of SOAP messages that endpoints configured with this binding can process.</span></span> <span data-ttu-id="498a8-176">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="498a8-176">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="498a8-177">reliableSession</span><span class="sxs-lookup"><span data-stu-id="498a8-177">reliableSession</span></span>](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="498a8-178">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="498a8-178">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="498a8-179">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="498a8-179">Parent Elements</span></span>  
  
|<span data-ttu-id="498a8-180">Elemento</span><span class="sxs-lookup"><span data-stu-id="498a8-180">Element</span></span>|<span data-ttu-id="498a8-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="498a8-181">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="498a8-182">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="498a8-182">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="498a8-183">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="498a8-183">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="498a8-184">Note</span><span class="sxs-lookup"><span data-stu-id="498a8-184">Remarks</span></span>  
 <span data-ttu-id="498a8-185">`WS2007HttpBinding` aggiunge un'associazione fornita dal sistema simile a `WSHttpBinding`, che tuttavia usa le versioni standard OASIS (Organization for the Advancement of Structured Information Standards) dei protocolli ReliableSession, Security e TransactionFlow.</span><span class="sxs-lookup"><span data-stu-id="498a8-185">The `WS2007HttpBinding` adds a system-provided binding similar to `WSHttpBinding` but uses the Organization for the Advancement of Structured Information Standards (OASIS) standard versions of the ReliableSession, Security, and TransactionFlow protocols.</span></span> <span data-ttu-id="498a8-186">Quando si usa questa associazione, non è necessario apportare modifiche al modello a oggetti o alle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="498a8-186">No changes to the object model or default settings are required when using this binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="498a8-187">Esempio</span><span class="sxs-lookup"><span data-stu-id="498a8-187">Example</span></span>  
  
```xml  
<configuration>  
    <system.ServiceModel>  
        <bindings>  
            <ws2007HttpBinding>  
                <binding   
                    closeTimeout="00:00:10"  
                    openTimeout="00:00:20"   
                    receiveTimeout="00:00:30"  
                    sendTimeout="00:00:40"  
                    bypassProxyOnLocal="false"  
                    transactionFlow="false"   
                    hostNameComparisonMode="WeakWildcard"  
                    maxReceivedMessageSize="1000"  
                    messageEncoding="Mtom"   
                    proxyAddress="http://www.contoso.com"  
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
           </ws2007HttpBinding>  
        </bindings>  
    </system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="498a8-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="498a8-188">See Also</span></span>  
 <xref:System.ServiceModel.WS2007HttpBinding>  
 <xref:System.ServiceModel.Configuration.WS2007HttpBindingElement>  
 [<span data-ttu-id="498a8-189">Associazioni</span><span class="sxs-lookup"><span data-stu-id="498a8-189">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="498a8-190">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="498a8-190">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="498a8-191">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="498a8-191">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="498a8-192">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="498a8-192">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
