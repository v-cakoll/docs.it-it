---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4bf8ad2f70499edfc72dd9fcd9a5d8a0aafbbc66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251932"
---
# <a name="nameclaimtype"></a><span data-ttu-id="33c29-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="33c29-101">\<nameClaimType></span></span>
<span data-ttu-id="33c29-102">Imposta il tipo di attestazione che <xref:System.Security.Principal.IIdentity.Name%2A> specifica la proprietà.</span><span class="sxs-lookup"><span data-stu-id="33c29-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="33c29-103">Il tipo di attestazione viene usato per cercare <xref:System.Security.Claims.Claim> un oggetto nella raccolta <xref:System.Security.Claims.ClaimsIdentity> di oggetti restituiti dal <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metodo di questo gestore di token.</span><span class="sxs-lookup"><span data-stu-id="33c29-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="33c29-104">Il valore dell'attestazione corrispondente viene quindi impostato come nome dell'oggetto <xref:System.Security.Principal.IIdentity> generato da questo gestore di token.</span><span class="sxs-lookup"><span data-stu-id="33c29-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
<span data-ttu-id="33c29-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33c29-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33c29-106">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="33c29-106">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="33c29-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="33c29-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="33c29-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="33c29-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="33c29-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Aggiungi >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="33c29-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="33c29-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> samlSecurityTokenRequirement**](samlsecuritytokenrequirement.md)</span><span class="sxs-lookup"><span data-stu-id="33c29-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)</span></span>\
<span data-ttu-id="33c29-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> nameClaimType**</span><span class="sxs-lookup"><span data-stu-id="33c29-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33c29-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33c29-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33c29-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="33c29-113">Attributes and Elements</span></span>  
 <span data-ttu-id="33c29-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="33c29-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33c29-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="33c29-115">Attributes</span></span>  
  
|<span data-ttu-id="33c29-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="33c29-116">Attribute</span></span>|<span data-ttu-id="33c29-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33c29-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33c29-118">value</span><span class="sxs-lookup"><span data-stu-id="33c29-118">value</span></span>|<span data-ttu-id="33c29-119">Stringa che specifica l'URI che rappresenta il tipo di attestazione dell'attestazione da utilizzare per <xref:System.Security.Principal.IIdentity.Name%2A> la proprietà.</span><span class="sxs-lookup"><span data-stu-id="33c29-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="33c29-120">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="33c29-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33c29-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="33c29-121">Child Elements</span></span>  
 <span data-ttu-id="33c29-122">Nessuna</span><span class="sxs-lookup"><span data-stu-id="33c29-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33c29-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="33c29-123">Parent Elements</span></span>  
  
|<span data-ttu-id="33c29-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="33c29-124">Element</span></span>|<span data-ttu-id="33c29-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33c29-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33c29-126">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="33c29-126">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="33c29-127">Fornisce la configurazione per <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la classe, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="33c29-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33c29-128">Note</span><span class="sxs-lookup"><span data-stu-id="33c29-128">Remarks</span></span>  
 <span data-ttu-id="33c29-129">L' `<nameClaimType>` elemento imposta la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> proprietà quando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="33c29-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33c29-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="33c29-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33c29-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33c29-131">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
