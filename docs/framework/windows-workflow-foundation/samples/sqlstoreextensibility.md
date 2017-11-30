---
title: SQLStoreExtensibility
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5da1b5a3-f144-41ba-b9c4-02818b28b15d
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 111e7aa4164d9fc811ebe3f5efb196df77d1ded0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sqlstoreextensibility"></a><span data-ttu-id="cbef4-102">SQLStoreExtensibility</span><span class="sxs-lookup"><span data-stu-id="cbef4-102">SQLStoreExtensibility</span></span>
<span data-ttu-id="cbef4-103">In questo esempio vengono illustrati l'uso e la configurazione delle proprietà promosse nell'archivio di istanze del flusso di lavoro SQL.</span><span class="sxs-lookup"><span data-stu-id="cbef4-103">This sample demonstrates the use and configuration of promoted properties in the SQL workflow instance store.</span></span> <span data-ttu-id="cbef4-104">L'archivio di istanze del flusso di lavoro SQL è un'implementazione basata su SQL di un archivio di istanze.</span><span class="sxs-lookup"><span data-stu-id="cbef4-104">The SQL workflow instance store is a SQL-based implementation of an instance store.</span></span> <span data-ttu-id="cbef4-105">Consente a un'istanza di salvare il relativo stato e caricarlo da e verso un database SQL Server o SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="cbef4-105">It allows an instance to save its state and load its state to and from a SQL Server or SQL Server Express database.</span></span> <span data-ttu-id="cbef4-106">La funzionalità di estensibilità dell'archivio consente all'utente di definire le proprietà che vengono archiviate nell'archivio di istanze.</span><span class="sxs-lookup"><span data-stu-id="cbef4-106">The store extensibility feature allows the user to define properties that are stored in the instance store.</span></span> <span data-ttu-id="cbef4-107">Queste proprietà vengono riportate in una visualizzazione di proprietà promosse che consente all'utente di eseguire query relative alle stesse.</span><span class="sxs-lookup"><span data-stu-id="cbef4-107">These properties are displayed in a promoted properties view that allows the user to query for them.</span></span>  
  
 <span data-ttu-id="cbef4-108">Questo esempio è costituito da un flusso di lavoro che implementa un servizio di conteggio.</span><span class="sxs-lookup"><span data-stu-id="cbef4-108">This sample consists of a workflow that implements a counting service.</span></span> <span data-ttu-id="cbef4-109">Una volta richiamato il metodo di avvio del servizio, il servizio conta da 0 a 29.</span><span class="sxs-lookup"><span data-stu-id="cbef4-109">Once the service's start method is invoked, the service counts from 0 to 29.</span></span> <span data-ttu-id="cbef4-110">Il contatore viene incrementato una volta ogni 2 secondi.</span><span class="sxs-lookup"><span data-stu-id="cbef4-110">The counter is incremented once every 2 seconds.</span></span> <span data-ttu-id="cbef4-111">Dopo ogni conteggio, il flusso di lavoro viene salvato in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="cbef4-111">After each count, the workflow persists.</span></span> <span data-ttu-id="cbef4-112">Il valore del contatore corrente viene archiviato nell'archivio di istanze come una proprietà promossa.</span><span class="sxs-lookup"><span data-stu-id="cbef4-112">The current counter value is stored in the instance store as a promoted property.</span></span>  
  
 <span data-ttu-id="cbef4-113">Il flusso di lavoro del conteggio è indipendente in un host del servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cbef4-113">The Counting Workflow is self-hosted by a Workflow Service Host.</span></span> <span data-ttu-id="cbef4-114">Il metodo `Main` del programma esegue le azioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="cbef4-114">The program's `Main` method performs the following actions:</span></span>  
  
-   <span data-ttu-id="cbef4-115">Crea un'istanza dell'host del servizio flusso di lavoro che ospita il flusso di lavoro del conteggio e definisce gli endpoint in cui quest'ultimo può essere raggiunto.</span><span class="sxs-lookup"><span data-stu-id="cbef4-115">Creates an instance of the Workflow Service Host that hosts the Counting Workflow and defines the endpoints under which the Counting Workflow can be reached.</span></span>  
  
-   <span data-ttu-id="cbef4-116">Definisce un comportamento dell'archivio di istanze del flusso di lavoro SQL usato per configurare l'archivio di istanze del flusso di lavoro SQL.</span><span class="sxs-lookup"><span data-stu-id="cbef4-116">Defines a SQL workflow instance store behavior, which is used to configure the SQL workflow instance store.</span></span> <span data-ttu-id="cbef4-117">In base alle istruzioni l'archivio considera `CountStatus` come proprietà promossa.</span><span class="sxs-lookup"><span data-stu-id="cbef4-117">The store is instructed to treat `CountStatus` as a promoted property.</span></span>  
  
