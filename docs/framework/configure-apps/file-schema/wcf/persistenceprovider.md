---
title: '&lt;persistenceProvider&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 447384ef34c1ca2c7e641f0ba0d3d3718139e579
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltpersistenceprovidergt"></a><span data-ttu-id="93f91-102">&lt;persistenceProvider&gt;</span><span class="sxs-lookup"><span data-stu-id="93f91-102">&lt;persistenceProvider&gt;</span></span>
<span data-ttu-id="93f91-103">Specifica il tipo di implementazione del provider di persistenza da usare, nonché il timeout da usare per le operazioni di persistenza.</span><span class="sxs-lookup"><span data-stu-id="93f91-103">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="93f91-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="93f91-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="93f91-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="93f91-105">\<behaviors></span></span>  
<span data-ttu-id="93f91-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="93f91-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="93f91-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="93f91-107">\<behavior></span></span>  
<span data-ttu-id="93f91-108">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="93f91-108">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93f91-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93f91-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"  
   type="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93f91-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="93f91-110">Attributes and Elements</span></span>  
 <span data-ttu-id="93f91-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="93f91-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93f91-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="93f91-112">Attributes</span></span>  
  
|<span data-ttu-id="93f91-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="93f91-113">Attribute</span></span>|<span data-ttu-id="93f91-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93f91-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93f91-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="93f91-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="93f91-116">Valore di tipo <xref:System.TimeSpan> che specifica il timeout usato per le operazioni di persistenza.</span><span class="sxs-lookup"><span data-stu-id="93f91-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="93f91-117">Il valore predefinito è "00: 00:30".</span><span class="sxs-lookup"><span data-stu-id="93f91-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="93f91-118">tipo</span><span class="sxs-lookup"><span data-stu-id="93f91-118">type</span></span>|<span data-ttu-id="93f91-119">Stringa che specifica il tipo della factory del provider di persistenza da usare.</span><span class="sxs-lookup"><span data-stu-id="93f91-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93f91-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="93f91-120">Child Elements</span></span>  
 <span data-ttu-id="93f91-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="93f91-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93f91-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="93f91-122">Parent Elements</span></span>  
  
|<span data-ttu-id="93f91-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="93f91-123">Element</span></span>|<span data-ttu-id="93f91-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93f91-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93f91-125">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="93f91-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="93f91-126">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="93f91-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93f91-127">Note</span><span class="sxs-lookup"><span data-stu-id="93f91-127">Remarks</span></span>  
 <span data-ttu-id="93f91-128">Questo elemento specifica il provider di persistenza da usare per serializzare lo stato di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="93f91-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="93f91-129">È necessario usarlo insieme a `wsHttpContextBinding`, che consente di passare le informazioni sullo stato nelle intestazioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="93f91-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93f91-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93f91-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>  
 <xref:System.ServiceModel.Persistence.PersistenceProvider>
