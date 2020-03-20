---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152541"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="9b7f4-101">\<> sessionTokenRequirement</span><span class="sxs-lookup"><span data-stu-id="9b7f4-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="9b7f4-102">Fornisce la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> configurazione per la classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="9b7f4-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="9b7f4-103">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b7f4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b7f4-104">&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="9b7f4-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="9b7f4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="9b7f4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="9b7f4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="9b7f4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="9b7f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<aggiungere>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="9b7f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="9b7f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>sessionTokenRequirement**</span><span class="sxs-lookup"><span data-stu-id="9b7f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b7f4-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b7f4-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b7f4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9b7f4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9b7f4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9b7f4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b7f4-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="9b7f4-112">Attributes</span></span>  
  
|<span data-ttu-id="9b7f4-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="9b7f4-113">Attribute</span></span>|<span data-ttu-id="9b7f4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b7f4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b7f4-115">lifetime</span><span class="sxs-lookup"><span data-stu-id="9b7f4-115">lifetime</span></span>|<span data-ttu-id="9b7f4-116">Specifica la durata dei token di sessione.</span><span class="sxs-lookup"><span data-stu-id="9b7f4-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b7f4-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9b7f4-117">Child Elements</span></span>  
 <span data-ttu-id="9b7f4-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="9b7f4-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b7f4-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9b7f4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9b7f4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b7f4-120">Element</span></span>|<span data-ttu-id="9b7f4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b7f4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b7f4-122">\<aggiungere></span><span class="sxs-lookup"><span data-stu-id="9b7f4-122">\<add></span></span>](add.md)|<span data-ttu-id="9b7f4-123">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="9b7f4-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9b7f4-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b7f4-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
