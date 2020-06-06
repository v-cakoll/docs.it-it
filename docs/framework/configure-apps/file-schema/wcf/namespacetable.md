---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: aefe7beec7335d80341e670961800907c2bd0200
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855104"
---
# \<namespaceTable>

<span data-ttu-id="88d6e-101">Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="88d6e-101">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**  
  
## <a name="syntax"></a><span data-ttu-id="88d6e-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="88d6e-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88d6e-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="88d6e-103">Attributes and elements</span></span>

<span data-ttu-id="88d6e-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="88d6e-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="88d6e-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="88d6e-105">Attributes</span></span>

<span data-ttu-id="88d6e-106">nessuno</span><span class="sxs-lookup"><span data-stu-id="88d6e-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="88d6e-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="88d6e-107">Child elements</span></span>

|     | <span data-ttu-id="88d6e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88d6e-108">Description</span></span> |
| --- | ----------- |
| [**\<filter>**](filter.md) | <span data-ttu-id="88d6e-109">Definisce un mapping del prefisso dello spazio dei nomi usato per espressioni XPath.</span><span class="sxs-lookup"><span data-stu-id="88d6e-109">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="88d6e-110">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="88d6e-110">Parent elements</span></span>

|     | <span data-ttu-id="88d6e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88d6e-111">Description</span></span> |
| --- | ----------- |
| [**\<routing>**](routing.md) | <span data-ttu-id="88d6e-112">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione ai quali inviare messaggi quando viene individuato un filtro.</span><span class="sxs-lookup"><span data-stu-id="88d6e-112">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="88d6e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88d6e-113">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
