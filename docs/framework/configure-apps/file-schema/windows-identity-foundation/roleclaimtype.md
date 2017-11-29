---
title: '&lt;roleClaimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 8a5de30d60478b6601781ac34fd481a6167462e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="1c121-102">&lt;roleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="1c121-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="1c121-103">Specifica il tipo di attestazione che definisce le attestazioni di tipo ruolo nella raccolta di <xref:System.Security.Claims.ClaimsIdentity> gli oggetti restituiti dal <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metodo del gestore di token.</span><span class="sxs-lookup"><span data-stu-id="1c121-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="1c121-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="1c121-104">\<system.identityModel></span></span>  
<span data-ttu-id="1c121-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="1c121-105">\<identityConfiguration></span></span>  
<span data-ttu-id="1c121-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="1c121-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="1c121-107">\<add></span><span class="sxs-lookup"><span data-stu-id="1c121-107">\<add></span></span>  
<span data-ttu-id="1c121-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="1c121-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="1c121-109">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="1c121-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c121-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c121-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c121-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1c121-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1c121-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1c121-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c121-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="1c121-113">Attributes</span></span>  
  
|<span data-ttu-id="1c121-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="1c121-114">Attribute</span></span>|<span data-ttu-id="1c121-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c121-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1c121-116">valore</span><span class="sxs-lookup"><span data-stu-id="1c121-116">value</span></span>|<span data-ttu-id="1c121-117">Stringa che specifica l'URI che rappresenta il tipo di attestazione dell'attestazione da usare per il tipo di attestazione del ruolo.</span><span class="sxs-lookup"><span data-stu-id="1c121-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c121-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1c121-118">Child Elements</span></span>  
 <span data-ttu-id="1c121-119">None</span><span class="sxs-lookup"><span data-stu-id="1c121-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c121-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1c121-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1c121-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c121-121">Element</span></span>|<span data-ttu-id="1c121-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c121-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c121-123">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="1c121-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="1c121-124">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (classe), la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="1c121-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c121-125">Note</span><span class="sxs-lookup"><span data-stu-id="1c121-125">Remarks</span></span>  
 <span data-ttu-id="1c121-126">Il `<roleClaimType>` set di elementi di <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> proprietà quando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="1c121-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c121-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c121-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c121-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c121-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
