---
title: '&lt;backupLists&gt;'
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: ff363f97b25496dc9bb3a691de7c8abf77c0dc9d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149124"
---
# <a name="ltbackuplistsgt"></a><span data-ttu-id="54658-102">&lt;backupLists&gt;</span><span class="sxs-lookup"><span data-stu-id="54658-102">&lt;backupLists&gt;</span></span>
<span data-ttu-id="54658-103">Rappresenta una sezione di configurazione per la definizione di un set di servizi di backup usati nella gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="54658-103">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="54658-104">Ogni elemento figlio è un elenco di backup che enumera un set di endpoint che si desidera il servizio di Routing da usare nel caso in cui non è possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="54658-104">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="54658-105">Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="54658-105">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="54658-106">In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.</span><span class="sxs-lookup"><span data-stu-id="54658-106">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="54658-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="54658-107">\<system.serviceModel></span></span>  
<span data-ttu-id="54658-108">\<routing ></span><span class="sxs-lookup"><span data-stu-id="54658-108">\<routing></span></span>  
<span data-ttu-id="54658-109">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="54658-109">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54658-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54658-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54658-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="54658-111">Attributes and Elements</span></span>  
 <span data-ttu-id="54658-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="54658-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54658-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="54658-113">Attributes</span></span>  
 <span data-ttu-id="54658-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="54658-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="54658-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="54658-115">Child Elements</span></span>  
  
|<span data-ttu-id="54658-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="54658-116">Element</span></span>|<span data-ttu-id="54658-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54658-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54658-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="54658-118">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="54658-119">Contiene un elenco di endpoint che si desidera il servizio di Routing da usare nel caso in cui non è possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="54658-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="54658-120">.</span><span class="sxs-lookup"><span data-stu-id="54658-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54658-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="54658-121">Parent Elements</span></span>  
  
|<span data-ttu-id="54658-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="54658-122">Element</span></span>|<span data-ttu-id="54658-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54658-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54658-124">\<routing ></span><span class="sxs-lookup"><span data-stu-id="54658-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="54658-125">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di routing che definiscono gli endpoint di destinazione per tabelle inviare messaggi a quando un filtro corrisponda.</span><span class="sxs-lookup"><span data-stu-id="54658-125">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54658-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54658-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
