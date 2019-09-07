---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 624b52c0618362f48063c8f7e7c53c5a68d7de8f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400034"
---
# <a name="privacynoticeat"></a><span data-ttu-id="327ef-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="327ef-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="327ef-102">Rappresenta un elemento di configurazione che specifica un'informativa sulla privacy usata nell'associazione `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="327ef-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
<span data-ttu-id="327ef-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="327ef-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="327ef-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="327ef-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="327ef-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="327ef-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="327ef-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="327ef-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="327ef-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="327ef-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="327ef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> privacyNotice**</span><span class="sxs-lookup"><span data-stu-id="327ef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="327ef-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="327ef-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="327ef-110">Type</span><span class="sxs-lookup"><span data-stu-id="327ef-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="327ef-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="327ef-111">Attributes and Elements</span></span>  
 <span data-ttu-id="327ef-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="327ef-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="327ef-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="327ef-113">Attributes</span></span>  
  
|<span data-ttu-id="327ef-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="327ef-114">Attribute</span></span>|<span data-ttu-id="327ef-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="327ef-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="327ef-116">Stringa che specifica l'URI presso cui è disponibile l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="327ef-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="327ef-117">Numero intero che specifica la versione dell'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="327ef-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="327ef-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="327ef-118">Child Elements</span></span>  
 <span data-ttu-id="327ef-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="327ef-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="327ef-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="327ef-120">Parent Elements</span></span>  
  
|<span data-ttu-id="327ef-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="327ef-121">Element</span></span>|<span data-ttu-id="327ef-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="327ef-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="327ef-123">\<binding></span><span class="sxs-lookup"><span data-stu-id="327ef-123">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="327ef-124">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="327ef-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="327ef-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="327ef-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="327ef-126">Associazioni</span><span class="sxs-lookup"><span data-stu-id="327ef-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="327ef-127">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="327ef-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="327ef-128">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="327ef-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="327ef-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="327ef-129">\<customBinding></span></span>](custombinding.md)
