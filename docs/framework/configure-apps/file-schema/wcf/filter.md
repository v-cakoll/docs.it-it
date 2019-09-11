---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855252"
---
# <a name="filter"></a><span data-ttu-id="8557b-101">\<Filtra ></span><span class="sxs-lookup"><span data-stu-id="8557b-101">\<filter></span></span>

<span data-ttu-id="8557b-102">Definisce un filtro di routing che determina il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché qualsiasi dato o parametro di supporto richiesto dal filtro.</span><span class="sxs-lookup"><span data-stu-id="8557b-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="8557b-103">[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8557b-103">[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8557b-104">&nbsp;&nbsp;[ **\<routing>** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="8557b-104">&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="8557b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Filtra >** ](filters-of-routing.md)</span><span class="sxs-lookup"><span data-stu-id="8557b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)</span></span>\
<span data-ttu-id="8557b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Filtra >**</span><span class="sxs-lookup"><span data-stu-id="8557b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8557b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8557b-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8557b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8557b-108">Attributes and elements</span></span>

<span data-ttu-id="8557b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8557b-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8557b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="8557b-110">Attributes</span></span>

| <span data-ttu-id="8557b-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="8557b-111">Attribute</span></span>  | <span data-ttu-id="8557b-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="8557b-112">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="8557b-113">customType</span><span class="sxs-lookup"><span data-stu-id="8557b-113">customType</span></span> | <span data-ttu-id="8557b-114">Stringa contenente il nome di tipo completo del tipo personalizzato da utilizzare come filtro.</span><span class="sxs-lookup"><span data-stu-id="8557b-114">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="8557b-115">Se `filterType` è impostato su `custom`, questo attributo contiene il nome completo del tipo della classe da creare.</span><span class="sxs-lookup"><span data-stu-id="8557b-115">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="8557b-116">`filterData`può contenere anche valori da usare durante la valutazione del filtro di tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8557b-116">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="8557b-117">filterData</span><span class="sxs-lookup"><span data-stu-id="8557b-117">filterData</span></span> | <span data-ttu-id="8557b-118">Stringa contenente i dati del filtro.</span><span class="sxs-lookup"><span data-stu-id="8557b-118">A string containing the filter data.</span></span> <span data-ttu-id="8557b-119">Per altre informazioni su come specificare questo attributo, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="8557b-119">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="8557b-120">filterType</span><span class="sxs-lookup"><span data-stu-id="8557b-120">filterType</span></span> | <span data-ttu-id="8557b-121">Stringa contenente i tipo di filtro.</span><span class="sxs-lookup"><span data-stu-id="8557b-121">A string containing the filter type.</span></span> <span data-ttu-id="8557b-122">L'attributo è di tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="8557b-122">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="8557b-123">Per altre informazioni sul funzionamento con l'attributo `filterData`, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="8557b-123">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="8557b-124">name</span><span class="sxs-lookup"><span data-stu-id="8557b-124">name</span></span>       | <span data-ttu-id="8557b-125">Stringa contenente il nome univoco di questo elemento di filtro.</span><span class="sxs-lookup"><span data-stu-id="8557b-125">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="8557b-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8557b-126">Child elements</span></span>

<span data-ttu-id="8557b-127">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8557b-127">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8557b-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8557b-128">Parent elements</span></span>

| <span data-ttu-id="8557b-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="8557b-129">Element</span></span> | <span data-ttu-id="8557b-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8557b-130">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="8557b-131">\<routing></span><span class="sxs-lookup"><span data-stu-id="8557b-131">\<routing></span></span>](routing.md) | <span data-ttu-id="8557b-132">Sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di Windows Communication Foundation<xref:System.ServiceModel.Dispatcher.MessageFilter> (WCF) da utilizzare durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="8557b-132">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8557b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8557b-133">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
