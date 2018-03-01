---
title: Contatori delle prestazioni di WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance counters [WCF]
ms.assetid: f559b2bd-ed83-4988-97a1-e88f06646609
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: be4ffac8444f6365dacb2b20db6abbb6792c2239
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-performance-counters"></a><span data-ttu-id="59aae-102">Contatori delle prestazioni di WCF</span><span class="sxs-lookup"><span data-stu-id="59aae-102">WCF Performance Counters</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="59aae-103"> include un vasto set di contatori delle prestazioni che consentono di misurare le prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="59aae-103"> includes a large set of performance counters to help you gauge your application's performance.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="59aae-104">Attivazione dei contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="59aae-104">Enabling Performance Counters</span></span>  
 <span data-ttu-id="59aae-105">È possibile attivare i contatori delle prestazioni per un servizio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] tramite il file di configurazione app.config del servizio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="59aae-105">You can enable performance counters for a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service through the app.config configuration file of the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service as follows:</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="59aae-106">L'attributo `performanceCounters` può essere impostato per attivare un tipo specifico di contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="59aae-106">The `performanceCounters` attribute can be set to enable a specific type of performance counters.</span></span> <span data-ttu-id="59aae-107">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="59aae-107">Valid values are</span></span>  
  
-   <span data-ttu-id="59aae-108">All: vengono attivati tutti i contatori della categoria (ServiceModelService, ServiceModelEndpoint e ServiceModelOperation).</span><span class="sxs-lookup"><span data-stu-id="59aae-108">All: All category counters (ServiceModelService, ServiceModelEndpoint and ServiceModelOperation) are enabled.</span></span>  
  
-   <span data-ttu-id="59aae-109">ServiceOnly: vengono attivati soltanto i contatori della categoria ServiceModelService.</span><span class="sxs-lookup"><span data-stu-id="59aae-109">ServiceOnly: Only ServiceModelService category counters are enabled.</span></span> <span data-ttu-id="59aae-110">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="59aae-110">This is the default value.</span></span>  
  
-   <span data-ttu-id="59aae-111">Off: vengono disattivati i contatori delle prestazioni della categoria ServiceModel\*.</span><span class="sxs-lookup"><span data-stu-id="59aae-111">Off: ServiceModel\* performance counters are disabled.</span></span>  
  
 <span data-ttu-id="59aae-112">Se si desidera abilitare contatori delle prestazioni per tutte le applicazioni [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], è possibile memorizzare le impostazioni di configurazione nel file Machine.config.</span><span class="sxs-lookup"><span data-stu-id="59aae-112">If you want to enable performance counters for all [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] applications, you can place the configuration settings in the Machine.config file.</span></span>  <span data-ttu-id="59aae-113">Vedere il **l'aumento delle dimensioni della memoria per i contatori delle prestazioni** sezione riportata di seguito per ulteriori informazioni sulla configurazione di memoria sufficiente per i contatori delle prestazioni nel computer.</span><span class="sxs-lookup"><span data-stu-id="59aae-113">Please see the **Increasing Memory Size for Performance Counters** section below for more information on configuring sufficient memory for performance counters on your machine.</span></span>  
  
 <span data-ttu-id="59aae-114">Se si usano punti di estensibilità di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], ad esempio invoker di operazioni personalizzati, è necessario creare anche i propri contatori delle prestazioni,</span><span class="sxs-lookup"><span data-stu-id="59aae-114">If you use [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] extensibility points such as custom operation invokers, you should also emit your own performance counters.</span></span> <span data-ttu-id="59aae-115">poiché se si implementa un punto di questo tipo, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] potrebbe non consentire più la creazione dei dati dei contatori delle prestazioni standard nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="59aae-115">This is because if you implement an extensibility point, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] may no longer emit the standard performance counter data in the default path.</span></span> <span data-ttu-id="59aae-116">Se non si implementa il supporto manuale dei contatori delle prestazioni, è possibile che i dati previsti di questi ultimi non vengano visualizzati.</span><span class="sxs-lookup"><span data-stu-id="59aae-116">If you do not implement manual performance counter support, you may not see the performance counter data you expect.</span></span>  
  
 <span data-ttu-id="59aae-117">È inoltre possibile abilitare contatori delle prestazioni nel codice nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="59aae-117">You can also enable performance counters in your code as follows,</span></span>  
  
