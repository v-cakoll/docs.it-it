---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 8432463ff62e4b5e54a491b574cc6a5285efe220
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397948"
---
# \<issuedTokenParameters>
<span data-ttu-id="fce3c-101">Specifica i parametri per un token di sicurezza emesso in uno scenario di sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="fce3c-101">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**  
  
## <a name="syntax"></a><span data-ttu-id="fce3c-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fce3c-102">Syntax</span></span>  
  
```xml  
<issuedTokenParameters defaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"
                       inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"
                       keySize="Integer"
                       keyType="AsymmetricKey/BearerKey/SymmetricKey"
                       tokenType="String">
  <additionalRequestParameters />
  <claimTypeRequirements>
    <add claimType="URI"
         isOptional="Boolean" />
  </claimTypeRequirements>
  <issuer address="String"
          binding="" />
  <issuerMetadata address="String" />
</issuedTokenParameters>
```  
  
## <a name="type"></a><span data-ttu-id="fce3c-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="fce3c-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fce3c-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fce3c-104">Attributes and Elements</span></span>  
 <span data-ttu-id="fce3c-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fce3c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fce3c-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="fce3c-106">Attributes</span></span>  
  
|<span data-ttu-id="fce3c-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="fce3c-107">Attribute</span></span>|<span data-ttu-id="fce3c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fce3c-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fce3c-109">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="fce3c-109">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="fce3c-110">Specifica le versioni delle specifiche di sicurezza (WS-Security, WS-Trust, WS-Secure Conversation e WS-Security Policy) che devono essere supportate dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="fce3c-110">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="fce3c-111">Questo valore è di tipo <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="fce3c-111">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="fce3c-112">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="fce3c-112">inclusionMode</span></span>|<span data-ttu-id="fce3c-113">Specifica i requisiti di inclusione del token.</span><span class="sxs-lookup"><span data-stu-id="fce3c-113">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="fce3c-114">L'attributo è di tipo <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="fce3c-114">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="fce3c-115">keySize</span><span class="sxs-lookup"><span data-stu-id="fce3c-115">keySize</span></span>|<span data-ttu-id="fce3c-116">Valore intero che specifica le dimensioni di chiave del token.</span><span class="sxs-lookup"><span data-stu-id="fce3c-116">An integer that specifies the token key size.</span></span> <span data-ttu-id="fce3c-117">Il valore predefinito è 256.</span><span class="sxs-lookup"><span data-stu-id="fce3c-117">The default value is 256.</span></span>|  
|<span data-ttu-id="fce3c-118">keyType</span><span class="sxs-lookup"><span data-stu-id="fce3c-118">keyType</span></span>|<span data-ttu-id="fce3c-119">Valore valido di <xref:System.IdentityModel.Tokens.SecurityKeyType> che specifica il tipo di chiave.</span><span class="sxs-lookup"><span data-stu-id="fce3c-119">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="fce3c-120">Il valore predefinito è `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="fce3c-120">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="fce3c-121">tokenType</span><span class="sxs-lookup"><span data-stu-id="fce3c-121">tokenType</span></span>|<span data-ttu-id="fce3c-122">Stringa che specifica il tipo di token.</span><span class="sxs-lookup"><span data-stu-id="fce3c-122">A string that specifies the token type.</span></span> <span data-ttu-id="fce3c-123">Il valore predefinito è http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML.</span><span class="sxs-lookup"><span data-stu-id="fce3c-123">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fce3c-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fce3c-124">Child Elements</span></span>  
  
|<span data-ttu-id="fce3c-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="fce3c-125">Element</span></span>|<span data-ttu-id="fce3c-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fce3c-126">Description</span></span>|  
|-------------|-----------------|  
|[\<additionalRequestParameters>](additionalrequestparameters-element.md)|<span data-ttu-id="fce3c-127">Raccolta di elementi di configurazione che specificano parametri di richiesta aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="fce3c-127">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="fce3c-128">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="fce3c-128">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="fce3c-129">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="fce3c-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="fce3c-130">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="fce3c-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="fce3c-131">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="fce3c-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[\<issuer>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="fce3c-132">Elemento di configurazione che specifica l'endpoint che emette il token corrente.</span><span class="sxs-lookup"><span data-stu-id="fce3c-132">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[\<issuerMetadata>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="fce3c-133">Elemento di configurazione che specifica l'indirizzo dell'endpoint dei metadati dell'emittente del token.</span><span class="sxs-lookup"><span data-stu-id="fce3c-133">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fce3c-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fce3c-134">Parent Elements</span></span>  
  
|<span data-ttu-id="fce3c-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="fce3c-135">Element</span></span>|<span data-ttu-id="fce3c-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fce3c-136">Description</span></span>|  
|-------------|-----------------|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="fce3c-137">Specifica i valori predefiniti usati per iniziare un servizio di conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="fce3c-137">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="fce3c-138">Specifica le opzioni di sicurezza di un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="fce3c-138">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fce3c-139">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fce3c-139">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="fce3c-140">Binding</span><span class="sxs-lookup"><span data-stu-id="fce3c-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fce3c-141">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="fce3c-141">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="fce3c-142">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="fce3c-142">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="fce3c-143">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="fce3c-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="fce3c-144">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="fce3c-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="fce3c-145">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="fce3c-145">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fce3c-146">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="fce3c-146">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fce3c-147">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="fce3c-147">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="fce3c-148">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="fce3c-148">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
