---
title: '&lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: c11fd38e7c40f740d4c1c36ab87c44744ed0daab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627983"
---
# <a name="ltbackuplistgt"></a><span data-ttu-id="d48a3-102">&lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="d48a3-102">&lt;backupList&gt;</span></span>
<span data-ttu-id="d48a3-103">Rappresenta una sezione di configurazione per la definizione di un elenco di backup che enumera un set di endpoint che si desidera il servizio di Routing da usare nel caso in cui non è possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="d48a3-103">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="d48a3-104">Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d48a3-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="d48a3-105">In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.</span><span class="sxs-lookup"><span data-stu-id="d48a3-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="d48a3-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d48a3-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d48a3-107">\<routing></span><span class="sxs-lookup"><span data-stu-id="d48a3-107">\<routing></span></span>  
<span data-ttu-id="d48a3-108">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="d48a3-108">\<backupLists></span></span>  
<span data-ttu-id="d48a3-109">\<backupList></span><span class="sxs-lookup"><span data-stu-id="d48a3-109">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d48a3-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d48a3-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d48a3-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d48a3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d48a3-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d48a3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d48a3-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="d48a3-113">Attributes</span></span>  
  
|<span data-ttu-id="d48a3-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="d48a3-114">Attribute</span></span>|<span data-ttu-id="d48a3-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d48a3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d48a3-116">name</span><span class="sxs-lookup"><span data-stu-id="d48a3-116">name</span></span>|<span data-ttu-id="d48a3-117">Stringa che specifica il nome usato per identificare l'elenco di endpoint.</span><span class="sxs-lookup"><span data-stu-id="d48a3-117">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d48a3-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d48a3-118">Child Elements</span></span>  
  
|<span data-ttu-id="d48a3-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d48a3-119">Element</span></span>|<span data-ttu-id="d48a3-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d48a3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d48a3-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="d48a3-121">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="d48a3-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d48a3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d48a3-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d48a3-123">Element</span></span>|<span data-ttu-id="d48a3-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d48a3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d48a3-125">\<routing></span><span class="sxs-lookup"><span data-stu-id="d48a3-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="d48a3-126">Elenco di endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="d48a3-126">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d48a3-127">Note</span><span class="sxs-lookup"><span data-stu-id="d48a3-127">Remarks</span></span>  
 <span data-ttu-id="d48a3-128">Questa sezione include una raccolta ordinata di endpoint ai quali verrà trasmesso un messaggio nel caso venga generata un'eccezione di comunicazione durante l'invio all'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="d48a3-128">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="d48a3-129">Se un invio all'endpoint primario elencato nel `endpointName` dell'attributo [ \<aggiungere >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) ha esito negativo con un'eccezione di comunicazione, il servizio di Routing tenterà di inviare il messaggio al primo endpoint in questo sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d48a3-129">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="d48a3-130">Se anche questo invio non riesce e viene generata un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio all'endpoint successivo incluso in questa sezione fino a quando il tentativo di invio non ha esito positivo, non viene restituito un errore diverso da un'eccezione di comunicazione o tutti gli endpoint inclusi nella raccolta non restituiscono un errore.</span><span class="sxs-lookup"><span data-stu-id="d48a3-130">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="d48a3-131">Nell'esempio seguente, se un invio all'endpoint primario denominato "Destination" restituisce un'eccezione di comunicazione, il servizio tenterà di inviare il messaggio a "alternateServiceQueue".</span><span class="sxs-lookup"><span data-stu-id="d48a3-131">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="d48a3-132">Se anche questo tentativo restituisce un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio all'endpoint successivo incluso nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="d48a3-132">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a><span data-ttu-id="d48a3-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d48a3-133">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
