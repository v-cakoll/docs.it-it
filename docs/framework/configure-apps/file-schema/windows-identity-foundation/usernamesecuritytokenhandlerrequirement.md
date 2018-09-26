---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: dfcaad8b150321fda2a86e601bf57204cbdc1a0e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216016"
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="a4db9-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="a4db9-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="a4db9-103">Fornisce la configurazione per il <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="a4db9-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="a4db9-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="a4db9-104">\<system.identityModel></span></span>  
<span data-ttu-id="a4db9-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a4db9-105">\<identityConfiguration></span></span>  
<span data-ttu-id="a4db9-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="a4db9-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="a4db9-107">\<add></span><span class="sxs-lookup"><span data-stu-id="a4db9-107">\<add></span></span>  
<span data-ttu-id="a4db9-108">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="a4db9-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4db9-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4db9-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4db9-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a4db9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a4db9-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a4db9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4db9-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="a4db9-112">Attributes</span></span>  
  
|<span data-ttu-id="a4db9-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="a4db9-113">Attribute</span></span>|<span data-ttu-id="a4db9-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4db9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4db9-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="a4db9-115">membershipProviderName</span></span>|<span data-ttu-id="a4db9-116">Specifica il <xref:System.Web.Security.MembershipProvider> che deve essere utilizzata dal gestore di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a4db9-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4db9-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a4db9-117">Child Elements</span></span>  
 <span data-ttu-id="a4db9-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="a4db9-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4db9-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a4db9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a4db9-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4db9-120">Element</span></span>|<span data-ttu-id="a4db9-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4db9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4db9-122">\<add></span><span class="sxs-lookup"><span data-stu-id="a4db9-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="a4db9-123">Aggiunge il gestore di token di sicurezza specificato nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="a4db9-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4db9-124">Note</span><span class="sxs-lookup"><span data-stu-id="a4db9-124">Remarks</span></span>  
 <span data-ttu-id="a4db9-125">Il `<userNameSecurityTokenHandlerRequirement>` set di elementi che il <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> proprietà quando un <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="a4db9-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4db9-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4db9-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
