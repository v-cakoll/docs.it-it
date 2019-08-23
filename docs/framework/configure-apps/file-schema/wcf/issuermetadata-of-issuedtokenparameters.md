---
title: <issuerMetadata> di <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: d9d7d41277eff1de43f717816b35fdc10d52192e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928883"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="a8039-102">\<> issuerMetadata di \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="a8039-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>
<span data-ttu-id="a8039-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a8039-103">\<system.serviceModel></span></span>  
<span data-ttu-id="a8039-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="a8039-104">\<bindings></span></span>  
<span data-ttu-id="a8039-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a8039-105">\<customBinding></span></span>  
<span data-ttu-id="a8039-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="a8039-106">\<binding></span></span>  
<span data-ttu-id="a8039-107">\<security></span><span class="sxs-lookup"><span data-stu-id="a8039-107">\<security></span></span>  
<span data-ttu-id="a8039-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="a8039-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="a8039-109">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="a8039-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8039-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8039-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8039-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a8039-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a8039-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a8039-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8039-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="a8039-113">Attributes</span></span>  
  
|<span data-ttu-id="a8039-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="a8039-114">Attribute</span></span>|<span data-ttu-id="a8039-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8039-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a8039-116">Address</span><span class="sxs-lookup"><span data-stu-id="a8039-116">address</span></span>|<span data-ttu-id="a8039-117">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="a8039-117">Required.</span></span> <span data-ttu-id="a8039-118">Stringa che specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="a8039-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="a8039-119">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="a8039-119">The address must be an absolute URI.</span></span> <span data-ttu-id="a8039-120">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="a8039-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8039-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a8039-121">Child Elements</span></span>  
  
|<span data-ttu-id="a8039-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8039-122">Element</span></span>|<span data-ttu-id="a8039-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8039-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8039-124">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="a8039-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="a8039-125">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="a8039-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="a8039-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="a8039-126">\<identity></span></span>](identity.md)|<span data-ttu-id="a8039-127">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="a8039-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8039-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a8039-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a8039-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8039-129">Element</span></span>|<span data-ttu-id="a8039-130">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a8039-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8039-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="a8039-131">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="a8039-132">Specifica i parametri di un token di sicurezza emesso in uno scenario di sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="a8039-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8039-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8039-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a8039-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="a8039-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="a8039-135">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="a8039-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a8039-136">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="a8039-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="a8039-137">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="a8039-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a8039-138">Associazioni</span><span class="sxs-lookup"><span data-stu-id="a8039-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a8039-139">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="a8039-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a8039-140">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="a8039-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a8039-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a8039-141">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="a8039-142">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a8039-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="a8039-143">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="a8039-143">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
