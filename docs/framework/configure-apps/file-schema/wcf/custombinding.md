---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: cdaaacf0dfa75209d001f6e8d6ac7175816048aa
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140800"
---
# \<customBinding>

<span data-ttu-id="979e3-101">Fornisce il controllo completo dello stack di messaggistica per l'utente.</span><span class="sxs-lookup"><span data-stu-id="979e3-101">Provides full control over the messaging stack for the user.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customBinding>**  

## <a name="syntax"></a><span data-ttu-id="979e3-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="979e3-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="979e3-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="979e3-103">Attributes and Elements</span></span>

<span data-ttu-id="979e3-104">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="979e3-104">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="979e3-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="979e3-105">Attributes</span></span>

|<span data-ttu-id="979e3-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="979e3-106">Attribute</span></span>|<span data-ttu-id="979e3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="979e3-107">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="979e3-108">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="979e3-108">closeTimeout</span></span>|<span data-ttu-id="979e3-109">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="979e3-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="979e3-110">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="979e3-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="979e3-111">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="979e3-111">The default is 00:01:00.</span></span>|
|<span data-ttu-id="979e3-112">name</span><span class="sxs-lookup"><span data-stu-id="979e3-112">name</span></span>|<span data-ttu-id="979e3-113">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="979e3-113">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="979e3-114">Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="979e3-114">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="979e3-115">A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome.</span><span class="sxs-lookup"><span data-stu-id="979e3-115">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="979e3-116">Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="979e3-116">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="979e3-117">openTimeout</span><span class="sxs-lookup"><span data-stu-id="979e3-117">openTimeout</span></span>|<span data-ttu-id="979e3-118">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="979e3-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="979e3-119">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="979e3-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="979e3-120">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="979e3-120">The default is 00:01:00.</span></span>|
|<span data-ttu-id="979e3-121">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="979e3-121">receiveTimeout</span></span>|<span data-ttu-id="979e3-122">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="979e3-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="979e3-123">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="979e3-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="979e3-124">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="979e3-124">The default is 00:01:00.</span></span>|
|<span data-ttu-id="979e3-125">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="979e3-125">sendTimeout</span></span>|<span data-ttu-id="979e3-126">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="979e3-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="979e3-127">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="979e3-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="979e3-128">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="979e3-128">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="979e3-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="979e3-129">Child Elements</span></span>

|<span data-ttu-id="979e3-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="979e3-130">Element</span></span>|<span data-ttu-id="979e3-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="979e3-131">Description</span></span>|
|-------------|-----------------|
|[\<compositeDuplex>](compositeduplex.md)|<span data-ttu-id="979e3-132">Specifica la messaggistica bidirezionale sull'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="979e3-132">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="979e3-133">Viene usato con trasporti che non consentono comunicazioni duplex a livello nativo, ad esempio, HTTP.</span><span class="sxs-lookup"><span data-stu-id="979e3-133">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="979e3-134">TCP, al contrario, consente comunicazioni duplex a livello nativo e non richiede l'uso di questo elemento di associazione affinché il servizio invii messaggi a un client.</span><span class="sxs-lookup"><span data-stu-id="979e3-134">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="979e3-135">Il client deve esporre un indirizzo affinché il servizio crei un contatto e stabilisca una connessione.</span><span class="sxs-lookup"><span data-stu-id="979e3-135">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="979e3-136">Questo indirizzo client è fornito dall'attributo `ClientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="979e3-136">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="979e3-137">L'elemento è di tipo <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span><span class="sxs-lookup"><span data-stu-id="979e3-137">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[\<pnrpPeerResolver>](pnrppeerresolver.md)|<span data-ttu-id="979e3-138">Specifica un resolver dei nomi peer PNRP (Peer Name Resolution Protocol).</span><span class="sxs-lookup"><span data-stu-id="979e3-138">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="979e3-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span><span class="sxs-lookup"><span data-stu-id="979e3-139">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[\<reliableSession>](reliablesession.md)|<span data-ttu-id="979e3-140">Specifica l'impostazione per WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="979e3-140">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="979e3-141">Quando questo elemento viene aggiunto a un'associazione personalizzata, il canale risultante può supportare assicurazioni di recapito una volta esatta.</span><span class="sxs-lookup"><span data-stu-id="979e3-141">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="979e3-142">L'elemento è di tipo <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span><span class="sxs-lookup"><span data-stu-id="979e3-142">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="979e3-143">Specifica le opzioni di sicurezza per l'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="979e3-143">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="979e3-144">L'elemento è di tipo <xref:System.ServiceModel.Configuration.SecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="979e3-144">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[\<sslStreamSecurity>](sslstreamsecurity.md)|<span data-ttu-id="979e3-145">Specifica le impostazioni di sicurezza per l'associazione del flusso SSL.</span><span class="sxs-lookup"><span data-stu-id="979e3-145">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="979e3-146">L'elemento è di tipo <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="979e3-146">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[\<transactionFlow>](transactionflow.md)|<span data-ttu-id="979e3-147">Specifica che l'associazione supporta il flusso delle transazioni e il protocollo che deve essere usato dall'attributo `transactionProtocol`.</span><span class="sxs-lookup"><span data-stu-id="979e3-147">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="979e3-148">L'elemento è di tipo <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span><span class="sxs-lookup"><span data-stu-id="979e3-148">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[\<windowsStreamSecurity>](windowsstreamsecurity.md)|<span data-ttu-id="979e3-149">Specifica le opzioni di sicurezza del flusso per un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="979e3-149">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="979e3-150">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="979e3-150">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="979e3-151">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="979e3-151">Parent Elements</span></span>

