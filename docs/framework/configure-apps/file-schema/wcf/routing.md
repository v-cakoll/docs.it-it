---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: fcf2d4eec93fd7127c6f800e1c739ad1fac49203
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399970"
---
# \<routing>

<span data-ttu-id="81304-101">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione ai quali inviare messaggi quando viene individuato un filtro.</span><span class="sxs-lookup"><span data-stu-id="81304-101">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**
  
## <a name="syntax"></a><span data-ttu-id="81304-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81304-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String"
               filterName="String"
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81304-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="81304-103">Attributes and elements</span></span>

<span data-ttu-id="81304-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="81304-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="81304-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="81304-105">Attributes</span></span>

<span data-ttu-id="81304-106">nessuno</span><span class="sxs-lookup"><span data-stu-id="81304-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="81304-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="81304-107">Child elements</span></span>

|     | <span data-ttu-id="81304-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81304-108">Description</span></span> |
| --- | ----------- |
| [**\<filters>**](filters-of-routing.md) | <span data-ttu-id="81304-109">Contiene un set di filtri di routing che determinano il tipo di Windows Communication Foundation (WCF) MessageFilter verrà usato durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="81304-109">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [**\<filterTables>**](filtertables.md) | <span data-ttu-id="81304-110">Contiene i mapping tra i filtri di routing e gli endpoint di destinazione per la specifica dell'endpoint da usare quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="81304-110">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="81304-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="81304-111">Parent elements</span></span>

|     | <span data-ttu-id="81304-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81304-112">Description</span></span> |
| --- | ----------- |
| **\<system.ServiceModel>** | <span data-ttu-id="81304-113">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="81304-113">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="81304-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81304-114">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
