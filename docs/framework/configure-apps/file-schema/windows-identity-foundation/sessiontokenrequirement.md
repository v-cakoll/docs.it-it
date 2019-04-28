---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 0c575e02862884e8f7ecf062138c36fe731f8e19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793770"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="89894-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="89894-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="89894-102">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="89894-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="89894-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="89894-103">\<system.identityModel></span></span>  
<span data-ttu-id="89894-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="89894-104">\<identityConfiguration></span></span>  
<span data-ttu-id="89894-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="89894-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="89894-106">\<add></span><span class="sxs-lookup"><span data-stu-id="89894-106">\<add></span></span>  
<span data-ttu-id="89894-107">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="89894-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89894-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89894-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89894-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="89894-109">Attributes and Elements</span></span>  
 <span data-ttu-id="89894-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="89894-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89894-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="89894-111">Attributes</span></span>  
  
|<span data-ttu-id="89894-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="89894-112">Attribute</span></span>|<span data-ttu-id="89894-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89894-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89894-114">durata</span><span class="sxs-lookup"><span data-stu-id="89894-114">lifetime</span></span>|<span data-ttu-id="89894-115">Specifica la durata dei token di sessione.</span><span class="sxs-lookup"><span data-stu-id="89894-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89894-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="89894-116">Child Elements</span></span>  
 <span data-ttu-id="89894-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="89894-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89894-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="89894-118">Parent Elements</span></span>  
  
|<span data-ttu-id="89894-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="89894-119">Element</span></span>|<span data-ttu-id="89894-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89894-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89894-121">\<add></span><span class="sxs-lookup"><span data-stu-id="89894-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="89894-122">Aggiunge il gestore di token di sicurezza specificato nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="89894-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="89894-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="89894-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
