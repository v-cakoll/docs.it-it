---
title: '&lt;routing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed2dd4e68584d6e79e18fc9b61fcc8f078615dac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltroutinggt"></a><span data-ttu-id="97f3a-102">&lt;routing&gt;</span><span class="sxs-lookup"><span data-stu-id="97f3a-102">&lt;routing&gt;</span></span>

<span data-ttu-id="97f3a-103">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] di <xref:System.ServiceModel.Dispatcher.MessageFilter> da usare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="97f3a-103">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="97f3a-104">[**\<System. ServiceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="97f3a-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="97f3a-105">&nbsp;&nbsp;**\<routing >**</span><span class="sxs-lookup"><span data-stu-id="97f3a-105">&nbsp;&nbsp;**\<routing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="97f3a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97f3a-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="97f3a-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="97f3a-107">Attributes and elements</span></span>

<span data-ttu-id="97f3a-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="97f3a-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="97f3a-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="97f3a-109">Attributes</span></span>

<span data-ttu-id="97f3a-110">Nessuno</span><span class="sxs-lookup"><span data-stu-id="97f3a-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="97f3a-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="97f3a-111">Child elements</span></span>

|     | <span data-ttu-id="97f3a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97f3a-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="97f3a-113">**\<i filtri >**</span><span class="sxs-lookup"><span data-stu-id="97f3a-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="97f3a-114">Contiene un set di filtri di routing che determinano il tipo di MessageFilter di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] che verrà utilizzato durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="97f3a-114">Contains a set of routing filters that determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="97f3a-115">**\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="97f3a-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="97f3a-116">Contiene i mapping tra i filtri di routing e gli endpoint di destinazione per la specifica dell'endpoint da usare quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="97f3a-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="97f3a-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="97f3a-117">Parent elements</span></span>

|     | <span data-ttu-id="97f3a-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97f3a-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="97f3a-119">**\<System. ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="97f3a-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="97f3a-120">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="97f3a-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="97f3a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97f3a-121">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
