---
title: '&lt;issuerMetadata&gt; di &lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: 74f5c1275eb7ef6a89d355b5ea279363ae6b8026
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546202"
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="f16d4-102">&lt;issuerMetadata&gt; di &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="f16d4-102">&lt;issuerMetadata&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="f16d4-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f16d4-103">\<system.serviceModel></span></span>  
<span data-ttu-id="f16d4-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="f16d4-104">\<bindings></span></span>  
<span data-ttu-id="f16d4-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f16d4-105">\<customBinding></span></span>  
<span data-ttu-id="f16d4-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="f16d4-106">\<binding></span></span>  
<span data-ttu-id="f16d4-107">\<security></span><span class="sxs-lookup"><span data-stu-id="f16d4-107">\<security></span></span>  
<span data-ttu-id="f16d4-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="f16d4-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="f16d4-109">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="f16d4-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f16d4-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f16d4-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f16d4-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f16d4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f16d4-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f16d4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f16d4-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="f16d4-113">Attributes</span></span>  
  
|<span data-ttu-id="f16d4-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="f16d4-114">Attribute</span></span>|<span data-ttu-id="f16d4-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f16d4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f16d4-116">address</span><span class="sxs-lookup"><span data-stu-id="f16d4-116">address</span></span>|<span data-ttu-id="f16d4-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f16d4-117">Required.</span></span> <span data-ttu-id="f16d4-118">Stringa che specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="f16d4-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="f16d4-119">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="f16d4-119">The address must be an absolute URI.</span></span> <span data-ttu-id="f16d4-120">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="f16d4-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f16d4-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f16d4-121">Child Elements</span></span>  
  
|<span data-ttu-id="f16d4-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="f16d4-122">Element</span></span>|<span data-ttu-id="f16d4-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f16d4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f16d4-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="f16d4-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="f16d4-125">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="f16d4-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="f16d4-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="f16d4-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="f16d4-127">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="f16d4-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f16d4-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f16d4-128">Parent Elements</span></span>  
  
|<span data-ttu-id="f16d4-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="f16d4-129">Element</span></span>|<span data-ttu-id="f16d4-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f16d4-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f16d4-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="f16d4-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="f16d4-132">Specifica i parametri di un token di sicurezza emesso in uno scenario di sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="f16d4-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f16d4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f16d4-133">See also</span></span>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f16d4-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="f16d4-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f16d4-135">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="f16d4-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f16d4-136">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="f16d4-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="f16d4-137">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="f16d4-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f16d4-138">Associazioni</span><span class="sxs-lookup"><span data-stu-id="f16d4-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f16d4-139">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="f16d4-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f16d4-140">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="f16d4-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f16d4-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f16d4-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="f16d4-142">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f16d4-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="f16d4-143">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="f16d4-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
