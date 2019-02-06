---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: f1f405c693d8ed9182baac60a06df7928058ee09
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759743"
---
# <a name="ws2007federationhttpbinding"></a><span data-ttu-id="f8d4b-101">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f8d4b-101">\<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="f8d4b-102">Un'associazione protetta e interoperabile che deriva da [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) e supporta la sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-102">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) and supports federated security.</span></span>  
  
 <span data-ttu-id="f8d4b-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f8d4b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f8d4b-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="f8d4b-104">\<bindings></span></span>  
<span data-ttu-id="f8d4b-105">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f8d4b-105">\<ws2007FederationHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8d4b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8d4b-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8d4b-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f8d4b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f8d4b-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8d4b-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="f8d4b-109">Attributes</span></span>  
  
|<span data-ttu-id="f8d4b-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="f8d4b-110">Attribute</span></span>|<span data-ttu-id="f8d4b-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8d4b-111">Description</span></span>|  
|---------------|-----------------|  
|`bypassProxyOnLocal`|<span data-ttu-id="f8d4b-112">Valore che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-112">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="f8d4b-113">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-113">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="f8d4b-114">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="f8d4b-115">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f8d4b-116">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-116">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="f8d4b-117">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-117">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="f8d4b-118">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-118">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="f8d4b-119">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-119">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="f8d4b-120">Dimensione massima del pool di buffer dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-120">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="f8d4b-121">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="f8d4b-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="f8d4b-122">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="f8d4b-123">La creazione e l'eliminazione dei buffer a ogni relativo uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="f8d4b-124">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="f8d4b-125">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione dei buffer.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="f8d4b-126">Dimensione massima del messaggio, incluse le intestazioni, che può essere ricevuto in un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-126">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="f8d4b-127">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-127">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="f8d4b-128">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="f8d4b-129">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-129">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="f8d4b-130">Definisce il codificatore usato per codificare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-130">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="f8d4b-131">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="f8d4b-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f8d4b-132">-Text: Usare un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-132">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="f8d4b-133">-Mtom: Usa un codificatore Message Transmission organizzazione Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="f8d4b-133">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="f8d4b-134">L'impostazione predefinita è Text.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-134">The default is Text.</span></span><br /><br /> <span data-ttu-id="f8d4b-135">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-135">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="f8d4b-136">Nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-136">The configuration name of the binding.</span></span> <span data-ttu-id="f8d4b-137">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-137">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="f8d4b-138">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-138">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f8d4b-139">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f8d4b-139">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="f8d4b-140">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="f8d4b-141">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f8d4b-142">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-142">The default is 00:01:00.</span></span>|  
|`privactyNoticeAt`|<span data-ttu-id="f8d4b-143">URI presso cui si trova l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-143">A URI at which the privacy notice is located.</span></span>|  
|`privactyNoticeVersion`|<span data-ttu-id="f8d4b-144">Versione dell'informativa sulla privacy corrente.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-144">The version of the current privacy notice.</span></span>|  
|`proxyAddress`|<span data-ttu-id="f8d4b-145">URI che specifica l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-145">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="f8d4b-146">Se `useDefaultWebProxy` è `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-146">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="f8d4b-147">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-147">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="f8d4b-148">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="f8d4b-149">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f8d4b-150">L'impostazione predefinita è 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-150">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="f8d4b-151">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="f8d4b-152">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f8d4b-153">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-153">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="f8d4b-154">Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-154">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="f8d4b-155">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="f8d4b-155">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f8d4b-156">-BigEndianUnicode: Codifica Unicode bigEndian.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-156">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="f8d4b-157">-Unicode: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-157">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="f8d4b-158">-UTF8: codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-158">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="f8d4b-159">L'impostazione predefinita è UTF8.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-159">The default is UTF8.</span></span> <span data-ttu-id="f8d4b-160">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-160">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="f8d4b-161">Valore che specifica se l'associazione supporta il flusso di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-161">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="f8d4b-162">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-162">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="f8d4b-163">Valore che indica se viene usato il proxy HTTP di sistema configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-163">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="f8d4b-164">L'indirizzo proxy deve essere `null`, ovvero non deve essere impostato, se l'attributo è `true`.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-164">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="f8d4b-165">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-165">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8d4b-166">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f8d4b-166">Child Elements</span></span>  
  
|<span data-ttu-id="f8d4b-167">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8d4b-167">Element</span></span>|<span data-ttu-id="f8d4b-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8d4b-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8d4b-169">\<security></span><span class="sxs-lookup"><span data-stu-id="f8d4b-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="f8d4b-170">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-170">Defines the security settings for the message.</span></span> <span data-ttu-id="f8d4b-171">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-171">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="f8d4b-172">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f8d4b-172">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="f8d4b-173">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-173">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="f8d4b-174">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-174">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="f8d4b-175">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f8d4b-175">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="f8d4b-176">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-176">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f8d4b-177">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f8d4b-177">Parent Elements</span></span>  
  
|<span data-ttu-id="f8d4b-178">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8d4b-178">Element</span></span>|<span data-ttu-id="f8d4b-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8d4b-179">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8d4b-180">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f8d4b-180">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="f8d4b-181">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-181">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8d4b-182">Note</span><span class="sxs-lookup"><span data-stu-id="f8d4b-182">Remarks</span></span>  
 <span data-ttu-id="f8d4b-183">La federazione è la possibilità di condividere le identità di autenticazione e di autorizzazione fra più aziende o domini trust.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-183">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="f8d4b-184">Per il mapping della rappresentazione dell'identità da un dominio trust a un altro, viene usato il protocollo WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-184">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="f8d4b-185">L'associazione HTTP federata supporta la sicurezza SOAP nonché una sicurezza a modalità mista, ma non supporta la sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-185">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="f8d4b-186">I servizi configurati con questa associazione devono usare il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="f8d4b-186">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="f8d4b-187">Per altre informazioni, vedere [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f8d4b-187">For more information, see [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8d4b-188">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8d4b-188">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f8d4b-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8d4b-189">See also</span></span>
- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [<span data-ttu-id="f8d4b-190">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f8d4b-190">\<wsFederationHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)
- [<span data-ttu-id="f8d4b-191">Associazioni</span><span class="sxs-lookup"><span data-stu-id="f8d4b-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f8d4b-192">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="f8d4b-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f8d4b-193">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="f8d4b-193">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f8d4b-194">\<binding></span><span class="sxs-lookup"><span data-stu-id="f8d4b-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
