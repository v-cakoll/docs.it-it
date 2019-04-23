---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 5202e162a7eb5fc4e36d6a6c0a2c18af48872a69
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130325"
---
# <a name="nameclaimtype"></a><span data-ttu-id="dbe67-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="dbe67-101">\<nameClaimType></span></span>
<span data-ttu-id="dbe67-102">Imposta il tipo di attestazione che specifica il <xref:System.Security.Principal.IIdentity.Name%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="dbe67-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="dbe67-103">Il tipo di attestazione viene usato per cercare un <xref:System.Security.Claims.Claim> nella raccolta di <xref:System.Security.Claims.ClaimsIdentity> gli oggetti restituiti dai <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metodo di questo gestore di token.</span><span class="sxs-lookup"><span data-stu-id="dbe67-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="dbe67-104">Il valore dell'attestazione corrisponda viene impostato come il nome del <xref:System.Security.Principal.IIdentity> generati da questo gestore di token.</span><span class="sxs-lookup"><span data-stu-id="dbe67-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="dbe67-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="dbe67-105">\<system.identityModel></span></span>  
<span data-ttu-id="dbe67-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="dbe67-106">\<identityConfiguration></span></span>  
<span data-ttu-id="dbe67-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="dbe67-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="dbe67-108">\<add></span><span class="sxs-lookup"><span data-stu-id="dbe67-108">\<add></span></span>  
<span data-ttu-id="dbe67-109">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="dbe67-109">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="dbe67-110">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="dbe67-110">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbe67-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbe67-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbe67-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dbe67-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dbe67-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dbe67-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbe67-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="dbe67-114">Attributes</span></span>  
  
|<span data-ttu-id="dbe67-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="dbe67-115">Attribute</span></span>|<span data-ttu-id="dbe67-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbe67-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dbe67-117">predefinito</span><span class="sxs-lookup"><span data-stu-id="dbe67-117">value</span></span>|<span data-ttu-id="dbe67-118">Stringa che specifica l'URI che rappresenta il tipo di attestazione dell'attestazione da utilizzare per il <xref:System.Security.Principal.IIdentity.Name%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="dbe67-118">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="dbe67-119">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dbe67-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbe67-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dbe67-120">Child Elements</span></span>  
 <span data-ttu-id="dbe67-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="dbe67-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dbe67-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dbe67-122">Parent Elements</span></span>  
  
|<span data-ttu-id="dbe67-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbe67-123">Element</span></span>|<span data-ttu-id="dbe67-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbe67-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbe67-125">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="dbe67-125">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="dbe67-126">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (classe), il <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="dbe67-126">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbe67-127">Note</span><span class="sxs-lookup"><span data-stu-id="dbe67-127">Remarks</span></span>  
 <span data-ttu-id="dbe67-128">Il `<nameClaimType>` set di elementi che il <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> proprietà quando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="dbe67-128">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbe67-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="dbe67-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dbe67-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbe67-130">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
