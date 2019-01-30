---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: b1de2a304a5dc4295497ea1f3b395240cb5ca9bc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254913"
---
# <a name="privacynoticeat"></a><span data-ttu-id="9ac71-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="9ac71-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="9ac71-102">Rappresenta un elemento di configurazione che specifica un'informativa sulla privacy usata nell'associazione `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="9ac71-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="9ac71-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9ac71-103">\<system.serviceModel></span></span>  
<span data-ttu-id="9ac71-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="9ac71-104">\<bindings></span></span>  
<span data-ttu-id="9ac71-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9ac71-105">\<customBinding></span></span>  
<span data-ttu-id="9ac71-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="9ac71-106">\<binding></span></span>  
<span data-ttu-id="9ac71-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="9ac71-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ac71-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ac71-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="9ac71-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="9ac71-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ac71-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9ac71-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9ac71-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9ac71-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ac71-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="9ac71-112">Attributes</span></span>  
  
|<span data-ttu-id="9ac71-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="9ac71-113">Attribute</span></span>|<span data-ttu-id="9ac71-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ac71-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="9ac71-115">Stringa che specifica l'URI presso cui è disponibile l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="9ac71-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="9ac71-116">Numero intero che specifica la versione dell'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="9ac71-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ac71-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9ac71-117">Child Elements</span></span>  
 <span data-ttu-id="9ac71-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9ac71-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ac71-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9ac71-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9ac71-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ac71-120">Element</span></span>|<span data-ttu-id="9ac71-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ac71-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ac71-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="9ac71-122">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="9ac71-123">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="9ac71-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ac71-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ac71-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9ac71-125">Associazioni</span><span class="sxs-lookup"><span data-stu-id="9ac71-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9ac71-126">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="9ac71-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9ac71-127">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="9ac71-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9ac71-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9ac71-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
