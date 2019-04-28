---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: ee7a0c23adca883af279addf9d1f221bd4056d00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772411"
---
# <a name="namespacetable"></a><span data-ttu-id="e55e0-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="e55e0-101">\<namespaceTable></span></span>

<span data-ttu-id="e55e0-102">Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="e55e0-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="e55e0-103">**\<system.serviceModel>** </span><span class="sxs-lookup"><span data-stu-id="e55e0-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="e55e0-104">&nbsp;&nbsp;**\<routing>** </span><span class="sxs-lookup"><span data-stu-id="e55e0-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="e55e0-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="e55e0-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="e55e0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e55e0-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e55e0-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e55e0-107">Attributes and elements</span></span>

<span data-ttu-id="e55e0-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e55e0-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e55e0-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="e55e0-109">Attributes</span></span>

<span data-ttu-id="e55e0-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="e55e0-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="e55e0-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e55e0-111">Child elements</span></span>

|     | <span data-ttu-id="e55e0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e55e0-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e55e0-113">**\<filter>**</span><span class="sxs-lookup"><span data-stu-id="e55e0-113">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="e55e0-114">Definisce un mapping del prefisso dello spazio dei nomi usato per espressioni XPath.</span><span class="sxs-lookup"><span data-stu-id="e55e0-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="e55e0-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e55e0-115">Parent elements</span></span>

|     | <span data-ttu-id="e55e0-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e55e0-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e55e0-117">**\<routing>**</span><span class="sxs-lookup"><span data-stu-id="e55e0-117">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="e55e0-118">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di routing che definiscono gli endpoint di destinazione per tabelle inviare messaggi a quando un filtro corrisponda.</span><span class="sxs-lookup"><span data-stu-id="e55e0-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e55e0-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e55e0-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
