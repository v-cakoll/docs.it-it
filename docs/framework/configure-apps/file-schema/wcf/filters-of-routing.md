---
title: <filters> di <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: ba60958ad33b46b40285f3f70001273bb3af3a63
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925610"
---
# <a name="filters-of-routing"></a><span data-ttu-id="1d1ab-102">\<Filtra > di \<> di routing</span><span class="sxs-lookup"><span data-stu-id="1d1ab-102">\<filters> of \<routing></span></span>

<span data-ttu-id="1d1ab-103">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di <xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) da utilizzare durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="1d1ab-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="1d1ab-104">[ **\<system.serviceModel>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="1d1ab-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="1d1ab-105">&nbsp;&nbsp;[ **\<routing>** ](routing.md) </span><span class="sxs-lookup"><span data-stu-id="1d1ab-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="1d1ab-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<filters>**</span><span class="sxs-lookup"><span data-stu-id="1d1ab-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="1d1ab-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d1ab-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d1ab-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1d1ab-108">Attributes and elements</span></span>

<span data-ttu-id="1d1ab-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1d1ab-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1d1ab-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="1d1ab-110">Attributes</span></span>

<span data-ttu-id="1d1ab-111">Nessuna</span><span class="sxs-lookup"><span data-stu-id="1d1ab-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="1d1ab-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1d1ab-112">Child elements</span></span>

|     | <span data-ttu-id="1d1ab-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d1ab-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1d1ab-114"> **\<filter>** </span><span class="sxs-lookup"><span data-stu-id="1d1ab-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="1d1ab-115">Contiene un filtro di routing che determina il tipo di Windows Communication Foundation (WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> ) che verrà utilizzato durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="1d1ab-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="1d1ab-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1d1ab-116">Parent elements</span></span>

|     | <span data-ttu-id="1d1ab-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d1ab-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1d1ab-118"> **\<routing>** </span><span class="sxs-lookup"><span data-stu-id="1d1ab-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="1d1ab-119">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di<xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione Invia messaggi a quando viene individuato un filtro.</span><span class="sxs-lookup"><span data-stu-id="1d1ab-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1d1ab-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d1ab-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
