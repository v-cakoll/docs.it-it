---
title: '&lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: fb2b324a2c128b470f1a9a21343408280c5e1862
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743244"
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="c8dcc-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="c8dcc-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="c8dcc-103">Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="c8dcc-104">**\<system.serviceModel>** </span><span class="sxs-lookup"><span data-stu-id="c8dcc-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="c8dcc-105">&nbsp;&nbsp;**\<routing>** </span><span class="sxs-lookup"><span data-stu-id="c8dcc-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="c8dcc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="c8dcc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c8dcc-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8dcc-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8dcc-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c8dcc-108">Attributes and elements</span></span>

<span data-ttu-id="c8dcc-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c8dcc-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="c8dcc-110">Attributes</span></span>

<span data-ttu-id="c8dcc-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="c8dcc-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="c8dcc-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c8dcc-112">Child elements</span></span>

|     | <span data-ttu-id="c8dcc-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8dcc-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c8dcc-114">**\<filter>**</span><span class="sxs-lookup"><span data-stu-id="c8dcc-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="c8dcc-115">Definisce un mapping del prefisso dello spazio dei nomi usato per espressioni XPath.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="c8dcc-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c8dcc-116">Parent elements</span></span>

|     | <span data-ttu-id="c8dcc-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8dcc-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c8dcc-118">**\<routing>**</span><span class="sxs-lookup"><span data-stu-id="c8dcc-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="c8dcc-119">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di routing che definiscono gli endpoint di destinazione per tabelle inviare messaggi a quando un filtro corrisponda.</span><span class="sxs-lookup"><span data-stu-id="c8dcc-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c8dcc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8dcc-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
