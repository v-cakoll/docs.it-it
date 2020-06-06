---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252154"
---
# \<caches>
<span data-ttu-id="e1a95-101">Registra le cache utilizzate per i token di sessione e il rilevamento della riproduzione dei token.</span><span class="sxs-lookup"><span data-stu-id="e1a95-101">Registers the caches used for session tokens and token replay detection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**  
  
## <a name="syntax"></a><span data-ttu-id="e1a95-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1a95-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1a95-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e1a95-103">Attributes and Elements</span></span>  
 <span data-ttu-id="e1a95-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e1a95-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1a95-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="e1a95-105">Attributes</span></span>  
 <span data-ttu-id="e1a95-106">nessuno</span><span class="sxs-lookup"><span data-stu-id="e1a95-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e1a95-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e1a95-107">Child Elements</span></span>  
  
|<span data-ttu-id="e1a95-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1a95-108">Element</span></span>|<span data-ttu-id="e1a95-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1a95-109">Description</span></span>|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](sessionsecuritytokencache.md)|<span data-ttu-id="e1a95-110">Registra una cache per i token di sessione con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e1a95-110">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[\<tokenReplayCache>](tokenreplaycache.md)|<span data-ttu-id="e1a95-111">Registra una cache di riproduzione dei token con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e1a95-111">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1a95-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e1a95-112">Parent Elements</span></span>  
  
|<span data-ttu-id="e1a95-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1a95-113">Element</span></span>|<span data-ttu-id="e1a95-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1a95-114">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="e1a95-115">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="e1a95-115">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e1a95-116">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e1a95-116">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1a95-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="e1a95-117">Remarks</span></span>  
 <span data-ttu-id="e1a95-118">Un `<caches>` elemento può essere specificato a livello di servizio nell' `<identityConfiguration>` elemento o nel livello di raccolta del gestore del token di sicurezza sotto l' `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="e1a95-118">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="e1a95-119">Le impostazioni in una raccolta di gestori di token eseguono l'override di quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="e1a95-119">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="e1a95-120">L' `<caches>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> classe.</span><span class="sxs-lookup"><span data-stu-id="e1a95-120">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="e1a95-121">Le cache configurate sono rappresentate dalla <xref:System.IdentityModel.Configuration.IdentityModelCaches> classe.</span><span class="sxs-lookup"><span data-stu-id="e1a95-121">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1a95-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1a95-122">Example</span></span>  
 <span data-ttu-id="e1a95-123">Nel codice XML seguente viene illustrata la configurazione di una cache personalizzata per i token di sicurezza della sessione ( <xref:System.IdentityModel.Tokens.SessionSecurityToken> ).</span><span class="sxs-lookup"><span data-stu-id="e1a95-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="e1a95-124">La configurazione è ricavata dall' `ClaimsAwareWebFarm` esempio.</span><span class="sxs-lookup"><span data-stu-id="e1a95-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
