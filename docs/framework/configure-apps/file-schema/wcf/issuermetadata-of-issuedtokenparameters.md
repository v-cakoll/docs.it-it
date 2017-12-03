---
title: '&lt;issuerMetadata&gt; di &lt;issuedTokenParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ccd0417aeebbaf08d28457dd94a4d1698882c79e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="82681-102">&lt;issuerMetadata&gt; di &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="82681-102">&lt;issuerMetadata&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="82681-103">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="82681-103">\<system.serviceModel></span></span>  
<span data-ttu-id="82681-104">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="82681-104">\<bindings></span></span>  
<span data-ttu-id="82681-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="82681-105">\<customBinding></span></span>  
<span data-ttu-id="82681-106">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="82681-106">\<binding></span></span>  
<span data-ttu-id="82681-107">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="82681-107">\<security></span></span>  
<span data-ttu-id="82681-108">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="82681-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="82681-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="82681-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82681-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82681-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address=String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82681-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="82681-111">Attributes and Elements</span></span>  
 <span data-ttu-id="82681-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="82681-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82681-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="82681-113">Attributes</span></span>  
  
|<span data-ttu-id="82681-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="82681-114">Attribute</span></span>|<span data-ttu-id="82681-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82681-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82681-116">address</span><span class="sxs-lookup"><span data-stu-id="82681-116">address</span></span>|<span data-ttu-id="82681-117">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="82681-117">Required.</span></span> <span data-ttu-id="82681-118">Stringa che specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="82681-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="82681-119">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="82681-119">The address must be an absolute URI.</span></span> <span data-ttu-id="82681-120">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="82681-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82681-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="82681-121">Child Elements</span></span>  
  
|<span data-ttu-id="82681-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="82681-122">Element</span></span>|<span data-ttu-id="82681-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82681-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82681-124">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="82681-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="82681-125">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="82681-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="82681-126">\<identità ></span><span class="sxs-lookup"><span data-stu-id="82681-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="82681-127">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="82681-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82681-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="82681-128">Parent Elements</span></span>  
  
|<span data-ttu-id="82681-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="82681-129">Element</span></span>|<span data-ttu-id="82681-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82681-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82681-131">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="82681-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="82681-132">Specifica i parametri di un token di sicurezza emesso in uno scenario di sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="82681-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82681-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82681-133">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="82681-134">L'autenticazione e identità del servizio</span><span class="sxs-lookup"><span data-stu-id="82681-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="82681-135">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="82681-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="82681-136">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="82681-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="82681-137">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="82681-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="82681-138">Associazioni</span><span class="sxs-lookup"><span data-stu-id="82681-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="82681-139">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="82681-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="82681-140">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="82681-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="82681-141">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="82681-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="82681-142">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="82681-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="82681-143">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="82681-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
