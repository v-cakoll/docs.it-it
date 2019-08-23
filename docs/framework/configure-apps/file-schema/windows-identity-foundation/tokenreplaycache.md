---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5747a4cfa93118dd41292904b168bbef02fec415
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944073"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="ca4ba-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="ca4ba-101">\<tokenReplayCache></span></span>
<span data-ttu-id="ca4ba-102">Registra una cache di riproduzione dei token con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ca4ba-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="ca4ba-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ca4ba-103">\<system.identityModel></span></span>  
<span data-ttu-id="ca4ba-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ca4ba-104">\<identityConfiguration></span></span>  
<span data-ttu-id="ca4ba-105">\<memorizza nella cache ></span><span class="sxs-lookup"><span data-stu-id="ca4ba-105">\<caches></span></span>  
<span data-ttu-id="ca4ba-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="ca4ba-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca4ba-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca4ba-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca4ba-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ca4ba-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ca4ba-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ca4ba-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca4ba-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="ca4ba-110">Attributes</span></span>  
  
|<span data-ttu-id="ca4ba-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="ca4ba-111">Attribute</span></span>|<span data-ttu-id="ca4ba-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="ca4ba-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca4ba-113">type</span><span class="sxs-lookup"><span data-stu-id="ca4ba-113">type</span></span>|<span data-ttu-id="ca4ba-114">Tipo che deriva dalla <xref:System.IdentityModel.Tokens.TokenReplayCache> classe.</span><span class="sxs-lookup"><span data-stu-id="ca4ba-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="ca4ba-115">Per ulteriori informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti ai tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="ca4ba-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="ca4ba-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ca4ba-116">Child Elements</span></span>  
 <span data-ttu-id="ca4ba-117">Nessuna</span><span class="sxs-lookup"><span data-stu-id="ca4ba-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca4ba-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ca4ba-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ca4ba-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca4ba-119">Element</span></span>|<span data-ttu-id="ca4ba-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca4ba-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca4ba-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="ca4ba-121">\<caches></span></span>](caches.md)|<span data-ttu-id="ca4ba-122">Registra le cache utilizzate da un servizio o da una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ca4ba-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca4ba-123">Note</span><span class="sxs-lookup"><span data-stu-id="ca4ba-123">Remarks</span></span>  
 <span data-ttu-id="ca4ba-124">La cache di riproduzione dei token viene utilizzata per rilevare i token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="ca4ba-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="ca4ba-125">Il rilevamento riproduzione token è abilitato dall'elemento [ >tokenReplayDetection,chespecificaanchelascadenzamassimaperitoken\<](tokenreplaydetection.md) .</span><span class="sxs-lookup"><span data-stu-id="ca4ba-125">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca4ba-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca4ba-126">Example</span></span>  
 <span data-ttu-id="ca4ba-127">Nel codice XML seguente viene illustrata la configurazione di una cache personalizzata per il rilevamento dei token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="ca4ba-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca4ba-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca4ba-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="ca4ba-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="ca4ba-129">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
