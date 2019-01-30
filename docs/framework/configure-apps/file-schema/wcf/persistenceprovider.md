---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 054991687a54ecbf95cc18f58717a4ed3e36f050
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260801"
---
# <a name="persistenceprovider"></a><span data-ttu-id="4d2e3-101">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="4d2e3-101">\<persistenceProvider></span></span>
<span data-ttu-id="4d2e3-102">Specifica il tipo di implementazione del provider di persistenza da usare, nonché il timeout da usare per le operazioni di persistenza.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="4d2e3-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4d2e3-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="4d2e3-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="4d2e3-104">\<behaviors></span></span>  
<span data-ttu-id="4d2e3-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4d2e3-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="4d2e3-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4d2e3-106">\<behavior></span></span>  
<span data-ttu-id="4d2e3-107">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="4d2e3-107">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d2e3-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d2e3-108">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d2e3-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4d2e3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4d2e3-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d2e3-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="4d2e3-111">Attributes</span></span>  
  
|<span data-ttu-id="4d2e3-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="4d2e3-112">Attribute</span></span>|<span data-ttu-id="4d2e3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d2e3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d2e3-114">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="4d2e3-114">persistenceOperationTimeout</span></span>|<span data-ttu-id="4d2e3-115">Valore di tipo <xref:System.TimeSpan> che specifica il timeout usato per le operazioni di persistenza.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-115">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="4d2e3-116">Il valore predefinito è "00: 00:30".</span><span class="sxs-lookup"><span data-stu-id="4d2e3-116">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="4d2e3-117">tipo</span><span class="sxs-lookup"><span data-stu-id="4d2e3-117">type</span></span>|<span data-ttu-id="4d2e3-118">Stringa che specifica il tipo della factory del provider di persistenza da usare.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-118">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d2e3-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4d2e3-119">Child Elements</span></span>  
 <span data-ttu-id="4d2e3-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d2e3-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4d2e3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4d2e3-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d2e3-122">Element</span></span>|<span data-ttu-id="4d2e3-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d2e3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d2e3-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4d2e3-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="4d2e3-125">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-125">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d2e3-126">Note</span><span class="sxs-lookup"><span data-stu-id="4d2e3-126">Remarks</span></span>  
 <span data-ttu-id="4d2e3-127">Questo elemento specifica il provider di persistenza da usare per serializzare lo stato di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-127">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="4d2e3-128">È necessario usarlo insieme a `wsHttpContextBinding`, che consente di passare le informazioni sullo stato nelle intestazioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="4d2e3-128">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d2e3-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d2e3-129">See also</span></span>
- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
