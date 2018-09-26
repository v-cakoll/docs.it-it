---
title: '&lt;tokenReplayCache&gt;'
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: d21a819f789b5be4bdf7ebf57b37a072e1d213ff
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47206220"
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="c95f6-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="c95f6-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="c95f6-103">Registra una cache di riproduzione dei token con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c95f6-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="c95f6-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c95f6-104">\<system.identityModel></span></span>  
<span data-ttu-id="c95f6-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c95f6-105">\<identityConfiguration></span></span>  
<span data-ttu-id="c95f6-106">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="c95f6-106">\<caches></span></span>  
<span data-ttu-id="c95f6-107">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="c95f6-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c95f6-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c95f6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c95f6-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c95f6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c95f6-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c95f6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c95f6-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="c95f6-111">Attributes</span></span>  
  
|<span data-ttu-id="c95f6-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="c95f6-112">Attribute</span></span>|<span data-ttu-id="c95f6-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c95f6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c95f6-114">tipo</span><span class="sxs-lookup"><span data-stu-id="c95f6-114">type</span></span>|<span data-ttu-id="c95f6-115">Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.TokenReplayCache> classe.</span><span class="sxs-lookup"><span data-stu-id="c95f6-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="c95f6-116">Per altre informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti a tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="c95f6-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="c95f6-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c95f6-117">Child Elements</span></span>  
 <span data-ttu-id="c95f6-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="c95f6-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c95f6-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c95f6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c95f6-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="c95f6-120">Element</span></span>|<span data-ttu-id="c95f6-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c95f6-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c95f6-122">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="c95f6-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="c95f6-123">Registra le cache utilizzate da un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c95f6-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c95f6-124">Note</span><span class="sxs-lookup"><span data-stu-id="c95f6-124">Remarks</span></span>  
 <span data-ttu-id="c95f6-125">La cache di riproduzione del token viene usata per rilevare i token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="c95f6-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="c95f6-126">Rilevamento riproduzione token è abilitato per il [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) elemento che specifica anche l'ora di scadenza massimo per i token.</span><span class="sxs-lookup"><span data-stu-id="c95f6-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c95f6-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="c95f6-127">Example</span></span>  
 <span data-ttu-id="c95f6-128">Il codice XML seguente viene illustrata la configurazione di una cache personalizzata per rilevare i token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="c95f6-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c95f6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c95f6-129">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [<span data-ttu-id="c95f6-130">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="c95f6-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
