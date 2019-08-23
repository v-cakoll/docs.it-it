---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 68de255b9f11dc4377159d1cc3efa575633db316
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918888"
---
# <a name="filter"></a><span data-ttu-id="6aa35-101">\<Filtra ></span><span class="sxs-lookup"><span data-stu-id="6aa35-101">\<filter></span></span>

<span data-ttu-id="6aa35-102">Definisce un filtro di routing che determina il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché qualsiasi dato o parametro di supporto richiesto dal filtro.</span><span class="sxs-lookup"><span data-stu-id="6aa35-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="6aa35-103">\<System. ServiceModel > \<routing > \<filtri > \<filtro ></span><span class="sxs-lookup"><span data-stu-id="6aa35-103">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="6aa35-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6aa35-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6aa35-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6aa35-105">Attributes and elements</span></span>

<span data-ttu-id="6aa35-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6aa35-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6aa35-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="6aa35-107">Attributes</span></span>

| <span data-ttu-id="6aa35-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="6aa35-108">Attribute</span></span>  | <span data-ttu-id="6aa35-109">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="6aa35-109">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="6aa35-110">customType</span><span class="sxs-lookup"><span data-stu-id="6aa35-110">customType</span></span> | <span data-ttu-id="6aa35-111">Stringa contenente il nome di tipo completo del tipo personalizzato da utilizzare come filtro.</span><span class="sxs-lookup"><span data-stu-id="6aa35-111">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="6aa35-112">Se `filterType` è impostato su `custom`, questo attributo contiene il nome completo del tipo della classe da creare.</span><span class="sxs-lookup"><span data-stu-id="6aa35-112">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="6aa35-113">`filterData`può contenere anche valori da usare durante la valutazione del filtro di tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6aa35-113">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="6aa35-114">filterData</span><span class="sxs-lookup"><span data-stu-id="6aa35-114">filterData</span></span> | <span data-ttu-id="6aa35-115">Stringa contenente i dati del filtro.</span><span class="sxs-lookup"><span data-stu-id="6aa35-115">A string containing the filter data.</span></span> <span data-ttu-id="6aa35-116">Per altre informazioni su come specificare questo attributo, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="6aa35-116">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="6aa35-117">filterType</span><span class="sxs-lookup"><span data-stu-id="6aa35-117">filterType</span></span> | <span data-ttu-id="6aa35-118">Stringa contenente i tipo di filtro.</span><span class="sxs-lookup"><span data-stu-id="6aa35-118">A string containing the filter type.</span></span> <span data-ttu-id="6aa35-119">L'attributo è di tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="6aa35-119">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="6aa35-120">Per altre informazioni sul funzionamento con l'attributo `filterData`, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="6aa35-120">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="6aa35-121">name</span><span class="sxs-lookup"><span data-stu-id="6aa35-121">name</span></span>       | <span data-ttu-id="6aa35-122">Stringa contenente il nome univoco di questo elemento di filtro.</span><span class="sxs-lookup"><span data-stu-id="6aa35-122">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="6aa35-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6aa35-123">Child elements</span></span>

<span data-ttu-id="6aa35-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6aa35-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6aa35-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6aa35-125">Parent elements</span></span>

| <span data-ttu-id="6aa35-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="6aa35-126">Element</span></span> | <span data-ttu-id="6aa35-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6aa35-127">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="6aa35-128">\<routing></span><span class="sxs-lookup"><span data-stu-id="6aa35-128">\<routing></span></span>](routing.md) | <span data-ttu-id="6aa35-129">Sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di Windows Communication Foundation<xref:System.ServiceModel.Dispatcher.MessageFilter> (WCF) da utilizzare durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="6aa35-129">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="6aa35-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6aa35-130">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
