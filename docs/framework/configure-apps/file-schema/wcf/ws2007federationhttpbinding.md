---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 20ba643fddbac8a488e5457f0195cc253d4d23f7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139322"
---
# \<ws2007FederationHttpBinding>

<span data-ttu-id="127cf-101">Associazione protetta e interoperabile che deriva da [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) e supporta la sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="127cf-101">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) and supports federated security.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws2007FederationHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="127cf-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="127cf-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="127cf-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="127cf-103">Attributes and Elements</span></span>

<span data-ttu-id="127cf-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="127cf-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="127cf-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="127cf-105">Attributes</span></span>

|<span data-ttu-id="127cf-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="127cf-106">Attribute</span></span>|<span data-ttu-id="127cf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="127cf-107">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="127cf-108">Valore che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="127cf-108">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="127cf-109">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="127cf-109">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="127cf-110">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="127cf-110">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="127cf-111">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="127cf-111">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="127cf-112">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="127cf-112">The default is 00:01:00.</span></span>|
|`hostNameComparisonMode`|<span data-ttu-id="127cf-113">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="127cf-113">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="127cf-114">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="127cf-114">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="127cf-115">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="127cf-115">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="127cf-116">Dimensione massima del pool di buffer dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="127cf-116">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="127cf-117">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="127cf-117">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="127cf-118">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="127cf-118">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="127cf-119">La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="127cf-119">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="127cf-120">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="127cf-120">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="127cf-121">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.</span><span class="sxs-lookup"><span data-stu-id="127cf-121">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="127cf-122">Dimensione massima del messaggio, incluse le intestazioni, che può essere ricevuto in un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="127cf-122">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="127cf-123">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="127cf-123">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="127cf-124">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="127cf-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="127cf-125">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="127cf-125">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="127cf-126">Definisce il codificatore usato per codificare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="127cf-126">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="127cf-127">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="127cf-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="127cf-128">-Text: usa un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="127cf-128">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="127cf-129">-MTOM: usare un codificatore Message Transmission Organization Mechanism 1,0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="127cf-129">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="127cf-130">L'impostazione predefinita è Text.</span><span class="sxs-lookup"><span data-stu-id="127cf-130">The default is Text.</span></span><br /><br /> <span data-ttu-id="127cf-131">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="127cf-131">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="127cf-132">Nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="127cf-132">The configuration name of the binding.</span></span> <span data-ttu-id="127cf-133">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="127cf-133">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="127cf-134">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="127cf-134">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="127cf-135">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="127cf-135">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="127cf-136">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="127cf-136">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="127cf-137">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="127cf-137">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="127cf-138">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="127cf-138">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="127cf-139">URI presso cui si trova l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="127cf-139">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="127cf-140">Versione dell'informativa sulla privacy corrente.</span><span class="sxs-lookup"><span data-stu-id="127cf-140">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="127cf-141">URI che specifica l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="127cf-141">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="127cf-142">Se `useDefaultWebProxy` è `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="127cf-142">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="127cf-143">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="127cf-143">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="127cf-144">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="127cf-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="127cf-145">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="127cf-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="127cf-146">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="127cf-146">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="127cf-147">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="127cf-147">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="127cf-148">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="127cf-148">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="127cf-149">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="127cf-149">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="127cf-150">Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="127cf-150">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="127cf-151">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="127cf-151">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="127cf-152">-BigEndianUnicode: codifica Unicode big endian.</span><span class="sxs-lookup"><span data-stu-id="127cf-152">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="127cf-153">-Unicode: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="127cf-153">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="127cf-154">-UTF8: codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="127cf-154">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="127cf-155">Il valore predefinito è UTF8.</span><span class="sxs-lookup"><span data-stu-id="127cf-155">The default is UTF8.</span></span> <span data-ttu-id="127cf-156">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="127cf-156">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="127cf-157">Valore che specifica se l'associazione supporta il flusso di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="127cf-157">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="127cf-158">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="127cf-158">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="127cf-159">Valore che indica se viene usato il proxy HTTP di sistema configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="127cf-159">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="127cf-160">L'indirizzo proxy deve essere `null`, ovvero non deve essere impostato, se l'attributo è `true`.</span><span class="sxs-lookup"><span data-stu-id="127cf-160">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="127cf-161">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="127cf-161">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="127cf-162">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="127cf-162">Child Elements</span></span>

|<span data-ttu-id="127cf-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="127cf-163">Element</span></span>|<span data-ttu-id="127cf-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="127cf-164">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="127cf-165">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="127cf-165">Defines the security settings for the message.</span></span> <span data-ttu-id="127cf-166">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="127cf-166">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="127cf-167">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="127cf-167">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="127cf-168">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="127cf-168">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="127cf-169">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="127cf-169">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="127cf-170">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="127cf-170">Parent Elements</span></span>

|<span data-ttu-id="127cf-171">Elemento</span><span class="sxs-lookup"><span data-stu-id="127cf-171">Element</span></span>|<span data-ttu-id="127cf-172">Descrizione</span><span class="sxs-lookup"><span data-stu-id="127cf-172">Description</span></span>|
|-------------|-----------------|
|[\<bindings>](bindings.md)|<span data-ttu-id="127cf-173">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="127cf-173">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="127cf-174">Commenti</span><span class="sxs-lookup"><span data-stu-id="127cf-174">Remarks</span></span>

<span data-ttu-id="127cf-175">La federazione è la possibilità di condividere le identità di autenticazione e di autorizzazione fra più aziende o domini trust.</span><span class="sxs-lookup"><span data-stu-id="127cf-175">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="127cf-176">Per il mapping della rappresentazione dell'identità da un dominio trust a un altro, viene usato il protocollo WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="127cf-176">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="127cf-177">L'associazione HTTP federata supporta la sicurezza SOAP nonché una sicurezza a modalità mista, ma non supporta la sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="127cf-177">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="127cf-178">I servizi configurati con questa associazione devono usare il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="127cf-178">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="127cf-179">Per altre informazioni, vedere [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="127cf-179">For more information, see [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="127cf-180">Esempio</span><span class="sxs-lookup"><span data-stu-id="127cf-180">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="127cf-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="127cf-181">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [\<wsFederationHttpBinding>](wsfederationhttpbinding.md)
- [<span data-ttu-id="127cf-182">Binding</span><span class="sxs-lookup"><span data-stu-id="127cf-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="127cf-183">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="127cf-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="127cf-184">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="127cf-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
