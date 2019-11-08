---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 011a46c15785b7ffa832db57925c7e7b5f76c67a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732503"
---
# <a name="wsfederationhttpbinding"></a><span data-ttu-id="88bba-101">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="88bba-101">\<wsFederationHttpBinding></span></span>

<span data-ttu-id="88bba-102">Definisce un'associazione che supporta WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="88bba-102">Defines a binding that supports WS-Federation.</span></span>

<span data-ttu-id="88bba-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="88bba-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="88bba-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="88bba-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="88bba-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="88bba-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="88bba-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**wsFederationHttpBinding >**</span><span class="sxs-lookup"><span data-stu-id="88bba-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFederationHttpBinding>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="88bba-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="88bba-107">Syntax</span></span>

```xml
<wsFederationHttpBinding>
  <binding bypassProxyOnLocal="Boolean"
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
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
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
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
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
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsFederationBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="88bba-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="88bba-108">Attributes and Elements</span></span>

<span data-ttu-id="88bba-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="88bba-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="88bba-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="88bba-110">Attributes</span></span>

|<span data-ttu-id="88bba-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="88bba-111">Attribute</span></span>|<span data-ttu-id="88bba-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88bba-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="88bba-113">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="88bba-113">bypassProxyOnLocal</span></span>|<span data-ttu-id="88bba-114">Valore booleano che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="88bba-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="88bba-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="88bba-115">The default is `false`.</span></span>|
|<span data-ttu-id="88bba-116">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="88bba-116">closeTimeout</span></span>|<span data-ttu-id="88bba-117">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="88bba-117">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="88bba-118">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="88bba-118">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="88bba-119">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="88bba-119">The default is 00:01:00.</span></span>|
|<span data-ttu-id="88bba-120">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="88bba-120">hostnameComparisonMode</span></span>|<span data-ttu-id="88bba-121">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="88bba-121">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="88bba-122">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="88bba-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="88bba-123">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="88bba-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|<span data-ttu-id="88bba-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="88bba-124">maxBufferPoolSize</span></span>|<span data-ttu-id="88bba-125">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="88bba-125">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="88bba-126">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="88bba-126">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="88bba-127">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="88bba-127">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="88bba-128">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="88bba-128">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="88bba-129">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="88bba-129">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="88bba-130">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="88bba-130">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|<span data-ttu-id="88bba-131">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="88bba-131">maxReceivedMessageSize</span></span>|<span data-ttu-id="88bba-132">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="88bba-132">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="88bba-133">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="88bba-133">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="88bba-134">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="88bba-134">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="88bba-135">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="88bba-135">The default is 65536.</span></span>|
|<span data-ttu-id="88bba-136">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="88bba-136">messageEncoding</span></span>|<span data-ttu-id="88bba-137">Definisce il codificatore usato per codificare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="88bba-137">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="88bba-138">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="88bba-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="88bba-139">-Text: usa un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="88bba-139">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="88bba-140">-MTOM: usare un codificatore Message Transmission Organization Mechanism 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="88bba-140">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="88bba-141">L'impostazione predefinita è Text.</span><span class="sxs-lookup"><span data-stu-id="88bba-141">The default is Text.</span></span><br /><br /> <span data-ttu-id="88bba-142">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="88bba-142">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|<span data-ttu-id="88bba-143">name</span><span class="sxs-lookup"><span data-stu-id="88bba-143">name</span></span>|<span data-ttu-id="88bba-144">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="88bba-144">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="88bba-145">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="88bba-145">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="88bba-146">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="88bba-146">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="88bba-147">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="88bba-147">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="88bba-148">openTimeout</span><span class="sxs-lookup"><span data-stu-id="88bba-148">openTimeout</span></span>|<span data-ttu-id="88bba-149">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="88bba-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="88bba-150">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="88bba-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="88bba-151">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="88bba-151">The default is 00:01:00.</span></span>|
|<span data-ttu-id="88bba-152">uriInformativaPrivacy</span><span class="sxs-lookup"><span data-stu-id="88bba-152">privacyNoticeAt</span></span>|<span data-ttu-id="88bba-153">Stringa che specifica l'URI presso cui è disponibile l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="88bba-153">A String that specifies a URI at which the privacy notice is located.</span></span>|
|<span data-ttu-id="88bba-154">privacyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="88bba-154">privacyNoticeVersion</span></span>|<span data-ttu-id="88bba-155">Numero intero che specifica la versione dell'informativa sulla privacy corrente.</span><span class="sxs-lookup"><span data-stu-id="88bba-155">An integer that specifies the version of the current privacy notice.</span></span>|
|<span data-ttu-id="88bba-156">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="88bba-156">proxyAddress</span></span>|<span data-ttu-id="88bba-157">URI che specifica l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="88bba-157">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="88bba-158">Se `useDefaultWebProxy` è `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="88bba-158">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="88bba-159">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="88bba-159">The default is `null`.</span></span>|
|<span data-ttu-id="88bba-160">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="88bba-160">receiveTimeout</span></span>|<span data-ttu-id="88bba-161">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="88bba-161">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="88bba-162">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="88bba-162">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="88bba-163">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="88bba-163">The default is 00:10:00.</span></span>|
|<span data-ttu-id="88bba-164">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="88bba-164">sendTimeout</span></span>|<span data-ttu-id="88bba-165">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="88bba-165">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="88bba-166">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="88bba-166">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="88bba-167">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="88bba-167">The default is 00:01:00.</span></span>|
|<span data-ttu-id="88bba-168">textEncoding</span><span class="sxs-lookup"><span data-stu-id="88bba-168">textEncoding</span></span>|<span data-ttu-id="88bba-169">Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="88bba-169">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="88bba-170">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="88bba-170">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="88bba-171">-BigEndianUnicode: codifica BigEndian Unicode.</span><span class="sxs-lookup"><span data-stu-id="88bba-171">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="88bba-172">-Unicode: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="88bba-172">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="88bba-173">-UTF8: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="88bba-173">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="88bba-174">L'impostazione predefinita è UTF8.</span><span class="sxs-lookup"><span data-stu-id="88bba-174">The default is UTF8.</span></span> <span data-ttu-id="88bba-175">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="88bba-175">This attribute is of type <xref:System.Text.Encoding>..</span></span>|
|<span data-ttu-id="88bba-176">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="88bba-176">transactionFlow</span></span>|<span data-ttu-id="88bba-177">Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="88bba-177">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="88bba-178">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="88bba-178">The default is `false`.</span></span>|
|<span data-ttu-id="88bba-179">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="88bba-179">useDefaultWebProxy</span></span>|<span data-ttu-id="88bba-180">Valore booleano che indica se viene usato il proxy HTTP di sistema configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="88bba-180">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="88bba-181">L'indirizzo proxy deve essere `null`, ovvero non deve essere impostato, se l'attributo è `true`.</span><span class="sxs-lookup"><span data-stu-id="88bba-181">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="88bba-182">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="88bba-182">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="88bba-183">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="88bba-183">Child Elements</span></span>

