---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2ff70d3a8636970434582e417e4549ab6b433fc1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738758"
---
# \<privacyNoticeAt>
<span data-ttu-id="33989-101">Rappresenta un elemento di configurazione che specifica un'informativa sulla privacy usata nell'associazione `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="33989-101">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**  
  
## <a name="syntax"></a><span data-ttu-id="33989-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33989-102">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="33989-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="33989-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33989-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="33989-104">Attributes and Elements</span></span>  
 <span data-ttu-id="33989-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="33989-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33989-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="33989-106">Attributes</span></span>  
  
|<span data-ttu-id="33989-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="33989-107">Attribute</span></span>|<span data-ttu-id="33989-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33989-108">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="33989-109">Stringa che specifica l'URI presso cui è disponibile l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="33989-109">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="33989-110">Numero intero che specifica la versione dell'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="33989-110">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33989-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="33989-111">Child Elements</span></span>  
 <span data-ttu-id="33989-112">No.</span><span class="sxs-lookup"><span data-stu-id="33989-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33989-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="33989-113">Parent Elements</span></span>  
  
|<span data-ttu-id="33989-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="33989-114">Element</span></span>|<span data-ttu-id="33989-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33989-115">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="33989-116">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="33989-116">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33989-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="33989-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="33989-118">Binding</span><span class="sxs-lookup"><span data-stu-id="33989-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="33989-119">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="33989-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="33989-120">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="33989-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
