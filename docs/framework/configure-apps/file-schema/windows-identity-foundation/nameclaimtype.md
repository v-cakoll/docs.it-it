---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 47366c5bb2bd9228268fce3ae6e1fb5ad457dab1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942613"
---
# <a name="nameclaimtype"></a><span data-ttu-id="d1384-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="d1384-101">\<nameClaimType></span></span>
<span data-ttu-id="d1384-102">Imposta il tipo di attestazione che <xref:System.Security.Principal.IIdentity.Name%2A> specifica la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d1384-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="d1384-103">Il tipo di attestazione viene usato per cercare <xref:System.Security.Claims.Claim> un oggetto nella raccolta <xref:System.Security.Claims.ClaimsIdentity> di oggetti restituiti dal <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metodo di questo gestore di token.</span><span class="sxs-lookup"><span data-stu-id="d1384-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="d1384-104">Il valore dell'attestazione corrispondente viene quindi impostato come nome dell'oggetto <xref:System.Security.Principal.IIdentity> generato da questo gestore di token.</span><span class="sxs-lookup"><span data-stu-id="d1384-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="d1384-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d1384-105">\<system.identityModel></span></span>  
<span data-ttu-id="d1384-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d1384-106">\<identityConfiguration></span></span>  
<span data-ttu-id="d1384-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d1384-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d1384-108">\<add></span><span class="sxs-lookup"><span data-stu-id="d1384-108">\<add></span></span>  
<span data-ttu-id="d1384-109">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="d1384-109">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="d1384-110">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="d1384-110">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1384-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d1384-111">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1384-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d1384-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d1384-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d1384-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1384-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="d1384-114">Attributes</span></span>  
  
|<span data-ttu-id="d1384-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="d1384-115">Attribute</span></span>|<span data-ttu-id="d1384-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d1384-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d1384-117">value</span><span class="sxs-lookup"><span data-stu-id="d1384-117">value</span></span>|<span data-ttu-id="d1384-118">Stringa che specifica l'URI che rappresenta il tipo di attestazione dell'attestazione da utilizzare per <xref:System.Security.Principal.IIdentity.Name%2A> la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d1384-118">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="d1384-119">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="d1384-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1384-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d1384-120">Child Elements</span></span>  
 <span data-ttu-id="d1384-121">Nessuna</span><span class="sxs-lookup"><span data-stu-id="d1384-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1384-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d1384-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d1384-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1384-123">Element</span></span>|<span data-ttu-id="d1384-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1384-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1384-125">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="d1384-125">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="d1384-126">Fornisce la configurazione per <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la classe, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="d1384-126">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1384-127">Note</span><span class="sxs-lookup"><span data-stu-id="d1384-127">Remarks</span></span>  
 <span data-ttu-id="d1384-128">L' `<nameClaimType>` elemento imposta la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> proprietà quando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="d1384-128">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1384-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1384-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1384-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1384-130">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