```  
using System.Configuration;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Diagnostics;  
Configuration config = ConfigurationManager.OpenExeConfiguration(  
    ConfigurationUserLevel.None);  
ServiceModelSectionGroup sg = ServiceModelSectionGroup.GetSectionGroup(config);  
sg.Diagnostic.PerformanceCounters = PerformanceCounterScope.All;  
config.Save();  
```  
  
## <a name="viewing-performance-data"></a><span data-ttu-id="59aae-118">Visualizzazione dei dati relativi alle prestazioni</span><span class="sxs-lookup"><span data-stu-id="59aae-118">Viewing Performance Data</span></span>  
 <span data-ttu-id="59aae-119">Per visualizzare i dati acquisiti dai contatori delle prestazioni è possibile usare lo strumento Performance Monitor (Perfmon.exe) di Windows.</span><span class="sxs-lookup"><span data-stu-id="59aae-119">To view data captured by the performance counters, you can use the Performance Monitor (Perfmon.exe) that comes with Windows.</span></span> <span data-ttu-id="59aae-120">È possibile avviare questo strumento, passare a **avviare**, fare clic su **eseguire** e tipo `perfmon.exe` nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="59aae-120">You can launch this tool by going to **Start**, and click **Run** and type `perfmon.exe` in the dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59aae-121">Le istanze del contatore delle prestazioni possono essere rilasciate prima che gli ultimi messaggi siano stati elaborati dal Dispatcher dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="59aae-121">Performance counter instances may be released before the last messages have been processed by the endpoint dispatcher.</span></span> <span data-ttu-id="59aae-122">In questo caso è possibile che i dati relativi alle prestazioni non vengano acquisiti per alcuni messaggi.</span><span class="sxs-lookup"><span data-stu-id="59aae-122">This can result in performance data not being captured for a few messages.</span></span>  
  
## <a name="increasing-memory-size-for-performance-counters"></a><span data-ttu-id="59aae-123">Aumento della dimensione della memoria per i contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="59aae-123">Increasing Memory Size for Performance Counters</span></span>  
 <span data-ttu-id="59aae-124">Per le categorie di contatori delle prestazioni [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] usa una memoria condivisa separata.</span><span class="sxs-lookup"><span data-stu-id="59aae-124">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] uses separate shared memory for its performance counter categories.</span></span>  
  
 <span data-ttu-id="59aae-125">Per impostazione predefinita, la memoria condivisa separata è impostata su un quarto della dimensione della memoria globale dei contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="59aae-125">By default, separate shared memory is set to a quarter the size of global performance counter memory.</span></span> <span data-ttu-id="59aae-126">La dimensione della memoria globale predefinita dei contatori delle prestazioni è di 524.288 byte.</span><span class="sxs-lookup"><span data-stu-id="59aae-126">The default global performance counter memory is 524,288 bytes.</span></span> <span data-ttu-id="59aae-127">Le tre categorie di contatori delle prestazioni di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] hanno quindi una dimensione predefinita di circa 128 KB ognuna.</span><span class="sxs-lookup"><span data-stu-id="59aae-127">Therefore, the three [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] performance counter categories have a default size of approximately 128KB each.</span></span> <span data-ttu-id="59aae-128">A seconda delle caratteristiche di runtime delle applicazioni [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] disponibili in un computer, la memoria dei contatori delle prestazioni può esaurirsi.</span><span class="sxs-lookup"><span data-stu-id="59aae-128">Depending upon the runtime characteristics of the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] applications on a machine, performance counter memory may be exhausted.</span></span> <span data-ttu-id="59aae-129">Quando si verifica questa condizione, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] scrive un errore nel registro eventi dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="59aae-129">When this happens, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] writes an error to the application event log.</span></span> <span data-ttu-id="59aae-130">Il contenuto dell'errore indica che un contatore delle prestazioni non è stato caricato e la voce contiene l'eccezione "System.InvalidOperationException: Memoria insufficiente per la visualizzazione del file dei contatori personalizzati".</span><span class="sxs-lookup"><span data-stu-id="59aae-130">The content of the error states that a performance counter was not loaded, and the entry contains the exception "System.InvalidOperationException: Custom counters file view is out of memory."</span></span> <span data-ttu-id="59aae-131">Se è attivata l'analisi al livello dell'errore, l'errore viene anche analizzato.</span><span class="sxs-lookup"><span data-stu-id="59aae-131">If tracing is enabled at the error level, this failure is also traced.</span></span> <span data-ttu-id="59aae-132">Quando la memoria dei contatori delle prestazioni è esaurita, l'esecuzione di applicazioni [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] con i contatori delle prestazioni attivati può comportare una riduzione del livello delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="59aae-132">If performance counter memory is exhausted, continuing to run your [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] applications with performance counters enabled could result in performance degradation.</span></span> <span data-ttu-id="59aae-133">In questo caso l'amministratore del computer dovrà configurare il computer per l'allocazione di memoria sufficiente a supportare il numero massimo di contatori delle prestazioni che possono essere presenti in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="59aae-133">If you are an administrator of the machine, you should configure it to allocate enough memory to support the maximum number of performance counters that can exist at any time.</span></span>  
  
 <span data-ttu-id="59aae-134">È possibile modificare la quantità di memoria del contatore delle prestazioni per le categorie di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="59aae-134">You can change the amount of performance counter memory for [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] categories in the registry.</span></span> <span data-ttu-id="59aae-135">A tale scopo, è necessario aggiungere un nuovo valore DWORD denominato `FileMappingSize` ai tre percorsi specificati di seguito e impostarlo sul valore desiderato espresso in byte.</span><span class="sxs-lookup"><span data-stu-id="59aae-135">To do so, you need to add a new DWORD value named `FileMappingSize` to the three following locations, and set it to the desired value in bytes.</span></span> <span data-ttu-id="59aae-136">Riavviare il computer per rendere effettive le modifiche.</span><span class="sxs-lookup"><span data-stu-id="59aae-136">Reboot your machine so that these changes are taken into effect.</span></span>  
  
