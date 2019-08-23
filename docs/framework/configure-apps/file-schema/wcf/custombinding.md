---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: 0b6f26c7b9e9d02b3ff20b53f42b09d671699ea5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919383"
---
# <a name="custombinding"></a><span data-ttu-id="99ec9-101">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="99ec9-101">\<customBinding></span></span>

<span data-ttu-id="99ec9-102">Fornisce il controllo completo dello stack di messaggistica per l'utente.</span><span class="sxs-lookup"><span data-stu-id="99ec9-102">Provides full control over the messaging stack for the user.</span></span>

<span data-ttu-id="99ec9-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="99ec9-103">\<system.serviceModel></span></span>\
<span data-ttu-id="99ec9-104">\<Binding > </span><span class="sxs-lookup"><span data-stu-id="99ec9-104">\<bindings></span></span>\
<span data-ttu-id="99ec9-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="99ec9-105">\<customBinding></span></span>

## <a name="syntax"></a><span data-ttu-id="99ec9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99ec9-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="99ec9-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="99ec9-107">Attributes and Elements</span></span>

<span data-ttu-id="99ec9-108">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="99ec9-108">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="99ec9-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="99ec9-109">Attributes</span></span>

|<span data-ttu-id="99ec9-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="99ec9-110">Attribute</span></span>|<span data-ttu-id="99ec9-111">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="99ec9-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="99ec9-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="99ec9-112">closeTimeout</span></span>|<span data-ttu-id="99ec9-113">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="99ec9-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="99ec9-114">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="99ec9-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="99ec9-115">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="99ec9-115">The default is 00:01:00.</span></span>|
|<span data-ttu-id="99ec9-116">name</span><span class="sxs-lookup"><span data-stu-id="99ec9-116">name</span></span>|<span data-ttu-id="99ec9-117">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="99ec9-117">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="99ec9-118">Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="99ec9-118">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="99ec9-119">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="99ec9-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="99ec9-120">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="99ec9-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="99ec9-121">openTimeout</span><span class="sxs-lookup"><span data-stu-id="99ec9-121">openTimeout</span></span>|<span data-ttu-id="99ec9-122">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="99ec9-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="99ec9-123">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="99ec9-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="99ec9-124">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="99ec9-124">The default is 00:01:00.</span></span>|
|<span data-ttu-id="99ec9-125">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="99ec9-125">receiveTimeout</span></span>|<span data-ttu-id="99ec9-126">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="99ec9-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="99ec9-127">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="99ec9-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="99ec9-128">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="99ec9-128">The default is 00:01:00.</span></span>|
|<span data-ttu-id="99ec9-129">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="99ec9-129">sendTimeout</span></span>|<span data-ttu-id="99ec9-130">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="99ec9-130">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="99ec9-131">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="99ec9-131">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="99ec9-132">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="99ec9-132">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="99ec9-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="99ec9-133">Child Elements</span></span>

