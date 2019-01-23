---
title: '&lt;serviceTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: f7aa623ee387f67f3bbff32249d3695049359cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524468"
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="bed40-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="bed40-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="bed40-103">Specifica il timeout per un servizio.</span><span class="sxs-lookup"><span data-stu-id="bed40-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="bed40-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bed40-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bed40-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="bed40-105">\<behaviors></span></span>  
<span data-ttu-id="bed40-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="bed40-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="bed40-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="bed40-107">\<behavior></span></span>  
<span data-ttu-id="bed40-108">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="bed40-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bed40-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bed40-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="bed40-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="bed40-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bed40-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bed40-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bed40-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bed40-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bed40-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="bed40-113">Attributes</span></span>  
  
|<span data-ttu-id="bed40-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="bed40-114">Attribute</span></span>|<span data-ttu-id="bed40-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bed40-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="bed40-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale una transazione deve essere propagata dal client al server.</span><span class="sxs-lookup"><span data-stu-id="bed40-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="bed40-117">Il valore predefinito è "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="bed40-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bed40-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bed40-118">Child Elements</span></span>  
 <span data-ttu-id="bed40-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bed40-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bed40-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bed40-120">Parent Elements</span></span>  
  
|<span data-ttu-id="bed40-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="bed40-121">Element</span></span>|<span data-ttu-id="bed40-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bed40-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bed40-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="bed40-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="bed40-124">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="bed40-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bed40-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bed40-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
