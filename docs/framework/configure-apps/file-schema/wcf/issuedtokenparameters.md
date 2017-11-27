---
title: '&lt;issuedTokenParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ef68585054d61de8c25b7e3effd1d72063d4589c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuedtokenparametersgt"></a><span data-ttu-id="136d1-102">&lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="136d1-102">&lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="136d1-103">Specifica i parametri per un token di sicurezza emesso in uno scenario di sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="136d1-103">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="136d1-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="136d1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="136d1-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="136d1-105">\<bindings></span></span>  
<span data-ttu-id="136d1-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="136d1-106">\<customBinding></span></span>  
<span data-ttu-id="136d1-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="136d1-107">\<binding></span></span>  
<span data-ttu-id="136d1-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="136d1-108">\<security></span></span>  
<span data-ttu-id="136d1-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="136d1-109">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="136d1-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="136d1-110">Syntax</span></span>  
  
```xml  
<issuedTokenParameters   
      DefaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"  
      inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"  
      keySize="Integer"  
   keyType="AsymmetricKey/BearerKey/SymmetricKey"  
      tokenType="String" >  
   <additionalRequestParameters />  
      <claimTypeRequirements>  
            <add claimType="URI"  
           isOptional="Boolean" />  
      </claimTypeRequirements>  
      <issuer address="String"   
                      binding=" " />  
      <issuerMetadata address="String" />   
</issuedTokenParameters>  
```  
  
## <a name="type"></a><span data-ttu-id="136d1-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="136d1-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="136d1-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="136d1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="136d1-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="136d1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="136d1-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="136d1-114">Attributes</span></span>  
  
|<span data-ttu-id="136d1-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="136d1-115">Attribute</span></span>|<span data-ttu-id="136d1-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="136d1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="136d1-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="136d1-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="136d1-118">Specifica le versioni delle specifiche di sicurezza (WS-Security, WS-Trust, WS-Secure Conversation e WS-Security Policy) che devono essere supportate dall'associazione.</span><span class="sxs-lookup"><span data-stu-id="136d1-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="136d1-119">Questo valore è di tipo <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="136d1-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="136d1-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="136d1-120">inclusionMode</span></span>|<span data-ttu-id="136d1-121">Specifica i requisiti di inclusione del token.</span><span class="sxs-lookup"><span data-stu-id="136d1-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="136d1-122">L'attributo è di tipo <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="136d1-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="136d1-123">keySize</span><span class="sxs-lookup"><span data-stu-id="136d1-123">keySize</span></span>|<span data-ttu-id="136d1-124">Valore intero che specifica le dimensioni di chiave del token.</span><span class="sxs-lookup"><span data-stu-id="136d1-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="136d1-125">Il valore predefinito è 256.</span><span class="sxs-lookup"><span data-stu-id="136d1-125">The default value is 256.</span></span>|  
|<span data-ttu-id="136d1-126">keyType</span><span class="sxs-lookup"><span data-stu-id="136d1-126">keyType</span></span>|<span data-ttu-id="136d1-127">Valore valido di <xref:System.IdentityModel.Tokens.SecurityKeyType> che specifica il tipo di chiave.</span><span class="sxs-lookup"><span data-stu-id="136d1-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="136d1-128">Il valore predefinito è `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="136d1-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="136d1-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="136d1-129">tokenType</span></span>|<span data-ttu-id="136d1-130">Stringa che specifica il tipo di token.</span><span class="sxs-lookup"><span data-stu-id="136d1-130">A string that specifies the token type.</span></span> <span data-ttu-id="136d1-131">L'impostazione predefinita è "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="136d1-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="136d1-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="136d1-132">Child Elements</span></span>  
  
|<span data-ttu-id="136d1-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="136d1-133">Element</span></span>|<span data-ttu-id="136d1-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="136d1-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="136d1-135">\<additionalRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="136d1-135">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="136d1-136">Raccolta di elementi di configurazione che specificano parametri di richiesta aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="136d1-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="136d1-137">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="136d1-137">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="136d1-138">Specifica una raccolta di tipi di attestazione obbligatori.</span><span class="sxs-lookup"><span data-stu-id="136d1-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="136d1-139">In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso.</span><span class="sxs-lookup"><span data-stu-id="136d1-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="136d1-140">Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="136d1-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="136d1-141">Ogni elemento di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.</span><span class="sxs-lookup"><span data-stu-id="136d1-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="136d1-142">\<autorità di certificazione ></span><span class="sxs-lookup"><span data-stu-id="136d1-142">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="136d1-143">Elemento di configurazione che specifica l'endpoint che emette il token corrente.</span><span class="sxs-lookup"><span data-stu-id="136d1-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="136d1-144">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="136d1-144">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="136d1-145">Elemento di configurazione che specifica l'indirizzo dell'endpoint dei metadati dell'emittente del token.</span><span class="sxs-lookup"><span data-stu-id="136d1-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="136d1-146">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="136d1-146">Parent Elements</span></span>  
  
|<span data-ttu-id="136d1-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="136d1-147">Element</span></span>|<span data-ttu-id="136d1-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="136d1-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="136d1-149">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="136d1-149">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="136d1-150">Specifica i valori predefiniti usati per iniziare un servizio di conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="136d1-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="136d1-151">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="136d1-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="136d1-152">Specifica le opzioni di sicurezza di un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="136d1-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="136d1-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="136d1-153">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="136d1-154">Associazioni</span><span class="sxs-lookup"><span data-stu-id="136d1-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="136d1-155">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="136d1-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="136d1-156">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="136d1-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="136d1-157">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="136d1-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="136d1-158">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="136d1-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="136d1-159">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="136d1-159">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)  
 [<span data-ttu-id="136d1-160">L'autenticazione e identità del servizio</span><span class="sxs-lookup"><span data-stu-id="136d1-160">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="136d1-161">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="136d1-161">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="136d1-162">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="136d1-162">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="136d1-163">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="136d1-163">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