|<span data-ttu-id="99ec9-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="99ec9-134">Element</span></span>|<span data-ttu-id="99ec9-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99ec9-135">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="99ec9-136">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="99ec9-136">\<compositeDuplex></span></span>](compositeduplex.md)|<span data-ttu-id="99ec9-137">Specifica la messaggistica bidirezionale sull'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="99ec9-137">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="99ec9-138">Viene usato con trasporti che non consentono comunicazioni duplex a livello nativo, ad esempio, HTTP.</span><span class="sxs-lookup"><span data-stu-id="99ec9-138">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="99ec9-139">TCP, al contrario, consente comunicazioni duplex a livello nativo e non richiede l'uso di questo elemento di associazione affinché il servizio invii messaggi a un client.</span><span class="sxs-lookup"><span data-stu-id="99ec9-139">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="99ec9-140">Il client deve esporre un indirizzo affinché il servizio crei un contatto e stabilisca una connessione.</span><span class="sxs-lookup"><span data-stu-id="99ec9-140">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="99ec9-141">Questo indirizzo client è fornito dall'attributo `ClientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="99ec9-141">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="99ec9-142">L'elemento è di tipo <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span><span class="sxs-lookup"><span data-stu-id="99ec9-142">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[<span data-ttu-id="99ec9-143">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="99ec9-143">\<pnrpPeerResolver></span></span>](pnrppeerresolver.md)|<span data-ttu-id="99ec9-144">Specifica un resolver dei nomi peer PNRP (Peer Name Resolution Protocol).</span><span class="sxs-lookup"><span data-stu-id="99ec9-144">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="99ec9-145">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span><span class="sxs-lookup"><span data-stu-id="99ec9-145">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[<span data-ttu-id="99ec9-146">\<reliableSession></span><span class="sxs-lookup"><span data-stu-id="99ec9-146">\<reliableSession></span></span>](reliablesession.md)|<span data-ttu-id="99ec9-147">Specifica l'impostazione per WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="99ec9-147">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="99ec9-148">Quando questo elemento viene aggiunto a un'associazione personalizzata, il canale risultante può supportare assicurazioni di recapito una volta esatta.</span><span class="sxs-lookup"><span data-stu-id="99ec9-148">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="99ec9-149">L'elemento è di tipo <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span><span class="sxs-lookup"><span data-stu-id="99ec9-149">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[<span data-ttu-id="99ec9-150">\<security></span><span class="sxs-lookup"><span data-stu-id="99ec9-150">\<security></span></span>](security-of-custombinding.md)|<span data-ttu-id="99ec9-151">Specifica le opzioni di sicurezza per l'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="99ec9-151">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="99ec9-152">L'elemento è di tipo <xref:System.ServiceModel.Configuration.SecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="99ec9-152">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[<span data-ttu-id="99ec9-153">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="99ec9-153">\<sslStreamSecurity></span></span>](sslstreamsecurity.md)|<span data-ttu-id="99ec9-154">Specifica le impostazioni di sicurezza per l'associazione del flusso SSL.</span><span class="sxs-lookup"><span data-stu-id="99ec9-154">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="99ec9-155">L'elemento è di tipo <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="99ec9-155">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[<span data-ttu-id="99ec9-156">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="99ec9-156">\<transactionFlow></span></span>](transactionflow.md)|<span data-ttu-id="99ec9-157">Specifica che l'associazione supporta il flusso delle transazioni e il protocollo che deve essere usato dall'attributo `transactionProtocol`.</span><span class="sxs-lookup"><span data-stu-id="99ec9-157">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="99ec9-158">L'elemento è di tipo <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span><span class="sxs-lookup"><span data-stu-id="99ec9-158">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[<span data-ttu-id="99ec9-159">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="99ec9-159">\<windowsStreamSecurity></span></span>](windowsstreamsecurity.md)|<span data-ttu-id="99ec9-160">Specifica le opzioni di sicurezza del flusso per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="99ec9-160">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="99ec9-161">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="99ec9-161">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="99ec9-162">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="99ec9-162">Parent Elements</span></span>

|<span data-ttu-id="99ec9-163">Elemento</span><span class="sxs-lookup"><span data-stu-id="99ec9-163">Element</span></span>|<span data-ttu-id="99ec9-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99ec9-164">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="99ec9-165">associazioni</span><span class="sxs-lookup"><span data-stu-id="99ec9-165">bindings</span></span>|<span data-ttu-id="99ec9-166">Contiene tutte le associazioni per le applicazioni Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="99ec9-166">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="99ec9-167">Note</span><span class="sxs-lookup"><span data-stu-id="99ec9-167">Remarks</span></span>

