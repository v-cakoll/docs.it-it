---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152541"
---
# \<sessionTokenRequirement>
<span data-ttu-id="95bfc-101">Fornisce la configurazione per la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="95bfc-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="95bfc-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95bfc-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95bfc-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="95bfc-103">Attributes and Elements</span></span>  
 <span data-ttu-id="95bfc-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="95bfc-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95bfc-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="95bfc-105">Attributes</span></span>  
  
|<span data-ttu-id="95bfc-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="95bfc-106">Attribute</span></span>|<span data-ttu-id="95bfc-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95bfc-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95bfc-108">lifetime</span><span class="sxs-lookup"><span data-stu-id="95bfc-108">lifetime</span></span>|<span data-ttu-id="95bfc-109">Specifica la durata dei token di sessione.</span><span class="sxs-lookup"><span data-stu-id="95bfc-109">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95bfc-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="95bfc-110">Child Elements</span></span>  
 <span data-ttu-id="95bfc-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="95bfc-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95bfc-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="95bfc-112">Parent Elements</span></span>  
  
|<span data-ttu-id="95bfc-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="95bfc-113">Element</span></span>|<span data-ttu-id="95bfc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95bfc-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="95bfc-115">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="95bfc-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="95bfc-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="95bfc-116">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
