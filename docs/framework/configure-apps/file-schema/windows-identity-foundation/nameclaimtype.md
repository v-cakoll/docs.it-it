---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4bf8ad2f70499edfc72dd9fcd9a5d8a0aafbbc66
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251932"
---
# \<nameClaimType>
<span data-ttu-id="56543-101">Imposta il tipo di attestazione che specifica la <xref:System.Security.Principal.IIdentity.Name%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="56543-101">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="56543-102">Il tipo di attestazione viene usato per cercare un oggetto <xref:System.Security.Claims.Claim> nella raccolta di <xref:System.Security.Claims.ClaimsIdentity> oggetti restituiti dal <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metodo di questo gestore di token.</span><span class="sxs-lookup"><span data-stu-id="56543-102">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="56543-103">Il valore dell'attestazione corrispondente viene quindi impostato come nome dell'oggetto <xref:System.Security.Principal.IIdentity> generato da questo gestore di token.</span><span class="sxs-lookup"><span data-stu-id="56543-103">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="56543-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56543-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56543-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="56543-105">Attributes and Elements</span></span>  
 <span data-ttu-id="56543-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="56543-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56543-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="56543-107">Attributes</span></span>  
  
|<span data-ttu-id="56543-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="56543-108">Attribute</span></span>|<span data-ttu-id="56543-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56543-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56543-110">Valore</span><span class="sxs-lookup"><span data-stu-id="56543-110">value</span></span>|<span data-ttu-id="56543-111">Stringa che specifica l'URI che rappresenta il tipo di attestazione dell'attestazione da utilizzare per la <xref:System.Security.Principal.IIdentity.Name%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="56543-111">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="56543-112">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="56543-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56543-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="56543-113">Child Elements</span></span>  
 <span data-ttu-id="56543-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="56543-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56543-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="56543-115">Parent Elements</span></span>  
  
|<span data-ttu-id="56543-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="56543-116">Element</span></span>|<span data-ttu-id="56543-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56543-117">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="56543-118">Fornisce la configurazione per la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> classe, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="56543-118">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56543-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="56543-119">Remarks</span></span>  
 <span data-ttu-id="56543-120">L' `<nameClaimType>` elemento imposta la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> proprietà quando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="56543-120">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56543-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="56543-121">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="56543-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56543-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
