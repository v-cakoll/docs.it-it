---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 8c7b7c9b42ac72b878aed4e12298dc3655f1e707
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115596"
---
# <a name="roleclaimtype"></a><span data-ttu-id="4bba7-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="4bba7-101">\<roleClaimType></span></span>
<span data-ttu-id="4bba7-102">Specifica il tipo di attestazione che definisce le attestazioni di tipo ruolo nella raccolta di <xref:System.Security.Claims.ClaimsIdentity> gli oggetti restituiti dai <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metodo del gestore del token.</span><span class="sxs-lookup"><span data-stu-id="4bba7-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="4bba7-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="4bba7-103">\<system.identityModel></span></span>  
<span data-ttu-id="4bba7-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4bba7-104">\<identityConfiguration></span></span>  
<span data-ttu-id="4bba7-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="4bba7-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="4bba7-106">\<add></span><span class="sxs-lookup"><span data-stu-id="4bba7-106">\<add></span></span>  
<span data-ttu-id="4bba7-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="4bba7-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="4bba7-108">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="4bba7-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bba7-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4bba7-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4bba7-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4bba7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4bba7-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4bba7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4bba7-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4bba7-112">Attributes</span></span>  
  
|<span data-ttu-id="4bba7-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="4bba7-113">Attribute</span></span>|<span data-ttu-id="4bba7-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4bba7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4bba7-115">predefinito</span><span class="sxs-lookup"><span data-stu-id="4bba7-115">value</span></span>|<span data-ttu-id="4bba7-116">Stringa che specifica l'URI che rappresenta il tipo di attestazione dell'attestazione da utilizzare per il tipo di attestazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="4bba7-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4bba7-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4bba7-117">Child Elements</span></span>  
 <span data-ttu-id="4bba7-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="4bba7-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4bba7-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4bba7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4bba7-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4bba7-120">Element</span></span>|<span data-ttu-id="4bba7-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4bba7-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4bba7-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="4bba7-122">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="4bba7-123">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (classe), il <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="4bba7-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bba7-124">Note</span><span class="sxs-lookup"><span data-stu-id="4bba7-124">Remarks</span></span>  
 <span data-ttu-id="4bba7-125">Il `<roleClaimType>` set di elementi che il <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> proprietà quando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="4bba7-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bba7-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="4bba7-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4bba7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bba7-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
