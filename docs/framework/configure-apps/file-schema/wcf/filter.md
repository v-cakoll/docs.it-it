---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855252"
---
# \<filter>

<span data-ttu-id="19a4c-101">Definisce un filtro di routing che determina il tipo di Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché qualsiasi dato o parametro di supporto richiesto dal filtro.</span><span class="sxs-lookup"><span data-stu-id="19a4c-101">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**  
  
## <a name="syntax"></a><span data-ttu-id="19a4c-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19a4c-102">Syntax</span></span>  
  
```xml  
<routing>
  <filters>
    <filter customType="String"
            filterData="String"
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
            name="String" />
  </filters>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19a4c-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="19a4c-103">Attributes and elements</span></span>

<span data-ttu-id="19a4c-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="19a4c-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="19a4c-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="19a4c-105">Attributes</span></span>

| <span data-ttu-id="19a4c-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="19a4c-106">Attribute</span></span>  | <span data-ttu-id="19a4c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19a4c-107">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="19a4c-108">customType</span><span class="sxs-lookup"><span data-stu-id="19a4c-108">customType</span></span> | <span data-ttu-id="19a4c-109">Stringa contenente il nome di tipo completo del tipo personalizzato da utilizzare come filtro.</span><span class="sxs-lookup"><span data-stu-id="19a4c-109">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="19a4c-110">Se `filterType` è impostato su `custom` , questo attributo contiene il nome completo del tipo della classe da creare.</span><span class="sxs-lookup"><span data-stu-id="19a4c-110">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="19a4c-111">`filterData`può contenere anche valori da usare durante la valutazione del filtro di tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="19a4c-111">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="19a4c-112">filterData</span><span class="sxs-lookup"><span data-stu-id="19a4c-112">filterData</span></span> | <span data-ttu-id="19a4c-113">Stringa contenente i dati del filtro.</span><span class="sxs-lookup"><span data-stu-id="19a4c-113">A string containing the filter data.</span></span> <span data-ttu-id="19a4c-114">Per altre informazioni su come specificare questo attributo, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="19a4c-114">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="19a4c-115">filterType</span><span class="sxs-lookup"><span data-stu-id="19a4c-115">filterType</span></span> | <span data-ttu-id="19a4c-116">Stringa contenente i tipo di filtro.</span><span class="sxs-lookup"><span data-stu-id="19a4c-116">A string containing the filter type.</span></span> <span data-ttu-id="19a4c-117">L'attributo è di tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="19a4c-117">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="19a4c-118">Per altre informazioni sul funzionamento con l'attributo `filterData`, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="19a4c-118">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="19a4c-119">name</span><span class="sxs-lookup"><span data-stu-id="19a4c-119">name</span></span>       | <span data-ttu-id="19a4c-120">Stringa contenente il nome univoco di questo elemento di filtro.</span><span class="sxs-lookup"><span data-stu-id="19a4c-120">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="19a4c-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="19a4c-121">Child elements</span></span>

<span data-ttu-id="19a4c-122">No.</span><span class="sxs-lookup"><span data-stu-id="19a4c-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="19a4c-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="19a4c-123">Parent elements</span></span>

| <span data-ttu-id="19a4c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="19a4c-124">Element</span></span> | <span data-ttu-id="19a4c-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19a4c-125">Description</span></span> |
| ------- | ----------- |
| [\<routing>](routing.md) | <span data-ttu-id="19a4c-126">Sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="19a4c-126">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="19a4c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19a4c-127">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
