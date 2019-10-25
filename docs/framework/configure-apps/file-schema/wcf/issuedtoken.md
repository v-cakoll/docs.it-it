---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 56439748926ada642018f48a5787634a50d0f180
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846864"
---
# <a name="issuedtoken"></a><span data-ttu-id="1fad8-101">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="1fad8-101">\<issuedToken></span></span>
<span data-ttu-id="1fad8-102">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="1fad8-102">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
<span data-ttu-id="1fad8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1fad8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1fad8-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1fad8-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1fad8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**comportamenti**](behaviors.md)\<</span><span class="sxs-lookup"><span data-stu-id="1fad8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1fad8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**endpointBehaviors**](endpointbehaviors.md) ></span><span class="sxs-lookup"><span data-stu-id="1fad8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="1fad8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **&nbsp;&nbsp;\<** ](behavior-of-endpointbehaviors.md) ></span><span class="sxs-lookup"><span data-stu-id="1fad8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\</span></span>
<span data-ttu-id="1fad8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**ClientCredentials**](clientcredentials.md) ></span><span class="sxs-lookup"><span data-stu-id="1fad8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="1fad8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**IssuedToken** ></span><span class="sxs-lookup"><span data-stu-id="1fad8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedToken>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fad8-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1fad8-110">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fad8-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1fad8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1fad8-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1fad8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fad8-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="1fad8-113">Attributes</span></span>  
  
|<span data-ttu-id="1fad8-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="1fad8-114">Attribute</span></span>|<span data-ttu-id="1fad8-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fad8-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="1fad8-116">Attributo booleano facoltativo che specifica se i token vengono memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="1fad8-116">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="1fad8-117">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="1fad8-117">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="1fad8-118">Attributo stringa facoltativo che specifica quali valori casuali (entropie) sono usati per le operazioni di handshake.</span><span class="sxs-lookup"><span data-stu-id="1fad8-118">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="1fad8-119">I valori comprendono `ClientEntropy`, `ServerEntropy` e `CombinedEntropy`. Il valore predefinito `CombinedEntropy`.</span><span class="sxs-lookup"><span data-stu-id="1fad8-119">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="1fad8-120">L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span><span class="sxs-lookup"><span data-stu-id="1fad8-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="1fad8-121">Attributo intero facoltativo che specifica la percentuale di un intervallo di tempo valido (fornito dall'emittente del token) che può trascorrere prima che un token venga rinnovato.</span><span class="sxs-lookup"><span data-stu-id="1fad8-121">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="1fad8-122">I valori sono compresi tra 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="1fad8-122">Values are from 0 to 100.</span></span> <span data-ttu-id="1fad8-123">Il valore predefinito è 60 e indica che una volta trascorso il 60% dell'intervallo di tempo il sistema esegue un tentativo di rinnovo.</span><span class="sxs-lookup"><span data-stu-id="1fad8-123">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="1fad8-124">Attributo facoltativo che specifica i comportamenti di canale da usare quando si comunica con l'emittente.</span><span class="sxs-lookup"><span data-stu-id="1fad8-124">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="1fad8-125">Attributo facoltativo che specifica i comportamenti di canale da usare quando si comunica con l'emittente locale.</span><span class="sxs-lookup"><span data-stu-id="1fad8-125">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="1fad8-126">Attributo Timespan facoltativo che, quando l'emittente del token (un servizio token di sicurezza) non specifica alcun intervallo, definisce la durata di memorizzazione nella cache dei token emessi.</span><span class="sxs-lookup"><span data-stu-id="1fad8-126">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="1fad8-127">Il valore predefinito è "10675199.02:48:05.4775807".</span><span class="sxs-lookup"><span data-stu-id="1fad8-127">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1fad8-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1fad8-128">Child Elements</span></span>  
  
|<span data-ttu-id="1fad8-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="1fad8-129">Element</span></span>|<span data-ttu-id="1fad8-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fad8-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fad8-131">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="1fad8-131">\<localIssuer></span></span>](localissuer.md)|<span data-ttu-id="1fad8-132">Specifica l'indirizzo dell'emittente locale del token e l'associazione usata per comunicare con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1fad8-132">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[<span data-ttu-id="1fad8-133">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1fad8-133">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="1fad8-134">Specifica i comportamenti di endpoint da usare quando si contatta un'emittente locale.</span><span class="sxs-lookup"><span data-stu-id="1fad8-134">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1fad8-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1fad8-135">Parent Elements</span></span>  
  
|<span data-ttu-id="1fad8-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="1fad8-136">Element</span></span>|<span data-ttu-id="1fad8-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fad8-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1fad8-138">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="1fad8-138">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="1fad8-139">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="1fad8-139">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fad8-140">Note</span><span class="sxs-lookup"><span data-stu-id="1fad8-140">Remarks</span></span>  
 <span data-ttu-id="1fad8-141">Un token emesso è un tipo di credenziale personalizzato usato, ad esempio, quando si esegue l'autenticazione con un servizio token di sicurezza in uno scenario federato.</span><span class="sxs-lookup"><span data-stu-id="1fad8-141">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="1fad8-142">Per impostazione predefinita, il token è un token SAML.</span><span class="sxs-lookup"><span data-stu-id="1fad8-142">By default, the token is a SAML token.</span></span> <span data-ttu-id="1fad8-143">Per altre informazioni, vedere [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md), [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="1fad8-143">For more information, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md), and [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="1fad8-144">Questa sezione contiene gli elementi usati per configurare un'autorità emittente locale di token oppure i comportamenti usati in un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1fad8-144">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="1fad8-145">Per istruzioni sulla configurazione di un client per l'uso di un'autorità emittente locale, vedere [procedura: configurare un'autorità emittente locale](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="1fad8-145">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fad8-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fad8-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="1fad8-147">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="1fad8-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="1fad8-148">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="1fad8-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1fad8-149">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="1fad8-149">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1fad8-150">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="1fad8-150">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="1fad8-151">Procedura: Creare un client federato</span><span class="sxs-lookup"><span data-stu-id="1fad8-151">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="1fad8-152">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="1fad8-152">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="1fad8-153">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="1fad8-153">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
