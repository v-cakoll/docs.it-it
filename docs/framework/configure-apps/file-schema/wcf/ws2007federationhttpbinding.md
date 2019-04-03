---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: e6215465acbf9bb94298d282d15f8735a0e20c8c
ms.sourcegitcommit: 5c2176883dc3107445702724a7caa7ac2f6cb0d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2019
ms.locfileid: "58890254"
---
# <a name="ws2007federationhttpbinding"></a><span data-ttu-id="69294-101">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="69294-101">\<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="69294-102">Un'associazione protetta e interoperabile che deriva da [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) e supporta la sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="69294-102">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) and supports federated security.</span></span>

```xml
<system.ServiceModel>
  <bindings>
    <ws2007FederationHttpBinding>
```

## <a name="syntax"></a><span data-ttu-id="69294-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69294-103">Syntax</span></span>

```xml
<ws2007FederationHttpBinding>
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
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
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
</ws2007FederationHttpBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="69294-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="69294-104">Attributes and Elements</span></span>

<span data-ttu-id="69294-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="69294-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="69294-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="69294-106">Attributes</span></span>

|<span data-ttu-id="69294-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="69294-107">Attribute</span></span>|<span data-ttu-id="69294-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69294-108">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="69294-109">Valore che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="69294-109">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="69294-110">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="69294-110">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="69294-111">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="69294-111">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="69294-112">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="69294-112">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="69294-113">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="69294-113">The default is 00:01:00.</span></span>|
|`hostNameComparisonMode`|<span data-ttu-id="69294-114">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="69294-114">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="69294-115">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="69294-115">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="69294-116">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="69294-116">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="69294-117">Dimensione massima del pool di buffer dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="69294-117">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="69294-118">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="69294-118">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="69294-119">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="69294-119">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="69294-120">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="69294-120">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="69294-121">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="69294-121">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="69294-122">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="69294-122">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="69294-123">Dimensione massima del messaggio, incluse le intestazioni, che può essere ricevuto in un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="69294-123">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="69294-124">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="69294-124">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="69294-125">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="69294-125">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="69294-126">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="69294-126">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="69294-127">Definisce il codificatore usato per codificare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="69294-127">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="69294-128">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="69294-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="69294-129">-Text: Usare un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="69294-129">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="69294-130">-Mtom: Usa un codificatore Message Transmission organizzazione Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="69294-130">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="69294-131">L'impostazione predefinita è Text.</span><span class="sxs-lookup"><span data-stu-id="69294-131">The default is Text.</span></span><br /><br /> <span data-ttu-id="69294-132">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="69294-132">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="69294-133">Nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="69294-133">The configuration name of the binding.</span></span> <span data-ttu-id="69294-134">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="69294-134">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="69294-135">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="69294-135">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="69294-136">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="69294-136">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="69294-137">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="69294-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="69294-138">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="69294-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="69294-139">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="69294-139">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="69294-140">URI presso cui si trova l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="69294-140">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="69294-141">Versione dell'informativa sulla privacy corrente.</span><span class="sxs-lookup"><span data-stu-id="69294-141">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="69294-142">URI che specifica l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="69294-142">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="69294-143">Se `useDefaultWebProxy` è `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="69294-143">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="69294-144">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="69294-144">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="69294-145">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="69294-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="69294-146">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="69294-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="69294-147">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="69294-147">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="69294-148">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="69294-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="69294-149">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="69294-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="69294-150">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="69294-150">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="69294-151">Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="69294-151">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="69294-152">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="69294-152">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="69294-153">-BigEndianUnicode: Codifica Unicode bigEndian.</span><span class="sxs-lookup"><span data-stu-id="69294-153">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="69294-154">-Unicode: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="69294-154">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="69294-155">-UTF8: codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="69294-155">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="69294-156">L'impostazione predefinita è UTF8.</span><span class="sxs-lookup"><span data-stu-id="69294-156">The default is UTF8.</span></span> <span data-ttu-id="69294-157">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="69294-157">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="69294-158">Valore che specifica se l'associazione supporta il flusso di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="69294-158">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="69294-159">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="69294-159">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="69294-160">Valore che indica se viene usato il proxy HTTP di sistema configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="69294-160">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="69294-161">L'indirizzo proxy deve essere `null`, ovvero non deve essere impostato, se l'attributo è `true`.</span><span class="sxs-lookup"><span data-stu-id="69294-161">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="69294-162">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="69294-162">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="69294-163">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="69294-163">Child Elements</span></span>

|<span data-ttu-id="69294-164">Elemento</span><span class="sxs-lookup"><span data-stu-id="69294-164">Element</span></span>|<span data-ttu-id="69294-165">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69294-165">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="69294-166">\<security></span><span class="sxs-lookup"><span data-stu-id="69294-166">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="69294-167">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="69294-167">Defines the security settings for the message.</span></span> <span data-ttu-id="69294-168">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="69294-168">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|[<span data-ttu-id="69294-169">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="69294-169">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="69294-170">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="69294-170">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="69294-171">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="69294-171">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|[<span data-ttu-id="69294-172">\<reliableSession></span><span class="sxs-lookup"><span data-stu-id="69294-172">\<reliableSession></span></span>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="69294-173">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="69294-173">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="69294-174">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="69294-174">Parent Elements</span></span>

|<span data-ttu-id="69294-175">Elemento</span><span class="sxs-lookup"><span data-stu-id="69294-175">Element</span></span>|<span data-ttu-id="69294-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69294-176">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="69294-177">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="69294-177">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="69294-178">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="69294-178">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="69294-179">Note</span><span class="sxs-lookup"><span data-stu-id="69294-179">Remarks</span></span>

<span data-ttu-id="69294-180">La federazione è la possibilità di condividere le identità di autenticazione e di autorizzazione fra più aziende o domini trust.</span><span class="sxs-lookup"><span data-stu-id="69294-180">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="69294-181">Per il mapping della rappresentazione dell'identità da un dominio trust a un altro, viene usato il protocollo WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="69294-181">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="69294-182">L'associazione HTTP federata supporta la sicurezza SOAP nonché una sicurezza a modalità mista, ma non supporta la sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="69294-182">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="69294-183">I servizi configurati con questa associazione devono usare il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="69294-183">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="69294-184">Per altre informazioni, vedere [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="69294-184">For more information, see [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="69294-185">Esempio</span><span class="sxs-lookup"><span data-stu-id="69294-185">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007FederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </ws2007FederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="69294-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69294-186">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [<span data-ttu-id="69294-187">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="69294-187">\<wsFederationHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)
- [<span data-ttu-id="69294-188">Associazioni</span><span class="sxs-lookup"><span data-stu-id="69294-188">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="69294-189">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="69294-189">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="69294-190">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="69294-190">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="69294-191">\<binding></span><span class="sxs-lookup"><span data-stu-id="69294-191">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
