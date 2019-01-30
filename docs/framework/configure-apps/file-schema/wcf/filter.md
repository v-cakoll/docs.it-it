---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: bff19f106d86c73dea80b8b57bb73442eaa2cf9f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278785"
---
# <a name="filter"></a><span data-ttu-id="378ec-101">\<filter></span><span class="sxs-lookup"><span data-stu-id="378ec-101">\<filter></span></span>

<span data-ttu-id="378ec-102">Definisce un filtro di routing che determina il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, come i dati di supporto o i parametri richiesti dal filtro.</span><span class="sxs-lookup"><span data-stu-id="378ec-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="378ec-103">\<system.serviceModel> \<routing> \<filters> \<filter></span><span class="sxs-lookup"><span data-stu-id="378ec-103">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="378ec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="378ec-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="378ec-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="378ec-105">Attributes and elements</span></span>

<span data-ttu-id="378ec-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="378ec-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="378ec-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="378ec-107">Attributes</span></span>

| <span data-ttu-id="378ec-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="378ec-108">Attribute</span></span>  | <span data-ttu-id="378ec-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="378ec-109">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="378ec-110">customType</span><span class="sxs-lookup"><span data-stu-id="378ec-110">customType</span></span> | <span data-ttu-id="378ec-111">Stringa contenente il nome di tipo completo del tipo personalizzato da utilizzare come filtro.</span><span class="sxs-lookup"><span data-stu-id="378ec-111">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="378ec-112">Se `filterType` è impostata su `custom`, questo attributo contiene il nome del tipo completo della classe da creare.</span><span class="sxs-lookup"><span data-stu-id="378ec-112">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="378ec-113">`filterData` può inoltre contenere valori da utilizzare durante la valutazione del filtro di tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="378ec-113">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="378ec-114">filterData</span><span class="sxs-lookup"><span data-stu-id="378ec-114">filterData</span></span> | <span data-ttu-id="378ec-115">Stringa contenente i dati del filtro.</span><span class="sxs-lookup"><span data-stu-id="378ec-115">A string containing the filter data.</span></span> <span data-ttu-id="378ec-116">Per altre informazioni su come specificare questo attributo, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="378ec-116">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="378ec-117">filterType</span><span class="sxs-lookup"><span data-stu-id="378ec-117">filterType</span></span> | <span data-ttu-id="378ec-118">Stringa contenente i tipo di filtro.</span><span class="sxs-lookup"><span data-stu-id="378ec-118">A string containing the filter type.</span></span> <span data-ttu-id="378ec-119">L'attributo è di tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="378ec-119">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="378ec-120">Per altre informazioni sul funzionamento con l'attributo `filterData`, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="378ec-120">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="378ec-121">name</span><span class="sxs-lookup"><span data-stu-id="378ec-121">name</span></span>       | <span data-ttu-id="378ec-122">Stringa contenente il nome univoco di questo elemento di filtro.</span><span class="sxs-lookup"><span data-stu-id="378ec-122">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="378ec-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="378ec-123">Child elements</span></span>

<span data-ttu-id="378ec-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="378ec-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="378ec-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="378ec-125">Parent elements</span></span>

| <span data-ttu-id="378ec-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="378ec-126">Element</span></span> | <span data-ttu-id="378ec-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="378ec-127">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="378ec-128">\<routing></span><span class="sxs-lookup"><span data-stu-id="378ec-128">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="378ec-129">Una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da usare durante la valutazione di messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="378ec-129">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="378ec-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="378ec-130">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
