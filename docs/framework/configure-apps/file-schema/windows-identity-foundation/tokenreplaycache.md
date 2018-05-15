---
title: '&lt;tokenReplayCache&gt;'
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 79022319944c4042c6f62a7521784b826b90d4ce
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="1f644-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="1f644-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="1f644-103">Registra una cache di riproduzione token con un servizio o una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1f644-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="1f644-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1f644-104">\<system.identityModel></span></span>  
<span data-ttu-id="1f644-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1f644-105">\<identityConfiguration></span></span>  
<span data-ttu-id="1f644-106">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="1f644-106">\<caches></span></span>  
<span data-ttu-id="1f644-107">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="1f644-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f644-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f644-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f644-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1f644-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1f644-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1f644-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f644-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="1f644-111">Attributes</span></span>  
  
|<span data-ttu-id="1f644-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="1f644-112">Attribute</span></span>|<span data-ttu-id="1f644-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f644-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1f644-114">tipo</span><span class="sxs-lookup"><span data-stu-id="1f644-114">type</span></span>|<span data-ttu-id="1f644-115">Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.TokenReplayCache> classe.</span><span class="sxs-lookup"><span data-stu-id="1f644-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="1f644-116">Per ulteriori informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti al tipo personalizzato].</span><span class="sxs-lookup"><span data-stu-id="1f644-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="1f644-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1f644-117">Child Elements</span></span>  
 <span data-ttu-id="1f644-118">Nessuno</span><span class="sxs-lookup"><span data-stu-id="1f644-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1f644-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1f644-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1f644-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f644-120">Element</span></span>|<span data-ttu-id="1f644-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f644-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f644-122">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="1f644-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="1f644-123">Registra la cache utilizzate da un servizio o una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1f644-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f644-124">Note</span><span class="sxs-lookup"><span data-stu-id="1f644-124">Remarks</span></span>  
 <span data-ttu-id="1f644-125">La cache di riproduzione token viene utilizzata per rilevare i token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="1f644-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="1f644-126">Rilevamento riproduzione token è abilitato per il [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) elemento specifica anche l'ora di scadenza massimo per i token.</span><span class="sxs-lookup"><span data-stu-id="1f644-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f644-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="1f644-127">Example</span></span>  
 <span data-ttu-id="1f644-128">Il codice XML seguente viene illustrata la configurazione di una cache per il rilevamento riproduzione token personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1f644-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f644-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f644-129">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [<span data-ttu-id="1f644-130">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="1f644-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
