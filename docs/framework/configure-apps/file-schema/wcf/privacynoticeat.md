---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2ff70d3a8636970434582e417e4549ab6b433fc1
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738758"
---
# <a name="privacynoticeat"></a><span data-ttu-id="245bc-101">\<privacyNoticeAt ></span><span class="sxs-lookup"><span data-stu-id="245bc-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="245bc-102">Rappresenta un elemento di configurazione che specifica un'informativa sulla privacy usata nell'associazione `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="245bc-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
<span data-ttu-id="245bc-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="245bc-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="245bc-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="245bc-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="245bc-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="245bc-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="245bc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="245bc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="245bc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="245bc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="245bc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<privacyNotice >**</span><span class="sxs-lookup"><span data-stu-id="245bc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="245bc-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="245bc-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="245bc-110">Digitare</span><span class="sxs-lookup"><span data-stu-id="245bc-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="245bc-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="245bc-111">Attributes and Elements</span></span>  
 <span data-ttu-id="245bc-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="245bc-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="245bc-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="245bc-113">Attributes</span></span>  
  
|<span data-ttu-id="245bc-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="245bc-114">Attribute</span></span>|<span data-ttu-id="245bc-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="245bc-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="245bc-116">Stringa che specifica l'URI presso cui è disponibile l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="245bc-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="245bc-117">Numero intero che specifica la versione dell'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="245bc-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="245bc-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="245bc-118">Child Elements</span></span>  
 <span data-ttu-id="245bc-119">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="245bc-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="245bc-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="245bc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="245bc-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="245bc-121">Element</span></span>|<span data-ttu-id="245bc-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="245bc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="245bc-123">\<binding ></span><span class="sxs-lookup"><span data-stu-id="245bc-123">\<binding></span></span>](bindings.md)|<span data-ttu-id="245bc-124">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="245bc-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="245bc-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="245bc-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="245bc-126">Associazioni</span><span class="sxs-lookup"><span data-stu-id="245bc-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="245bc-127">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="245bc-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="245bc-128">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="245bc-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="245bc-129">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="245bc-129">\<customBinding></span></span>](custombinding.md)
