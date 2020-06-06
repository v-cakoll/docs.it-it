---
title: <add> di <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: d75142209ad8706d0cad5ce188d9d991a5e881bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850592"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="300e5-102">\<add> di \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="300e5-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="300e5-103">Rappresenta un elemento di configurazione che specifica indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="300e5-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="300e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="300e5-104">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="300e5-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="300e5-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="300e5-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="300e5-106">Attributes and Elements</span></span>  
 <span data-ttu-id="300e5-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="300e5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="300e5-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="300e5-108">Attributes</span></span>  
  
|<span data-ttu-id="300e5-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="300e5-109">Attribute</span></span>|<span data-ttu-id="300e5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="300e5-110">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="300e5-111">Stringa che specifica un indirizzo di base usato dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="300e5-111">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="300e5-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="300e5-112">Child Elements</span></span>  
 <span data-ttu-id="300e5-113">No.</span><span class="sxs-lookup"><span data-stu-id="300e5-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="300e5-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="300e5-114">Parent Elements</span></span>  
  
|<span data-ttu-id="300e5-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="300e5-115">Element</span></span>|<span data-ttu-id="300e5-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="300e5-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="300e5-117">Raccolta di elementi `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="300e5-117">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="300e5-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="300e5-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="300e5-119">Hosting</span><span class="sxs-lookup"><span data-stu-id="300e5-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
