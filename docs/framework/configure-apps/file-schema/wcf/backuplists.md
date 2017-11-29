---
title: '&lt;backupLists&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f63dbad93fb36eab1b44c3f4135be3530ebdf340
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltbackuplistsgt"></a><span data-ttu-id="b1070-102">&lt;backupLists&gt;</span><span class="sxs-lookup"><span data-stu-id="b1070-102">&lt;backupLists&gt;</span></span>
<span data-ttu-id="b1070-103">Rappresenta una sezione di configurazione per la definizione di un set di servizi di backup usati nella gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="b1070-103">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="b1070-104">Ogni elemento figlio è un elenco di backup che enumera un set di endpoint che si desidera che il servizio di Routing da utilizzare nel caso in cui l'endpoint primario non è raggiungibile.</span><span class="sxs-lookup"><span data-stu-id="b1070-104">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="b1070-105">Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b1070-105">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="b1070-106">In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.</span><span class="sxs-lookup"><span data-stu-id="b1070-106">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="b1070-107">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b1070-107">\<system.serviceModel></span></span>  
<span data-ttu-id="b1070-108">\<routing ></span><span class="sxs-lookup"><span data-stu-id="b1070-108">\<routing></span></span>  
<span data-ttu-id="b1070-109">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="b1070-109">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1070-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1070-110">Syntax</span></span>  
  
```xml
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b1070-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b1070-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b1070-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b1070-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1070-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="b1070-113">Attributes</span></span>  
 <span data-ttu-id="b1070-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b1070-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b1070-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b1070-115">Child Elements</span></span>  
  
|<span data-ttu-id="b1070-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1070-116">Element</span></span>|<span data-ttu-id="b1070-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1070-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1070-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="b1070-118">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="b1070-119">Contiene un elenco di endpoint che si desidera che il servizio di Routing da utilizzare nel caso in cui l'endpoint primario non è raggiungibile.</span><span class="sxs-lookup"><span data-stu-id="b1070-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="b1070-120">.</span><span class="sxs-lookup"><span data-stu-id="b1070-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1070-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b1070-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b1070-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1070-122">Element</span></span>|<span data-ttu-id="b1070-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1070-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1070-124">\<routing ></span><span class="sxs-lookup"><span data-stu-id="b1070-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="b1070-125">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] di <xref:System.ServiceModel.Dispatcher.MessageFilter> da usare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione ai quali inviare i messaggi quando viene trovata una corrispondenza di filtro.</span><span class="sxs-lookup"><span data-stu-id="b1070-125">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1070-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1070-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
