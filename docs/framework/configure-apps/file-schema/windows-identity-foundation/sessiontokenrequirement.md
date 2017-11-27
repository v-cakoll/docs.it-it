---
title: '&lt;sessionTokenRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 8b729f588d2195992b231661f7bb718240141fdd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="86f31-102">&lt;sessionTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="86f31-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="86f31-103">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> classe o classi derivate.</span><span class="sxs-lookup"><span data-stu-id="86f31-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="86f31-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="86f31-104">\<system.identityModel></span></span>  
<span data-ttu-id="86f31-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="86f31-105">\<identityConfiguration></span></span>  
<span data-ttu-id="86f31-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="86f31-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="86f31-107">\<add></span><span class="sxs-lookup"><span data-stu-id="86f31-107">\<add></span></span>  
<span data-ttu-id="86f31-108">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="86f31-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86f31-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86f31-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86f31-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="86f31-110">Attributes and Elements</span></span>  
 <span data-ttu-id="86f31-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="86f31-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86f31-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="86f31-112">Attributes</span></span>  
  
|<span data-ttu-id="86f31-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="86f31-113">Attribute</span></span>|<span data-ttu-id="86f31-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86f31-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="86f31-115">durata</span><span class="sxs-lookup"><span data-stu-id="86f31-115">lifetime</span></span>|<span data-ttu-id="86f31-116">Specifica la durata del token di sessione.</span><span class="sxs-lookup"><span data-stu-id="86f31-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86f31-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="86f31-117">Child Elements</span></span>  
 <span data-ttu-id="86f31-118">None</span><span class="sxs-lookup"><span data-stu-id="86f31-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86f31-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="86f31-119">Parent Elements</span></span>  
  
|<span data-ttu-id="86f31-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="86f31-120">Element</span></span>|<span data-ttu-id="86f31-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86f31-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86f31-122">\<add></span><span class="sxs-lookup"><span data-stu-id="86f31-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="86f31-123">Aggiunge il gestore di token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="86f31-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="86f31-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="86f31-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
