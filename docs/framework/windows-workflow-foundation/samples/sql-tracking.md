---
title: Rilevamento SQL
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2eeb5cf57e6efac77de4a76fe8131189273d5438
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="sql-tracking"></a><span data-ttu-id="f8538-102">Rilevamento SQL</span><span class="sxs-lookup"><span data-stu-id="f8538-102">SQL Tracking</span></span>
<span data-ttu-id="f8538-103">In questo esempio viene illustrato come scrivere un partecipante del rilevamento SQL personalizzato che scrive record di rilevamento in un database SQL.</span><span class="sxs-lookup"><span data-stu-id="f8538-103">This sample demonstrates how to write a custom SQL tracking participant, that writes tracking records to a SQL database.</span></span> <span data-ttu-id="f8538-104">Windows Workflow Foundation (WF) fornisce del flusso di lavoro di rilevamento per ottenere visibilità nell'esecuzione di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f8538-104">Windows Workflow Foundation (WF) provides workflow tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="f8538-105">Il runtime di rilevamento crea record di rilevamento del flusso di lavoro durante l'esecuzione di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="f8538-105">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="f8538-106"> flusso di lavoro di rilevamento, vedere [flusso di lavoro rilevamento e traccia](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="f8538-106"> workflow tracking, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f8538-107">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="f8538-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="f8538-108">Verificare di avere installato SQL Server 2008, SQL Server 2008 Express o una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="f8538-108">Verify you have SQL Server 2008, SQL Server 2008 Express or newer installed.</span></span> <span data-ttu-id="f8538-109">Gli script impacchettati con l'esempio presuppongono l'uso di un'istanza di SQL Express sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="f8538-109">The scripts packaged with the sample assume the use of a SQL Express instance on your local computer.</span></span> <span data-ttu-id="f8538-110">Se si dispone di un'istanza diversa, modificare gli script correlati al database prima di eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="f8538-110">If you have a different instance please modify the database-related scripts before running the sample.</span></span>  
  
2.  <span data-ttu-id="f8538-111">Creare il database di rilevamento di SQL Server eseguendo Trackingsetup.cmd nella directory degli script (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span><span class="sxs-lookup"><span data-stu-id="f8538-111">Create the SQL Server tracking database by running Trackingsetup.cmd in the scripts directory (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span></span> <span data-ttu-id="f8538-112">Verrà creato un database denominato TrackingSample.</span><span class="sxs-lookup"><span data-stu-id="f8538-112">This creates a database called TrackingSample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8538-113">Lo script crea il database nell'istanza predefinita di SQL Express.</span><span class="sxs-lookup"><span data-stu-id="f8538-113">The script creates the database on the default instance of SQL Express.</span></span> <span data-ttu-id="f8538-114">Se si desidera installarlo in un'istanza di database diversa, modificare lo script Trackingsetup.cmd.</span><span class="sxs-lookup"><span data-stu-id="f8538-114">If you want to install it on a different database instance, edit the Trackingsetup.cmd script.</span></span>  
  
3.  <span data-ttu-id="f8538-115">Aprire SqlTrackingSample.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8538-115">Open SqlTrackingSample.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
4.  <span data-ttu-id="f8538-116">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="f8538-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5.  <span data-ttu-id="f8538-117">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f8538-117">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="f8538-118">Viene aperta la finestra del browser in cui viene mostrata la visualizzazione directory per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f8538-118">The browser window opens and shows the directory listing for the application.</span></span>  
  
6.  <span data-ttu-id="f8538-119">Nel browser fare clic su StockPriceService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="f8538-119">In the browser, click StockPriceService.xamlx.</span></span>  
  
7.  <span data-ttu-id="f8538-120">Nel browser viene visualizzata la pagina StockPriceService contenente l'indirizzo WSDL del servizio locale.</span><span class="sxs-lookup"><span data-stu-id="f8538-120">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="f8538-121">Copiare questo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="f8538-121">Copy this address.</span></span>  
  
     <span data-ttu-id="f8538-122">Un esempio di indirizzo WSDL del servizio locale è http://localhost:65193/StockPriceService.xamlx?wsdl.</span><span class="sxs-lookup"><span data-stu-id="f8538-122">An example of the local service WSDL address is http://localhost:65193/StockPriceService.xamlx?wsdl.</span></span>  
  
8.  <span data-ttu-id="f8538-123">Tramite [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], eseguire il client di prova WCF (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="f8538-123">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], run the WCF test client (WcfTestClient.exe).</span></span> <span data-ttu-id="f8538-124">che si trova nella directory Microsoft Visual Studio 10.0\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="f8538-124">It is located in the Microsoft Visual Studio 10.0\Common7\IDE directory.</span></span>  
  
9. <span data-ttu-id="f8538-125">Nel client di prova WCF fare clic su di **File** dal menu **Aggiungi servizio**.</span><span class="sxs-lookup"><span data-stu-id="f8538-125">In the WCF test client, click the **File** menu and select **Add Service**.</span></span> <span data-ttu-id="f8538-126">Incollare l'indirizzo del servizio locale nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="f8538-126">Paste the local service address in the textbox.</span></span> <span data-ttu-id="f8538-127">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="f8538-127">Click **OK** to close the dialog.</span></span>  
  
10. <span data-ttu-id="f8538-128">Nel client di prova WCF fare doppio clic su **GetStockPrice**.</span><span class="sxs-lookup"><span data-stu-id="f8538-128">In the WCF test client, double click **GetStockPrice**.</span></span> <span data-ttu-id="f8538-129">Verrà visualizzata la `GetStockPrice` operazione che accetta un parametro, digitare il valore `Contoso` e fare clic su **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="f8538-129">This opens the `GetStockPrice` operation that takes one parameter, type in the value `Contoso` and click **Invoke**.</span></span>  
  
11. <span data-ttu-id="f8538-130">I record di rilevamento creati vengono scritti in un database SQL.</span><span class="sxs-lookup"><span data-stu-id="f8538-130">The emitted tracking records are written to a SQL database.</span></span> <span data-ttu-id="f8538-131">Per visualizzare i record di rilevamento, aprire il database TrackingSample in SQL Management Studio e passare alle tabelle.</span><span class="sxs-lookup"><span data-stu-id="f8538-131">To view the tracking records, open the TrackingSample database in SQL Management Studio and navigate to the tables.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="f8538-132"> SQL Server Management Studio, vedere [Introduzione a SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645).</span><span class="sxs-lookup"><span data-stu-id="f8538-132"> SQL Server Management Studio, see [Introducing SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645).</span></span> <span data-ttu-id="f8538-133">SQL Server 2008 Management Studio Express può essere scaricato [qui](http://go.microsoft.com/fwlink/?LinkId=180520).</span><span class="sxs-lookup"><span data-stu-id="f8538-133">SQL Server 2008 Management Studio Express can be downloaded [here](http://go.microsoft.com/fwlink/?LinkId=180520).</span></span> <span data-ttu-id="f8538-134">Eseguendo una query di selezione sulle tabelle vengono visualizzati i dati all'interno dei record di rilevamento archiviati nelle rispettive tabelle.</span><span class="sxs-lookup"><span data-stu-id="f8538-134">Running a select query on the tables displays the data within the tracking records stored in the respective tables.</span></span>  
  
#### <a name="to-uninstall-the-sample"></a><span data-ttu-id="f8538-135">Per disinstallare l'esempio</span><span class="sxs-lookup"><span data-stu-id="f8538-135">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="f8538-136">Eseguire lo script Trackingcleanup.cmd nella directory di esempio (\WF\Basic\Tracking\SqlTracking).</span><span class="sxs-lookup"><span data-stu-id="f8538-136">Run theTrackingcleanup.cmd script in the sample directory (\WF\Basic\Tracking\SqlTracking).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8538-137">Trackingcleanup.cmd tenta di eliminare il database nel computer locale SQL Express.</span><span class="sxs-lookup"><span data-stu-id="f8538-137">The Trackingcleanup.cmd attempts to delete the database in your local computer SQL Express.</span></span> <span data-ttu-id="f8538-138">Se si usa un'altra istanza di SQL Server, modificare Trackingcleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="f8538-138">If you are using another SQL server instance, edit Trackingcleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f8538-139">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="f8538-139">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f8538-140">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="f8538-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f8538-141">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f8538-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f8538-142">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="f8538-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a><span data-ttu-id="f8538-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8538-143">See Also</span></span>  
 [<span data-ttu-id="f8538-144">Esempi di monitoraggio di AppFabric</span><span class="sxs-lookup"><span data-stu-id="f8538-144">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
