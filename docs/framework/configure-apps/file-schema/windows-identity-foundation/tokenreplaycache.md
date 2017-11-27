---
title: '&lt;tokenReplayCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e43e79416ddb8862cbc6e52d9d449a02b123af83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="7e8a0-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="7e8a0-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="7e8a0-103">Registra una cache di riproduzione token con un servizio o una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7e8a0-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="7e8a0-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="7e8a0-104">\<system.identityModel></span></span>  
<span data-ttu-id="7e8a0-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="7e8a0-105">\<identityConfiguration></span></span>  
<span data-ttu-id="7e8a0-106">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="7e8a0-106">\<caches></span></span>  
<span data-ttu-id="7e8a0-107">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="7e8a0-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e8a0-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e8a0-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e8a0-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7e8a0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7e8a0-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7e8a0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e8a0-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="7e8a0-111">Attributes</span></span>  
  
|<span data-ttu-id="7e8a0-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="7e8a0-112">Attribute</span></span>|<span data-ttu-id="7e8a0-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e8a0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e8a0-114">type</span><span class="sxs-lookup"><span data-stu-id="7e8a0-114">type</span></span>|<span data-ttu-id="7e8a0-115">Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.TokenReplayCache> classe.</span><span class="sxs-lookup"><span data-stu-id="7e8a0-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="7e8a0-116">Per ulteriori informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti al tipo personalizzato].</span><span class="sxs-lookup"><span data-stu-id="7e8a0-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="7e8a0-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7e8a0-117">Child Elements</span></span>  
 <span data-ttu-id="7e8a0-118">None</span><span class="sxs-lookup"><span data-stu-id="7e8a0-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e8a0-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7e8a0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7e8a0-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="7e8a0-120">Element</span></span>|<span data-ttu-id="7e8a0-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e8a0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e8a0-122">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="7e8a0-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="7e8a0-123">Registra la cache utilizzate da un servizio o una raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7e8a0-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e8a0-124">Note</span><span class="sxs-lookup"><span data-stu-id="7e8a0-124">Remarks</span></span>  
 <span data-ttu-id="7e8a0-125">La cache di riproduzione token viene utilizzata per rilevare i token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="7e8a0-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="7e8a0-126">Rilevamento riproduzione token è abilitato per il [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) elemento specifica anche l'ora di scadenza massimo per i token.</span><span class="sxs-lookup"><span data-stu-id="7e8a0-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e8a0-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="7e8a0-127">Example</span></span>  
 <span data-ttu-id="7e8a0-128">Il codice XML seguente viene illustrata la configurazione di una cache per il rilevamento riproduzione token personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7e8a0-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e8a0-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e8a0-129">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [<span data-ttu-id="7e8a0-130">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="7e8a0-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
