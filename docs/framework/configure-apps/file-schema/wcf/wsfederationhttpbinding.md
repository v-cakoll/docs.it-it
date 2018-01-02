---
title: '&lt;wsFederationHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 18a12bc127dca49e319eac0f6fbcfc6ab6cbfc55
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltwsfederationhttpbindinggt"></a><span data-ttu-id="44929-102">&lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="44929-102">&lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="44929-103">Definisce un'associazione che supporta WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="44929-103">Defines a binding that supports WS-Federation.</span></span>  
  
 <span data-ttu-id="44929-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="44929-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="44929-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="44929-105">\<bindings></span></span>  
<span data-ttu-id="44929-106">elemento wsFederationBinding</span><span class="sxs-lookup"><span data-stu-id="44929-106">wsFederationBinding element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44929-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44929-107">Syntax</span></span>  
  
```xml  
<wsFederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"   
        hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        privacyNoticeAt="Uri"  
        privacyNoticeVersion="Integer"  
        proxyAddress="Uri"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
        textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/ Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <security mode="None/Message/TransportWithMessageCredential">  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
                        <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
                          </headers>  
                              <identity>  
                                 <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
                        </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
           </message>  
        </security>  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />    </binding>  
</wsFederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44929-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="44929-108">Attributes and Elements</span></span>  
 <span data-ttu-id="44929-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="44929-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44929-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="44929-110">Attributes</span></span>  
  
|<span data-ttu-id="44929-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="44929-111">Attribute</span></span>|<span data-ttu-id="44929-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44929-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44929-113">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="44929-113">bypassProxyOnLocal</span></span>|<span data-ttu-id="44929-114">Valore booleano che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="44929-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="44929-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="44929-115">The default is `false`.</span></span>|  
|<span data-ttu-id="44929-116">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="44929-116">closeTimeout</span></span>|<span data-ttu-id="44929-117">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="44929-117">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="44929-118">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="44929-118">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="44929-119">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="44929-119">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="44929-120">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="44929-120">hostnameComparisonMode</span></span>|<span data-ttu-id="44929-121">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="44929-121">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="44929-122">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="44929-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="44929-123">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="44929-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="44929-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="44929-124">maxBufferPoolSize</span></span>|<span data-ttu-id="44929-125">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="44929-125">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="44929-126">Il valore predefinito è 524.288 byte (512 * 1024).</span><span class="sxs-lookup"><span data-stu-id="44929-126">The default is 524,288 bytes (512 * 1024).</span></span> <span data-ttu-id="44929-127">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="44929-127">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="44929-128">La creazione e l'eliminazione dei buffer a ogni relativo uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="44929-128">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="44929-129">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="44929-129">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="44929-130">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione dei buffer.</span><span class="sxs-lookup"><span data-stu-id="44929-130">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="44929-131">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="44929-131">maxReceivedMessageSize</span></span>|<span data-ttu-id="44929-132">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="44929-132">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="44929-133">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="44929-133">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="44929-134">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="44929-134">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="44929-135">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="44929-135">The default is 65536.</span></span>|  
|<span data-ttu-id="44929-136">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="44929-136">messageEncoding</span></span>|<span data-ttu-id="44929-137">Definisce il codificatore usato per codificare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="44929-137">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="44929-138">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="44929-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="44929-139">-Text: Usa un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="44929-139">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="44929-140">-Mtom: Usa un codificatore Message Transmission Organization meccanismo 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="44929-140">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="44929-141">L'impostazione predefinita è Text.</span><span class="sxs-lookup"><span data-stu-id="44929-141">The default is Text.</span></span><br /><br /> <span data-ttu-id="44929-142">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="44929-142">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="44929-143">name</span><span class="sxs-lookup"><span data-stu-id="44929-143">name</span></span>|<span data-ttu-id="44929-144">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="44929-144">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="44929-145">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="44929-145">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="44929-146">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="44929-146">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="44929-147">Per ulteriori informazioni sulla configurazione predefinita e senza nome associazioni e comportamenti, vedere [configurazione semplificata](../../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="44929-147">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="44929-148">openTimeout</span><span class="sxs-lookup"><span data-stu-id="44929-148">openTimeout</span></span>|<span data-ttu-id="44929-149">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="44929-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="44929-150">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="44929-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="44929-151">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="44929-151">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="44929-152">privactyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="44929-152">privactyNoticeAt</span></span>|<span data-ttu-id="44929-153">Stringa che specifica l'URI presso cui è disponibile l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="44929-153">A String that specifies a URI at which the privacy notice is located.</span></span>|  
|<span data-ttu-id="44929-154">privactyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="44929-154">privactyNoticeVersion</span></span>|<span data-ttu-id="44929-155">Numero intero che specifica la versione dell'informativa sulla privacy corrente.</span><span class="sxs-lookup"><span data-stu-id="44929-155">An integer that specifies the version of the current privacy notice.</span></span>|  
|<span data-ttu-id="44929-156">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="44929-156">proxyAddress</span></span>|<span data-ttu-id="44929-157">URI che specifica l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="44929-157">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="44929-158">Se `useDefaultWebProxy` è `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="44929-158">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="44929-159">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="44929-159">The default is `null`.</span></span>|  
|<span data-ttu-id="44929-160">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="44929-160">receiveTimeout</span></span>|<span data-ttu-id="44929-161">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="44929-161">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="44929-162">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="44929-162">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="44929-163">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="44929-163">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="44929-164">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="44929-164">sendTimeout</span></span>|<span data-ttu-id="44929-165">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="44929-165">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="44929-166">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="44929-166">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="44929-167">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="44929-167">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="44929-168">textEncoding</span><span class="sxs-lookup"><span data-stu-id="44929-168">textEncoding</span></span>|<span data-ttu-id="44929-169">Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="44929-169">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="44929-170">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="44929-170">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="44929-171">-BigEndianUnicode: Codifica Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="44929-171">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="44929-172">-Unicode: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="44929-172">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="44929-173">-UTF8: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="44929-173">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="44929-174">L'impostazione predefinita è UTF8.</span><span class="sxs-lookup"><span data-stu-id="44929-174">The default is UTF8.</span></span> <span data-ttu-id="44929-175">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="44929-175">This attribute is of type <xref:System.Text.Encoding>..</span></span>|  
|<span data-ttu-id="44929-176">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="44929-176">transactionFlow</span></span>|<span data-ttu-id="44929-177">Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="44929-177">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="44929-178">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="44929-178">The default is `false`.</span></span>|  
|<span data-ttu-id="44929-179">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="44929-179">useDefaultWebProxy</span></span>|<span data-ttu-id="44929-180">Valore booleano che indica se viene usato il proxy HTTP di sistema configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="44929-180">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="44929-181">L'indirizzo proxy deve essere `null`, ovvero non deve essere impostato, se l'attributo è `true`.</span><span class="sxs-lookup"><span data-stu-id="44929-181">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="44929-182">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="44929-182">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44929-183">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="44929-183">Child Elements</span></span>  
  
