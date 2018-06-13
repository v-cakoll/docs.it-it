---
title: '&lt;Routing&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 1771d8a2603a8f61af6ba6e2acf6243d2fd073f7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747726"
---
# <a name="ltroutinggt"></a><span data-ttu-id="8c178-102">&lt;Routing&gt;</span><span class="sxs-lookup"><span data-stu-id="8c178-102">&lt;routing&gt;</span></span>

<span data-ttu-id="8c178-103">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di routing che definiscono gli endpoint di destinazione a tabelle inviare messaggi quando un filtro trovata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="8c178-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="8c178-104">[**\<System. ServiceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="8c178-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="8c178-105">&nbsp;&nbsp;**\<routing >**</span><span class="sxs-lookup"><span data-stu-id="8c178-105">&nbsp;&nbsp;**\<routing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8c178-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c178-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="8c178-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8c178-107">Attributes and elements</span></span>

<span data-ttu-id="8c178-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8c178-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8c178-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="8c178-109">Attributes</span></span>

<span data-ttu-id="8c178-110">Nessuno</span><span class="sxs-lookup"><span data-stu-id="8c178-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="8c178-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8c178-111">Child elements</span></span>

|     | <span data-ttu-id="8c178-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c178-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8c178-113">**\<i filtri >**</span><span class="sxs-lookup"><span data-stu-id="8c178-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="8c178-114">Contiene un set di filtri di routing che determinano che il tipo di MessageFilter di Windows Communication Foundation (WCF) verrà utilizzato durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="8c178-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="8c178-115">**\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="8c178-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="8c178-116">Contiene i mapping tra i filtri di routing e gli endpoint di destinazione per la specifica dell'endpoint da usare quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="8c178-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="8c178-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8c178-117">Parent elements</span></span>

|     | <span data-ttu-id="8c178-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c178-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="8c178-119">**\<System. ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="8c178-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="8c178-120">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="8c178-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8c178-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c178-121">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
