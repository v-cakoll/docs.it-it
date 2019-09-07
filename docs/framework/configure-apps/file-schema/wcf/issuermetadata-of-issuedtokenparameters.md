---
title: <issuerMetadata> di <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400351"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="8ffb1-102">\<> issuerMetadata di \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="8ffb1-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

<span data-ttu-id="8ffb1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8ffb1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8ffb1-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8ffb1-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8ffb1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8ffb1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8ffb1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="8ffb1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="8ffb1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="8ffb1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8ffb1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="8ffb1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="8ffb1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedTokenParameters**](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="8ffb1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="8ffb1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> issuerMetadata**</span><span class="sxs-lookup"><span data-stu-id="8ffb1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ffb1-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ffb1-111">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ffb1-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8ffb1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8ffb1-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ffb1-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="8ffb1-114">Attributes</span></span>  
  
|<span data-ttu-id="8ffb1-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="8ffb1-115">Attribute</span></span>|<span data-ttu-id="8ffb1-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="8ffb1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ffb1-117">Address</span><span class="sxs-lookup"><span data-stu-id="8ffb1-117">address</span></span>|<span data-ttu-id="8ffb1-118">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-118">Required.</span></span> <span data-ttu-id="8ffb1-119">Stringa che specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-119">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="8ffb1-120">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-120">The address must be an absolute URI.</span></span> <span data-ttu-id="8ffb1-121">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-121">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ffb1-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8ffb1-122">Child Elements</span></span>  
  
|<span data-ttu-id="8ffb1-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="8ffb1-123">Element</span></span>|<span data-ttu-id="8ffb1-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ffb1-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ffb1-125">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="8ffb1-125">\<headers></span></span>](headers-element.md)|<span data-ttu-id="8ffb1-126">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-126">A collection of address headers.</span></span>|  
|[<span data-ttu-id="8ffb1-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="8ffb1-127">\<identity></span></span>](identity.md)|<span data-ttu-id="8ffb1-128">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-128">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8ffb1-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8ffb1-129">Parent Elements</span></span>  
  
|<span data-ttu-id="8ffb1-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="8ffb1-130">Element</span></span>|<span data-ttu-id="8ffb1-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ffb1-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ffb1-132">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="8ffb1-132">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="8ffb1-133">Specifica i parametri di un token di sicurezza emesso in uno scenario di sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="8ffb1-133">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ffb1-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ffb1-134">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8ffb1-135">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="8ffb1-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8ffb1-136">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="8ffb1-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8ffb1-137">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="8ffb1-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="8ffb1-138">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="8ffb1-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8ffb1-139">Associazioni</span><span class="sxs-lookup"><span data-stu-id="8ffb1-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8ffb1-140">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="8ffb1-140">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8ffb1-141">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="8ffb1-141">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8ffb1-142">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8ffb1-142">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="8ffb1-143">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="8ffb1-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="8ffb1-144">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="8ffb1-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
