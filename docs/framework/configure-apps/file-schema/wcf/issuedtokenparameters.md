---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 6bdf56e3d2084dec8d44e1c4d3f0c1e50b711b92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758237"
---
# <a name="issuedtokenparameters"></a><span data-ttu-id="8812b-101">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="8812b-101">\<issuedTokenParameters></span></span>
<span data-ttu-id="8812b-102">Specifica i parametri per un token di sicurezza emesso in uno scenario di sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="8812b-102">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="8812b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8812b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="8812b-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="8812b-104">\<bindings></span></span>  
<span data-ttu-id="8812b-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8812b-105">\<customBinding></span></span>  
<span data-ttu-id="8812b-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="8812b-106">\<binding></span></span>  
<span data-ttu-id="8812b-107">\<security></span><span class="sxs-lookup"><span data-stu-id="8812b-107">\<security></span></span>  
<span data-ttu-id="8812b-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="8812b-108">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8812b-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8812b-109">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="8812b-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="8812b-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8812b-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8812b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8812b-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8812b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8812b-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="8812b-113">Attributes</span></span>  
  
|<span data-ttu-id="8812b-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="8812b-114">Attribute</span></span>|<span data-ttu-id="8812b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8812b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8812b-116">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="8812b-116">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="8812b-117">Specifica le versioni delle specifiche di sicurezza (WS-Security, WS-Trust, WS-Secure Conversation e WS-Security Policy) che devono essere supportate dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="8812b-117">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="8812b-118">Questo valore è di tipo <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="8812b-118">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="8812b-119">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="8812b-119">inclusionMode</span></span>|<span data-ttu-id="8812b-120">Specifica i requisiti di inclusione del token.</span><span class="sxs-lookup"><span data-stu-id="8812b-120">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="8812b-121">L'attributo è di tipo <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="8812b-121">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="8812b-122">keySize</span><span class="sxs-lookup"><span data-stu-id="8812b-122">keySize</span></span>|<span data-ttu-id="8812b-123">Valore intero che specifica le dimensioni di chiave del token.</span><span class="sxs-lookup"><span data-stu-id="8812b-123">An integer that specifies the token key size.</span></span> <span data-ttu-id="8812b-124">Il valore predefinito è 256.</span><span class="sxs-lookup"><span data-stu-id="8812b-124">The default value is 256.</span></span>|  
|<span data-ttu-id="8812b-125">keyType</span><span class="sxs-lookup"><span data-stu-id="8812b-125">keyType</span></span>|<span data-ttu-id="8812b-126">Valore valido di <xref:System.IdentityModel.Tokens.SecurityKeyType> che specifica il tipo di chiave.</span><span class="sxs-lookup"><span data-stu-id="8812b-126">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="8812b-127">Il valore predefinito è `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="8812b-127">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="8812b-128">tokenType</span><span class="sxs-lookup"><span data-stu-id="8812b-128">tokenType</span></span>|<span data-ttu-id="8812b-129">Stringa che specifica il tipo di token.</span><span class="sxs-lookup"><span data-stu-id="8812b-129">A string that specifies the token type.</span></span> <span data-ttu-id="8812b-130">Il valore predefinito è http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML.</span><span class="sxs-lookup"><span data-stu-id="8812b-130">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8812b-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8812b-131">Child Elements</span></span>  
  
|<span data-ttu-id="8812b-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="8812b-132">Element</span></span>|<span data-ttu-id="8812b-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8812b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8812b-134">\<additionalRequestParameters></span><span class="sxs-lookup"><span data-stu-id="8812b-134">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="8812b-135">Raccolta di elementi di configurazione che specificano parametri di richiesta aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="8812b-135">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="8812b-136">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="8812b-136">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="8812b-137">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8812b-137">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="8812b-138">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="8812b-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="8812b-139">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="8812b-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="8812b-140">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="8812b-140">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="8812b-141">\<issuer></span><span class="sxs-lookup"><span data-stu-id="8812b-141">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="8812b-142">Elemento di configurazione che specifica l'endpoint che emette il token corrente.</span><span class="sxs-lookup"><span data-stu-id="8812b-142">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="8812b-143">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="8812b-143">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="8812b-144">Elemento di configurazione che specifica l'indirizzo dell'endpoint dei metadati dell'emittente del token.</span><span class="sxs-lookup"><span data-stu-id="8812b-144">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8812b-145">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8812b-145">Parent Elements</span></span>  
  
|<span data-ttu-id="8812b-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="8812b-146">Element</span></span>|<span data-ttu-id="8812b-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8812b-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8812b-148">\<secureConversationBootstrap></span><span class="sxs-lookup"><span data-stu-id="8812b-148">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="8812b-149">Specifica i valori predefiniti usati per iniziare un servizio di conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="8812b-149">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="8812b-150">\<security></span><span class="sxs-lookup"><span data-stu-id="8812b-150">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="8812b-151">Specifica le opzioni di sicurezza di un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8812b-151">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8812b-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8812b-152">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8812b-153">Associazioni</span><span class="sxs-lookup"><span data-stu-id="8812b-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8812b-154">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="8812b-154">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8812b-155">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="8812b-155">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8812b-156">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8812b-156">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="8812b-157">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="8812b-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="8812b-158">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="8812b-158">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="8812b-159">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="8812b-159">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8812b-160">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="8812b-160">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8812b-161">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="8812b-161">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="8812b-162">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="8812b-162">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
