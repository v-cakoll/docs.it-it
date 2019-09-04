---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252154"
---
# <a name="caches"></a><span data-ttu-id="24d55-101">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="24d55-101">\<caches></span></span>
<span data-ttu-id="24d55-102">Registra le cache utilizzate per i token di sessione e il rilevamento della riproduzione dei token.</span><span class="sxs-lookup"><span data-stu-id="24d55-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
<span data-ttu-id="24d55-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="24d55-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="24d55-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="24d55-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="24d55-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="24d55-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="24d55-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<memorizza nella cache >**</span><span class="sxs-lookup"><span data-stu-id="24d55-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24d55-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24d55-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24d55-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="24d55-108">Attributes and Elements</span></span>  
 <span data-ttu-id="24d55-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="24d55-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24d55-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="24d55-110">Attributes</span></span>  
 <span data-ttu-id="24d55-111">Nessuna</span><span class="sxs-lookup"><span data-stu-id="24d55-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="24d55-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="24d55-112">Child Elements</span></span>  
  
|<span data-ttu-id="24d55-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="24d55-113">Element</span></span>|<span data-ttu-id="24d55-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="24d55-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24d55-115">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="24d55-115">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="24d55-116">Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="24d55-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="24d55-117">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="24d55-117">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="24d55-118">Registra una cache di riproduzione dei token con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="24d55-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="24d55-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="24d55-119">Parent Elements</span></span>  
  
|<span data-ttu-id="24d55-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="24d55-120">Element</span></span>|<span data-ttu-id="24d55-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24d55-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24d55-122">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="24d55-122">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="24d55-123">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="24d55-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="24d55-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="24d55-124">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="24d55-125">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="24d55-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24d55-126">Note</span><span class="sxs-lookup"><span data-stu-id="24d55-126">Remarks</span></span>  
 <span data-ttu-id="24d55-127">Un `<caches>` elemento può essere specificato a livello di servizio `<identityConfiguration>` nell'elemento o nel livello di raccolta del gestore del token di sicurezza `<securityTokenHandlerConfiguration>` sotto l'elemento.</span><span class="sxs-lookup"><span data-stu-id="24d55-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="24d55-128">Le impostazioni in una raccolta di gestori di token eseguono l'override di quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="24d55-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="24d55-129">L' `<caches>` elemento è rappresentato <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="24d55-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="24d55-130">Le cache configurate sono rappresentate <xref:System.IdentityModel.Configuration.IdentityModelCaches> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="24d55-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24d55-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="24d55-131">Example</span></span>  
 <span data-ttu-id="24d55-132">Nel codice XML seguente viene illustrata la configurazione di una cache personalizzata per i token di<xref:System.IdentityModel.Tokens.SessionSecurityToken>sicurezza della sessione ().</span><span class="sxs-lookup"><span data-stu-id="24d55-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="24d55-133">La configurazione è ricavata `ClaimsAwareWebFarm` dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="24d55-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
