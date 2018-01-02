---
title: '&lt;callbackTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71fc89a4b9735c13429b31d8cd7c5995f641afa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="eff04-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="eff04-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="eff04-103">Specifica il valore di timeout durante la propagazione delle transazioni dal server al client in un scenario di contratto di callback duplex.</span><span class="sxs-lookup"><span data-stu-id="eff04-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="eff04-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="eff04-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="eff04-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="eff04-105">\<behaviors></span></span>  
<span data-ttu-id="eff04-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="eff04-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="eff04-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="eff04-107">\<behavior></span></span>  
<span data-ttu-id="eff04-108">\<callbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="eff04-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eff04-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eff04-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="eff04-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="eff04-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eff04-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eff04-111">Attributes and Elements</span></span>  
 <span data-ttu-id="eff04-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eff04-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eff04-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="eff04-113">Attributes</span></span>  
  
|<span data-ttu-id="eff04-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="eff04-114">Attribute</span></span>|<span data-ttu-id="eff04-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eff04-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="eff04-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale le transazioni devono essere completate o interrotte automaticamente.</span><span class="sxs-lookup"><span data-stu-id="eff04-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="eff04-117">Il valore predefinito è "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="eff04-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eff04-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eff04-118">Child Elements</span></span>  
 <span data-ttu-id="eff04-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="eff04-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eff04-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eff04-120">Parent Elements</span></span>  
  
|<span data-ttu-id="eff04-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="eff04-121">Element</span></span>|<span data-ttu-id="eff04-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eff04-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eff04-123">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="eff04-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="eff04-124">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="eff04-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eff04-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eff04-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
