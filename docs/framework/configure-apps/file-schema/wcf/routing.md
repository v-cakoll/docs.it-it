---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: fcf2d4eec93fd7127c6f800e1c739ad1fac49203
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399970"
---
# <a name="routing"></a><span data-ttu-id="911a2-101">\<routing></span><span class="sxs-lookup"><span data-stu-id="911a2-101">\<routing></span></span>

<span data-ttu-id="911a2-102">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di <xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione Invia messaggi a quando viene individuato un filtro.</span><span class="sxs-lookup"><span data-stu-id="911a2-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="911a2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="911a2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="911a2-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="911a2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="911a2-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<> di routing**</span><span class="sxs-lookup"><span data-stu-id="911a2-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="911a2-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="911a2-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="911a2-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="911a2-107">Attributes and elements</span></span>

<span data-ttu-id="911a2-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="911a2-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="911a2-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="911a2-109">Attributes</span></span>

<span data-ttu-id="911a2-110">Nessuna</span><span class="sxs-lookup"><span data-stu-id="911a2-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="911a2-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="911a2-111">Child elements</span></span>

|     | <span data-ttu-id="911a2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="911a2-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="911a2-113"> **\<Filtra >** </span><span class="sxs-lookup"><span data-stu-id="911a2-113">**\<filters>**</span></span>](filters-of-routing.md) | <span data-ttu-id="911a2-114">Contiene un set di filtri di routing che determinano il tipo di Windows Communication Foundation (WCF) MessageFilter verrà usato durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="911a2-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="911a2-115"> **\<filterTables>** </span><span class="sxs-lookup"><span data-stu-id="911a2-115">**\<filterTables>**</span></span>](filtertables.md) | <span data-ttu-id="911a2-116">Contiene i mapping tra i filtri di routing e gli endpoint di destinazione per la specifica dell'endpoint da usare quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="911a2-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="911a2-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="911a2-117">Parent elements</span></span>

|     | <span data-ttu-id="911a2-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="911a2-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="911a2-119">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="911a2-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="911a2-120">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="911a2-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="911a2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="911a2-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
