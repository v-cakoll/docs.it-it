---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: dfa6c0d84582d55595f00f149adfdcaa9d554d6b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271950"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="c8197-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="c8197-101">\<tokenReplayCache></span></span>
<span data-ttu-id="c8197-102">Registra una cache di riproduzione dei token con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c8197-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="c8197-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c8197-103">\<system.identityModel></span></span>  
<span data-ttu-id="c8197-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c8197-104">\<identityConfiguration></span></span>  
<span data-ttu-id="c8197-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="c8197-105">\<caches></span></span>  
<span data-ttu-id="c8197-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="c8197-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8197-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8197-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8197-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c8197-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c8197-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c8197-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8197-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="c8197-110">Attributes</span></span>  
  
|<span data-ttu-id="c8197-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="c8197-111">Attribute</span></span>|<span data-ttu-id="c8197-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8197-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8197-113">tipo</span><span class="sxs-lookup"><span data-stu-id="c8197-113">type</span></span>|<span data-ttu-id="c8197-114">Un tipo da cui deriva il <xref:System.IdentityModel.Tokens.TokenReplayCache> classe.</span><span class="sxs-lookup"><span data-stu-id="c8197-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="c8197-115">Per altre informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti a tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="c8197-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="c8197-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c8197-116">Child Elements</span></span>  
 <span data-ttu-id="c8197-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="c8197-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8197-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c8197-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c8197-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c8197-119">Element</span></span>|<span data-ttu-id="c8197-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8197-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8197-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="c8197-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="c8197-122">Registra le cache utilizzate da un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c8197-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8197-123">Note</span><span class="sxs-lookup"><span data-stu-id="c8197-123">Remarks</span></span>  
 <span data-ttu-id="c8197-124">La cache di riproduzione del token viene usata per rilevare i token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="c8197-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="c8197-125">Rilevamento riproduzione token è abilitato per il [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) elemento che specifica anche l'ora di scadenza massimo per i token.</span><span class="sxs-lookup"><span data-stu-id="c8197-125">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8197-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8197-126">Example</span></span>  
 <span data-ttu-id="c8197-127">Il codice XML seguente viene illustrata la configurazione di una cache personalizzata per rilevare i token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="c8197-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8197-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8197-128">See also</span></span>
- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="c8197-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="c8197-129">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