|<span data-ttu-id="44929-184">Elemento</span><span class="sxs-lookup"><span data-stu-id="44929-184">Element</span></span>|<span data-ttu-id="44929-185">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44929-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44929-186">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="44929-186">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="44929-187">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="44929-187">Defines the security settings for the message.</span></span> <span data-ttu-id="44929-188">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="44929-188">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="44929-189">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="44929-189">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="44929-190">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="44929-190">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="44929-191">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="44929-191">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="44929-192">reliableSession</span><span class="sxs-lookup"><span data-stu-id="44929-192">reliableSession</span></span>](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="44929-193">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="44929-193">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44929-194">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="44929-194">Parent Elements</span></span>  
  
|<span data-ttu-id="44929-195">Elemento</span><span class="sxs-lookup"><span data-stu-id="44929-195">Element</span></span>|<span data-ttu-id="44929-196">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44929-196">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44929-197">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="44929-197">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="44929-198">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="44929-198">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44929-199">Note</span><span class="sxs-lookup"><span data-stu-id="44929-199">Remarks</span></span>  
 <span data-ttu-id="44929-200">La federazione è la possibilità di condividere le identità di autenticazione e di autorizzazione fra più sistemi.</span><span class="sxs-lookup"><span data-stu-id="44929-200">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="44929-201">Queste identità possono fare riferimento agli utenti o ai computer.</span><span class="sxs-lookup"><span data-stu-id="44929-201">These identities can refer to users or to machines.</span></span> <span data-ttu-id="44929-202">Il protocollo HTTP federato supporta la sicurezza SOAP e una sicurezza a modalità mista, ma non supporta l'uso esclusivo della sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="44929-202">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="44929-203">Questa associazione consente al sistema [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] di supportare il protocollo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="44929-203">This binding provides [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] support for the WS-Federation protocol.</span></span> <span data-ttu-id="44929-204">I servizi configurati con questa associazione devono usare il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="44929-204">Services configured with this binding must use the HTTP transport.</span></span>  
  
 <span data-ttu-id="44929-205">Le associazioni sono costituite da uno stack di elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="44929-205">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="44929-206">Lo stack di elementi di associazione in</span><span class="sxs-lookup"><span data-stu-id="44929-206">The stack of binding elements in</span></span>  
  
 <span data-ttu-id="44929-207">`wsFederationHttpBinding` è uguale a quello incluso in `wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="44929-207">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>  
  
 <span data-ttu-id="44929-208">Quando [ \<sicurezza >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) è impostata sul valore predefinito di <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span><span class="sxs-lookup"><span data-stu-id="44929-208">when [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>  
  
 <span data-ttu-id="44929-209">Il `wsFederationHttpBinding` controlla i dettagli delle impostazioni di protezione messaggio [ \<messaggio >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="44929-209">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="44929-210">Si noti che il [ \<sicurezza >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) elemento consente di ottenere l'accesso solo quando la sicurezza utilizzata dall'associazione non può essere modificata dopo l'associazione viene creata.</span><span class="sxs-lookup"><span data-stu-id="44929-210">Note that the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>  
  
 <span data-ttu-id="44929-211">`wsFederationHttpBinding` fornisce inoltre un attributo privactyNoticeAt per impostare e recuperare l'URI in corrispondenza del quale si trova l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="44929-211">The `wsFederationHttpBinding` also provides a privactyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>  
  
 <span data-ttu-id="44929-212">La sicurezza del criterio è particolarmente importante negli scenari della federazione.</span><span class="sxs-lookup"><span data-stu-id="44929-212">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="44929-213">Il consiglio è usare qualche forma di sicurezza, ad esempio HTTPS, per proteggere il criterio dagli utenti malintenzionati.</span><span class="sxs-lookup"><span data-stu-id="44929-213">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>  
  
 <span data-ttu-id="44929-214">In scenari della federazione che usano questa associazione, il criterio del servizio contiene potenzialmente importanti informazioni quali la chiave da usare per crittografare il token emesso (SAML), il tipo di attestazioni in cui inserire il token e così via.</span><span class="sxs-lookup"><span data-stu-id="44929-214">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="44929-215">Se questo criterio viene manomesso, un pirata informatico potrebbe individuare la chiave del token emesso per eseguire ulteriori manomissioni, divulgare informazioni e altri comportamenti dannosi.</span><span class="sxs-lookup"><span data-stu-id="44929-215">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="44929-216">Per aiutare a impedire questa possibilità, il criterio deve essere ottenuto in modo protetto dal servizio, ad esempio usando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="44929-216">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>  
  
 <span data-ttu-id="44929-217">Per ulteriori informazioni su questa associazione, vedere [procedura: creare una classe WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="44929-217">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44929-218">Esempio</span><span class="sxs-lookup"><span data-stu-id="44929-218">Example</span></span>  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<wsFederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="false"  
        transactionFlow="false"  
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://foo/bar"   
        textEncoding="Utf16TextEncoding"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" enabled="true" />  
        <security mode="None">  
           <message negotiateServiceCredential="false"  
                algorithmSuite="Aes128"  
                issuedTokenType="saml"   
                issuedKeyType="PublicKey">  
               <issuer address="http://localhost/Sts" />  
           </message>  
        </security>  
    </binding>  
</wsFederationBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44929-219">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44929-219">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>  
 [<span data-ttu-id="44929-220">Procedura: Creare una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="44929-220">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="44929-221">Associazioni</span><span class="sxs-lookup"><span data-stu-id="44929-221">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="44929-222">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="44929-222">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="44929-223">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="44929-223">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="44929-224">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="44929-224">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
