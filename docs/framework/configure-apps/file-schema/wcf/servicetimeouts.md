---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: a1792fec4f86c9ac31107c043b976cfafcfa4c13
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937087"
---
# <a name="servicetimeouts"></a><span data-ttu-id="2931b-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="2931b-101">\<serviceTimeouts></span></span>
<span data-ttu-id="2931b-102">Specifica il timeout per un servizio.</span><span class="sxs-lookup"><span data-stu-id="2931b-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="2931b-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2931b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2931b-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="2931b-104">\<behaviors></span></span>  
<span data-ttu-id="2931b-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2931b-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="2931b-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="2931b-106">\<behavior></span></span>  
<span data-ttu-id="2931b-107">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="2931b-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2931b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2931b-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="2931b-109">Type</span><span class="sxs-lookup"><span data-stu-id="2931b-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2931b-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2931b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2931b-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2931b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2931b-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="2931b-112">Attributes</span></span>  
  
|<span data-ttu-id="2931b-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="2931b-113">Attribute</span></span>|<span data-ttu-id="2931b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2931b-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="2931b-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale una transazione deve essere propagata dal client al server.</span><span class="sxs-lookup"><span data-stu-id="2931b-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="2931b-116">Il valore predefinito è "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="2931b-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2931b-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2931b-117">Child Elements</span></span>  
 <span data-ttu-id="2931b-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2931b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2931b-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2931b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2931b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="2931b-120">Element</span></span>|<span data-ttu-id="2931b-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2931b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2931b-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2931b-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="2931b-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="2931b-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2931b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2931b-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
