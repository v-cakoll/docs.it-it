---
title: '&lt;sessionTokenRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6c40948633eaf892db06e9bba756158dfc3c4a2e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="145e4-102">&lt;sessionTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="145e4-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="145e4-103">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> classe o classi derivate.</span><span class="sxs-lookup"><span data-stu-id="145e4-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="145e4-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="145e4-104">\<system.identityModel></span></span>  
<span data-ttu-id="145e4-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="145e4-105">\<identityConfiguration></span></span>  
<span data-ttu-id="145e4-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="145e4-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="145e4-107">\<add></span><span class="sxs-lookup"><span data-stu-id="145e4-107">\<add></span></span>  
<span data-ttu-id="145e4-108">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="145e4-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="145e4-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="145e4-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="145e4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="145e4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="145e4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="145e4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="145e4-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="145e4-112">Attributes</span></span>  
  
|<span data-ttu-id="145e4-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="145e4-113">Attribute</span></span>|<span data-ttu-id="145e4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="145e4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="145e4-115">durata</span><span class="sxs-lookup"><span data-stu-id="145e4-115">lifetime</span></span>|<span data-ttu-id="145e4-116">Specifica la durata del token di sessione.</span><span class="sxs-lookup"><span data-stu-id="145e4-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="145e4-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="145e4-117">Child Elements</span></span>  
 <span data-ttu-id="145e4-118">Nessuno</span><span class="sxs-lookup"><span data-stu-id="145e4-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="145e4-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="145e4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="145e4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="145e4-120">Element</span></span>|<span data-ttu-id="145e4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="145e4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="145e4-122">\<add></span><span class="sxs-lookup"><span data-stu-id="145e4-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="145e4-123">Aggiunge il gestore di token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="145e4-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="145e4-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="145e4-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
