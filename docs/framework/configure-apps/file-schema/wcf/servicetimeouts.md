---
title: '&lt;serviceTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 4cb4b4ae6fe01430989d9ee5f3d94b16778595aa
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148474"
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="c211a-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="c211a-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="c211a-103">Specifica il timeout per un servizio.</span><span class="sxs-lookup"><span data-stu-id="c211a-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="c211a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c211a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c211a-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="c211a-105">\<behaviors></span></span>  
<span data-ttu-id="c211a-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c211a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c211a-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="c211a-107">\<behavior></span></span>  
<span data-ttu-id="c211a-108">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="c211a-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c211a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c211a-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="c211a-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="c211a-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c211a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c211a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c211a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c211a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c211a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="c211a-113">Attributes</span></span>  
  
|<span data-ttu-id="c211a-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="c211a-114">Attribute</span></span>|<span data-ttu-id="c211a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c211a-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="c211a-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale una transazione deve essere propagata dal client al server.</span><span class="sxs-lookup"><span data-stu-id="c211a-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="c211a-117">Il valore predefinito è "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="c211a-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c211a-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c211a-118">Child Elements</span></span>  
 <span data-ttu-id="c211a-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c211a-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c211a-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c211a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c211a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c211a-121">Element</span></span>|<span data-ttu-id="c211a-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c211a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c211a-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c211a-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c211a-124">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="c211a-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c211a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c211a-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
