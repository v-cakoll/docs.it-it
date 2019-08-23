---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: b65cc4d04b5304e93b70509c9db3bc2248accb7f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926441"
---
# <a name="backuplists"></a><span data-ttu-id="3fe8c-101">\<> backupLists</span><span class="sxs-lookup"><span data-stu-id="3fe8c-101">\<backupLists></span></span>
<span data-ttu-id="3fe8c-102">Rappresenta una sezione di configurazione per la definizione di un set di servizi di backup usati nella gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="3fe8c-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="3fe8c-103">Ogni elemento figlio è un elenco di backup che enumera un set di endpoint che si desidera vengano utilizzati dal servizio di routing nel caso in cui non sia possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="3fe8c-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="3fe8c-104">Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3fe8c-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="3fe8c-105">In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.</span><span class="sxs-lookup"><span data-stu-id="3fe8c-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="3fe8c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3fe8c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3fe8c-107">\<routing></span><span class="sxs-lookup"><span data-stu-id="3fe8c-107">\<routing></span></span>  
<span data-ttu-id="3fe8c-108">\<> backupLists</span><span class="sxs-lookup"><span data-stu-id="3fe8c-108">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fe8c-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fe8c-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fe8c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3fe8c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3fe8c-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3fe8c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fe8c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="3fe8c-112">Attributes</span></span>  
 <span data-ttu-id="3fe8c-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3fe8c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3fe8c-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3fe8c-114">Child Elements</span></span>  
  
|<span data-ttu-id="3fe8c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="3fe8c-115">Element</span></span>|<span data-ttu-id="3fe8c-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="3fe8c-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fe8c-117">\<filter></span><span class="sxs-lookup"><span data-stu-id="3fe8c-117">\<filter></span></span>](filter.md)|<span data-ttu-id="3fe8c-118">Contiene un elenco di endpoint che si desidera vengano utilizzati dal servizio di routing nel caso in cui non sia possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="3fe8c-118">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="3fe8c-119">.</span><span class="sxs-lookup"><span data-stu-id="3fe8c-119">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3fe8c-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3fe8c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3fe8c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3fe8c-121">Element</span></span>|<span data-ttu-id="3fe8c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3fe8c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fe8c-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="3fe8c-123">\<routing></span></span>](routing.md)|<span data-ttu-id="3fe8c-124">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di<xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione Invia messaggi a quando viene individuato un filtro.</span><span class="sxs-lookup"><span data-stu-id="3fe8c-124">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3fe8c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fe8c-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
