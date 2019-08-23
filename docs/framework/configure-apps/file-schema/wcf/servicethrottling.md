---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: 77ed5e91f09d9e658deeb7996baaca445b4e0c90
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937100"
---
# <a name="servicethrottling"></a><span data-ttu-id="a3e0a-101">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="a3e0a-101">\<serviceThrottling></span></span>
<span data-ttu-id="a3e0a-102">Specifica il meccanismo della limitazione di un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a3e0a-102">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="a3e0a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a3e0a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a3e0a-104">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="a3e0a-104">\<behaviors></span></span>  
<span data-ttu-id="a3e0a-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a3e0a-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="a3e0a-106">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="a3e0a-106">\<behavior></span></span>  
<span data-ttu-id="a3e0a-107">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="a3e0a-107">\<serviceThrottling></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3e0a-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3e0a-108">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3e0a-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a3e0a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a3e0a-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3e0a-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="a3e0a-111">Attributes</span></span>  
  
|<span data-ttu-id="a3e0a-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="a3e0a-112">Attribute</span></span>|<span data-ttu-id="a3e0a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3e0a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a3e0a-114">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="a3e0a-114">maxConcurrentCalls</span></span>|<span data-ttu-id="a3e0a-115">Numero intero positivo che limita il numero di messaggi attualmente elaborati in un oggetto <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-115">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="a3e0a-116">Le chiamate oltre il limite vengono accodate.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-116">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="a3e0a-117">L'impostazione di questo valore su 0 è equivalente alla relativa impostazione su Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-117">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="a3e0a-118">L'impostazione predefinita è 16 \* il numero dei processori.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-118">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="a3e0a-119">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="a3e0a-119">maxConcurrentInstances</span></span>|<span data-ttu-id="a3e0a-120">Numero intero positivo che limita il numero di oggetti <xref:System.ServiceModel.InstanceContext> eseguiti contemporaneamente in un oggetto <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-120">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="a3e0a-121">Le richieste di creare istanze aggiuntive vengono messe in coda e completate quando diventa disponibile uno slot sotto il limite.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-121">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="a3e0a-122">L'impostazione predefinita è la somma di maxConcurrentSessions più MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="a3e0a-122">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="a3e0a-123">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="a3e0a-123">maxConcurrentSessions</span></span>|<span data-ttu-id="a3e0a-124">Numero intero positivo che limita il numero di sessioni che possono essere accettate da un oggetto <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-124">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="a3e0a-125">Il servizio accetterà le connessioni oltre il limite, ma sono attivi solo i canali sotto il limite (i messaggi vengono letti dal canale).</span><span class="sxs-lookup"><span data-stu-id="a3e0a-125">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="a3e0a-126">L'impostazione di questo valore su 0 è equivalente alla relativa impostazione su Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-126">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="a3e0a-127">L'impostazione predefinita è 100 \* il numero dei processori.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-127">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3e0a-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a3e0a-128">Child Elements</span></span>  
 <span data-ttu-id="a3e0a-129">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3e0a-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a3e0a-130">Parent Elements</span></span>  
  
|<span data-ttu-id="a3e0a-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3e0a-131">Element</span></span>|<span data-ttu-id="a3e0a-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3e0a-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3e0a-133">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a3e0a-133">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a3e0a-134">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-134">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3e0a-135">Note</span><span class="sxs-lookup"><span data-stu-id="a3e0a-135">Remarks</span></span>  
 <span data-ttu-id="a3e0a-136">I controlli di limitazione pongono dei limiti sul numero di chiamate, istanze o sessioni simultanee per impedire l'uso eccessivo di risorse.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-136">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="a3e0a-137">Viene scritta una traccia ogni volta che viene raggiunto il valore di attributi.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-137">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="a3e0a-138">La prima traccia viene scritta come un avviso.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-138">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3e0a-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="a3e0a-139">Example</span></span>  
 <span data-ttu-id="a3e0a-140">Nell'esempio di configurazione seguente viene specificato che il servizio limita il numero massimo di chiamate simultanee a 2 e il numero massimo di istanze simultanee a 10.</span><span class="sxs-lookup"><span data-stu-id="a3e0a-140">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="a3e0a-141">Per un esempio dettagliato dell'esecuzione di questo esempio, vedere [limitazione delle richieste](../../../wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="a3e0a-141">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDebug includeExceptionDetailInFaults="False" />
      <serviceMetadata httpGetEnabled="True" />
      <!-- Specify throttling behavior -->
      <serviceThrottling maxConcurrentCalls="2"
                         maxConcurrentInstances="10" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="a3e0a-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3e0a-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="a3e0a-143">Uso di ServiceThrottlingBehavior per controllare le prestazioni del servizio WCF</span><span class="sxs-lookup"><span data-stu-id="a3e0a-143">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
