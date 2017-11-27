---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 4ffe9764eb730be4859fb66ae2f0cc845c9404e8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="896e7-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="896e7-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="896e7-103">Fornisce la configurazione per il <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> classe o classi derivate.</span><span class="sxs-lookup"><span data-stu-id="896e7-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="896e7-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="896e7-104">\<system.identityModel></span></span>  
<span data-ttu-id="896e7-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="896e7-105">\<identityConfiguration></span></span>  
<span data-ttu-id="896e7-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="896e7-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="896e7-107">\<add></span><span class="sxs-lookup"><span data-stu-id="896e7-107">\<add></span></span>  
<span data-ttu-id="896e7-108">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="896e7-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="896e7-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="896e7-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="896e7-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="896e7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="896e7-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="896e7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="896e7-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="896e7-112">Attributes</span></span>  
  
|<span data-ttu-id="896e7-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="896e7-113">Attribute</span></span>|<span data-ttu-id="896e7-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="896e7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="896e7-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="896e7-115">membershipProviderName</span></span>|<span data-ttu-id="896e7-116">Specifica il <xref:System.Web.Security.MembershipProvider> che deve essere utilizzata dal gestore di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="896e7-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="896e7-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="896e7-117">Child Elements</span></span>  
 <span data-ttu-id="896e7-118">None</span><span class="sxs-lookup"><span data-stu-id="896e7-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="896e7-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="896e7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="896e7-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="896e7-120">Element</span></span>|<span data-ttu-id="896e7-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="896e7-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="896e7-122">\<add></span><span class="sxs-lookup"><span data-stu-id="896e7-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="896e7-123">Aggiunge il gestore di token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="896e7-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="896e7-124">Note</span><span class="sxs-lookup"><span data-stu-id="896e7-124">Remarks</span></span>  
 <span data-ttu-id="896e7-125">Il `<userNameSecurityTokenHandlerRequirement>` set di elementi di <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> proprietà quando un <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="896e7-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="896e7-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="896e7-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
