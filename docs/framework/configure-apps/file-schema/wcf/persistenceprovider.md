---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 7c4d9ae29ca1e543217d444e05a661b48e2cbb62
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400070"
---
# <a name="persistenceprovider"></a><span data-ttu-id="34336-101">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="34336-101">\<persistenceProvider></span></span>
<span data-ttu-id="34336-102">Specifica il tipo di implementazione del provider di persistenza da usare, nonché il timeout da usare per le operazioni di persistenza.</span><span class="sxs-lookup"><span data-stu-id="34336-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
<span data-ttu-id="34336-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="34336-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="34336-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="34336-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="34336-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="34336-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="34336-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="34336-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="34336-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="34336-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="34336-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> persistenceProvider**</span><span class="sxs-lookup"><span data-stu-id="34336-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34336-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34336-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34336-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="34336-110">Attributes and Elements</span></span>  
 <span data-ttu-id="34336-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="34336-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34336-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="34336-112">Attributes</span></span>  
  
|<span data-ttu-id="34336-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="34336-113">Attribute</span></span>|<span data-ttu-id="34336-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34336-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34336-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="34336-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="34336-116">Valore di tipo <xref:System.TimeSpan> che specifica il timeout usato per le operazioni di persistenza.</span><span class="sxs-lookup"><span data-stu-id="34336-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="34336-117">Il valore predefinito è "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="34336-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="34336-118">type</span><span class="sxs-lookup"><span data-stu-id="34336-118">type</span></span>|<span data-ttu-id="34336-119">Stringa che specifica il tipo della factory del provider di persistenza da usare.</span><span class="sxs-lookup"><span data-stu-id="34336-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34336-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="34336-120">Child Elements</span></span>  
 <span data-ttu-id="34336-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="34336-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34336-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="34336-122">Parent Elements</span></span>  
  
|<span data-ttu-id="34336-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="34336-123">Element</span></span>|<span data-ttu-id="34336-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34336-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34336-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="34336-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="34336-126">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="34336-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34336-127">Note</span><span class="sxs-lookup"><span data-stu-id="34336-127">Remarks</span></span>  
 <span data-ttu-id="34336-128">Questo elemento specifica il provider di persistenza da usare per serializzare lo stato di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="34336-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="34336-129">È necessario usarlo insieme a `wsHttpContextBinding`, che consente di passare le informazioni sullo stato nelle intestazioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="34336-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34336-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34336-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
