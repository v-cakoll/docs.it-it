---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: 60ce3cdfd7c78d152c71cdd652532cc96a6be296
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2019
ms.locfileid: "59481119"
---
# <a name="custombinding"></a><span data-ttu-id="bedbe-101">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="bedbe-101">\<customBinding></span></span>

<span data-ttu-id="bedbe-102">Fornisce il controllo completo dello stack di messaggistica per l'utente.</span><span class="sxs-lookup"><span data-stu-id="bedbe-102">Provides full control over the messaging stack for the user.</span></span>

<span data-ttu-id="bedbe-103">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="bedbe-103">\<system.serviceModel>\\</span></span>
<span data-ttu-id="bedbe-104">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="bedbe-104">\<bindings>\\</span></span>
<span data-ttu-id="bedbe-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="bedbe-105">\<customBinding></span></span>

## <a name="syntax"></a><span data-ttu-id="bedbe-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bedbe-106">Syntax</span></span>

```xml
<customBinding>
  <binding name="String"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
    <compositeDuplex clientBaseAddress="Uri" />
    <reliableSession acknowledgementInterval="TimeSpan"
                     advancedFlowControl="Boolean"
                     bufferedMessagesQuota="Integer"
                     inactivityTimeout="TimeSpan"
                     maxPendingChannels="Integer"
                     maxRetryCount="Integer"
                     ordered="Boolean" />
    <pnrpPeerResolver />
    <windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
    <sslStreamSecurity requireClientCertificate="Boolean" />
    <transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              contextMode="Cookie"
              defaultProtectionLevel="Sign"
              enableKeyDerivation="false"
              keyEntropyMode="ClientEntropy"
              messageProtectionOrder="SignBeforeEncryptAndEncryptSignature"
              securityVersion="WSSecurityXXX2005">
      <localClientSettings cacheCookies="false"
                           detectReplays="false"
                           maxCookieCachingTime="00:07:24" />
      <localServiceSettings replayCacheSize="9"
                            maxClockSkew="00:00:03"
                            replayWindow="00:07:22.2190000" />
    </security>
    <binaryMessageEncoding maxReadPoolSize="Integer"
                           maxWritePoolSize="Integer"
                           maxSessionSize="Integer" />
    <httpsTransport manualAddressing="Boolean"
                    maxMessageSize="Integer"
                    authenticationScheme="Negotiate"
                    bypassProxyOnLocal="Boolean"
                    hostNameComparisonMode="Exact"
                    mapAddressingHeadersToHttpHeaders="Boolean"
                    proxyaddress="Uri"
                    realm="String"
                    requireClientCertificate="Boolean" />
    <peerTransport manualAddressing="false"
                   maxMessageSize="20002"
                   listenIPAddress="202.10.1.9"
                   messageAuthentication="false"
                   peerNodeAuthenticationMode="None"
                   port="1000" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean">
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                            issuedCookieLifeTime="TimeSpan"
                            maxStatefulNegotiations="Integer"
                            replayCacheSize="Integer"
                            maxClockSkew="TimeSpan"
                            negotiationTimeout="TimeSpan"
                            replayWindow="TimeSpan"
                            inactivityTimeout="TimeSpan"
                            sessionKeyRenewalInterval="TimeSpan"
                            sessionKeyRolloverInterval="TimeSpan"
                            reconnectOnTransportFailure="Boolean"
                            maxConcurrentSessions="Integer"
                            timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
    </security>
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean" >
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                           issuedCookieLifeTime="TimeSpan"
                           maxStatefulNegotiations="Integer"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           negotiationTimeout="TimeSpan"
                           replayWindow="TimeSpan"
                           inactivityTimeout="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           maxConcurrentSessions="Integer"
                           timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
      <genericIssuedTokenParameters>
        <localIssuerIssuedTokenParameters keyType="SymmetricKey/PublicKey"
                                          keySize="Integer"
                                          tokenType="String" />
        <issuedTokenParametersEndpointAddress address="URI"
                                              bindingConfiguration="String"
                                              binding="String" />
        <issuedTokenClient localIssuerChannelBehaviors="String"
                           cacheIssuedTokens="Boolean"
                           maxIssuedTokenCachingTime="TimeSpan"
                           keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy" />
        <issuedTokenClientBehavior issuerAddress="String"
                                   behaviorConfiguration="String" />
        <issuedTokenClientBehavior address="URI"
                                   bindingConfiguration="String"
                                   binding="String" />
      </genericIssuedTokenParameters>
    </security>
  </binding>
</customBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bedbe-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bedbe-107">Attributes and Elements</span></span>

<span data-ttu-id="bedbe-108">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bedbe-108">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="bedbe-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="bedbe-109">Attributes</span></span>

|<span data-ttu-id="bedbe-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="bedbe-110">Attribute</span></span>|<span data-ttu-id="bedbe-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bedbe-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="bedbe-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="bedbe-112">closeTimeout</span></span>|<span data-ttu-id="bedbe-113">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="bedbe-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="bedbe-114">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="bedbe-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bedbe-115">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="bedbe-115">The default is 00:01:00.</span></span>|
|<span data-ttu-id="bedbe-116">name</span><span class="sxs-lookup"><span data-stu-id="bedbe-116">name</span></span>|<span data-ttu-id="bedbe-117">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="bedbe-117">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="bedbe-118">Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="bedbe-118">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="bedbe-119">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="bedbe-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="bedbe-120">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="bedbe-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="bedbe-121">openTimeout</span><span class="sxs-lookup"><span data-stu-id="bedbe-121">openTimeout</span></span>|<span data-ttu-id="bedbe-122">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="bedbe-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="bedbe-123">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="bedbe-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bedbe-124">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="bedbe-124">The default is 00:01:00.</span></span>|
|<span data-ttu-id="bedbe-125">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="bedbe-125">receiveTimeout</span></span>|<span data-ttu-id="bedbe-126">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="bedbe-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="bedbe-127">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="bedbe-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bedbe-128">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="bedbe-128">The default is 00:01:00.</span></span>|
|<span data-ttu-id="bedbe-129">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="bedbe-129">sendTimeout</span></span>|<span data-ttu-id="bedbe-130">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="bedbe-130">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="bedbe-131">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="bedbe-131">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="bedbe-132">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="bedbe-132">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="bedbe-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bedbe-133">Child Elements</span></span>

|<span data-ttu-id="bedbe-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="bedbe-134">Element</span></span>|<span data-ttu-id="bedbe-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bedbe-135">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bedbe-136">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="bedbe-136">\<compositeDuplex></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)|<span data-ttu-id="bedbe-137">Specifica la messaggistica bidirezionale sull'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="bedbe-137">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="bedbe-138">Viene usato con trasporti che non consentono comunicazioni duplex a livello nativo, ad esempio, HTTP.</span><span class="sxs-lookup"><span data-stu-id="bedbe-138">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="bedbe-139">TCP, al contrario, consente comunicazioni duplex a livello nativo e non richiede l'uso di questo elemento di associazione affinché il servizio invii messaggi a un client.</span><span class="sxs-lookup"><span data-stu-id="bedbe-139">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="bedbe-140">Il client deve esporre un indirizzo affinché il servizio crei un contatto e stabilisca una connessione.</span><span class="sxs-lookup"><span data-stu-id="bedbe-140">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="bedbe-141">Questo indirizzo client è fornito dall'attributo `ClientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="bedbe-141">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="bedbe-142">L'elemento è di tipo <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span><span class="sxs-lookup"><span data-stu-id="bedbe-142">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[<span data-ttu-id="bedbe-143">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="bedbe-143">\<pnrpPeerResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/pnrppeerresolver.md)|<span data-ttu-id="bedbe-144">Specifica un resolver dei nomi peer PNRP (Peer Name Resolution Protocol).</span><span class="sxs-lookup"><span data-stu-id="bedbe-144">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="bedbe-145">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span><span class="sxs-lookup"><span data-stu-id="bedbe-145">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[<span data-ttu-id="bedbe-146">\<reliableSession></span><span class="sxs-lookup"><span data-stu-id="bedbe-146">\<reliableSession></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md)|<span data-ttu-id="bedbe-147">Specifica l'impostazione per WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="bedbe-147">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="bedbe-148">Quando questo elemento viene aggiunto a un'associazione personalizzata, il canale risultante può supportare assicurazioni di recapito una volta esatta.</span><span class="sxs-lookup"><span data-stu-id="bedbe-148">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="bedbe-149">L'elemento è di tipo <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span><span class="sxs-lookup"><span data-stu-id="bedbe-149">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[<span data-ttu-id="bedbe-150">\<security></span><span class="sxs-lookup"><span data-stu-id="bedbe-150">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="bedbe-151">Specifica le opzioni di sicurezza per l'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="bedbe-151">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="bedbe-152">L'elemento è di tipo <xref:System.ServiceModel.Configuration.SecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="bedbe-152">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[<span data-ttu-id="bedbe-153">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="bedbe-153">\<sslStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)|<span data-ttu-id="bedbe-154">Specifica le impostazioni di sicurezza per l'associazione del flusso SSL.</span><span class="sxs-lookup"><span data-stu-id="bedbe-154">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="bedbe-155">L'elemento è di tipo <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="bedbe-155">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[<span data-ttu-id="bedbe-156">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="bedbe-156">\<transactionFlow></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md)|<span data-ttu-id="bedbe-157">Specifica che l'associazione supporta il flusso delle transazioni e il protocollo che deve essere usato dall'attributo `transactionProtocol`.</span><span class="sxs-lookup"><span data-stu-id="bedbe-157">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="bedbe-158">L'elemento è di tipo <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span><span class="sxs-lookup"><span data-stu-id="bedbe-158">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[<span data-ttu-id="bedbe-159">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="bedbe-159">\<windowsStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsstreamsecurity.md)|<span data-ttu-id="bedbe-160">Specifica le opzioni di sicurezza del flusso per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="bedbe-160">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="bedbe-161">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="bedbe-161">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bedbe-162">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bedbe-162">Parent Elements</span></span>

|<span data-ttu-id="bedbe-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="bedbe-163">Element</span></span>|<span data-ttu-id="bedbe-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bedbe-164">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="bedbe-165">associazioni</span><span class="sxs-lookup"><span data-stu-id="bedbe-165">bindings</span></span>|<span data-ttu-id="bedbe-166">Contiene tutte le associazioni per le applicazioni Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bedbe-166">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bedbe-167">Note</span><span class="sxs-lookup"><span data-stu-id="bedbe-167">Remarks</span></span>

<span data-ttu-id="bedbe-168">Le associazioni personalizzate forniscono il controllo completo dello stack dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="bedbe-168">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="bedbe-169">È possibile creare associazioni speciali su misura aggiungendo gli elementi di configurazione per le entità specifiche.</span><span class="sxs-lookup"><span data-stu-id="bedbe-169">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="bedbe-170">Ad esempio, l'utente può combinare la sezione `httpsTransport`, la sezione `reliableSession` e la sezione `security` per creare un'associazione affidabile e protetto basata su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="bedbe-170">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="bedbe-171">Un'associazione singola definisce lo stack dei messaggi specificando gli elementi di configurazione per gli elementi dello stack nell'ordine in cui vengono visualizzati nello stack.</span><span class="sxs-lookup"><span data-stu-id="bedbe-171">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="bedbe-172">Ogni elemento definisce e configura un elemento dello stack.</span><span class="sxs-lookup"><span data-stu-id="bedbe-172">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="bedbe-173">Deve esistere un solo elemento di trasporto in ogni associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="bedbe-173">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="bedbe-174">Senza questo elemento, lo stack dei messaggi è incompleto.</span><span class="sxs-lookup"><span data-stu-id="bedbe-174">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="bedbe-175">L'ordine in cui gli elementi vengono visualizzati nello stack è importante, perché è l'ordine in cui le operazioni vengono applicate al messaggio.</span><span class="sxs-lookup"><span data-stu-id="bedbe-175">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="bedbe-176">L'ordine consigliato per gli elementi dello stack è il seguente:</span><span class="sxs-lookup"><span data-stu-id="bedbe-176">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="bedbe-177">Transazioni (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="bedbe-177">Transactions (optional)</span></span>

2. <span data-ttu-id="bedbe-178">Messaggistica affidabile (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="bedbe-178">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="bedbe-179">Sicurezza (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="bedbe-179">Security (optional)</span></span>

4. <span data-ttu-id="bedbe-180">Trasporto</span><span class="sxs-lookup"><span data-stu-id="bedbe-180">Transport</span></span>

5. <span data-ttu-id="bedbe-181">Codificatore (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="bedbe-181">Encoder (optional)</span></span>

<span data-ttu-id="bedbe-182">Usare un'associazione personalizzata quando una delle associazioni fornite dal sistema non soddisfa i requisiti del servizio.</span><span class="sxs-lookup"><span data-stu-id="bedbe-182">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="bedbe-183">Un'associazione personalizzata potrebbe essere usata, ad esempio, per abilitare l'uso di un nuovo trasporto o di un nuovo codificatore a un endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="bedbe-183">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="bedbe-184">Un'associazione personalizzata viene costruita usando uno dei <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> da una raccolta di elementi di associazione in uno stack in un ordine specifico:</span><span class="sxs-lookup"><span data-stu-id="bedbe-184">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="bedbe-185">All'inizio si trova una classe <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> facoltativa che consente la propagazione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="bedbe-185">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="bedbe-186">Quindi una classe <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> facoltativa che fornisce una sessione e un meccanismo di ordinamento come definito nella specifica WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="bedbe-186">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="bedbe-187">Questa nozione di sessione può attraversare SOAP e può trasportare intermediari.</span><span class="sxs-lookup"><span data-stu-id="bedbe-187">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="bedbe-188">Segue un elemento di associazione di sicurezza facoltativo che fornisce funzionalità di sicurezza quali, ad esempio, autorizzazione, autenticazione, protezione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="bedbe-188">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="bedbe-189">Gli elementi di associazione di sicurezza seguenti sono forniti da Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="bedbe-189">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="bedbe-190">Seguono i modelli di messaggio facoltativi specificati dagli elementi di associazione:</span><span class="sxs-lookup"><span data-stu-id="bedbe-190">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="bedbe-191">Quindi gli elementi di associazione di trasporto facoltativi di aggiornamenti/helper:</span><span class="sxs-lookup"><span data-stu-id="bedbe-191">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="bedbe-192">Segue quindi un elemento di associazione obbligatorio di codifica dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="bedbe-192">Next is a required message encoding binding element.</span></span> <span data-ttu-id="bedbe-193">È possibile usare un trasporto proprio o una delle associazioni di codifica del messaggio seguenti:</span><span class="sxs-lookup"><span data-stu-id="bedbe-193">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="bedbe-194">Segue infine un elemento di trasporto obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="bedbe-194">At the bottom is a required transport element.</span></span> <span data-ttu-id="bedbe-195">È possibile usare un trasporto personalizzato o usare uno degli elementi forniti da Windows Communication Foundation (WCF) di associazione del trasporto:</span><span class="sxs-lookup"><span data-stu-id="bedbe-195">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="bedbe-196">Nella tabella seguente viene fornito un riepilogo delle opzioni per ogni livello.</span><span class="sxs-lookup"><span data-stu-id="bedbe-196">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="bedbe-197">Livello</span><span class="sxs-lookup"><span data-stu-id="bedbe-197">Layer</span></span>|<span data-ttu-id="bedbe-198">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bedbe-198">Options</span></span>|<span data-ttu-id="bedbe-199">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="bedbe-199">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="bedbe-200">Flusso transazioni</span><span class="sxs-lookup"><span data-stu-id="bedbe-200">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="bedbe-201">No</span><span class="sxs-lookup"><span data-stu-id="bedbe-201">No</span></span>|
|<span data-ttu-id="bedbe-202">Affidabilità</span><span class="sxs-lookup"><span data-stu-id="bedbe-202">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="bedbe-203">No</span><span class="sxs-lookup"><span data-stu-id="bedbe-203">No</span></span>|
|<span data-ttu-id="bedbe-204">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="bedbe-204">Security</span></span>|<span data-ttu-id="bedbe-205">Simmetrico, asimmetrico, livello di trasporto</span><span class="sxs-lookup"><span data-stu-id="bedbe-205">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="bedbe-206">No</span><span class="sxs-lookup"><span data-stu-id="bedbe-206">No</span></span>|
|<span data-ttu-id="bedbe-207">Cambio di forma</span><span class="sxs-lookup"><span data-stu-id="bedbe-207">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="bedbe-208">No</span><span class="sxs-lookup"><span data-stu-id="bedbe-208">No</span></span>|
|<span data-ttu-id="bedbe-209">Aggiornamenti del trasporto</span><span class="sxs-lookup"><span data-stu-id="bedbe-209">Transport Upgrades</span></span>|<span data-ttu-id="bedbe-210">Flusso SSL, flusso di Windows, resolver Peer</span><span class="sxs-lookup"><span data-stu-id="bedbe-210">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="bedbe-211">No</span><span class="sxs-lookup"><span data-stu-id="bedbe-211">No</span></span>|
|<span data-ttu-id="bedbe-212">Codifica</span><span class="sxs-lookup"><span data-stu-id="bedbe-212">Encoding</span></span>|<span data-ttu-id="bedbe-213">Testo, binario, MTOM, personalizzata</span><span class="sxs-lookup"><span data-stu-id="bedbe-213">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="bedbe-214">Yes</span><span class="sxs-lookup"><span data-stu-id="bedbe-214">Yes</span></span>|
|<span data-ttu-id="bedbe-215">Trasporto</span><span class="sxs-lookup"><span data-stu-id="bedbe-215">Transport</span></span>|<span data-ttu-id="bedbe-216">TCP, named pipe, HTTP, HTTPS, versioni di MSMQ, personalizzato</span><span class="sxs-lookup"><span data-stu-id="bedbe-216">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="bedbe-217">Yes</span><span class="sxs-lookup"><span data-stu-id="bedbe-217">Yes</span></span>|

<span data-ttu-id="bedbe-218">È inoltre possibile definire elementi di associazione personalizzati e inserirli tra i livelli appena elencati.</span><span class="sxs-lookup"><span data-stu-id="bedbe-218">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="bedbe-219">Per una discussione su come usare un'associazione personalizzata per modificare un'associazione fornita dal sistema, vedere [come: Personalizzare un'associazione fornita dal sistema](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="bedbe-219">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bedbe-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bedbe-220">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="bedbe-221">\<binding></span><span class="sxs-lookup"><span data-stu-id="bedbe-221">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="bedbe-222">Associazioni</span><span class="sxs-lookup"><span data-stu-id="bedbe-222">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="bedbe-223">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="bedbe-223">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="bedbe-224">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="bedbe-224">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="bedbe-225">Elemento customBinding</span><span class="sxs-lookup"><span data-stu-id="bedbe-225">customBinding Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="bedbe-226">Associazioni</span><span class="sxs-lookup"><span data-stu-id="bedbe-226">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="bedbe-227">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="bedbe-227">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="bedbe-228">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="bedbe-228">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
