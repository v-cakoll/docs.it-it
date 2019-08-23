---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 4fc9e1332effc51e183a84cf2d3653357277d2ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934146"
---
# <a name="persistenceprovider"></a><span data-ttu-id="5604b-101">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="5604b-101">\<persistenceProvider></span></span>
<span data-ttu-id="5604b-102">Specifica il tipo di implementazione del provider di persistenza da usare, nonché il timeout da usare per le operazioni di persistenza.</span><span class="sxs-lookup"><span data-stu-id="5604b-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="5604b-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5604b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5604b-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="5604b-104">\<behaviors></span></span>  
<span data-ttu-id="5604b-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5604b-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="5604b-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="5604b-106">\<behavior></span></span>  
<span data-ttu-id="5604b-107">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="5604b-107">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5604b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5604b-108">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5604b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5604b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5604b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5604b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5604b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="5604b-111">Attributes</span></span>  
  
|<span data-ttu-id="5604b-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="5604b-112">Attribute</span></span>|<span data-ttu-id="5604b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5604b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5604b-114">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="5604b-114">persistenceOperationTimeout</span></span>|<span data-ttu-id="5604b-115">Valore di tipo <xref:System.TimeSpan> che specifica il timeout usato per le operazioni di persistenza.</span><span class="sxs-lookup"><span data-stu-id="5604b-115">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="5604b-116">Il valore predefinito è "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="5604b-116">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="5604b-117">type</span><span class="sxs-lookup"><span data-stu-id="5604b-117">type</span></span>|<span data-ttu-id="5604b-118">Stringa che specifica il tipo della factory del provider di persistenza da usare.</span><span class="sxs-lookup"><span data-stu-id="5604b-118">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5604b-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5604b-119">Child Elements</span></span>  
 <span data-ttu-id="5604b-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5604b-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5604b-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5604b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5604b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="5604b-122">Element</span></span>|<span data-ttu-id="5604b-123">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="5604b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5604b-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5604b-124">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5604b-125">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="5604b-125">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5604b-126">Note</span><span class="sxs-lookup"><span data-stu-id="5604b-126">Remarks</span></span>  
 <span data-ttu-id="5604b-127">Questo elemento specifica il provider di persistenza da usare per serializzare lo stato di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="5604b-127">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="5604b-128">È necessario usarlo insieme a `wsHttpContextBinding`, che consente di passare le informazioni sullo stato nelle intestazioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="5604b-128">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5604b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5604b-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
