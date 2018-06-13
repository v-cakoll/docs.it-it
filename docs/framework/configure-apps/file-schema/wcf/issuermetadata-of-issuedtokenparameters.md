---
title: '&lt;issuerMetadata&gt; di &lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: 82c04fe71ec67b2c539dae9c41eb35350c72d923
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746514"
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="1bd3a-102">&lt;issuerMetadata&gt; di &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="1bd3a-102">&lt;issuerMetadata&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="1bd3a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1bd3a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="1bd3a-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="1bd3a-104">\<bindings></span></span>  
<span data-ttu-id="1bd3a-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1bd3a-105">\<customBinding></span></span>  
<span data-ttu-id="1bd3a-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="1bd3a-106">\<binding></span></span>  
<span data-ttu-id="1bd3a-107">\<security></span><span class="sxs-lookup"><span data-stu-id="1bd3a-107">\<security></span></span>  
<span data-ttu-id="1bd3a-108">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="1bd3a-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="1bd3a-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="1bd3a-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bd3a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bd3a-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address=String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bd3a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1bd3a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1bd3a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1bd3a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bd3a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="1bd3a-113">Attributes</span></span>  
  
|<span data-ttu-id="1bd3a-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="1bd3a-114">Attribute</span></span>|<span data-ttu-id="1bd3a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bd3a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1bd3a-116">address</span><span class="sxs-lookup"><span data-stu-id="1bd3a-116">address</span></span>|<span data-ttu-id="1bd3a-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1bd3a-117">Required.</span></span> <span data-ttu-id="1bd3a-118">Stringa che specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1bd3a-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="1bd3a-119">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="1bd3a-119">The address must be an absolute URI.</span></span> <span data-ttu-id="1bd3a-120">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="1bd3a-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bd3a-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1bd3a-121">Child Elements</span></span>  
  
|<span data-ttu-id="1bd3a-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="1bd3a-122">Element</span></span>|<span data-ttu-id="1bd3a-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bd3a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bd3a-124">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="1bd3a-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="1bd3a-125">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1bd3a-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="1bd3a-126">\<identità ></span><span class="sxs-lookup"><span data-stu-id="1bd3a-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="1bd3a-127">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="1bd3a-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1bd3a-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1bd3a-128">Parent Elements</span></span>  
  
|<span data-ttu-id="1bd3a-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="1bd3a-129">Element</span></span>|<span data-ttu-id="1bd3a-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bd3a-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bd3a-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="1bd3a-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="1bd3a-132">Specifica i parametri di un token di sicurezza emesso in uno scenario di sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="1bd3a-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1bd3a-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bd3a-133">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="1bd3a-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="1bd3a-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="1bd3a-135">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="1bd3a-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="1bd3a-136">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1bd3a-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="1bd3a-137">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="1bd3a-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="1bd3a-138">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1bd3a-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1bd3a-139">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="1bd3a-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="1bd3a-140">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1bd3a-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="1bd3a-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1bd3a-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="1bd3a-142">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1bd3a-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="1bd3a-143">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1bd3a-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
