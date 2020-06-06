---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 7c4d9ae29ca1e543217d444e05a661b48e2cbb62
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400070"
---
# \<persistenceProvider>
<span data-ttu-id="aa577-101">Specifica il tipo di implementazione del provider di persistenza da usare, nonché il timeout da usare per le operazioni di persistenza.</span><span class="sxs-lookup"><span data-stu-id="aa577-101">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**  
  
## <a name="syntax"></a><span data-ttu-id="aa577-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa577-102">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa577-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="aa577-103">Attributes and Elements</span></span>  
 <span data-ttu-id="aa577-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="aa577-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa577-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="aa577-105">Attributes</span></span>  
  
|<span data-ttu-id="aa577-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="aa577-106">Attribute</span></span>|<span data-ttu-id="aa577-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa577-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa577-108">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="aa577-108">persistenceOperationTimeout</span></span>|<span data-ttu-id="aa577-109">Valore di tipo <xref:System.TimeSpan> che specifica il timeout usato per le operazioni di persistenza.</span><span class="sxs-lookup"><span data-stu-id="aa577-109">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="aa577-110">Il valore predefinito è "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="aa577-110">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="aa577-111">tipo</span><span class="sxs-lookup"><span data-stu-id="aa577-111">type</span></span>|<span data-ttu-id="aa577-112">Stringa che specifica il tipo della factory del provider di persistenza da usare.</span><span class="sxs-lookup"><span data-stu-id="aa577-112">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa577-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="aa577-113">Child Elements</span></span>  
 <span data-ttu-id="aa577-114">No.</span><span class="sxs-lookup"><span data-stu-id="aa577-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa577-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="aa577-115">Parent Elements</span></span>  
  
|<span data-ttu-id="aa577-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa577-116">Element</span></span>|<span data-ttu-id="aa577-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa577-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="aa577-118">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="aa577-118">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa577-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="aa577-119">Remarks</span></span>  
 <span data-ttu-id="aa577-120">Questo elemento specifica il provider di persistenza da usare per serializzare lo stato di un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="aa577-120">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="aa577-121">È necessario usarlo insieme a `wsHttpContextBinding`, che consente di passare le informazioni sullo stato nelle intestazioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="aa577-121">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa577-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa577-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
