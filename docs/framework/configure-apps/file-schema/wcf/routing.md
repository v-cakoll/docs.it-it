---
title: '&lt;Routing&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 220c18ab8ea6222fcf7d9fb8a93950281c9de796
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145146"
---
# <a name="ltroutinggt"></a><span data-ttu-id="45a70-102">&lt;Routing&gt;</span><span class="sxs-lookup"><span data-stu-id="45a70-102">&lt;routing&gt;</span></span>

<span data-ttu-id="45a70-103">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di routing che definiscono gli endpoint di destinazione per tabelle inviare messaggi a quando un filtro corrisponda.</span><span class="sxs-lookup"><span data-stu-id="45a70-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="45a70-104">[**\<System. ServiceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="45a70-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="45a70-105">&nbsp;&nbsp;**\<routing >**</span><span class="sxs-lookup"><span data-stu-id="45a70-105">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="45a70-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45a70-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45a70-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="45a70-107">Attributes and elements</span></span>

<span data-ttu-id="45a70-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="45a70-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="45a70-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="45a70-109">Attributes</span></span>

<span data-ttu-id="45a70-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="45a70-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="45a70-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="45a70-111">Child elements</span></span>

|     | <span data-ttu-id="45a70-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45a70-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="45a70-113">**\<i filtri >**</span><span class="sxs-lookup"><span data-stu-id="45a70-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="45a70-114">Contiene un set di filtri di routing che determinano che il tipo di MessageFilter di Windows Communication Foundation (WCF) da utilizzare durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="45a70-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="45a70-115">**\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="45a70-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="45a70-116">Contiene i mapping tra i filtri di routing e gli endpoint di destinazione per la specifica dell'endpoint da usare quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="45a70-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="45a70-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="45a70-117">Parent elements</span></span>

|     | <span data-ttu-id="45a70-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45a70-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="45a70-119">**\<System. ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="45a70-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="45a70-120">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="45a70-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="45a70-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45a70-121">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
