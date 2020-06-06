---
title: <filters> di <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: c9bc3a2c379e14d8cf687676a3ec40702d150e1e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855245"
---
# <a name="filters-of-routing"></a><span data-ttu-id="b7f88-102">\<filters> di \<routing></span><span class="sxs-lookup"><span data-stu-id="b7f88-102">\<filters> of \<routing></span></span>

<span data-ttu-id="b7f88-103">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="b7f88-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**  
  
## <a name="syntax"></a><span data-ttu-id="b7f88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7f88-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7f88-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b7f88-105">Attributes and elements</span></span>

<span data-ttu-id="b7f88-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b7f88-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b7f88-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="b7f88-107">Attributes</span></span>

<span data-ttu-id="b7f88-108">nessuno</span><span class="sxs-lookup"><span data-stu-id="b7f88-108">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="b7f88-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b7f88-109">Child elements</span></span>

|     | <span data-ttu-id="b7f88-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7f88-110">Description</span></span> |
| --- | ----------- |
| [**\<filter>**](filter.md) | <span data-ttu-id="b7f88-111">Contiene un filtro di routing che determina il tipo di Windows Communication Foundation (WCF) che <xref:System.ServiceModel.Dispatcher.MessageFilter> verrà utilizzato durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="b7f88-111">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="b7f88-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b7f88-112">Parent elements</span></span>

|     | <span data-ttu-id="b7f88-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7f88-113">Description</span></span> |
| --- | ----------- |
| [**\<routing>**](routing.md) | <span data-ttu-id="b7f88-114">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione ai quali inviare messaggi quando viene individuato un filtro.</span><span class="sxs-lookup"><span data-stu-id="b7f88-114">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b7f88-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7f88-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
