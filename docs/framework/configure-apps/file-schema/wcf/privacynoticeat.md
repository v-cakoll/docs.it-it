---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: e2ce2111e4bb26cc6a51b4a772b1d8a4d3238c70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200766"
---
# <a name="privacynoticeat"></a><span data-ttu-id="319b1-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="319b1-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="319b1-102">Rappresenta un elemento di configurazione che specifica un'informativa sulla privacy usata nell'associazione `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="319b1-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="319b1-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="319b1-103">\<system.serviceModel></span></span>  
<span data-ttu-id="319b1-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="319b1-104">\<bindings></span></span>  
<span data-ttu-id="319b1-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="319b1-105">\<customBinding></span></span>  
<span data-ttu-id="319b1-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="319b1-106">\<binding></span></span>  
<span data-ttu-id="319b1-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="319b1-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="319b1-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="319b1-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="319b1-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="319b1-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="319b1-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="319b1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="319b1-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="319b1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="319b1-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="319b1-112">Attributes</span></span>  
  
|<span data-ttu-id="319b1-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="319b1-113">Attribute</span></span>|<span data-ttu-id="319b1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="319b1-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="319b1-115">Stringa che specifica l'URI presso cui è disponibile l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="319b1-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="319b1-116">Numero intero che specifica la versione dell'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="319b1-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="319b1-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="319b1-117">Child Elements</span></span>  
 <span data-ttu-id="319b1-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="319b1-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="319b1-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="319b1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="319b1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="319b1-120">Element</span></span>|<span data-ttu-id="319b1-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="319b1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="319b1-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="319b1-122">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="319b1-123">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="319b1-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="319b1-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="319b1-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="319b1-125">Associazioni</span><span class="sxs-lookup"><span data-stu-id="319b1-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="319b1-126">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="319b1-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="319b1-127">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="319b1-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="319b1-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="319b1-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
