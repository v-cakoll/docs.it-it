---
title: '&lt;namespaceTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 470dd2dcc2e8554bb89eec159c6b96b24795c5d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="d508b-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="d508b-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="d508b-103">Rappresenta una sezione di configurazione per la definizione di un set di elementi contenenti lo spazio dei nomi da anteporre ai mapping che possono quindi essere usati nei filtri XPath per il routing.</span><span class="sxs-lookup"><span data-stu-id="d508b-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="d508b-104">**\<System. ServiceModel >** </span><span class="sxs-lookup"><span data-stu-id="d508b-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="d508b-105">&nbsp;&nbsp;**\<routing >** </span><span class="sxs-lookup"><span data-stu-id="d508b-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="d508b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="d508b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d508b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d508b-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="d508b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d508b-108">Attributes and elements</span></span>

<span data-ttu-id="d508b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d508b-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d508b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d508b-110">Attributes</span></span>

<span data-ttu-id="d508b-111">Nessuno</span><span class="sxs-lookup"><span data-stu-id="d508b-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="d508b-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d508b-112">Child elements</span></span>

|     | <span data-ttu-id="d508b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d508b-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d508b-114">**\<Filtro >**</span><span class="sxs-lookup"><span data-stu-id="d508b-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="d508b-115">Definisce un mapping del prefisso dello spazio dei nomi usato per espressioni XPath.</span><span class="sxs-lookup"><span data-stu-id="d508b-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="d508b-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d508b-116">Parent elements</span></span>

|     | <span data-ttu-id="d508b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d508b-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d508b-118">**\<routing >**</span><span class="sxs-lookup"><span data-stu-id="d508b-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="d508b-119">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] di <xref:System.ServiceModel.Dispatcher.MessageFilter> da usare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="d508b-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d508b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d508b-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
