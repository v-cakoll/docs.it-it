---
title: Modello di configurazione gerarchica
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28dcc698-226c-4b77-9e51-8bf45a36216c
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9b3b170e3e6453c14f557786572c54ac6f67c3db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="hierarchical-configuration-model"></a><span data-ttu-id="aff91-102">Modello di configurazione gerarchica</span><span class="sxs-lookup"><span data-stu-id="aff91-102">Hierarchical Configuration Model</span></span>
<span data-ttu-id="aff91-103">In questo esempio viene descritto come implementare una gerarchia di file di configurazione per i servizi.</span><span class="sxs-lookup"><span data-stu-id="aff91-103">This sample demonstrates how to implement a hierarchy of configuration files for services.</span></span> <span data-ttu-id="aff91-104">Viene inoltre descritto come associazioni, comportamenti del servizio e comportamenti dell'endpoint vengono ereditati dai livelli superiori nella gerarchia.</span><span class="sxs-lookup"><span data-stu-id="aff91-104">It also shows how bindings, service behaviors, and endpoint behaviors are inherited from higher levels in the hierarchy.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="aff91-105">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="aff91-105">Sample details</span></span>  
 <span data-ttu-id="aff91-106">Una delle funzionalità sviluppate per [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] è il miglioramento nel modello di configurazione gerarchico.</span><span class="sxs-lookup"><span data-stu-id="aff91-106">One of the features developed for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] is the improvement in the hierarchical configuration model.</span></span> <span data-ttu-id="aff91-107">Un esempio di un modello di configurazione gerarchico può essere quello definito da Machine.config -> Rootweb.config -> Web.config. In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], le associazioni e i comportamenti definiti nei livelli superiori della gerarchia di configurazione vengono aggiunti ai servizi senza configurazione esplicita.</span><span class="sxs-lookup"><span data-stu-id="aff91-107">An example of a hierarchical configuration model would be the one defined by Machine.config -> Rootweb.config -> Web.config. In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], those bindings and behaviors that are defined in upper levels in the configuration hierarchy are added to your services with no explicit configuration.</span></span> <span data-ttu-id="aff91-108">In questo esempio viene illustrato come è possibile semplificare la configurazione del servizio basandosi sugli elementi di configurazione definiti a livello di applicazione o computer.</span><span class="sxs-lookup"><span data-stu-id="aff91-108">This sample shows how it is possible to simplify your service configuration by relying on configuration elements defined at the computer or the application level.</span></span>  
  
 <span data-ttu-id="aff91-109">Questo esempio è costituito da nove servizi, definiti in tre livelli di gerarchia.</span><span class="sxs-lookup"><span data-stu-id="aff91-109">This sample consists of nine services, defined in three levels of hierarchy.</span></span> <span data-ttu-id="aff91-110">`Service1` è alla radice.</span><span class="sxs-lookup"><span data-stu-id="aff91-110">`Service1` is at the root.</span></span> <span data-ttu-id="aff91-111">`Service2` e `Service3` ereditano gli elementi predefiniti da `Service1`.</span><span class="sxs-lookup"><span data-stu-id="aff91-111">`Service2` and `Service3` inherit the default elements from `Service1`.</span></span> <span data-ttu-id="aff91-112">`Service4`, `Service5`, `Service6` e `Service7` sono definiti a un terzo livello della gerarchia, ereditando gli elementi predefiniti da `Service3`.</span><span class="sxs-lookup"><span data-stu-id="aff91-112">`Service4`, `Service5`, `Service6` and `Service7` are defined at a third level of the hierarchy, inheriting the default elements from `Service3`.</span></span> <span data-ttu-id="aff91-113">Infine, `Service10` e `Service11` sono a un quarto livello della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="aff91-113">Finally `Service10` and `Service11` are at a fourth level of the hierarchy.</span></span>  
  
 <span data-ttu-id="aff91-114">Tutti i servizi implementano il contratto `IDesc`.</span><span class="sxs-lookup"><span data-stu-id="aff91-114">All the services implement the `IDesc` contract.</span></span> <span data-ttu-id="aff91-115">Gli elementi seguenti sono la definizione dell'interfaccia `IDesc`, che mostra i metodi esposti in questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="aff91-115">The following is the definition of the `IDesc` interface that shows the methods exposed in this interface.</span></span> <span data-ttu-id="aff91-116">L'interfaccia `IDesc` è definita in Service1.cs.</span><span class="sxs-lookup"><span data-stu-id="aff91-116">The `IDesc` interface is defined in Service1.cs.</span></span>  
  