<span data-ttu-id="99ec9-168">Le associazioni personalizzate forniscono il controllo completo dello stack dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="99ec9-168">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="99ec9-169">È possibile creare associazioni speciali su misura aggiungendo gli elementi di configurazione per le entità specifiche.</span><span class="sxs-lookup"><span data-stu-id="99ec9-169">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="99ec9-170">Ad esempio, l'utente può combinare la sezione `httpsTransport`, la sezione `reliableSession` e la sezione `security` per creare un'associazione affidabile e protetto basata su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="99ec9-170">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="99ec9-171">Un'associazione singola definisce lo stack dei messaggi specificando gli elementi di configurazione per gli elementi dello stack nell'ordine in cui vengono visualizzati nello stack.</span><span class="sxs-lookup"><span data-stu-id="99ec9-171">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="99ec9-172">Ogni elemento definisce e configura un elemento dello stack.</span><span class="sxs-lookup"><span data-stu-id="99ec9-172">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="99ec9-173">Deve esistere un solo elemento di trasporto in ogni associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="99ec9-173">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="99ec9-174">Senza questo elemento, lo stack dei messaggi è incompleto.</span><span class="sxs-lookup"><span data-stu-id="99ec9-174">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="99ec9-175">L'ordine in cui gli elementi vengono visualizzati nello stack è importante, perché è l'ordine in cui le operazioni vengono applicate al messaggio.</span><span class="sxs-lookup"><span data-stu-id="99ec9-175">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="99ec9-176">L'ordine consigliato per gli elementi dello stack è il seguente:</span><span class="sxs-lookup"><span data-stu-id="99ec9-176">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="99ec9-177">Transazioni (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="99ec9-177">Transactions (optional)</span></span>

