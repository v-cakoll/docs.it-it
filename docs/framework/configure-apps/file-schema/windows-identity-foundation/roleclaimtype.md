---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0ce2e06ee895d09de193bac1fe7038e71794dda4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942535"
---
# <a name="roleclaimtype"></a><span data-ttu-id="33184-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="33184-101">\<roleClaimType></span></span>
<span data-ttu-id="33184-102">Specifica il tipo di attestazione che definisce le attestazioni del tipo di <xref:System.Security.Claims.ClaimsIdentity> ruolo nella raccolta di <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> oggetti restituiti dal metodo del gestore del token.</span><span class="sxs-lookup"><span data-stu-id="33184-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="33184-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="33184-103">\<system.identityModel></span></span>  
<span data-ttu-id="33184-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="33184-104">\<identityConfiguration></span></span>  
<span data-ttu-id="33184-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="33184-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="33184-106">\<add></span><span class="sxs-lookup"><span data-stu-id="33184-106">\<add></span></span>  
<span data-ttu-id="33184-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="33184-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="33184-108">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="33184-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33184-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33184-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33184-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="33184-110">Attributes and Elements</span></span>  
 <span data-ttu-id="33184-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="33184-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33184-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="33184-112">Attributes</span></span>  
  
|<span data-ttu-id="33184-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="33184-113">Attribute</span></span>|<span data-ttu-id="33184-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33184-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33184-115">value</span><span class="sxs-lookup"><span data-stu-id="33184-115">value</span></span>|<span data-ttu-id="33184-116">Stringa che specifica l'URI che rappresenta il tipo di attestazione dell'attestazione da utilizzare per il tipo di attestazione del ruolo.</span><span class="sxs-lookup"><span data-stu-id="33184-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33184-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="33184-117">Child Elements</span></span>  
 <span data-ttu-id="33184-118">Nessuna</span><span class="sxs-lookup"><span data-stu-id="33184-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33184-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="33184-119">Parent Elements</span></span>  
  
|<span data-ttu-id="33184-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="33184-120">Element</span></span>|<span data-ttu-id="33184-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33184-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33184-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="33184-122">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="33184-123">Fornisce la configurazione per <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la classe, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="33184-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33184-124">Note</span><span class="sxs-lookup"><span data-stu-id="33184-124">Remarks</span></span>  
 <span data-ttu-id="33184-125">L' `<roleClaimType>` elemento imposta la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> proprietà quando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="33184-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33184-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="33184-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33184-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33184-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
