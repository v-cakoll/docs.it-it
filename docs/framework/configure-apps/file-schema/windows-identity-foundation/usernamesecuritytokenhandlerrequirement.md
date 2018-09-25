---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: dfcaad8b150321fda2a86e601bf57204cbdc1a0e
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075033"
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="590c4-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="590c4-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="590c4-103">Fornisce la configurazione per il <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="590c4-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="590c4-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="590c4-104">\<system.identityModel></span></span>  
<span data-ttu-id="590c4-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="590c4-105">\<identityConfiguration></span></span>  
<span data-ttu-id="590c4-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="590c4-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="590c4-107">\<add></span><span class="sxs-lookup"><span data-stu-id="590c4-107">\<add></span></span>  
<span data-ttu-id="590c4-108">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="590c4-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="590c4-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="590c4-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="590c4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="590c4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="590c4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="590c4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="590c4-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="590c4-112">Attributes</span></span>  
  
|<span data-ttu-id="590c4-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="590c4-113">Attribute</span></span>|<span data-ttu-id="590c4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="590c4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="590c4-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="590c4-115">membershipProviderName</span></span>|<span data-ttu-id="590c4-116">Specifica il <xref:System.Web.Security.MembershipProvider> che deve essere utilizzata dal gestore di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="590c4-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="590c4-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="590c4-117">Child Elements</span></span>  
 <span data-ttu-id="590c4-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="590c4-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="590c4-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="590c4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="590c4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="590c4-120">Element</span></span>|<span data-ttu-id="590c4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="590c4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="590c4-122">\<add></span><span class="sxs-lookup"><span data-stu-id="590c4-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="590c4-123">Aggiunge il gestore di token di sicurezza specificato nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="590c4-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="590c4-124">Note</span><span class="sxs-lookup"><span data-stu-id="590c4-124">Remarks</span></span>  
 <span data-ttu-id="590c4-125">Il `<userNameSecurityTokenHandlerRequirement>` set di elementi che il <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> proprietà quando un <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="590c4-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="590c4-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="590c4-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