2. <span data-ttu-id="99ec9-178">Messaggistica affidabile (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="99ec9-178">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="99ec9-179">Sicurezza (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="99ec9-179">Security (optional)</span></span>

4. <span data-ttu-id="99ec9-180">Trasporto</span><span class="sxs-lookup"><span data-stu-id="99ec9-180">Transport</span></span>

5. <span data-ttu-id="99ec9-181">Codificatore (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="99ec9-181">Encoder (optional)</span></span>

<span data-ttu-id="99ec9-182">Usare un'associazione personalizzata quando una delle associazioni fornite dal sistema non soddisfa i requisiti del servizio.</span><span class="sxs-lookup"><span data-stu-id="99ec9-182">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="99ec9-183">Un'associazione personalizzata potrebbe essere usata, ad esempio, per abilitare l'uso di un nuovo trasporto o di un nuovo codificatore a un endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="99ec9-183">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="99ec9-184">Un'associazione personalizzata viene costruita usando uno dei <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> da una raccolta di elementi di associazione in uno stack in un ordine specifico:</span><span class="sxs-lookup"><span data-stu-id="99ec9-184">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="99ec9-185">All'inizio si trova una classe <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> facoltativa che consente la propagazione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="99ec9-185">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="99ec9-186">Quindi una classe <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> facoltativa che fornisce una sessione e un meccanismo di ordinamento come definito nella specifica WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="99ec9-186">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="99ec9-187">Questa nozione di sessione può attraversare SOAP e può trasportare intermediari.</span><span class="sxs-lookup"><span data-stu-id="99ec9-187">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="99ec9-188">Segue un elemento di associazione di sicurezza facoltativo che fornisce funzionalità di sicurezza quali, ad esempio, autorizzazione, autenticazione, protezione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="99ec9-188">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="99ec9-189">I seguenti elementi di associazione di sicurezza vengono forniti da Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="99ec9-189">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="99ec9-190">Seguono i modelli di messaggio facoltativi specificati dagli elementi di associazione:</span><span class="sxs-lookup"><span data-stu-id="99ec9-190">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="99ec9-191">Quindi gli elementi di associazione di trasporto facoltativi di aggiornamenti/helper:</span><span class="sxs-lookup"><span data-stu-id="99ec9-191">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="99ec9-192">Segue quindi un elemento di associazione obbligatorio di codifica dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="99ec9-192">Next is a required message encoding binding element.</span></span> <span data-ttu-id="99ec9-193">È possibile usare un trasporto proprio o una delle associazioni di codifica del messaggio seguenti:</span><span class="sxs-lookup"><span data-stu-id="99ec9-193">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="99ec9-194">Segue infine un elemento di trasporto obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="99ec9-194">At the bottom is a required transport element.</span></span> <span data-ttu-id="99ec9-195">È possibile utilizzare il trasporto personalizzato o utilizzare uno degli elementi di associazione del trasporto forniti da Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="99ec9-195">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="99ec9-196">Nella tabella seguente viene fornito un riepilogo delle opzioni per ogni livello.</span><span class="sxs-lookup"><span data-stu-id="99ec9-196">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="99ec9-197">Livello</span><span class="sxs-lookup"><span data-stu-id="99ec9-197">Layer</span></span>|<span data-ttu-id="99ec9-198">Opzioni</span><span class="sxs-lookup"><span data-stu-id="99ec9-198">Options</span></span>|<span data-ttu-id="99ec9-199">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="99ec9-199">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="99ec9-200">Flusso transazioni</span><span class="sxs-lookup"><span data-stu-id="99ec9-200">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="99ec9-201">No</span><span class="sxs-lookup"><span data-stu-id="99ec9-201">No</span></span>|
|<span data-ttu-id="99ec9-202">Affidabilità</span><span class="sxs-lookup"><span data-stu-id="99ec9-202">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="99ec9-203">No</span><span class="sxs-lookup"><span data-stu-id="99ec9-203">No</span></span>|
|<span data-ttu-id="99ec9-204">Security</span><span class="sxs-lookup"><span data-stu-id="99ec9-204">Security</span></span>|<span data-ttu-id="99ec9-205">Simmetrico, asimmetrico, livello di trasporto</span><span class="sxs-lookup"><span data-stu-id="99ec9-205">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="99ec9-206">No</span><span class="sxs-lookup"><span data-stu-id="99ec9-206">No</span></span>|
|<span data-ttu-id="99ec9-207">Cambio di forma</span><span class="sxs-lookup"><span data-stu-id="99ec9-207">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="99ec9-208">No</span><span class="sxs-lookup"><span data-stu-id="99ec9-208">No</span></span>|
|<span data-ttu-id="99ec9-209">Aggiornamenti del trasporto</span><span class="sxs-lookup"><span data-stu-id="99ec9-209">Transport Upgrades</span></span>|<span data-ttu-id="99ec9-210">Flusso SSL, flusso di Windows, resolver Peer</span><span class="sxs-lookup"><span data-stu-id="99ec9-210">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="99ec9-211">No</span><span class="sxs-lookup"><span data-stu-id="99ec9-211">No</span></span>|
|<span data-ttu-id="99ec9-212">Codifica</span><span class="sxs-lookup"><span data-stu-id="99ec9-212">Encoding</span></span>|<span data-ttu-id="99ec9-213">Testo, binario, MTOM, personalizzata</span><span class="sxs-lookup"><span data-stu-id="99ec9-213">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="99ec9-214">Sì</span><span class="sxs-lookup"><span data-stu-id="99ec9-214">Yes</span></span>|
|<span data-ttu-id="99ec9-215">Trasporto</span><span class="sxs-lookup"><span data-stu-id="99ec9-215">Transport</span></span>|<span data-ttu-id="99ec9-216">TCP, named pipe, HTTP, HTTPS, versioni di MSMQ, personalizzato</span><span class="sxs-lookup"><span data-stu-id="99ec9-216">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="99ec9-217">Sì</span><span class="sxs-lookup"><span data-stu-id="99ec9-217">Yes</span></span>|

<span data-ttu-id="99ec9-218">È inoltre possibile definire elementi di associazione personalizzati e inserirli tra i livelli appena elencati.</span><span class="sxs-lookup"><span data-stu-id="99ec9-218">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="99ec9-219">Per informazioni su come usare un'associazione personalizzata per modificare un'associazione fornita dal sistema, vedere [procedura: Personalizzare un'associazione](../../../wcf/extending/how-to-customize-a-system-provided-binding.md)fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="99ec9-219">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="99ec9-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99ec9-220">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="99ec9-221">\<binding></span><span class="sxs-lookup"><span data-stu-id="99ec9-221">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="99ec9-222">Associazioni</span><span class="sxs-lookup"><span data-stu-id="99ec9-222">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="99ec9-223">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="99ec9-223">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="99ec9-224">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="99ec9-224">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="99ec9-225">CustomBinding (elemento)</span><span class="sxs-lookup"><span data-stu-id="99ec9-225">customBinding Element</span></span>](custombinding.md)
- [<span data-ttu-id="99ec9-226">Associazioni</span><span class="sxs-lookup"><span data-stu-id="99ec9-226">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="99ec9-227">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="99ec9-227">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="99ec9-228">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="99ec9-228">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
