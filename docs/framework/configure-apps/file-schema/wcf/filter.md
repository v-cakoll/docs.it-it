---
title: '&lt;filter&gt;'
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 9fae9a599299fdd8cf1e996593514fc0ef38b6ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645509"
---
# <a name="ltfiltergt"></a><span data-ttu-id="ecfd7-102">&lt;filter&gt;</span><span class="sxs-lookup"><span data-stu-id="ecfd7-102">&lt;filter&gt;</span></span>

<span data-ttu-id="ecfd7-103">Definisce un filtro di routing che determina il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, come i dati di supporto o i parametri richiesti dal filtro.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-103">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="ecfd7-104">\<system.serviceModel> \<routing> \<filters> \<filter></span><span class="sxs-lookup"><span data-stu-id="ecfd7-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="ecfd7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ecfd7-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecfd7-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ecfd7-106">Attributes and elements</span></span>

<span data-ttu-id="ecfd7-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ecfd7-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="ecfd7-108">Attributes</span></span>

| <span data-ttu-id="ecfd7-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="ecfd7-109">Attribute</span></span>  | <span data-ttu-id="ecfd7-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecfd7-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="ecfd7-111">customType</span><span class="sxs-lookup"><span data-stu-id="ecfd7-111">customType</span></span> | <span data-ttu-id="ecfd7-112">Stringa contenente il nome di tipo completo del tipo personalizzato da utilizzare come filtro.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="ecfd7-113">Se `filterType` è impostata su `custom`, questo attributo contiene il nome del tipo completo della classe da creare.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="ecfd7-114">`filterData` può inoltre contenere valori da utilizzare durante la valutazione del filtro di tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="ecfd7-115">filterData</span><span class="sxs-lookup"><span data-stu-id="ecfd7-115">filterData</span></span> | <span data-ttu-id="ecfd7-116">Stringa contenente i dati del filtro.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-116">A string containing the filter data.</span></span> <span data-ttu-id="ecfd7-117">Per altre informazioni su come specificare questo attributo, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="ecfd7-118">filterType</span><span class="sxs-lookup"><span data-stu-id="ecfd7-118">filterType</span></span> | <span data-ttu-id="ecfd7-119">Stringa contenente i tipo di filtro.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-119">A string containing the filter type.</span></span> <span data-ttu-id="ecfd7-120">L'attributo è di tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="ecfd7-121">Per altre informazioni sul funzionamento con l'attributo `filterData`, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="ecfd7-122">name</span><span class="sxs-lookup"><span data-stu-id="ecfd7-122">name</span></span>       | <span data-ttu-id="ecfd7-123">Stringa contenente il nome univoco di questo elemento di filtro.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="ecfd7-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ecfd7-124">Child elements</span></span>

<span data-ttu-id="ecfd7-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ecfd7-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ecfd7-126">Parent elements</span></span>

| <span data-ttu-id="ecfd7-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="ecfd7-127">Element</span></span> | <span data-ttu-id="ecfd7-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecfd7-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="ecfd7-129">\<routing></span><span class="sxs-lookup"><span data-stu-id="ecfd7-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="ecfd7-130">Una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da usare durante la valutazione di messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="ecfd7-130">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ecfd7-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecfd7-131">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
