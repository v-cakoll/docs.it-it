---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 478211755b9131c03b72777ee95ff7223b9092c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850278"
---
# \<backupList>
<span data-ttu-id="48ecf-101">Rappresenta una sezione di configurazione per la definizione di un backup che enumera un set di endpoint che si desidera vengano utilizzati dal servizio di routing quando non è possibile raggiungere l'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="48ecf-101">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="48ecf-102">Se il primo endpoint dell'elenco non funziona, il servizio di routing eseguirà automaticamente il failover nel successivo endpoint dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="48ecf-102">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="48ecf-103">In questo modo è possibile migliorare rapidamente l'affidabilità all'applicazione senza che sia necessario indicare all'applicazione client come gestire modelli complessi o la posizione in cui i servizi sono distribuiti.</span><span class="sxs-lookup"><span data-stu-id="48ecf-103">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupList>**  
  
## <a name="syntax"></a><span data-ttu-id="48ecf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48ecf-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48ecf-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="48ecf-105">Attributes and Elements</span></span>  
 <span data-ttu-id="48ecf-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="48ecf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48ecf-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="48ecf-107">Attributes</span></span>  
  
|<span data-ttu-id="48ecf-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="48ecf-108">Attribute</span></span>|<span data-ttu-id="48ecf-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48ecf-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="48ecf-110">name</span><span class="sxs-lookup"><span data-stu-id="48ecf-110">name</span></span>|<span data-ttu-id="48ecf-111">Stringa che specifica il nome usato per identificare l'elenco di endpoint.</span><span class="sxs-lookup"><span data-stu-id="48ecf-111">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48ecf-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="48ecf-112">Child Elements</span></span>  
  
|<span data-ttu-id="48ecf-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="48ecf-113">Element</span></span>|<span data-ttu-id="48ecf-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48ecf-114">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="48ecf-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="48ecf-115">Parent Elements</span></span>  
  
|<span data-ttu-id="48ecf-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="48ecf-116">Element</span></span>|<span data-ttu-id="48ecf-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48ecf-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="48ecf-118">Elenco di endpoint di backup.</span><span class="sxs-lookup"><span data-stu-id="48ecf-118">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48ecf-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="48ecf-119">Remarks</span></span>  
 <span data-ttu-id="48ecf-120">Questa sezione include una raccolta ordinata di endpoint ai quali verrà trasmesso un messaggio nel caso venga generata un'eccezione di comunicazione durante l'invio all'endpoint primario.</span><span class="sxs-lookup"><span data-stu-id="48ecf-120">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="48ecf-121">Se un invio all'endpoint primario elencato nell' `endpointName` attributo di ha [\<add>](add-of-entries.md) esito negativo con un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio al primo endpoint in questa sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="48ecf-121">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="48ecf-122">Se anche questo invio non riesce e viene generata un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio all'endpoint successivo incluso in questa sezione fino a quando il tentativo di invio non ha esito positivo, non viene restituito un errore diverso da un'eccezione di comunicazione o tutti gli endpoint inclusi nella raccolta non restituiscono un errore.</span><span class="sxs-lookup"><span data-stu-id="48ecf-122">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="48ecf-123">Nell'esempio seguente, se un invio all'endpoint primario denominato "Destination" restituisce un'eccezione di comunicazione, il servizio tenterà di inviare il messaggio a "alternateServiceQueue".</span><span class="sxs-lookup"><span data-stu-id="48ecf-123">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="48ecf-124">Se anche questo tentativo restituisce un'eccezione di comunicazione, il servizio di routing tenterà di inviare il messaggio all'endpoint successivo incluso nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="48ecf-124">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="48ecf-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48ecf-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
