---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0f651377346b1f14a4226128cd5cf7059543adca
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251918"
---
# <a name="roleclaimtype"></a><span data-ttu-id="19afb-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="19afb-101">\<roleClaimType></span></span>
<span data-ttu-id="19afb-102">Specifica il tipo di attestazione che definisce le attestazioni del tipo di <xref:System.Security.Claims.ClaimsIdentity> ruolo nella raccolta di <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> oggetti restituiti dal metodo del gestore del token.</span><span class="sxs-lookup"><span data-stu-id="19afb-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
<span data-ttu-id="19afb-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="19afb-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="19afb-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="19afb-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="19afb-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="19afb-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="19afb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="19afb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="19afb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Aggiungi >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="19afb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="19afb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> samlSecurityTokenRequirement**](samlsecuritytokenrequirement.md)</span><span class="sxs-lookup"><span data-stu-id="19afb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)</span></span>\
<span data-ttu-id="19afb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> roleClaimType**</span><span class="sxs-lookup"><span data-stu-id="19afb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19afb-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19afb-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19afb-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="19afb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="19afb-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="19afb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19afb-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="19afb-113">Attributes</span></span>  
  
|<span data-ttu-id="19afb-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="19afb-114">Attribute</span></span>|<span data-ttu-id="19afb-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19afb-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19afb-116">value</span><span class="sxs-lookup"><span data-stu-id="19afb-116">value</span></span>|<span data-ttu-id="19afb-117">Stringa che specifica l'URI che rappresenta il tipo di attestazione dell'attestazione da utilizzare per il tipo di attestazione del ruolo.</span><span class="sxs-lookup"><span data-stu-id="19afb-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19afb-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="19afb-118">Child Elements</span></span>  
 <span data-ttu-id="19afb-119">Nessuna</span><span class="sxs-lookup"><span data-stu-id="19afb-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19afb-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="19afb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="19afb-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="19afb-121">Element</span></span>|<span data-ttu-id="19afb-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19afb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19afb-123">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="19afb-123">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="19afb-124">Fornisce la configurazione per <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la classe, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="19afb-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19afb-125">Note</span><span class="sxs-lookup"><span data-stu-id="19afb-125">Remarks</span></span>  
 <span data-ttu-id="19afb-126">L' `<roleClaimType>` elemento imposta la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> proprietà quando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="19afb-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19afb-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="19afb-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="19afb-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19afb-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
