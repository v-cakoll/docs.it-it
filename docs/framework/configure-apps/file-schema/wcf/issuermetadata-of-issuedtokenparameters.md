---
title: <issuerMetadata> di <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400351"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="9fca7-102">\<issuerMetadata> di \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="9fca7-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="9fca7-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9fca7-103">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fca7-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9fca7-104">Attributes and Elements</span></span>  
 <span data-ttu-id="9fca7-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9fca7-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fca7-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="9fca7-106">Attributes</span></span>  
  
|<span data-ttu-id="9fca7-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="9fca7-107">Attribute</span></span>|<span data-ttu-id="9fca7-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9fca7-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9fca7-109">address</span><span class="sxs-lookup"><span data-stu-id="9fca7-109">address</span></span>|<span data-ttu-id="9fca7-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9fca7-110">Required.</span></span> <span data-ttu-id="9fca7-111">Stringa che specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="9fca7-111">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="9fca7-112">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="9fca7-112">The address must be an absolute URI.</span></span> <span data-ttu-id="9fca7-113">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="9fca7-113">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fca7-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9fca7-114">Child Elements</span></span>  
  
|<span data-ttu-id="9fca7-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="9fca7-115">Element</span></span>|<span data-ttu-id="9fca7-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9fca7-116">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="9fca7-117">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="9fca7-117">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="9fca7-118">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="9fca7-118">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9fca7-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9fca7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9fca7-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9fca7-120">Element</span></span>|<span data-ttu-id="9fca7-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9fca7-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="9fca7-122">Specifica i parametri di un token di sicurezza emesso in uno scenario di sicurezza federata.</span><span class="sxs-lookup"><span data-stu-id="9fca7-122">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9fca7-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9fca7-123">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9fca7-124">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="9fca7-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="9fca7-125">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="9fca7-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="9fca7-126">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="9fca7-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="9fca7-127">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="9fca7-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="9fca7-128">Binding</span><span class="sxs-lookup"><span data-stu-id="9fca7-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9fca7-129">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="9fca7-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9fca7-130">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="9fca7-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="9fca7-131">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9fca7-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="9fca7-132">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="9fca7-132">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