```  
// Define a service contract  
[ServiceContract(Namespace="http://Microsoft.Samples.ConfigHierarchicalModel")]  
public interface IDesc  
{  
    [OperationContract]  
    List<string> ListEndpoints();  
    [OperationContract]  
    List<string> ListServiceBehaviors();  
    [OperationContract]  
    List<string> ListEndpointBehaviors();  
}  
```  
  
 <span data-ttu-id="aff91-117">L'implementazione di tali metodi da parte dei servizi è semplice.</span><span class="sxs-lookup"><span data-stu-id="aff91-117">The implementation of these methods by the services is straightforward.</span></span> <span data-ttu-id="aff91-118">`ListEndpoints` scorre tutti gli endpoint del servizio e restituisce un elenco di tutti gli endpoint a disposizione del servizio.</span><span class="sxs-lookup"><span data-stu-id="aff91-118">`ListEndpoints` iterates through all the service endpoints and returns a list of all the endpoints that the service has.</span></span> <span data-ttu-id="aff91-119">`ListServiceBehaviors` scorre tutti i comportamenti aggiunti al servizio e restituisce l'elenco di tutti i comportamenti associati al servizio.</span><span class="sxs-lookup"><span data-stu-id="aff91-119">`ListServiceBehaviors` iterates through all the behaviors added to the service and returns the list of all the service behaviors associated with the service.</span></span> <span data-ttu-id="aff91-120">`ListEndpointBehaviors` si comporta in modo analogo a `ListServiceBehaviors`, ma restituisce l'elenco dei comportamenti degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="aff91-120">`ListEndpointBehaviors` behaves in a similar way to `ListServiceBehaviors`, but it returns the list of endpoint behaviors instead.</span></span>  
  
 <span data-ttu-id="aff91-121">L'implementazione consente al client di conoscere quanti endpoint il servizio sta esponendo e quali comportamenti del servizio e comportamenti dell'endpoint sono stati aggiunti al servizio.</span><span class="sxs-lookup"><span data-stu-id="aff91-121">This implementation allows the client to know how many endpoints the service is exposing and which service behaviors and endpoint behaviors have been added to the service.</span></span> <span data-ttu-id="aff91-122">Il client implementato come parte dell'esempio aggiunge un riferimento al servizio a tutti i servizi nella soluzione e mostra tali elementi per ognuno dei servizi.</span><span class="sxs-lookup"><span data-stu-id="aff91-122">The client that has been implemented as part of the sample adds a service reference to all the services in the solution and shows these elements for each one of the services.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="aff91-123">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="aff91-123">To use this sample</span></span>  
  
#### <a name="to-run-the-client"></a><span data-ttu-id="aff91-124">Per eseguire il client.</span><span class="sxs-lookup"><span data-stu-id="aff91-124">To run the client</span></span>  
  
1.  <span data-ttu-id="aff91-125">Utilizzando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], aprire il file ConfigHierarchicalModel.sln.</span><span class="sxs-lookup"><span data-stu-id="aff91-125">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ConfigHierarchicalModel.sln file.</span></span>  
  
2.  <span data-ttu-id="aff91-126">Se il progetto client non è già stato configurato come progetto di avvio, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="aff91-126">The client project is not already set up as the start-up project, follow these steps.</span></span>  
  
    1.  <span data-ttu-id="aff91-127">In **Esplora**, la soluzione e quindi scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aff91-127">In **Solution Explorer**, right-click the solution and then select **Properties**.</span></span>  
  
    2.  <span data-ttu-id="aff91-128">In **proprietà comuni**selezionare **progetto di avvio**, quindi fare clic su **progetto di avvio singolo**.</span><span class="sxs-lookup"><span data-stu-id="aff91-128">In **Common Properties**, select **Startup Project**, and then click **Single startup project**.</span></span>  
  
    3.  <span data-ttu-id="aff91-129">Dal **progetto di avvio singolo** elenco a discesa, selezionare **Client**.</span><span class="sxs-lookup"><span data-stu-id="aff91-129">From the **Single startup project** drop-down, select **Client**.</span></span>  
  
    4.  <span data-ttu-id="aff91-130">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="aff91-130">Click **OK** to close the dialog.</span></span>  
  
3.  <span data-ttu-id="aff91-131">Per compilare l'esempio, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="aff91-131">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="aff91-132">Premere CTRL+F5 per eseguire il client.</span><span class="sxs-lookup"><span data-stu-id="aff91-132">To run the client, press Ctrl+F5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aff91-133">Se questi passaggi non funzionano, verificare che l'ambiente sia stato configurato correttamente, usando i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="aff91-133">If these steps do not work, then make sure that your environment has been properly set up, using the following steps.</span></span>  
>   
>  1.  <span data-ttu-id="aff91-134">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="aff91-134">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
> 2.  <span data-ttu-id="aff91-135">Per compilare la soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="aff91-135">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
> 3.  <span data-ttu-id="aff91-136">Per eseguire l'esempio in uno o più configurazioni di computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="aff91-136">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aff91-137">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="aff91-137">The samples may already be installed on your computer.</span></span> <span data-ttu-id="aff91-138">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="aff91-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="aff91-139">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aff91-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="aff91-140">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="aff91-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## <a name="see-also"></a><span data-ttu-id="aff91-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aff91-141">See Also</span></span>  
 [<span data-ttu-id="aff91-142">Esempi di gestione di AppFabric</span><span class="sxs-lookup"><span data-stu-id="aff91-142">AppFabric Management Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193960)
