---
title: '&lt;roleClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 909df1bd6054d9737f91c30c3c6b2d68b932281c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755188"
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="75112-102">&lt;roleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="75112-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="75112-103">Specifica il tipo di attestazione che definisce le attestazioni di tipo ruolo nella raccolta di <xref:System.Security.Claims.ClaimsIdentity> gli oggetti restituiti dal <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metodo del gestore di token.</span><span class="sxs-lookup"><span data-stu-id="75112-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="75112-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="75112-104">\<system.identityModel></span></span>  
<span data-ttu-id="75112-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="75112-105">\<identityConfiguration></span></span>  
<span data-ttu-id="75112-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="75112-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="75112-107">\<add></span><span class="sxs-lookup"><span data-stu-id="75112-107">\<add></span></span>  
<span data-ttu-id="75112-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="75112-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="75112-109">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="75112-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75112-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75112-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75112-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="75112-111">Attributes and Elements</span></span>  
 <span data-ttu-id="75112-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="75112-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75112-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="75112-113">Attributes</span></span>  
  
|<span data-ttu-id="75112-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="75112-114">Attribute</span></span>|<span data-ttu-id="75112-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75112-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75112-116">predefinito</span><span class="sxs-lookup"><span data-stu-id="75112-116">value</span></span>|<span data-ttu-id="75112-117">Stringa che specifica l'URI che rappresenta il tipo di attestazione dell'attestazione da usare per il tipo di attestazione del ruolo.</span><span class="sxs-lookup"><span data-stu-id="75112-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75112-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="75112-118">Child Elements</span></span>  
 <span data-ttu-id="75112-119">Nessuno</span><span class="sxs-lookup"><span data-stu-id="75112-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75112-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="75112-120">Parent Elements</span></span>  
  
|<span data-ttu-id="75112-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="75112-121">Element</span></span>|<span data-ttu-id="75112-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75112-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75112-123">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="75112-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="75112-124">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (classe), la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="75112-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75112-125">Note</span><span class="sxs-lookup"><span data-stu-id="75112-125">Remarks</span></span>  
 <span data-ttu-id="75112-126">Il `<roleClaimType>` set di elementi di <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> proprietà quando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="75112-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75112-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="75112-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="75112-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75112-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
