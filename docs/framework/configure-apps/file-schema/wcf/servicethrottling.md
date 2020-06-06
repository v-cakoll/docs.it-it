---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: ad87a5876381a7224341babdb076c85edcd1dd87
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399571"
---
# \<serviceThrottling>
<span data-ttu-id="556b0-101">Specifica il meccanismo della limitazione di un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="556b0-101">Specifies the throttling mechanism of a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceThrottling>**  
  
## <a name="syntax"></a><span data-ttu-id="556b0-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="556b0-102">Syntax</span></span>  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="556b0-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="556b0-103">Attributes and Elements</span></span>  
 <span data-ttu-id="556b0-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="556b0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="556b0-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="556b0-105">Attributes</span></span>  
  
|<span data-ttu-id="556b0-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="556b0-106">Attribute</span></span>|<span data-ttu-id="556b0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="556b0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="556b0-108">maxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="556b0-108">maxConcurrentCalls</span></span>|<span data-ttu-id="556b0-109">Numero intero positivo che limita il numero di messaggi attualmente elaborati in un oggetto <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="556b0-109">A positive integer that limits the number of messages that currently process across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="556b0-110">Le chiamate oltre il limite vengono accodate.</span><span class="sxs-lookup"><span data-stu-id="556b0-110">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="556b0-111">L'impostazione di questo valore su 0 è equivalente alla relativa impostazione su Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="556b0-111">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="556b0-112">L'impostazione predefinita è 16 \* il numero dei processori.</span><span class="sxs-lookup"><span data-stu-id="556b0-112">The default is 16 \* processor count.</span></span>|  
|<span data-ttu-id="556b0-113">maxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="556b0-113">maxConcurrentInstances</span></span>|<span data-ttu-id="556b0-114">Numero intero positivo che limita il numero di oggetti <xref:System.ServiceModel.InstanceContext> eseguiti contemporaneamente in un oggetto <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="556b0-114">A positive integer that limits the number of <xref:System.ServiceModel.InstanceContext> objects that execute at one time across a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="556b0-115">Le richieste di creare istanze aggiuntive vengono messe in coda e completate quando diventa disponibile uno slot sotto il limite.</span><span class="sxs-lookup"><span data-stu-id="556b0-115">Requests to create additional instances are queued and complete when a slot below the limit becomes available.</span></span> <span data-ttu-id="556b0-116">L'impostazione predefinita è la somma di maxConcurrentSessions più MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="556b0-116">The default is the sum of maxConcurrentSessions and MaxConcurrentCalls</span></span>|  
|<span data-ttu-id="556b0-117">maxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="556b0-117">maxConcurrentSessions</span></span>|<span data-ttu-id="556b0-118">Numero intero positivo che limita il numero di sessioni che possono essere accettate da un oggetto <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="556b0-118">A positive integer that limits the number of sessions a <xref:System.ServiceModel.ServiceHost> object can accept.</span></span><br /><br /> <span data-ttu-id="556b0-119">Il servizio accetterà le connessioni oltre il limite, ma sono attivi solo i canali sotto il limite (i messaggi vengono letti dal canale).</span><span class="sxs-lookup"><span data-stu-id="556b0-119">The service will accept connections in excess of the limit, but only the channels below the limit are active (messages are read from the channel).</span></span> <span data-ttu-id="556b0-120">L'impostazione di questo valore su 0 è equivalente alla relativa impostazione su Int32.MaxValue.</span><span class="sxs-lookup"><span data-stu-id="556b0-120">Setting this value to 0 is equivalent to setting it to Int32.MaxValue.</span></span> <span data-ttu-id="556b0-121">L'impostazione predefinita è 100 \* il numero dei processori.</span><span class="sxs-lookup"><span data-stu-id="556b0-121">The default is 100 \* processor count.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="556b0-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="556b0-122">Child Elements</span></span>  
 <span data-ttu-id="556b0-123">No.</span><span class="sxs-lookup"><span data-stu-id="556b0-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="556b0-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="556b0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="556b0-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="556b0-125">Element</span></span>|<span data-ttu-id="556b0-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="556b0-126">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="556b0-127">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="556b0-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="556b0-128">Commenti</span><span class="sxs-lookup"><span data-stu-id="556b0-128">Remarks</span></span>  
 <span data-ttu-id="556b0-129">I controlli di limitazione pongono dei limiti sul numero di chiamate, istanze o sessioni simultanee per impedire l'uso eccessivo di risorse.</span><span class="sxs-lookup"><span data-stu-id="556b0-129">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span>  
  
 <span data-ttu-id="556b0-130">Viene scritta una traccia ogni volta che viene raggiunto il valore di attributi.</span><span class="sxs-lookup"><span data-stu-id="556b0-130">A trace is written every time the value of attributes is reached.</span></span> <span data-ttu-id="556b0-131">La prima traccia viene scritta come un avviso.</span><span class="sxs-lookup"><span data-stu-id="556b0-131">The first trace is written as a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="556b0-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="556b0-132">Example</span></span>  
 <span data-ttu-id="556b0-133">Nell'esempio di configurazione seguente viene specificato che il servizio limita il numero massimo di chiamate simultanee a 2 e il numero massimo di istanze simultanee a 10.</span><span class="sxs-lookup"><span data-stu-id="556b0-133">The following configuration example specifies that the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span> <span data-ttu-id="556b0-134">Per un esempio dettagliato dell'esecuzione di questo esempio, vedere [limitazione delle richieste](../../../wcf/samples/throttling.md).</span><span class="sxs-lookup"><span data-stu-id="556b0-134">For a detailed example of running this example, see [Throttling](../../../wcf/samples/throttling.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="556b0-135">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="556b0-135">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [<span data-ttu-id="556b0-136">Uso di ServiceThrottlingBehavior per controllare le prestazioni dei servizi WCF</span><span class="sxs-lookup"><span data-stu-id="556b0-136">Using ServiceThrottlingBehavior to Control WCF Service Performance</span></span>](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
