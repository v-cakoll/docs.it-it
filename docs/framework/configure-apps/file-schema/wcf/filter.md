---
title: '&lt;filtro&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 186c511cd8a69cef5e30e369641628a10a0972d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltergt"></a><span data-ttu-id="3771a-102">&lt;filtro&gt;</span><span class="sxs-lookup"><span data-stu-id="3771a-102">&lt;filter&gt;</span></span>

<span data-ttu-id="3771a-103">Definisce un filtro di routing che determina il tipo di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] di <xref:System.ServiceModel.Dispatcher.MessageFilter> da usare durante la valutazione di messaggi in arrivo, nonché gli eventuali dati o parametri di supporto necessari per il filtro.</span><span class="sxs-lookup"><span data-stu-id="3771a-103">Defines a routing filter, which determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="3771a-104">\<System. ServiceModel > \<routing > \<filtri > \<filtro ></span><span class="sxs-lookup"><span data-stu-id="3771a-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>

## <a name="syntax"></a><span data-ttu-id="3771a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3771a-105">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="3771a-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3771a-106">Attributes and elements</span></span>

<span data-ttu-id="3771a-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3771a-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3771a-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="3771a-108">Attributes</span></span>

| <span data-ttu-id="3771a-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="3771a-109">Attribute</span></span>  | <span data-ttu-id="3771a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3771a-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="3771a-111">customType</span><span class="sxs-lookup"><span data-stu-id="3771a-111">customType</span></span> | <span data-ttu-id="3771a-112">Stringa contenente il nome di tipo completo del tipo personalizzato da utilizzare come filtro.</span><span class="sxs-lookup"><span data-stu-id="3771a-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="3771a-113">Se `filterType` è impostato su `custom`, questo attributo contiene il nome completo del tipo di classe da creare.</span><span class="sxs-lookup"><span data-stu-id="3771a-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="3771a-114">`filterData`può inoltre contenere i valori da utilizzare durante la valutazione del filtro di tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3771a-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="3771a-115">filterData</span><span class="sxs-lookup"><span data-stu-id="3771a-115">filterData</span></span> | <span data-ttu-id="3771a-116">Stringa contenente i dati del filtro.</span><span class="sxs-lookup"><span data-stu-id="3771a-116">A string containing the filter data.</span></span> <span data-ttu-id="3771a-117">Per altre informazioni su come specificare questo attributo, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="3771a-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="3771a-118">filterType</span><span class="sxs-lookup"><span data-stu-id="3771a-118">filterType</span></span> | <span data-ttu-id="3771a-119">Stringa contenente i tipo di filtro.</span><span class="sxs-lookup"><span data-stu-id="3771a-119">A string containing the filter type.</span></span> <span data-ttu-id="3771a-120">L'attributo è di tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="3771a-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="3771a-121">Per altre informazioni sul funzionamento con l'attributo `filterData`, vedere <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="3771a-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="3771a-122">name</span><span class="sxs-lookup"><span data-stu-id="3771a-122">name</span></span>       | <span data-ttu-id="3771a-123">Stringa contenente il nome univoco di questo elemento di filtro.</span><span class="sxs-lookup"><span data-stu-id="3771a-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="3771a-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3771a-124">Child elements</span></span>

<span data-ttu-id="3771a-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3771a-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3771a-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3771a-126">Parent elements</span></span>

| <span data-ttu-id="3771a-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="3771a-127">Element</span></span> | <span data-ttu-id="3771a-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3771a-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="3771a-129">\<routing ></span><span class="sxs-lookup"><span data-stu-id="3771a-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="3771a-130">Sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> da usare durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="3771a-130">A configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3771a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3771a-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