-   <span data-ttu-id="cbef4-118">Crea un client che chiama il metodo di avvio del flusso di lavoro del conteggio.</span><span class="sxs-lookup"><span data-stu-id="cbef4-118">Creates a client that calls the start method of the counting workflow.</span></span>  
  
 <span data-ttu-id="cbef4-119">Dopo l'avvio del programma, il contatore avvia automaticamente il conteggio.</span><span class="sxs-lookup"><span data-stu-id="cbef4-119">Once the program is started, the counter automatically starts counting.</span></span> <span data-ttu-id="cbef4-120">Notare che potrebbero essere necessari alcuni secondi per caricare l'istanza e configurare l'archivio di istanze del flusso di lavoro SQL.</span><span class="sxs-lookup"><span data-stu-id="cbef4-120">Note that it might take a few seconds to load the instance and configure the SQL workflow instance store.</span></span>  
  
 <span data-ttu-id="cbef4-121">Per promuovere il valore del contatore come una proprietà personalizzata, è necessario effettuare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cbef4-121">To promote the counter value as a custom property, the following steps must be taken:</span></span>  
  
1.  <span data-ttu-id="cbef4-122">La classe `CounterStatus` definisce un'estensione dell'istanza di tipo <xref:System.Activities.Persistence.PersistenceParticipant>, che è usata dalle attività per fornire le variabili di stato.</span><span class="sxs-lookup"><span data-stu-id="cbef4-122">The class `CounterStatus` defines an instance extension of type <xref:System.Activities.Persistence.PersistenceParticipant>, which is used by activities to supply the state variables.</span></span> <span data-ttu-id="cbef4-123">`Count` è definito come valore di sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="cbef4-123">`Count` is defined as a write-only value.</span></span> <span data-ttu-id="cbef4-124">Quando un'istanza del flusso di lavoro raggiunge un punto di persistenza, l'estensione dell'istanza salva la proprietà `Count` nella raccolta dati di persistenza.</span><span class="sxs-lookup"><span data-stu-id="cbef4-124">When a workflow instance comes to a persistence point, the instance extension saves the `Count` property into the persistence data collection.</span></span>  
  
2.  <span data-ttu-id="cbef4-125">Quando viene creato l'archivio di istanze, viene definita la nuova proprietà `CountStatus` tramite il metodo `store.Promote()`.</span><span class="sxs-lookup"><span data-stu-id="cbef4-125">When creating the instance store, a new property, `CountStatus`, is defined through the `store.Promote()` method.</span></span>  
  
3.  <span data-ttu-id="cbef4-126">L'attività `SaveCounter` del flusso di lavoro assegna il valore del contatore corrente al campo di stato `Count`.</span><span class="sxs-lookup"><span data-stu-id="cbef4-126">The workflow's `SaveCounter` activity assigns the current counter value to the `Count` status field.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="cbef4-127">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="cbef4-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="cbef4-128">Creare il database dell'archivio di istanze.</span><span class="sxs-lookup"><span data-stu-id="cbef4-128">Create the instance store database.</span></span>  
  
    1.  <span data-ttu-id="cbef4-129">Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbef4-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="cbef4-130">Passare alla directory di esempio (\WF\Basic\Persistence\SqlStoreExtensibility\CS) ed eseguire CreateInstanceStore.cmd al prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbef4-130">Navigate to the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility\CS) and run CreateInstanceStore.cmd in the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
        > [!WARNING]
        >  <span data-ttu-id="cbef4-131">Lo script CreateInstanceStore.cmd tenta di creare il database nell'istanza predefinita di SQL Server 2008 Express.</span><span class="sxs-lookup"><span data-stu-id="cbef4-131">The CreateInstanceStore.cmd script attempts to create the database on the default instance of SQL Server 2008 Express.</span></span> <span data-ttu-id="cbef4-132">Se si desidera installare il database in un'istanza diversa, modificare lo script.</span><span class="sxs-lookup"><span data-stu-id="cbef4-132">If you want to install the database on a different instance, modify the script to do so.</span></span>  
  
2.  <span data-ttu-id="cbef4-133">Aprire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], caricare la soluzione SqlStoreExtensibility.sln e compilarla premendo CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="cbef4-133">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and load the SqlStoreExtensibility.sln solution and build it by pressing CTRL+SHIFT+B.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="cbef4-134">Se il database è stato installato in un'istanza non predefinita di SQL Server, aggiornare la stringa di connessione nel codice prima di compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="cbef4-134">If you installed the database on a non-default instance of SQL Server, update the connection string in the code prior to building the solution.</span></span>  
  
