---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0f651377346b1f14a4226128cd5cf7059543adca
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251918"
---
# \<roleClaimType>
<span data-ttu-id="814df-101">Specifica il tipo di attestazione che definisce le attestazioni del tipo di ruolo nella raccolta di <xref:System.Security.Claims.ClaimsIdentity> oggetti restituiti dal <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metodo del gestore del token.</span><span class="sxs-lookup"><span data-stu-id="814df-101">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="814df-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="814df-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="814df-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="814df-103">Attributes and Elements</span></span>  
 <span data-ttu-id="814df-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="814df-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="814df-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="814df-105">Attributes</span></span>  
  
|<span data-ttu-id="814df-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="814df-106">Attribute</span></span>|<span data-ttu-id="814df-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="814df-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="814df-108">Valore</span><span class="sxs-lookup"><span data-stu-id="814df-108">value</span></span>|<span data-ttu-id="814df-109">Stringa che specifica l'URI che rappresenta il tipo di attestazione dell'attestazione da utilizzare per il tipo di attestazione del ruolo.</span><span class="sxs-lookup"><span data-stu-id="814df-109">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="814df-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="814df-110">Child Elements</span></span>  
 <span data-ttu-id="814df-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="814df-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="814df-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="814df-112">Parent Elements</span></span>  
  
|<span data-ttu-id="814df-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="814df-113">Element</span></span>|<span data-ttu-id="814df-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="814df-114">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="814df-115">Fornisce la configurazione per la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> classe, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="814df-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="814df-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="814df-116">Remarks</span></span>  
 <span data-ttu-id="814df-117">L' `<roleClaimType>` elemento imposta la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> proprietà quando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="814df-117">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="814df-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="814df-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="814df-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="814df-119">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