|<span data-ttu-id="979e3-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="979e3-152">Element</span></span>|<span data-ttu-id="979e3-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="979e3-153">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="979e3-154">associazioni</span><span class="sxs-lookup"><span data-stu-id="979e3-154">bindings</span></span>|<span data-ttu-id="979e3-155">Contiene tutte le associazioni per le applicazioni Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="979e3-155">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="979e3-156">Commenti</span><span class="sxs-lookup"><span data-stu-id="979e3-156">Remarks</span></span>

<span data-ttu-id="979e3-157">Le associazioni personalizzate forniscono il controllo completo dello stack dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="979e3-157">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="979e3-158">È possibile creare associazioni speciali su misura aggiungendo gli elementi di configurazione per le entità specifiche.</span><span class="sxs-lookup"><span data-stu-id="979e3-158">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="979e3-159">Ad esempio, l'utente può combinare la sezione `httpsTransport`, la sezione `reliableSession` e la sezione `security` per creare un'associazione affidabile e protetto basata su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="979e3-159">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="979e3-160">Un'associazione singola definisce lo stack dei messaggi specificando gli elementi di configurazione per gli elementi dello stack nell'ordine in cui vengono visualizzati nello stack.</span><span class="sxs-lookup"><span data-stu-id="979e3-160">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="979e3-161">Ogni elemento definisce e configura un elemento dello stack.</span><span class="sxs-lookup"><span data-stu-id="979e3-161">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="979e3-162">Deve esistere un solo elemento di trasporto in ogni associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="979e3-162">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="979e3-163">Senza questo elemento, lo stack dei messaggi è incompleto.</span><span class="sxs-lookup"><span data-stu-id="979e3-163">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="979e3-164">L'ordine in cui gli elementi vengono visualizzati nello stack è importante, perché è l'ordine in cui le operazioni vengono applicate al messaggio.</span><span class="sxs-lookup"><span data-stu-id="979e3-164">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="979e3-165">L'ordine consigliato per gli elementi dello stack è il seguente:</span><span class="sxs-lookup"><span data-stu-id="979e3-165">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="979e3-166">Transazioni (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="979e3-166">Transactions (optional)</span></span>

