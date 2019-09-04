---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 968c48df9e92a1dfbfb6e248b06cf4f97cece8b4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251822"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="58d27-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="58d27-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="58d27-102">Fornisce la configurazione per <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> la classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="58d27-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="58d27-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="58d27-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="58d27-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="58d27-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="58d27-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="58d27-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="58d27-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="58d27-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="58d27-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Aggiungi >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="58d27-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="58d27-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> sessionTokenRequirement**</span><span class="sxs-lookup"><span data-stu-id="58d27-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d27-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58d27-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58d27-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="58d27-110">Attributes and Elements</span></span>  
 <span data-ttu-id="58d27-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="58d27-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58d27-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="58d27-112">Attributes</span></span>  
  
|<span data-ttu-id="58d27-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="58d27-113">Attribute</span></span>|<span data-ttu-id="58d27-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="58d27-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58d27-115">durata</span><span class="sxs-lookup"><span data-stu-id="58d27-115">lifetime</span></span>|<span data-ttu-id="58d27-116">Specifica la durata dei token di sessione.</span><span class="sxs-lookup"><span data-stu-id="58d27-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58d27-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="58d27-117">Child Elements</span></span>  
 <span data-ttu-id="58d27-118">Nessuna</span><span class="sxs-lookup"><span data-stu-id="58d27-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58d27-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="58d27-119">Parent Elements</span></span>  
  
|<span data-ttu-id="58d27-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="58d27-120">Element</span></span>|<span data-ttu-id="58d27-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58d27-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58d27-122">\<add></span><span class="sxs-lookup"><span data-stu-id="58d27-122">\<add></span></span>](add.md)|<span data-ttu-id="58d27-123">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="58d27-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="58d27-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="58d27-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
