---
title: '&lt;filters&gt; di &lt;routing&gt;'
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 9f0fa9bf51d264346738172f57a8efca7950fdb7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltersgt-of-ltroutinggt"></a><span data-ttu-id="b6740-102">&lt;filters&gt; di &lt;routing&gt;</span><span class="sxs-lookup"><span data-stu-id="b6740-102">&lt;filters&gt; of &lt;routing&gt;</span></span>

<span data-ttu-id="b6740-103">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="b6740-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="b6740-104">[**\<System. ServiceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="b6740-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="b6740-105">&nbsp;&nbsp;[**\<routing >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="b6740-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="b6740-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<i filtri >**</span><span class="sxs-lookup"><span data-stu-id="b6740-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b6740-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6740-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="b6740-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b6740-108">Attributes and elements</span></span>

<span data-ttu-id="b6740-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b6740-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b6740-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b6740-110">Attributes</span></span>

<span data-ttu-id="b6740-111">Nessuno</span><span class="sxs-lookup"><span data-stu-id="b6740-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="b6740-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b6740-112">Child elements</span></span>

|     | <span data-ttu-id="b6740-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6740-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b6740-114">**\<Filtro >**</span><span class="sxs-lookup"><span data-stu-id="b6740-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="b6740-115">Contiene un filtro di routing che determina il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> verrà utilizzato durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="b6740-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="b6740-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b6740-116">Parent elements</span></span>

|     | <span data-ttu-id="b6740-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6740-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b6740-118">**\<routing >**</span><span class="sxs-lookup"><span data-stu-id="b6740-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="b6740-119">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di routing che definiscono gli endpoint di destinazione a tabelle inviare messaggi quando un filtro trovata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="b6740-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b6740-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6740-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
