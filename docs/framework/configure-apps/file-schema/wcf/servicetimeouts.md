---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 801a7aaf1f0d0fa267fa8cca3d2e7fd02919c475
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399555"
---
# <a name="servicetimeouts"></a><span data-ttu-id="7d233-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="7d233-101">\<serviceTimeouts></span></span>
<span data-ttu-id="7d233-102">Specifica il timeout per un servizio.</span><span class="sxs-lookup"><span data-stu-id="7d233-102">Specifies the timeout for a service.</span></span>  
  
<span data-ttu-id="7d233-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d233-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7d233-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7d233-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7d233-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d233-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7d233-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d233-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="7d233-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7d233-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="7d233-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceTimeouts**</span><span class="sxs-lookup"><span data-stu-id="7d233-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d233-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d233-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="7d233-110">Type</span><span class="sxs-lookup"><span data-stu-id="7d233-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d233-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7d233-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7d233-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7d233-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d233-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="7d233-113">Attributes</span></span>  
  
|<span data-ttu-id="7d233-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="7d233-114">Attribute</span></span>|<span data-ttu-id="7d233-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d233-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="7d233-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale una transazione deve essere propagata dal client al server.</span><span class="sxs-lookup"><span data-stu-id="7d233-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="7d233-117">Il valore predefinito è "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="7d233-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d233-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7d233-118">Child Elements</span></span>  
 <span data-ttu-id="7d233-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7d233-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d233-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7d233-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7d233-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d233-121">Element</span></span>|<span data-ttu-id="7d233-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d233-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d233-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7d233-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7d233-124">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="7d233-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d233-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d233-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
