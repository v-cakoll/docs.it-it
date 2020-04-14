---
title: Rilevamento SQL
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 72bfcaac2903b3e7fa5679422ad4feaa79e93211
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243180"
---
# <a name="sql-tracking"></a><span data-ttu-id="4fef7-102">Rilevamento SQL</span><span class="sxs-lookup"><span data-stu-id="4fef7-102">SQL tracking</span></span>

<span data-ttu-id="4fef7-103">In questo esempio viene illustrato come scrivere un partecipante di rilevamento SQL personalizzato che scrive i record di rilevamento in un database SQL.</span><span class="sxs-lookup"><span data-stu-id="4fef7-103">This sample demonstrates how to write a custom SQL tracking participant that writes tracking records to a SQL database.</span></span> <span data-ttu-id="4fef7-104">Windows Workflow Foundation (WF) fornisce il rilevamento del flusso di lavoro per ottenere visibilità sull'esecuzione di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4fef7-104">Windows Workflow Foundation (WF) provides workflow tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="4fef7-105">Il runtime di rilevamento crea record di rilevamento del flusso di lavoro durante l'esecuzione di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="4fef7-105">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> <span data-ttu-id="4fef7-106">Per ulteriori informazioni sul rilevamento del flusso di lavoro, vedere [Rilevamento e traccia del flusso di lavoro](../workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="4fef7-106">For more information about workflow tracking, see [Workflow Tracking and Tracing](../workflow-tracking-and-tracing.md).</span></span>

## <a name="use-the-sample"></a><span data-ttu-id="4fef7-107">Usare l'esempio</span><span class="sxs-lookup"><span data-stu-id="4fef7-107">Use the sample</span></span>

1. <span data-ttu-id="4fef7-108">Verificare di avere installato SQL Server 2008, SQL Server 2008 Express o una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="4fef7-108">Verify you have SQL Server 2008, SQL Server 2008 Express or newer installed.</span></span> <span data-ttu-id="4fef7-109">Gli script impacchettati con l'esempio presuppongono l'uso di un'istanza di SQL Express sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="4fef7-109">The scripts packaged with the sample assume the use of a SQL Express instance on your local computer.</span></span> <span data-ttu-id="4fef7-110">Se si dispone di un'istanza diversa, modificare gli script correlati al database prima di eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="4fef7-110">If you have a different instance please modify the database-related scripts before running the sample.</span></span>

2. <span data-ttu-id="4fef7-111">Creare il database di rilevamento di SQL Server eseguendo Trackingsetup.cmd nella directory degli script (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span><span class="sxs-lookup"><span data-stu-id="4fef7-111">Create the SQL Server tracking database by running Trackingsetup.cmd in the scripts directory (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span></span> <span data-ttu-id="4fef7-112">Verrà creato un database denominato TrackingSample.</span><span class="sxs-lookup"><span data-stu-id="4fef7-112">This creates a database called TrackingSample.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4fef7-113">Lo script crea il database nell'istanza predefinita di SQL Express.</span><span class="sxs-lookup"><span data-stu-id="4fef7-113">The script creates the database on the default instance of SQL Express.</span></span> <span data-ttu-id="4fef7-114">Se si desidera installarlo in un'istanza di database diversa, modificare lo script Trackingsetup.cmd.</span><span class="sxs-lookup"><span data-stu-id="4fef7-114">If you want to install it on a different database instance, edit the Trackingsetup.cmd script.</span></span>

3. <span data-ttu-id="4fef7-115">Aprire SqlTrackingSample.sln in Visual Studio 2010.Open SqlTrackingSample.sln in Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="4fef7-115">Open SqlTrackingSample.sln in Visual Studio 2010.</span></span>

4. <span data-ttu-id="4fef7-116">Premere **Ctrl**+**Maiusc**+**B** per compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="4fef7-116">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

5. <span data-ttu-id="4fef7-117">Premere **F5** per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4fef7-117">Press **F5** to run the application.</span></span>

   <span data-ttu-id="4fef7-118">Viene aperta la finestra del browser in cui viene mostrata la visualizzazione directory per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4fef7-118">The browser window opens and shows the directory listing for the application.</span></span>

6. <span data-ttu-id="4fef7-119">Nel browser fare clic su StockPriceService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="4fef7-119">In the browser, click StockPriceService.xamlx.</span></span>

7. <span data-ttu-id="4fef7-120">Nel browser viene visualizzata la pagina StockPriceService contenente l'indirizzo WSDL del servizio locale.</span><span class="sxs-lookup"><span data-stu-id="4fef7-120">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="4fef7-121">Copiare questo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="4fef7-121">Copy this address.</span></span>

   <span data-ttu-id="4fef7-122">Un esempio dell'indirizzo WSDL `http://localhost:65193/StockPriceService.xamlx?wsdl`del servizio locale è .</span><span class="sxs-lookup"><span data-stu-id="4fef7-122">An example of the local service WSDL address is `http://localhost:65193/StockPriceService.xamlx?wsdl`.</span></span>

8. <span data-ttu-id="4fef7-123">Utilizzando Esplora file, eseguire il client di test WCF (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="4fef7-123">Using File Explorer, run the WCF test client (WcfTestClient.exe).</span></span> <span data-ttu-id="4fef7-124">Si trova nella *directory di Microsoft Visual Studio 10.0, Common7, IDE*.</span><span class="sxs-lookup"><span data-stu-id="4fef7-124">It's located in the *Microsoft Visual Studio 10.0\Common7\IDE directory*.</span></span>

9. <span data-ttu-id="4fef7-125">Nel client di test WCF, fare clic sul menu **File** e selezionare **Aggiungi servizio**.</span><span class="sxs-lookup"><span data-stu-id="4fef7-125">In the WCF test client, click the **File** menu and select **Add Service**.</span></span> <span data-ttu-id="4fef7-126">Incollare l'indirizzo del servizio locale nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="4fef7-126">Paste the local service address in the textbox.</span></span> <span data-ttu-id="4fef7-127">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="4fef7-127">Click **OK** to close the dialog.</span></span>

10. <span data-ttu-id="4fef7-128">Nel client di test WCF fare doppio clic su **GetStockPrice**.</span><span class="sxs-lookup"><span data-stu-id="4fef7-128">In the WCF test client, double click **GetStockPrice**.</span></span> <span data-ttu-id="4fef7-129">Verrà aperta `GetStockPrice` l'operazione che accetta un `Contoso` parametro, digitare il valore e fare clic su **Richiama**.</span><span class="sxs-lookup"><span data-stu-id="4fef7-129">This opens the `GetStockPrice` operation that takes one parameter, type in the value `Contoso` and click **Invoke**.</span></span>

11. <span data-ttu-id="4fef7-130">I record di rilevamento creati vengono scritti in un database SQL.</span><span class="sxs-lookup"><span data-stu-id="4fef7-130">The emitted tracking records are written to a SQL database.</span></span> <span data-ttu-id="4fef7-131">Per visualizzare i record di rilevamento, aprire il database TrackingSample in SQL Management Studio e passare alle tabelle.</span><span class="sxs-lookup"><span data-stu-id="4fef7-131">To view the tracking records, open the TrackingSample database in SQL Management Studio and navigate to the tables.</span></span> <span data-ttu-id="4fef7-132">Eseguendo una query di selezione sulle tabelle vengono visualizzati i dati all'interno dei record di rilevamento archiviati nelle rispettive tabelle.</span><span class="sxs-lookup"><span data-stu-id="4fef7-132">Running a select query on the tables displays the data within the tracking records stored in the respective tables.</span></span>

   <span data-ttu-id="4fef7-133">Per ulteriori informazioni su SQL Server Management Studio, vedere [Introduzione a SQL Server Management Studio.](/sql/ssms/sql-server-management-studio-ssms)</span><span class="sxs-lookup"><span data-stu-id="4fef7-133">For more information about SQL Server Management Studio, see [Introducing SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms).</span></span> <span data-ttu-id="4fef7-134">Scaricare SQL Server Management Studio [qui](https://aka.ms/ssmsfullsetup).</span><span class="sxs-lookup"><span data-stu-id="4fef7-134">Download SQL Server Management Studio [here](https://aka.ms/ssmsfullsetup).</span></span>

## <a name="uninstall-the-sample"></a><span data-ttu-id="4fef7-135">Disinstallare l'esempio</span><span class="sxs-lookup"><span data-stu-id="4fef7-135">Uninstall the sample</span></span>

1. <span data-ttu-id="4fef7-136">Eseguire lo script Trackingcleanup.cmd nella directory di esempio (*.*</span><span class="sxs-lookup"><span data-stu-id="4fef7-136">Run theTrackingcleanup.cmd script in the sample directory (*\WF\Basic\Tracking\SqlTracking*).</span></span>

    > [!NOTE]
    > <span data-ttu-id="4fef7-137">Trackingcleanup.cmd tenta di eliminare il database nel computer locale SQL Express.</span><span class="sxs-lookup"><span data-stu-id="4fef7-137">The Trackingcleanup.cmd attempts to delete the database in your local computer SQL Express.</span></span> <span data-ttu-id="4fef7-138">Se si usa un'altra istanza di SQL Server, modificare Trackingcleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="4fef7-138">If you are using another SQL server instance, edit Trackingcleanup.cmd.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4fef7-139">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="4fef7-139">The samples may already be installed on your computer.</span></span> <span data-ttu-id="4fef7-140">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="4fef7-140">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="4fef7-141">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4fef7-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4fef7-142">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="4fef7-142">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`

## <a name="see-also"></a><span data-ttu-id="4fef7-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fef7-143">See also</span></span>

- <span data-ttu-id="4fef7-144">[Monitoraggio](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="4fef7-144">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