-   <span data-ttu-id="59aae-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="59aae-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span></span>  
  
-   <span data-ttu-id="59aae-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="59aae-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span></span>  
  
-   <span data-ttu-id="59aae-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="59aae-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span></span>  
  
 <span data-ttu-id="59aae-140">Quando numerosi oggetti (ad esempio, ServiceHost) vengono eliminati ma rimangono in attesa di essere sottoposti all'operazione di Garbage Collection, il contatore delle prestazioni `PrivateBytes` registra un valore insolitamente elevato.</span><span class="sxs-lookup"><span data-stu-id="59aae-140">When a large number of objects (for example, ServiceHost) are disposed of but waiting to be garbage-collected, the `PrivateBytes` performance counter will register an unusually high number.</span></span> <span data-ttu-id="59aae-141">Per risolvere questo problema è possibile aggiungere contatori specifici dell'applicazione o usare l'attributo `performanceCounters` per attivare soltanto i contatori a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="59aae-141">To resolve this problem, you can either add your own application-specific counters, or use the `performanceCounters` attribute to enable only service-level counters.</span></span>  
  
## <a name="types-of-performance-counters"></a><span data-ttu-id="59aae-142">Tipi di contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="59aae-142">Types of Performance Counters</span></span>  
 <span data-ttu-id="59aae-143">I contatori delle prestazioni vengono applicati a tre livelli differenti: servizio, endpoint e operazione.</span><span class="sxs-lookup"><span data-stu-id="59aae-143">Performance counters are scoped to three different levels: Service, Endpoint and Operation.</span></span>  
  
 <span data-ttu-id="59aae-144">Per recuperare il nome di un'istanza di contatore delle prestazioni è possibile usare WMI.</span><span class="sxs-lookup"><span data-stu-id="59aae-144">You can use WMI to retrieve the name of a performance counter instance.</span></span> <span data-ttu-id="59aae-145">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="59aae-145">For example,</span></span>  
  
-   <span data-ttu-id="59aae-146">Nome dell'istanza del contatore servizio può essere ottenuto tramite WMI [servizio](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) proprietà "CounterInstanceName" dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="59aae-146">Service counter instance name can be obtained through WMI [Service](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) instance's "CounterInstanceName" property.</span></span>  
  
-   <span data-ttu-id="59aae-147">Nome dell'istanza del contatore endpoint può essere ottenuto tramite WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) proprietà "CounterInstanceName" dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="59aae-147">Endpoint counter instance name can be obtained through WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) instance's "CounterInstanceName" property.</span></span>  
  
