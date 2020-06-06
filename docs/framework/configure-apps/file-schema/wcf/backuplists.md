---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5f2bb030d13389e15cb44f1ddff3b8168b4f2140
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850262"
---
# \<backupLists>
<span data-ttu-id="1524b-101">Rappresenta una sezione di configurazione per la definizione di un set di servizi di backup usati nella gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="1524b-101">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="1524b-102">Ogni elemento figlio è un elenco di backup che enumera un set di endpoint che si desidera vengano utilizzati dal servizio di routing quando non è possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="1524b-102">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="1524b-103">Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1524b-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="1524b-104">In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.</span><span class="sxs-lookup"><span data-stu-id="1524b-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**  
  
## <a name="syntax"></a><span data-ttu-id="1524b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1524b-105">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1524b-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1524b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1524b-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1524b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1524b-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="1524b-108">Attributes</span></span>  
 <span data-ttu-id="1524b-109">No.</span><span class="sxs-lookup"><span data-stu-id="1524b-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1524b-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1524b-110">Child Elements</span></span>  
  
|<span data-ttu-id="1524b-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="1524b-111">Element</span></span>|<span data-ttu-id="1524b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1524b-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)|<span data-ttu-id="1524b-113">Contiene un elenco di endpoint che dovranno essere usati nel servizio di routing quando non è possibile raggiungere l'endpoint primario. </span><span class="sxs-lookup"><span data-stu-id="1524b-113">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="1524b-114">.</span><span class="sxs-lookup"><span data-stu-id="1524b-114">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1524b-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1524b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="1524b-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="1524b-116">Element</span></span>|<span data-ttu-id="1524b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1524b-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="1524b-118">Rappresenta una sezione di configurazione per la definizione di un set di filtri di routing che determinano il tipo di Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di tabelle di routing che definiscono gli endpoint di destinazione ai quali inviare messaggi quando viene individuato un filtro.</span><span class="sxs-lookup"><span data-stu-id="1524b-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1524b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1524b-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
