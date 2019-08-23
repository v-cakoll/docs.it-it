---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 0316e983446644671ead2f8f843dc91b493b29c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933161"
---
# <a name="namespacetable"></a><span data-ttu-id="78e7f-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="78e7f-101">\<namespaceTable></span></span>

<span data-ttu-id="78e7f-102">Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="78e7f-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="78e7f-103">**\<system.serviceModel>**  </span><span class="sxs-lookup"><span data-stu-id="78e7f-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="78e7f-104">&nbsp;&nbsp; **\<routing>**  </span><span class="sxs-lookup"><span data-stu-id="78e7f-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="78e7f-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="78e7f-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="78e7f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78e7f-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78e7f-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="78e7f-107">Attributes and elements</span></span>

<span data-ttu-id="78e7f-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="78e7f-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="78e7f-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="78e7f-109">Attributes</span></span>

<span data-ttu-id="78e7f-110">Nessuna</span><span class="sxs-lookup"><span data-stu-id="78e7f-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="78e7f-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="78e7f-111">Child elements</span></span>

|     | <span data-ttu-id="78e7f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78e7f-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="78e7f-113"> **\<filter>** </span><span class="sxs-lookup"><span data-stu-id="78e7f-113">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="78e7f-114">Definisce un mapping del prefisso dello spazio dei nomi usato per espressioni XPath.</span><span class="sxs-lookup"><span data-stu-id="78e7f-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="78e7f-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="78e7f-115">Parent elements</span></span>

|     | <span data-ttu-id="78e7f-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="78e7f-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="78e7f-117"> **\<routing>** </span><span class="sxs-lookup"><span data-stu-id="78e7f-117">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="78e7f-118">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di<xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione Invia messaggi a quando viene individuato un filtro.</span><span class="sxs-lookup"><span data-stu-id="78e7f-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="78e7f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78e7f-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
