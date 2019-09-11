---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5f2bb030d13389e15cb44f1ddff3b8168b4f2140
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850262"
---
# <a name="backuplists"></a><span data-ttu-id="919e4-101">\<> backupLists</span><span class="sxs-lookup"><span data-stu-id="919e4-101">\<backupLists></span></span>
<span data-ttu-id="919e4-102">Rappresenta una sezione di configurazione per la definizione di un set di servizi di backup usati nella gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="919e4-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="919e4-103">Ogni elemento figlio è un elenco di backup che enumera un set di endpoint che si desidera vengano utilizzati dal servizio di routing nel caso in cui non sia possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="919e4-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="919e4-104">Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="919e4-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="919e4-105">In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.</span><span class="sxs-lookup"><span data-stu-id="919e4-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
<span data-ttu-id="919e4-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="919e4-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="919e4-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="919e4-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="919e4-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di routing**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="919e4-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="919e4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> backupLists**</span><span class="sxs-lookup"><span data-stu-id="919e4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="919e4-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="919e4-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="919e4-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="919e4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="919e4-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="919e4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="919e4-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="919e4-113">Attributes</span></span>  
 <span data-ttu-id="919e4-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="919e4-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="919e4-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="919e4-115">Child Elements</span></span>  
  
|<span data-ttu-id="919e4-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="919e4-116">Element</span></span>|<span data-ttu-id="919e4-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="919e4-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="919e4-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="919e4-118">\<filter></span></span>](filter.md)|<span data-ttu-id="919e4-119">Contiene un elenco di endpoint che si desidera vengano utilizzati dal servizio di routing nel caso in cui non sia possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="919e4-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="919e4-120">.</span><span class="sxs-lookup"><span data-stu-id="919e4-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="919e4-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="919e4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="919e4-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="919e4-122">Element</span></span>|<span data-ttu-id="919e4-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="919e4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="919e4-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="919e4-124">\<routing></span></span>](routing.md)|<span data-ttu-id="919e4-125">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di<xref:System.ServiceModel.Dispatcher.MessageFilter> Windows Communication Foundation (WCF) da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione Invia messaggi a quando viene individuato un filtro.</span><span class="sxs-lookup"><span data-stu-id="919e4-125">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="919e4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="919e4-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
