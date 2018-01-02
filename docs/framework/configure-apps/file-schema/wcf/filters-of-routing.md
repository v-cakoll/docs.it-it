---
title: '&lt;filters&gt; di &lt;routing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2687101aa868ae77ce0ae818afd9df906f8525c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltersgt-of-ltroutinggt"></a><span data-ttu-id="3d23d-102">&lt;filters&gt; di &lt;routing&gt;</span><span class="sxs-lookup"><span data-stu-id="3d23d-102">&lt;filters&gt; of &lt;routing&gt;</span></span>

<span data-ttu-id="3d23d-103">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> da usare durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="3d23d-103">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="3d23d-104">[**\<System. ServiceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="3d23d-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="3d23d-105">&nbsp;&nbsp;[**\<routing >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="3d23d-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="3d23d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<i filtri >**</span><span class="sxs-lookup"><span data-stu-id="3d23d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3d23d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d23d-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="3d23d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3d23d-108">Attributes and elements</span></span>

<span data-ttu-id="3d23d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3d23d-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3d23d-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3d23d-110">Attributes</span></span>

<span data-ttu-id="3d23d-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="3d23d-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="3d23d-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3d23d-112">Child elements</span></span>

|     | <span data-ttu-id="3d23d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d23d-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3d23d-114">**\<Filtro >**</span><span class="sxs-lookup"><span data-stu-id="3d23d-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="3d23d-115">Contiene un filtro di routing che determina il tipo di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> che verrà utilizzato durante la valutazione di messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="3d23d-115">Contains a routing filter that determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="3d23d-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3d23d-116">Parent elements</span></span>

|     | <span data-ttu-id="3d23d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d23d-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="3d23d-118">**\<routing >**</span><span class="sxs-lookup"><span data-stu-id="3d23d-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="3d23d-119">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] di <xref:System.ServiceModel.Dispatcher.MessageFilter> da usare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="3d23d-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="3d23d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d23d-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
