---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 9f3a95fd0a39f199eaf13c7509aff22caa0e3b66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251777"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="03499-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="03499-101">\<tokenReplayCache></span></span>
<span data-ttu-id="03499-102">Registra una cache di riproduzione dei token con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="03499-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="03499-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="03499-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="03499-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="03499-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="03499-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="03499-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="03499-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memorizza nella cache >** ](caches.md)</span><span class="sxs-lookup"><span data-stu-id="03499-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="03499-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> tokenReplayCache**</span><span class="sxs-lookup"><span data-stu-id="03499-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03499-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03499-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03499-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="03499-109">Attributes and Elements</span></span>  
 <span data-ttu-id="03499-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="03499-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03499-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="03499-111">Attributes</span></span>  
  
|<span data-ttu-id="03499-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="03499-112">Attribute</span></span>|<span data-ttu-id="03499-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="03499-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03499-114">type</span><span class="sxs-lookup"><span data-stu-id="03499-114">type</span></span>|<span data-ttu-id="03499-115">Tipo che deriva dalla <xref:System.IdentityModel.Tokens.TokenReplayCache> classe.</span><span class="sxs-lookup"><span data-stu-id="03499-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="03499-116">Per ulteriori informazioni su come specificare un oggetto personalizzato `type`, vedere [riferimenti ai tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="03499-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="03499-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="03499-117">Child Elements</span></span>  
 <span data-ttu-id="03499-118">Nessuna</span><span class="sxs-lookup"><span data-stu-id="03499-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03499-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="03499-119">Parent Elements</span></span>  
  
|<span data-ttu-id="03499-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="03499-120">Element</span></span>|<span data-ttu-id="03499-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03499-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03499-122">\<caches></span><span class="sxs-lookup"><span data-stu-id="03499-122">\<caches></span></span>](caches.md)|<span data-ttu-id="03499-123">Registra le cache utilizzate da un servizio o da una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="03499-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03499-124">Note</span><span class="sxs-lookup"><span data-stu-id="03499-124">Remarks</span></span>  
 <span data-ttu-id="03499-125">La cache di riproduzione dei token viene utilizzata per rilevare i token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="03499-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="03499-126">Il rilevamento riproduzione token è abilitato dall'elemento [ >tokenReplayDetection,chespecificaanchelascadenzamassimaperitoken\<](tokenreplaydetection.md) .</span><span class="sxs-lookup"><span data-stu-id="03499-126">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03499-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="03499-127">Example</span></span>  
 <span data-ttu-id="03499-128">Nel codice XML seguente viene illustrata la configurazione di una cache personalizzata per il rilevamento dei token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="03499-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="03499-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03499-129">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="03499-130">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="03499-130">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
