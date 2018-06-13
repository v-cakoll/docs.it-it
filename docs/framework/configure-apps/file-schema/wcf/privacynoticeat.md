---
title: '&lt;privacyNoticeAt&gt;'
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2914a3716b9e2adb6ebc47fd73ccee027a3b65da
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749244"
---
# <a name="ltprivacynoticeatgt"></a><span data-ttu-id="ff459-102">&lt;privacyNoticeAt&gt;</span><span class="sxs-lookup"><span data-stu-id="ff459-102">&lt;privacyNoticeAt&gt;</span></span>
<span data-ttu-id="ff459-103">Rappresenta un elemento di configurazione che specifica un'informativa sulla privacy usata nell'associazione `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="ff459-103">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="ff459-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ff459-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ff459-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="ff459-105">\<bindings></span></span>  
<span data-ttu-id="ff459-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ff459-106">\<customBinding></span></span>  
<span data-ttu-id="ff459-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="ff459-107">\<binding></span></span>  
<span data-ttu-id="ff459-108">\<privacyNotice ></span><span class="sxs-lookup"><span data-stu-id="ff459-108">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff459-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff459-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"  
        version="Integer" />  
```  
  
## <a name="type"></a><span data-ttu-id="ff459-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="ff459-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff459-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ff459-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ff459-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ff459-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff459-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="ff459-113">Attributes</span></span>  
  
|<span data-ttu-id="ff459-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="ff459-114">Attribute</span></span>|<span data-ttu-id="ff459-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff459-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="ff459-116">Stringa che specifica l'URI presso cui è disponibile l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="ff459-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="ff459-117">Numero intero che specifica la versione dell'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="ff459-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff459-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ff459-118">Child Elements</span></span>  
 <span data-ttu-id="ff459-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ff459-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff459-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ff459-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ff459-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff459-121">Element</span></span>|<span data-ttu-id="ff459-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff459-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff459-123">\<binding></span><span class="sxs-lookup"><span data-stu-id="ff459-123">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="ff459-124">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ff459-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff459-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff459-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="ff459-126">Associazioni</span><span class="sxs-lookup"><span data-stu-id="ff459-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ff459-127">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="ff459-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="ff459-128">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ff459-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="ff459-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ff459-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
