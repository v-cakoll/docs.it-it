---
title: '&lt;serviceTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d8bfde535eb417614eee4ec6a2db7985152be33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="13c94-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="13c94-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="13c94-103">Specifica il timeout per un servizio.</span><span class="sxs-lookup"><span data-stu-id="13c94-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="13c94-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="13c94-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="13c94-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="13c94-105">\<behaviors></span></span>  
<span data-ttu-id="13c94-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="13c94-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="13c94-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="13c94-107">\<behavior></span></span>  
<span data-ttu-id="13c94-108">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="13c94-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13c94-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13c94-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="13c94-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="13c94-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13c94-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="13c94-111">Attributes and Elements</span></span>  
 <span data-ttu-id="13c94-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="13c94-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13c94-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="13c94-113">Attributes</span></span>  
  
|<span data-ttu-id="13c94-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="13c94-114">Attribute</span></span>|<span data-ttu-id="13c94-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13c94-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="13c94-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale una transazione deve essere propagata dal client al server.</span><span class="sxs-lookup"><span data-stu-id="13c94-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="13c94-117">Il valore predefinito è "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="13c94-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13c94-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="13c94-118">Child Elements</span></span>  
 <span data-ttu-id="13c94-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="13c94-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13c94-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="13c94-120">Parent Elements</span></span>  
  
|<span data-ttu-id="13c94-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="13c94-121">Element</span></span>|<span data-ttu-id="13c94-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13c94-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13c94-123">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="13c94-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="13c94-124">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="13c94-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13c94-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13c94-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
