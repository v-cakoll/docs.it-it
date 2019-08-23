---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: fed8964e03b80e365fdc5eafd45b4fc372a6e352
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944259"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="e9477-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="e9477-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="e9477-102">Fornisce la configurazione per <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> la classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="e9477-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="e9477-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e9477-103">\<system.identityModel></span></span>  
<span data-ttu-id="e9477-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e9477-104">\<identityConfiguration></span></span>  
<span data-ttu-id="e9477-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e9477-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e9477-106">\<add></span><span class="sxs-lookup"><span data-stu-id="e9477-106">\<add></span></span>  
<span data-ttu-id="e9477-107">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="e9477-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9477-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9477-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9477-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e9477-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e9477-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e9477-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9477-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e9477-111">Attributes</span></span>  
  
|<span data-ttu-id="e9477-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="e9477-112">Attribute</span></span>|<span data-ttu-id="e9477-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9477-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9477-114">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="e9477-114">membershipProviderName</span></span>|<span data-ttu-id="e9477-115">Specifica l' <xref:System.Web.Security.MembershipProvider> oggetto che deve essere utilizzato dal gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e9477-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9477-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e9477-116">Child Elements</span></span>  
 <span data-ttu-id="e9477-117">Nessuna</span><span class="sxs-lookup"><span data-stu-id="e9477-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9477-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e9477-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e9477-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9477-119">Element</span></span>|<span data-ttu-id="e9477-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e9477-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9477-121">\<add></span><span class="sxs-lookup"><span data-stu-id="e9477-121">\<add></span></span>](add.md)|<span data-ttu-id="e9477-122">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="e9477-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9477-123">Note</span><span class="sxs-lookup"><span data-stu-id="e9477-123">Remarks</span></span>  
 <span data-ttu-id="e9477-124">L' `<userNameSecurityTokenHandlerRequirement>` elemento imposta la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> proprietà quando un <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="e9477-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9477-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9477-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
