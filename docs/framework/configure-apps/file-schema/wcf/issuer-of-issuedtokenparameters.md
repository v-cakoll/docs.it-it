---
title: <issuer> di <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bdd5ad45984fae7b39defe82c4af75845dfda1b6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397937"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="e9145-102">\<issuer> di \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="e9145-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="e9145-103">Specifica il servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e9145-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="e9145-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9145-104">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9145-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e9145-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e9145-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e9145-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9145-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="e9145-107">Attributes</span></span>  
  
|<span data-ttu-id="e9145-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="e9145-108">Attribute</span></span>|<span data-ttu-id="e9145-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9145-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9145-110">address</span><span class="sxs-lookup"><span data-stu-id="e9145-110">address</span></span>|<span data-ttu-id="e9145-111">Stringa obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="e9145-111">Required string.</span></span> <span data-ttu-id="e9145-112">URL del servizio STS.</span><span class="sxs-lookup"><span data-stu-id="e9145-112">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9145-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e9145-113">Child Elements</span></span>  
  
|<span data-ttu-id="e9145-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9145-114">Element</span></span>|<span data-ttu-id="e9145-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9145-115">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="e9145-116">Raccolta delle intestazioni di indirizzi per gli endpoint che il generatore può creare.</span><span class="sxs-lookup"><span data-stu-id="e9145-116">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="e9145-117">Quando si usa un token emesso, specifica le impostazioni che consentono al client di autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="e9145-117">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9145-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e9145-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e9145-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9145-119">Element</span></span>|<span data-ttu-id="e9145-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9145-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="e9145-121">Specifica il token corrente emesso.</span><span class="sxs-lookup"><span data-stu-id="e9145-121">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9145-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e9145-122">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e9145-123">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="e9145-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e9145-124">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="e9145-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e9145-125">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="e9145-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="e9145-126">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="e9145-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e9145-127">Binding</span><span class="sxs-lookup"><span data-stu-id="e9145-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e9145-128">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="e9145-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e9145-129">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="e9145-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="e9145-130">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="e9145-130">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="e9145-131">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="e9145-131">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