3.  <span data-ttu-id="cbef4-135">Eseguire l'esempio con privilegi di amministratore passando alla directory bin del progetto (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], destro del mouse su SqlStoreExtensibility.exe e scegliendo **runas Amministratore**.</span><span class="sxs-lookup"><span data-stu-id="cbef4-135">Run the sample with administrator privileges by navigating to the project’s bin directory (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], right-clicking SqlStoreExtensibility.exe and selecting **Run as Administrator**.</span></span>  
  
### <a name="to-verify-the-sample-is-working-correctly"></a><span data-ttu-id="cbef4-136">Per verificare che l'esempio funzioni correttamente</span><span class="sxs-lookup"><span data-stu-id="cbef4-136">To verify the sample is working correctly</span></span>  
  
1.  <span data-ttu-id="cbef4-137">Utilizzare SQL Server Management Studio per visualizzare il contenuto della tabella istanza selezionando **database**, **InstanceStore**e quindi  **System.ServiceModel.Activities.DurableInstancing.InstanceTable** in Esplora oggetti, fare doppio clic su **System.ServiceModel.Activities.DurableInstancing.InstanceTable** e selezionare  **Selezionare le prime 1000 righe**.</span><span class="sxs-lookup"><span data-stu-id="cbef4-137">Use SQL Server Management Studio to view the contents of the instance table by selecting **Databases**, **InstanceStore**, and then **System.ServiceModel.Activities.DurableInstancing.InstanceTable** in the Object Explorer, right-click **System.ServiceModel.Activities.DurableInstancing.InstanceTable** and select **Select Top 1000 Rows**.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="cbef4-138">SQL Server Management Studio, vedere [Introduzione a SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645)</span><span class="sxs-lookup"><span data-stu-id="cbef4-138"> SQL Server Management Studio, see [Introducing SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645)</span></span>  
  
2.  <span data-ttu-id="cbef4-139">Osservare le istanze del flusso di lavoro elencate.</span><span class="sxs-lookup"><span data-stu-id="cbef4-139">Observe the workflow instances listed.</span></span>  
  
3.  <span data-ttu-id="cbef4-140">A un prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] eseguire lo script QueryInstanceStore.cmd che si trova nella directory di esempio (\WF\Basic\Persistence\SqlStoreExtensibility) .</span><span class="sxs-lookup"><span data-stu-id="cbef4-140">In a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, run the QueryInstanceStore.cmd script located in the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility).</span></span>  
  
4.  <span data-ttu-id="cbef4-141">Osservare il valore del contatore visualizzato sotto **CountStatus**.</span><span class="sxs-lookup"><span data-stu-id="cbef4-141">Observe the counter value displayed under **CountStatus**.</span></span>  
  
5.  <span data-ttu-id="cbef4-142">Eseguire lo script alcune volte per visualizzare il **CountStats** valore modifica.</span><span class="sxs-lookup"><span data-stu-id="cbef4-142">Run the script a few times to see the **CountStats** value change.</span></span>  
  
6.  <span data-ttu-id="cbef4-143">Premere INVIO per terminare l'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cbef4-143">Press ENTER to terminate the workflow application.</span></span>  
  
### <a name="to-uninstall-the-sample"></a><span data-ttu-id="cbef4-144">Per disinstallare l'esempio</span><span class="sxs-lookup"><span data-stu-id="cbef4-144">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="cbef4-145">Rimuovere il database dell'archivio di istanze eseguendo lo script RemoveInstanceStore.cmd che si trova nella directory di esempio (\WF\Basic\Persistence\SqlStoreExtensibility).</span><span class="sxs-lookup"><span data-stu-id="cbef4-145">Remove the instance store database by running the RemoveInstanceStore.cmd script located in the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cbef4-146">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="cbef4-146">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cbef4-147">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="cbef4-147">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cbef4-148">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbef4-148">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cbef4-149">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="cbef4-149">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\SQLStoreExtensibility`  
  
## <a name="see-also"></a><span data-ttu-id="cbef4-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbef4-150">See Also</span></span>  
 [<span data-ttu-id="cbef4-151">Persistenza del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cbef4-151">Workflow Persistence</span></span>](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [<span data-ttu-id="cbef4-152">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="cbef4-152">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="cbef4-153">Hosting di AppFabric ed esempi di persistenza</span><span class="sxs-lookup"><span data-stu-id="cbef4-153">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
