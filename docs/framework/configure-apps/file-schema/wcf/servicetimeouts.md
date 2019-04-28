---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 5c2f0ef7ad509eb5d6c686802c3fe5a75ea1a258
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758093"
---
# <a name="servicetimeouts"></a><span data-ttu-id="efd56-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="efd56-101">\<serviceTimeouts></span></span>
<span data-ttu-id="efd56-102">Specifica il timeout per un servizio.</span><span class="sxs-lookup"><span data-stu-id="efd56-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="efd56-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="efd56-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="efd56-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="efd56-104">\<behaviors></span></span>  
<span data-ttu-id="efd56-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="efd56-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="efd56-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="efd56-106">\<behavior></span></span>  
<span data-ttu-id="efd56-107">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="efd56-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efd56-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="efd56-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="efd56-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="efd56-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efd56-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="efd56-110">Attributes and Elements</span></span>  
 <span data-ttu-id="efd56-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="efd56-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efd56-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="efd56-112">Attributes</span></span>  
  
|<span data-ttu-id="efd56-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="efd56-113">Attribute</span></span>|<span data-ttu-id="efd56-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efd56-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="efd56-115">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale una transazione deve essere propagata dal client al server.</span><span class="sxs-lookup"><span data-stu-id="efd56-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="efd56-116">Il valore predefinito è "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="efd56-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efd56-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="efd56-117">Child Elements</span></span>  
 <span data-ttu-id="efd56-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="efd56-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="efd56-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="efd56-119">Parent Elements</span></span>  
  
|<span data-ttu-id="efd56-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="efd56-120">Element</span></span>|<span data-ttu-id="efd56-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efd56-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efd56-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="efd56-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="efd56-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="efd56-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efd56-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efd56-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
