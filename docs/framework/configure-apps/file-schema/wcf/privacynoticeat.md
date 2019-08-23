---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: f7349bf61082c5d8e5bd4249e01b8835a1861cb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934265"
---
# <a name="privacynoticeat"></a><span data-ttu-id="4f9d7-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="4f9d7-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="4f9d7-102">Rappresenta un elemento di configurazione che specifica un'informativa sulla privacy usata nell'associazione `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="4f9d7-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="4f9d7-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4f9d7-103">\<system.serviceModel></span></span>  
<span data-ttu-id="4f9d7-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="4f9d7-104">\<bindings></span></span>  
<span data-ttu-id="4f9d7-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4f9d7-105">\<customBinding></span></span>  
<span data-ttu-id="4f9d7-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f9d7-106">\<binding></span></span>  
<span data-ttu-id="4f9d7-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="4f9d7-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f9d7-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f9d7-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="4f9d7-109">Type</span><span class="sxs-lookup"><span data-stu-id="4f9d7-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f9d7-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4f9d7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4f9d7-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4f9d7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f9d7-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4f9d7-112">Attributes</span></span>  
  
|<span data-ttu-id="4f9d7-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="4f9d7-113">Attribute</span></span>|<span data-ttu-id="4f9d7-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4f9d7-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="4f9d7-115">Stringa che specifica l'URI presso cui è disponibile l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="4f9d7-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="4f9d7-116">Numero intero che specifica la versione dell'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="4f9d7-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f9d7-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4f9d7-117">Child Elements</span></span>  
 <span data-ttu-id="4f9d7-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4f9d7-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f9d7-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4f9d7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4f9d7-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f9d7-120">Element</span></span>|<span data-ttu-id="4f9d7-121">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4f9d7-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f9d7-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f9d7-122">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="4f9d7-123">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4f9d7-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f9d7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f9d7-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4f9d7-125">Associazioni</span><span class="sxs-lookup"><span data-stu-id="4f9d7-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4f9d7-126">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="4f9d7-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4f9d7-127">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="4f9d7-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4f9d7-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4f9d7-128">\<customBinding></span></span>](custombinding.md)