|<span data-ttu-id="88bba-184">Elemento</span><span class="sxs-lookup"><span data-stu-id="88bba-184">Element</span></span>|<span data-ttu-id="88bba-185">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88bba-185">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="88bba-186">\<security ></span><span class="sxs-lookup"><span data-stu-id="88bba-186">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="88bba-187">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="88bba-187">Defines the security settings for the message.</span></span> <span data-ttu-id="88bba-188">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="88bba-188">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="88bba-189">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="88bba-189">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="88bba-190">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="88bba-190">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="88bba-191">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="88bba-191">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="88bba-192">[\<reliableSession >](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="88bba-192">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="88bba-193">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="88bba-193">Specifies if reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="88bba-194">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="88bba-194">Parent Elements</span></span>

|<span data-ttu-id="88bba-195">Elemento</span><span class="sxs-lookup"><span data-stu-id="88bba-195">Element</span></span>|<span data-ttu-id="88bba-196">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88bba-196">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="88bba-197">\<bindings ></span><span class="sxs-lookup"><span data-stu-id="88bba-197">\<bindings></span></span>](bindings.md)|<span data-ttu-id="88bba-198">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="88bba-198">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="88bba-199">Note</span><span class="sxs-lookup"><span data-stu-id="88bba-199">Remarks</span></span>

