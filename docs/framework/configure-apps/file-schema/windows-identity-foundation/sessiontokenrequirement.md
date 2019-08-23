---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 254d34149892abeaf31b9227f7567eb0a66ec0b6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943669"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="8107c-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="8107c-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="8107c-102">Fornisce la configurazione per <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> la classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="8107c-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="8107c-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="8107c-103">\<system.identityModel></span></span>  
<span data-ttu-id="8107c-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="8107c-104">\<identityConfiguration></span></span>  
<span data-ttu-id="8107c-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="8107c-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="8107c-106">\<add></span><span class="sxs-lookup"><span data-stu-id="8107c-106">\<add></span></span>  
<span data-ttu-id="8107c-107">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="8107c-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8107c-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8107c-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8107c-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8107c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8107c-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8107c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8107c-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8107c-111">Attributes</span></span>  
  
|<span data-ttu-id="8107c-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="8107c-112">Attribute</span></span>|<span data-ttu-id="8107c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8107c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8107c-114">durata</span><span class="sxs-lookup"><span data-stu-id="8107c-114">lifetime</span></span>|<span data-ttu-id="8107c-115">Specifica la durata dei token di sessione.</span><span class="sxs-lookup"><span data-stu-id="8107c-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8107c-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8107c-116">Child Elements</span></span>  
 <span data-ttu-id="8107c-117">Nessuna</span><span class="sxs-lookup"><span data-stu-id="8107c-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8107c-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8107c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8107c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="8107c-119">Element</span></span>|<span data-ttu-id="8107c-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="8107c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8107c-121">\<add></span><span class="sxs-lookup"><span data-stu-id="8107c-121">\<add></span></span>](add.md)|<span data-ttu-id="8107c-122">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="8107c-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8107c-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="8107c-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
