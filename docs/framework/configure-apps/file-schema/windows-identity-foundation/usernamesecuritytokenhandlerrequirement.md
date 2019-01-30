---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 18769794da8528f085c567264827db5aa6b214f1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271889"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="03355-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="03355-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="03355-102">Fornisce la configurazione per il <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="03355-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="03355-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="03355-103">\<system.identityModel></span></span>  
<span data-ttu-id="03355-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="03355-104">\<identityConfiguration></span></span>  
<span data-ttu-id="03355-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="03355-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="03355-106">\<add></span><span class="sxs-lookup"><span data-stu-id="03355-106">\<add></span></span>  
<span data-ttu-id="03355-107">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="03355-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03355-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03355-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03355-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="03355-109">Attributes and Elements</span></span>  
 <span data-ttu-id="03355-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="03355-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03355-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="03355-111">Attributes</span></span>  
  
|<span data-ttu-id="03355-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="03355-112">Attribute</span></span>|<span data-ttu-id="03355-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03355-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03355-114">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="03355-114">membershipProviderName</span></span>|<span data-ttu-id="03355-115">Specifica il <xref:System.Web.Security.MembershipProvider> che deve essere utilizzata dal gestore di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="03355-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03355-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="03355-116">Child Elements</span></span>  
 <span data-ttu-id="03355-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="03355-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03355-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="03355-118">Parent Elements</span></span>  
  
|<span data-ttu-id="03355-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="03355-119">Element</span></span>|<span data-ttu-id="03355-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03355-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03355-121">\<add></span><span class="sxs-lookup"><span data-stu-id="03355-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="03355-122">Aggiunge il gestore di token di sicurezza specificato nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="03355-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03355-123">Note</span><span class="sxs-lookup"><span data-stu-id="03355-123">Remarks</span></span>  
 <span data-ttu-id="03355-124">Il `<userNameSecurityTokenHandlerRequirement>` set di elementi che il <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> proprietà quando un <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="03355-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03355-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="03355-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