<span data-ttu-id="88bba-200">La federazione è la possibilità di condividere le identità di autenticazione e di autorizzazione fra più sistemi.</span><span class="sxs-lookup"><span data-stu-id="88bba-200">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="88bba-201">Queste identità possono fare riferimento agli utenti o ai computer.</span><span class="sxs-lookup"><span data-stu-id="88bba-201">These identities can refer to users or to machines.</span></span> <span data-ttu-id="88bba-202">Il protocollo HTTP federato supporta la sicurezza SOAP e una sicurezza a modalità mista, ma non supporta l'uso esclusivo della sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="88bba-202">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="88bba-203">Questa associazione fornisce il supporto Windows Communication Foundation (WCF) per il protocollo WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="88bba-203">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="88bba-204">I servizi configurati con questa associazione devono usare il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="88bba-204">Services configured with this binding must use the HTTP transport.</span></span>

<span data-ttu-id="88bba-205">Le associazioni sono costituite da uno stack di elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="88bba-205">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="88bba-206">Lo stack di elementi di associazione in</span><span class="sxs-lookup"><span data-stu-id="88bba-206">The stack of binding elements in</span></span>

<span data-ttu-id="88bba-207">`wsFederationHttpBinding` è uguale a quello incluso in `wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="88bba-207">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>

<span data-ttu-id="88bba-208">Quando [\<> di sicurezza](security-of-wsfederationhttpbinding.md) è impostato sul valore predefinito di <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span><span class="sxs-lookup"><span data-stu-id="88bba-208">when [\<security>](security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>

<span data-ttu-id="88bba-209">Il `wsFederationHttpBinding` controlla i dettagli delle impostazioni di sicurezza del messaggio in [\<> messaggio](message-element-of-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="88bba-209">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="88bba-210">Si noti che l'elemento [\<security >](security-of-wsfederationhttpbinding.md) fornisce accesso get solo perché la sicurezza utilizzata dall'associazione non può essere modificata dopo la creazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="88bba-210">Note that the [\<security>](security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>

<span data-ttu-id="88bba-211">Il `wsFederationHttpBinding` fornisce anche un attributo privacyNoticeAt per impostare e recuperare l'URI in cui si trova l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="88bba-211">The `wsFederationHttpBinding` also provides a privacyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>

<span data-ttu-id="88bba-212">La sicurezza del criterio è particolarmente importante negli scenari della federazione.</span><span class="sxs-lookup"><span data-stu-id="88bba-212">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="88bba-213">Il consiglio è usare qualche forma di sicurezza, ad esempio HTTPS, per proteggere il criterio dagli utenti malintenzionati.</span><span class="sxs-lookup"><span data-stu-id="88bba-213">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>

<span data-ttu-id="88bba-214">In scenari della federazione che usano questa associazione, il criterio del servizio contiene potenzialmente importanti informazioni quali la chiave da usare per crittografare il token emesso (SAML), il tipo di attestazioni in cui inserire il token e così via.</span><span class="sxs-lookup"><span data-stu-id="88bba-214">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="88bba-215">Se questo criterio viene manomesso, un pirata informatico potrebbe individuare la chiave del token emesso per eseguire ulteriori manomissioni, divulgare informazioni e altri comportamenti dannosi.</span><span class="sxs-lookup"><span data-stu-id="88bba-215">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="88bba-216">Per aiutare a impedire questa possibilità, il criterio deve essere ottenuto in modo protetto dal servizio, ad esempio usando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="88bba-216">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>

<span data-ttu-id="88bba-217">Per ulteriori informazioni su questa associazione, vedere [procedura: creare un WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="88bba-217">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="88bba-218">Esempio</span><span class="sxs-lookup"><span data-stu-id="88bba-218">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsFederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
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

## <a name="see-also"></a><span data-ttu-id="88bba-219">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88bba-219">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [<span data-ttu-id="88bba-220">Procedura: Creare una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="88bba-220">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="88bba-221">Associazioni</span><span class="sxs-lookup"><span data-stu-id="88bba-221">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="88bba-222">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="88bba-222">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="88bba-223">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="88bba-223">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="88bba-224">\<binding ></span><span class="sxs-lookup"><span data-stu-id="88bba-224">\<binding></span></span>](bindings.md)
