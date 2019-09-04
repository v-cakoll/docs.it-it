---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 5863c01e97e7f5fb6fe07c43174c0d6cb7a0a25d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251742"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="4dc69-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="4dc69-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="4dc69-102">Fornisce la configurazione per <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> la classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="4dc69-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="4dc69-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4dc69-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4dc69-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="4dc69-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="4dc69-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="4dc69-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="4dc69-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="4dc69-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="4dc69-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Aggiungi >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="4dc69-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="4dc69-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> userNameSecurityTokenHandlerRequirement**</span><span class="sxs-lookup"><span data-stu-id="4dc69-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dc69-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4dc69-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4dc69-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4dc69-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4dc69-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4dc69-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4dc69-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4dc69-112">Attributes</span></span>  
  
|<span data-ttu-id="4dc69-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="4dc69-113">Attribute</span></span>|<span data-ttu-id="4dc69-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4dc69-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4dc69-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="4dc69-115">membershipProviderName</span></span>|<span data-ttu-id="4dc69-116">Specifica l' <xref:System.Web.Security.MembershipProvider> oggetto che deve essere utilizzato dal gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4dc69-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4dc69-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4dc69-117">Child Elements</span></span>  
 <span data-ttu-id="4dc69-118">Nessuna</span><span class="sxs-lookup"><span data-stu-id="4dc69-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4dc69-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4dc69-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4dc69-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4dc69-120">Element</span></span>|<span data-ttu-id="4dc69-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4dc69-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4dc69-122">\<add></span><span class="sxs-lookup"><span data-stu-id="4dc69-122">\<add></span></span>](add.md)|<span data-ttu-id="4dc69-123">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="4dc69-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dc69-124">Note</span><span class="sxs-lookup"><span data-stu-id="4dc69-124">Remarks</span></span>  
 <span data-ttu-id="4dc69-125">L' `<userNameSecurityTokenHandlerRequirement>` elemento imposta la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> proprietà quando un <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="4dc69-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dc69-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="4dc69-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
