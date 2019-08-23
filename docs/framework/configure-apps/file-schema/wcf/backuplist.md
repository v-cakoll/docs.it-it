---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: d5feab6cb374f98e683cf15f797de4f478e23131
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919914"
---
# <a name="backuplist"></a><span data-ttu-id="7f9b0-101">\<> di backup</span><span class="sxs-lookup"><span data-stu-id="7f9b0-101">\<backupList></span></span>
<span data-ttu-id="7f9b0-102">Rappresenta una sezione di configurazione per la definizione di un elenco di backup che enumera un set di endpoint che si desidera vengano utilizzati dal servizio di routing nel caso in cui non sia possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="7f9b0-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="7f9b0-103">Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7f9b0-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="7f9b0-104">In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.</span><span class="sxs-lookup"><span data-stu-id="7f9b0-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="7f9b0-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7f9b0-105">\<system.serviceModel></span></span>  
<span data-ttu-id="7f9b0-106">\<routing></span><span class="sxs-lookup"><span data-stu-id="7f9b0-106">\<routing></span></span>  
<span data-ttu-id="7f9b0-107">\<> backupLists</span><span class="sxs-lookup"><span data-stu-id="7f9b0-107">\<backupLists></span></span>  
<span data-ttu-id="7f9b0-108">\<> di backup</span><span class="sxs-lookup"><span data-stu-id="7f9b0-108">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f9b0-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f9b0-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f9b0-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7f9b0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7f9b0-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7f9b0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f9b0-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7f9b0-112">Attributes</span></span>  
  
|<span data-ttu-id="7f9b0-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7f9b0-113">Attribute</span></span>|<span data-ttu-id="7f9b0-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7f9b0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f9b0-115">name</span><span class="sxs-lookup"><span data-stu-id="7f9b0-115">name</span></span>|<span data-ttu-id="7f9b0-116">Stringa che specifica il nome usato per identificare l'elenco di endpoint.</span><span class="sxs-lookup"><span data-stu-id="7f9b0-116">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f9b0-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7f9b0-117">Child Elements</span></span>  
  
|<span data-ttu-id="7f9b0-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f9b0-118">Element</span></span>|<span data-ttu-id="7f9b0-119">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="7f9b0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f9b0-120">\<filter></span><span class="sxs-lookup"><span data-stu-id="7f9b0-120">\<filter></span></span>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="7f9b0-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7f9b0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7f9b0-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f9b0-122">Element</span></span>|<span data-ttu-id="7f9b0-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f9b0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f9b0-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="7f9b0-124">\<routing></span></span>](routing.md)|<span data-ttu-id="7f9b0-125">Elenco di endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="7f9b0-125">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f9b0-126">Note</span><span class="sxs-lookup"><span data-stu-id="7f9b0-126">Remarks</span></span>  
 <span data-ttu-id="7f9b0-127">Questa sezione include una raccolta ordinata di endpoint ai quali verrà trasmesso un messaggio nel caso venga generata un'eccezione di comunicazione durante l'invio all'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="7f9b0-127">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="7f9b0-128">Se un invio all'endpoint primario elencato nell' `endpointName` attributo di [ \<Add >](add-of-entries.md) ha esito negativo con un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio al primo endpoint in questa sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7f9b0-128">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="7f9b0-129">Se anche questo invio non riesce e viene generata un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio all'endpoint successivo incluso in questa sezione fino a quando il tentativo di invio non ha esito positivo, non viene restituito un errore diverso da un'eccezione di comunicazione o tutti gli endpoint inclusi nella raccolta non restituiscono un errore.</span><span class="sxs-lookup"><span data-stu-id="7f9b0-129">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="7f9b0-130">Nell'esempio seguente, se un invio all'endpoint primario denominato "Destination" restituisce un'eccezione di comunicazione, il servizio tenterà di inviare il messaggio a "alternateServiceQueue".</span><span class="sxs-lookup"><span data-stu-id="7f9b0-130">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="7f9b0-131">Se anche questo tentativo restituisce un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio all'endpoint successivo incluso nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="7f9b0-131">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7f9b0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f9b0-132">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