-   <span data-ttu-id="59aae-148">Nome dell'istanza del contatore operazione può essere ottenuto tramite WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) metodo "GetOperationCounterInstanceName" dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="59aae-148">Operation counter instance name can be obtained through WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) instance's "GetOperationCounterInstanceName" method.</span></span>  
  
 <span data-ttu-id="59aae-149">Per ulteriori informazioni su WMI, vedere [tramite Strumentazione gestione Windows per la diagnostica](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span><span class="sxs-lookup"><span data-stu-id="59aae-149">For more information on WMI, see [Using Windows Management Instrumentation for Diagnostics](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span></span>  
  
### <a name="service-performance-counters"></a><span data-ttu-id="59aae-150">Contatori delle prestazioni a livello di servizio</span><span class="sxs-lookup"><span data-stu-id="59aae-150">Service performance counters</span></span>  
 <span data-ttu-id="59aae-151">I contatori delle prestazioni del servizio misurano il comportamento del servizio nel suo insieme e possono essere usati per diagnosticare le prestazioni dell'intero servizio.</span><span class="sxs-lookup"><span data-stu-id="59aae-151">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="59aae-152">Sono reperibili nell'oggetto prestazione `ServiceModelService 4.0.0.0` in caso di visualizzazione con Performance Monitor.</span><span class="sxs-lookup"><span data-stu-id="59aae-152">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="59aae-153">Le istanze vengono denominate usando il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="59aae-153">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
 <span data-ttu-id="59aae-154">Un contatore nell'ambito di un servizio viene aggregato dal contatore in una raccolta di endpoint.</span><span class="sxs-lookup"><span data-stu-id="59aae-154">A counter in a service scope is aggregated from counter in a collection of endpoints.</span></span>  
  
 <span data-ttu-id="59aae-155">I contatori delle prestazioni per la creazione dell'istanza di servizio vengono incrementati alla creazione di un nuovo contesto InstanceContext.</span><span class="sxs-lookup"><span data-stu-id="59aae-155">Performance counters for service instance creation are incremented when a new InstanceContext is created.</span></span> <span data-ttu-id="59aae-156">Si noti che un nuovo contesto InstanceContext viene creato anche quando si riceve un messaggio di non attivazione (con un servizio esistente) o quando vi è una connessione a un'istanza da una determinata sessione, si termina la sessione e ci si riconnette da un'altra sessione.</span><span class="sxs-lookup"><span data-stu-id="59aae-156">Note that a new InstanceContext is created even when you receive a non-activating message (with an existing service), or when you connect to an instance from one session, end the session, and then reconnect from another session.</span></span>  
  
### <a name="endpoint-performance-counters"></a><span data-ttu-id="59aae-157">Contatori delle prestazioni a livello di endpoint</span><span class="sxs-lookup"><span data-stu-id="59aae-157">Endpoint performance counters</span></span>  
 <span data-ttu-id="59aae-158">I contatori delle prestazioni a livello di endpoint consentono di analizzare i dati che riflettono la modalità di accettazione dei messaggi da parte di un endpoint.</span><span class="sxs-lookup"><span data-stu-id="59aae-158">Endpoint performance counters enable you to look at data reflecting how an endpoint is accepting messages.</span></span> <span data-ttu-id="59aae-159">Sono reperibili nell'oggetto prestazione `ServiceModelEndpoint 4.0.0.0` in caso di visualizzazione con Performance Monitor.</span><span class="sxs-lookup"><span data-stu-id="59aae-159">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing using the Performance Monitor.</span></span> <span data-ttu-id="59aae-160">Le istanze vengono denominate usando il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="59aae-160">The instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="59aae-161">I dati sono simili a quelli raccolti per le singole operazioni, ma vengono aggregati soltanto nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="59aae-161">The data is similar to what is collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
 <span data-ttu-id="59aae-162">Un contatore nell'ambito di un endpoint viene aggregato dai contatori in una raccolta di operazioni.</span><span class="sxs-lookup"><span data-stu-id="59aae-162">A counter in an endpoint scope is aggregated from counters in a collection of operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59aae-163">Se due endpoint hanno nomi e indirizzi di contratto identici, vengono mappati alla stessa istanza di contatore.</span><span class="sxs-lookup"><span data-stu-id="59aae-163">If two endpoints have identical contract names and addresses, they are mapped to the same counter instance.</span></span>  
  
### <a name="operation-performance-counters"></a><span data-ttu-id="59aae-164">Contatori delle prestazioni a livello di operazione</span><span class="sxs-lookup"><span data-stu-id="59aae-164">Operation performance counters</span></span>  
 <span data-ttu-id="59aae-165">I contatori delle prestazioni a livello di operazione sono reperibili nell'oggetto prestazione `ServiceModelOperation 4.0.0.0` in caso di visualizzazione con Performance Monitor.</span><span class="sxs-lookup"><span data-stu-id="59aae-165">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="59aae-166">Ogni operazione ha un'istanza singola.</span><span class="sxs-lookup"><span data-stu-id="59aae-166">Each operation has an individual instance.</span></span> <span data-ttu-id="59aae-167">Ovvero, se un determinato contratto ha 10 operazioni, ad esso sono associate 10 istanze di contatore per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="59aae-167">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="59aae-168">Le istanze di oggetti vengono denominate usando il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="59aae-168">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="59aae-169">Questo contatore consente di misurare come viene usata la chiamata e le prestazioni dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="59aae-169">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
 <span data-ttu-id="59aae-170">Quando i contatori sono visibili su più ambiti, i dati raccolti da un ambito di livello superiore vengono aggregati ai dati relativi ad ambiti di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="59aae-170">When counters are visible at multiple scopes, data gathered from a higher scope are aggregated with data from lower scopes.</span></span> <span data-ttu-id="59aae-171">Ad esempio, il contatore `Calls` in un endpoint rappresenta la somma di tutte le chiamate a operazioni all'interno dell'endpoint; mentre il contatore `Calls` in un servizio rappresenta la somma di tutte le chiamate a tutti gli endpoint all'interno del servizio.</span><span class="sxs-lookup"><span data-stu-id="59aae-171">For example, `Calls` at an endpoint represents the sum of all operation calls within the endpoint; `Calls` at a service represents the sum of all calls to all endpoints within the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59aae-172">Se in un contratto sono presenti nomi di operazione duplicati, per entrambe le operazioni è possibile ottenere soltanto le istanze di un solo contatore.</span><span class="sxs-lookup"><span data-stu-id="59aae-172">If you have duplicate operation names on a contract, you only get one counter instances for both operations.</span></span>  
  
## <a name="programming-the-wcf-performance-counters"></a><span data-ttu-id="59aae-173">Programmazione dei contatori delle prestazioni di WCF</span><span class="sxs-lookup"><span data-stu-id="59aae-173">Programming the WCF Performance Counters</span></span>  
 <span data-ttu-id="59aae-174">Nella cartella di installazione dell'SDK sono presenti diversi file che consentono di accedere ai contatori delle prestazioni di [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="59aae-174">Several files are installed in the SDK install folder so that you can access the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] performance counters programmatically.</span></span> <span data-ttu-id="59aae-175">Di seguito è riportato l'elenco di questi file.</span><span class="sxs-lookup"><span data-stu-id="59aae-175">These files are listed as follows.</span></span>  
  
-   <span data-ttu-id="59aae-176">_ServiceModelEndpointPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="59aae-176">_ServiceModelEndpointPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="59aae-177">_ServiceModelOperationPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="59aae-177">_ServiceModelOperationPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="59aae-178">_ServiceModelServicePerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="59aae-178">_ServiceModelServicePerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="59aae-179">_SMSvcHostPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="59aae-179">_SMSvcHostPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="59aae-180">_TransactionBridgePerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="59aae-180">_TransactionBridgePerfCounters.vrg</span></span>  
  
 <span data-ttu-id="59aae-181">Per ulteriori informazioni sull'accesso ai contatori a livello di codice, vedere [architettura di programmazione del contatore delle prestazioni](http://go.microsoft.com/fwlink/?LinkId=95179).</span><span class="sxs-lookup"><span data-stu-id="59aae-181">For more information on how to access the counters programmatically, see [Performance Counter Programming Architecture](http://go.microsoft.com/fwlink/?LinkId=95179).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59aae-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59aae-182">See Also</span></span>  
 [<span data-ttu-id="59aae-183">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="59aae-183">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
