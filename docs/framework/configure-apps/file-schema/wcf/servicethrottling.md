---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: ad87a5876381a7224341babdb076c85edcd1dd87
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399571"
---
# <a name="servicethrottling"></a><span data-ttu-id="c7281-101">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="c7281-101">\<serviceThrottling></span></span>
<span data-ttu-id="c7281-102">Specifica il meccanismo della limitazione di un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c7281-102">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
<span data-ttu-id="c7281-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c7281-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c7281-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c7281-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c7281-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c7281-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="c7281-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c7281-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="c7281-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c7281-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="c7281-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceThrottling**</span><span class="sxs-lookup"><span data-stu-id="c7281-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceThrottling>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7281-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7281-109">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7281-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c7281-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c7281-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c7281-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7281-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c7281-112">Attributes</span></span>  
  
|<span data-ttu-id="c7281-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c7281-113">Attribute</span></span>|<span data-ttu-id="c7281-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7281-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c7281-115">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="c7281-115">maxConcurrentCalls</span></span>|<span data-ttu-id="c7281-116">Numero intero positivo che limita il numero di messaggi attualmente elaborati in un oggetto <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c7281-116">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="c7281-117">Le chiamate oltre il limite vengono accodate.</span><span class="sxs-lookup"><span data-stu-id="c7281-117">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="c7281-118">L'impostazione di questo valore su 0 è equivalente alla relativa impostazione su Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="c7281-118">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="c7281-119">L'impostazione predefinita è 16 \* il numero dei processori.</span><span class="sxs-lookup"><span data-stu-id="c7281-119">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="c7281-120">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="c7281-120">maxConcurrentInstances</span></span>|<span data-ttu-id="c7281-121">Numero intero positivo che limita il numero di oggetti <xref:System.ServiceModel.InstanceContext> eseguiti contemporaneamente in un oggetto <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c7281-121">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="c7281-122">Le richieste di creare istanze aggiuntive vengono messe in coda e completate quando diventa disponibile uno slot sotto il limite.</span><span class="sxs-lookup"><span data-stu-id="c7281-122">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="c7281-123">L'impostazione predefinita è la somma di maxConcurrentSessions più MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="c7281-123">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="c7281-124">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="c7281-124">maxConcurrentSessions</span></span>|<span data-ttu-id="c7281-125">Numero intero positivo che limita il numero di sessioni che possono essere accettate da un oggetto <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c7281-125">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="c7281-126">Il servizio accetterà le connessioni oltre il limite, ma sono attivi solo i canali sotto il limite (i messaggi vengono letti dal canale).</span><span class="sxs-lookup"><span data-stu-id="c7281-126">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="c7281-127">L'impostazione di questo valore su 0 è equivalente alla relativa impostazione su Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="c7281-127">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="c7281-128">L'impostazione predefinita è 100 \* il numero dei processori.</span><span class="sxs-lookup"><span data-stu-id="c7281-128">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7281-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c7281-129">Child Elements</span></span>  
 <span data-ttu-id="c7281-130">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c7281-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7281-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c7281-131">Parent Elements</span></span>  
  
|<span data-ttu-id="c7281-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7281-132">Element</span></span>|<span data-ttu-id="c7281-133">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c7281-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7281-134">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c7281-134">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c7281-135">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="c7281-135">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7281-136">Note</span><span class="sxs-lookup"><span data-stu-id="c7281-136">Remarks</span></span>  
 <span data-ttu-id="c7281-137">I controlli di limitazione pongono dei limiti sul numero di chiamate, istanze o sessioni simultanee per impedire l'uso eccessivo di risorse.</span><span class="sxs-lookup"><span data-stu-id="c7281-137">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="c7281-138">Viene scritta una traccia ogni volta che viene raggiunto il valore di attributi.</span><span class="sxs-lookup"><span data-stu-id="c7281-138">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="c7281-139">La prima traccia viene scritta come un avviso.</span><span class="sxs-lookup"><span data-stu-id="c7281-139">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7281-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="c7281-140">Example</span></span>  
 <span data-ttu-id="c7281-141">Nell'esempio di configurazione seguente viene specificato che il servizio limita il numero massimo di chiamate simultanee a 2 e il numero massimo di istanze simultanee a 10.</span><span class="sxs-lookup"><span data-stu-id="c7281-141">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="c7281-142">Per un esempio dettagliato dell'esecuzione di questo esempio, vedere [limitazione delle richieste](../../../wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="c7281-142">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c7281-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7281-143">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="c7281-144">Uso di ServiceThrottlingBehavior per controllare le prestazioni del servizio WCF</span><span class="sxs-lookup"><span data-stu-id="c7281-144">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
