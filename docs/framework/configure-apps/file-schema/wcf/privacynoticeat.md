---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: e2ce2111e4bb26cc6a51b4a772b1d8a4d3238c70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200766"
---
# <a name="privacynoticeat"></a><span data-ttu-id="b00f9-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="b00f9-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="b00f9-102">Rappresenta un elemento di configurazione che specifica un'informativa sulla privacy usata nell'associazione `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="b00f9-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="b00f9-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b00f9-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b00f9-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="b00f9-104">\<bindings></span></span>  
<span data-ttu-id="b00f9-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b00f9-105">\<customBinding></span></span>  
<span data-ttu-id="b00f9-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="b00f9-106">\<binding></span></span>  
<span data-ttu-id="b00f9-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="b00f9-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b00f9-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b00f9-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="b00f9-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="b00f9-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b00f9-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b00f9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b00f9-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b00f9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b00f9-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="b00f9-112">Attributes</span></span>  
  
|<span data-ttu-id="b00f9-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="b00f9-113">Attribute</span></span>|<span data-ttu-id="b00f9-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b00f9-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="b00f9-115">Stringa che specifica l'URI presso cui è disponibile l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="b00f9-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="b00f9-116">Numero intero che specifica la versione dell'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="b00f9-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b00f9-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b00f9-117">Child Elements</span></span>  
 <span data-ttu-id="b00f9-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b00f9-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b00f9-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b00f9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b00f9-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="b00f9-120">Element</span></span>|<span data-ttu-id="b00f9-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b00f9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b00f9-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="b00f9-122">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b00f9-123">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b00f9-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b00f9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b00f9-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b00f9-125">Associazioni</span><span class="sxs-lookup"><span data-stu-id="b00f9-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b00f9-126">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="b00f9-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b00f9-127">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="b00f9-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b00f9-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b00f9-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
