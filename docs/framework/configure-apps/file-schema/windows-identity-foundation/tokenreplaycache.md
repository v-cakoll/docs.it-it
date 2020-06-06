---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 9f3a95fd0a39f199eaf13c7509aff22caa0e3b66
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251777"
---
# \<tokenReplayCache>
<span data-ttu-id="c58ed-101">Registra una cache di riproduzione dei token con un servizio o una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c58ed-101">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a><span data-ttu-id="c58ed-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c58ed-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c58ed-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c58ed-103">Attributes and Elements</span></span>  
 <span data-ttu-id="c58ed-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c58ed-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c58ed-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="c58ed-105">Attributes</span></span>  
  
|<span data-ttu-id="c58ed-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="c58ed-106">Attribute</span></span>|<span data-ttu-id="c58ed-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c58ed-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c58ed-108">type</span><span class="sxs-lookup"><span data-stu-id="c58ed-108">type</span></span>|<span data-ttu-id="c58ed-109">Tipo che deriva dalla <xref:System.IdentityModel.Tokens.TokenReplayCache> classe.</span><span class="sxs-lookup"><span data-stu-id="c58ed-109">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="c58ed-110">Per ulteriori informazioni su come specificare un oggetto personalizzato `type` , vedere [riferimenti ai tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="c58ed-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="c58ed-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c58ed-111">Child Elements</span></span>  
 <span data-ttu-id="c58ed-112">nessuno</span><span class="sxs-lookup"><span data-stu-id="c58ed-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c58ed-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c58ed-113">Parent Elements</span></span>  
  
|<span data-ttu-id="c58ed-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="c58ed-114">Element</span></span>|<span data-ttu-id="c58ed-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c58ed-115">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="c58ed-116">Registra le cache utilizzate da un servizio o da una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c58ed-116">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c58ed-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="c58ed-117">Remarks</span></span>  
 <span data-ttu-id="c58ed-118">La cache di riproduzione dei token viene utilizzata per rilevare i token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="c58ed-118">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="c58ed-119">Il rilevamento della riproduzione dei token è abilitato dall' [\<tokenReplayDetection>](tokenreplaydetection.md) elemento, che specifica anche il tempo massimo di scadenza per i token.</span><span class="sxs-lookup"><span data-stu-id="c58ed-119">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c58ed-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="c58ed-120">Example</span></span>  
 <span data-ttu-id="c58ed-121">Nel codice XML seguente viene illustrata la configurazione di una cache personalizzata per il rilevamento dei token riprodotti.</span><span class="sxs-lookup"><span data-stu-id="c58ed-121">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c58ed-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c58ed-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