2. <span data-ttu-id="979e3-167">Messaggistica affidabile (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="979e3-167">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="979e3-168">Sicurezza (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="979e3-168">Security (optional)</span></span>

4. <span data-ttu-id="979e3-169">Trasporto</span><span class="sxs-lookup"><span data-stu-id="979e3-169">Transport</span></span>

5. <span data-ttu-id="979e3-170">Codificatore (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="979e3-170">Encoder (optional)</span></span>

<span data-ttu-id="979e3-171">Usare un'associazione personalizzata quando una delle associazioni fornite dal sistema non soddisfa i requisiti del servizio.</span><span class="sxs-lookup"><span data-stu-id="979e3-171">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="979e3-172">Un'associazione personalizzata potrebbe essere usata, ad esempio, per abilitare l'uso di un nuovo trasporto o di un nuovo codificatore a un endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="979e3-172">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="979e3-173">Un'associazione personalizzata viene costruita usando uno dei <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> da una raccolta di elementi di associazione in uno stack in un ordine specifico:</span><span class="sxs-lookup"><span data-stu-id="979e3-173">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="979e3-174">All'inizio si trova una classe <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> facoltativa che consente la propagazione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="979e3-174">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="979e3-175">Quindi una classe <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> facoltativa che fornisce una sessione e un meccanismo di ordinamento come definito nella specifica WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="979e3-175">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="979e3-176">Questa nozione di sessione può attraversare SOAP e può trasportare intermediari.</span><span class="sxs-lookup"><span data-stu-id="979e3-176">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="979e3-177">Segue un elemento di associazione di sicurezza facoltativo che fornisce funzionalità di sicurezza quali, ad esempio, autorizzazione, autenticazione, protezione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="979e3-177">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="979e3-178">I seguenti elementi di associazione di sicurezza vengono forniti da Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="979e3-178">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="979e3-179">Seguono i modelli di messaggio facoltativi specificati dagli elementi di associazione:</span><span class="sxs-lookup"><span data-stu-id="979e3-179">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="979e3-180">Quindi gli elementi di associazione di trasporto facoltativi di aggiornamenti/helper:</span><span class="sxs-lookup"><span data-stu-id="979e3-180">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="979e3-181">Segue quindi un elemento di associazione obbligatorio di codifica dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="979e3-181">Next is a required message encoding binding element.</span></span> <span data-ttu-id="979e3-182">È possibile usare un trasporto proprio o una delle associazioni di codifica del messaggio seguenti:</span><span class="sxs-lookup"><span data-stu-id="979e3-182">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="979e3-183">Segue infine un elemento di trasporto obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="979e3-183">At the bottom is a required transport element.</span></span> <span data-ttu-id="979e3-184">È possibile utilizzare il trasporto personalizzato o utilizzare uno degli elementi di associazione del trasporto forniti da Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="979e3-184">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="979e3-185">Nella tabella seguente viene fornito un riepilogo delle opzioni per ogni livello.</span><span class="sxs-lookup"><span data-stu-id="979e3-185">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="979e3-186">Livello</span><span class="sxs-lookup"><span data-stu-id="979e3-186">Layer</span></span>|<span data-ttu-id="979e3-187">Opzioni</span><span class="sxs-lookup"><span data-stu-id="979e3-187">Options</span></span>|<span data-ttu-id="979e3-188">Necessario</span><span class="sxs-lookup"><span data-stu-id="979e3-188">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="979e3-189">Flusso transazioni</span><span class="sxs-lookup"><span data-stu-id="979e3-189">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="979e3-190">No</span><span class="sxs-lookup"><span data-stu-id="979e3-190">No</span></span>|
|<span data-ttu-id="979e3-191">Affidabilità</span><span class="sxs-lookup"><span data-stu-id="979e3-191">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="979e3-192">No</span><span class="sxs-lookup"><span data-stu-id="979e3-192">No</span></span>|
|<span data-ttu-id="979e3-193">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="979e3-193">Security</span></span>|<span data-ttu-id="979e3-194">Simmetrico, asimmetrico, livello di trasporto</span><span class="sxs-lookup"><span data-stu-id="979e3-194">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="979e3-195">No</span><span class="sxs-lookup"><span data-stu-id="979e3-195">No</span></span>|
|<span data-ttu-id="979e3-196">Cambio di forma</span><span class="sxs-lookup"><span data-stu-id="979e3-196">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="979e3-197">No</span><span class="sxs-lookup"><span data-stu-id="979e3-197">No</span></span>|
|<span data-ttu-id="979e3-198">Aggiornamenti del trasporto</span><span class="sxs-lookup"><span data-stu-id="979e3-198">Transport Upgrades</span></span>|<span data-ttu-id="979e3-199">Flusso SSL, flusso di Windows, resolver Peer</span><span class="sxs-lookup"><span data-stu-id="979e3-199">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="979e3-200">No</span><span class="sxs-lookup"><span data-stu-id="979e3-200">No</span></span>|
|<span data-ttu-id="979e3-201">Codifica</span><span class="sxs-lookup"><span data-stu-id="979e3-201">Encoding</span></span>|<span data-ttu-id="979e3-202">Testo, binario, MTOM, personalizzata</span><span class="sxs-lookup"><span data-stu-id="979e3-202">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="979e3-203">Sì</span><span class="sxs-lookup"><span data-stu-id="979e3-203">Yes</span></span>|
|<span data-ttu-id="979e3-204">Trasporto</span><span class="sxs-lookup"><span data-stu-id="979e3-204">Transport</span></span>|<span data-ttu-id="979e3-205">TCP, named pipe, HTTP, HTTPS, versioni di MSMQ, personalizzato</span><span class="sxs-lookup"><span data-stu-id="979e3-205">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="979e3-206">Sì</span><span class="sxs-lookup"><span data-stu-id="979e3-206">Yes</span></span>|

<span data-ttu-id="979e3-207">È inoltre possibile definire elementi di associazione personalizzati e inserirli tra i livelli appena elencati.</span><span class="sxs-lookup"><span data-stu-id="979e3-207">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="979e3-208">Per una discussione su come usare un'associazione personalizzata per modificare un'associazione fornita dal sistema, vedere [procedura: personalizzare un'associazione fornita dal sistema](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="979e3-208">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="979e3-209">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="979e3-209">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<binding>](bindings.md)
- [<span data-ttu-id="979e3-210">Binding</span><span class="sxs-lookup"><span data-stu-id="979e3-210">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="979e3-211">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="979e3-211">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="979e3-212">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="979e3-212">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="979e3-213">CustomBinding (elemento)</span><span class="sxs-lookup"><span data-stu-id="979e3-213">customBinding Element</span></span>](custombinding.md)
- [<span data-ttu-id="979e3-214">Binding</span><span class="sxs-lookup"><span data-stu-id="979e3-214">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="979e3-215">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="979e3-215">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="979e3-216">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="979e3-216">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
