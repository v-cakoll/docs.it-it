---
title: Processo di approvazione dei documenti
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: d1e37dcbc21239822937c57d9779a52357aac518
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717709"
---
# <a name="document-approval-process"></a><span data-ttu-id="59ef2-102">Processo di approvazione dei documenti</span><span class="sxs-lookup"><span data-stu-id="59ef2-102">Document Approval Process</span></span>
<span data-ttu-id="59ef2-103">In questo esempio illustra l'uso di molte funzionalità di Windows Workflow Foundation (WF) e Windows Communication Foundation (WCF) tra loro.</span><span class="sxs-lookup"><span data-stu-id="59ef2-103">This sample demonstrates the use of many Windows Workflow Foundation (WF) and Windows Communication Foundation (WCF) features together.</span></span> <span data-ttu-id="59ef2-104">Insieme implementano uno scenario del processo di approvazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="59ef2-104">Together they implement a document approval process scenario.</span></span> <span data-ttu-id="59ef2-105">Un'applicazione client può inviare documenti da sottoporre ad approvazione e approvare documenti.</span><span class="sxs-lookup"><span data-stu-id="59ef2-105">A client application can submit documents for approval and approve documents.</span></span> <span data-ttu-id="59ef2-106">Un'applicazione di gestione delle approvazioni è utile per semplificare le comunicazioni tra i client e per applicare le regole del processo di approvazione</span><span class="sxs-lookup"><span data-stu-id="59ef2-106">An approval manager application exists to facilitate communications between clients and to enforce the rules of the approval process.</span></span> <span data-ttu-id="59ef2-107">che consiste in un flusso di lavoro che può eseguire molti tipi di approvazione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-107">The approval process is a workflow that can execute several types of approval.</span></span> <span data-ttu-id="59ef2-108">Le attività servono per ottenere un processo di approvazione singola, di approvazione a quorum (una percentuale del gruppo di responsabili approvazione) e di approvazione complessa costituito da un'approvazione a quorum e una singola in sequenza.</span><span class="sxs-lookup"><span data-stu-id="59ef2-108">Activities exist to get a single approval, a quorum approval (a percentage of set of approvers), and a complex approval process that consists of a quorum and single approval in a sequence.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="59ef2-109">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="59ef2-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="59ef2-110">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="59ef2-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="59ef2-111">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="59ef2-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="59ef2-112">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="59ef2-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`  
  
## <a name="sample-details"></a><span data-ttu-id="59ef2-113">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="59ef2-113">Sample Details</span></span>  
 <span data-ttu-id="59ef2-114">Nell'elemento grafico seguente viene illustrato il flusso di lavoro del processo di approvazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="59ef2-114">The following graphic demonstrates the document approval process workflow.</span></span>  
  
 <span data-ttu-id="59ef2-115">![Un flusso di lavoro documenti processo approvazione](./media/approvalprocess.jpg "ApprovalProcess")</span><span class="sxs-lookup"><span data-stu-id="59ef2-115">![A document approval process workflow](./media/approvalprocess.jpg "ApprovalProcess")</span></span>  
  
 <span data-ttu-id="59ef2-116">Dalla prospettiva del client, il processo di approvazione funziona nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="59ef2-116">From the client's perspective, the approval process functions as follows:</span></span>  
  
1.  <span data-ttu-id="59ef2-117">Un client esegue una sottoscrizione per essere un utente del sistema del processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-117">A client subscribes to be a user in the approval process system.</span></span>  
  
2.  <span data-ttu-id="59ef2-118">Un client WCF invia a un servizio WCF ospitato dall'applicazione di gestione delle approvazioni.</span><span class="sxs-lookup"><span data-stu-id="59ef2-118">A WCF client sends to a WCF service hosted by the approval manager application.</span></span>  
  
3.  <span data-ttu-id="59ef2-119">Al client viene restituito un ID utente univoco.</span><span class="sxs-lookup"><span data-stu-id="59ef2-119">A unique user ID is returned to the client.</span></span> <span data-ttu-id="59ef2-120">Il client può ora partecipare ai processi di approvazione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-120">The client can now participate in approval processes.</span></span>  
  
4.  <span data-ttu-id="59ef2-121">Una volta inserito, un client può inviare un documento per l'approvazione usando un processo di approvazione singolo, a quorum o complesso.</span><span class="sxs-lookup"><span data-stu-id="59ef2-121">Once joined, a client can send a document for approval using single, quorum or complex approval processes.</span></span>  
  
5.  <span data-ttu-id="59ef2-122">La selezione di un pulsante nell'interfaccia del client avvia un'istanza del flusso di lavoro in un host dei servizi flusso di lavoro del client.</span><span class="sxs-lookup"><span data-stu-id="59ef2-122">A button in the client’s interface is clicked, starting a workflow instance in a client Workflow Service Host.</span></span>  
  
6.  <span data-ttu-id="59ef2-123">Il flusso di lavoro invia una richiesta di approvazione all'applicazione di gestione delle approvazioni.</span><span class="sxs-lookup"><span data-stu-id="59ef2-123">The workflow sends an approval request to the approval manager application.</span></span>  
  
7.  <span data-ttu-id="59ef2-124">Il proprietario del flusso di lavoro avvia un flusso di lavoro per rappresentare un processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-124">The workflow manager starts a workflow on its own side to represent an approval process.</span></span>  
  
8.  <span data-ttu-id="59ef2-125">Una volta che il proprietario ha eseguito il flusso di lavoro di approvazione, i risultati vengono restituiti al client.</span><span class="sxs-lookup"><span data-stu-id="59ef2-125">Once the manager approval workflow executes, the results are sent back to the client.</span></span>  
  
9. <span data-ttu-id="59ef2-126">Il client visualizza i risultati.</span><span class="sxs-lookup"><span data-stu-id="59ef2-126">The client displays the results.</span></span>  
  
10. <span data-ttu-id="59ef2-127">Un client può ricevere una richiesta di approvazione e rispondere alla richiesta in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="59ef2-127">A client may receive an approval request and respond to the request at any point in time.</span></span>  
  
11. <span data-ttu-id="59ef2-128">Un servizio WCF ospitato nel client può ricevere una richiesta di approvazione dall'applicazione di gestione delle approvazioni.</span><span class="sxs-lookup"><span data-stu-id="59ef2-128">A WCF service hosted on the client can receive an approval request from the approval manager application.</span></span>  
  
12. <span data-ttu-id="59ef2-129">Le informazioni sul documento vengono presentate nel client per la revisione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-129">The document information is presented on the client for review.</span></span>  
  
13. <span data-ttu-id="59ef2-130">L'utente può approvare o rifiutare il documento.</span><span class="sxs-lookup"><span data-stu-id="59ef2-130">The user can approve or reject the document.</span></span>  
  
14. <span data-ttu-id="59ef2-131">Un client WCF viene usato per inviare una risposta di approvazione all'applicazione di gestione delle approvazioni.</span><span class="sxs-lookup"><span data-stu-id="59ef2-131">A WCF client is used to send an approval response back to the approval manager application.</span></span>  
  
 <span data-ttu-id="59ef2-132">Dal punto di vista dell'applicazione di gestione delle approvazioni, il processo di approvazione funziona nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="59ef2-132">From the approval manager application’s point of view, the approval process functions as follows:</span></span>  
  
1.  <span data-ttu-id="59ef2-133">Un client richiede la partecipazione al sistema del processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-133">A client requests to participate to the approval process system.</span></span>  
  
2.  <span data-ttu-id="59ef2-134">Un servizio WCF in responsabile dell'approvazione riceve una richiesta a far parte del sistema del processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-134">A WCF service on the approval manager receives a request to be part of the approval process system.</span></span>  
  
3.  <span data-ttu-id="59ef2-135">Viene generato un ID univoco per il client.</span><span class="sxs-lookup"><span data-stu-id="59ef2-135">A unique ID is generated for the client.</span></span> <span data-ttu-id="59ef2-136">Le informazioni utente vengono archiviate in un database.</span><span class="sxs-lookup"><span data-stu-id="59ef2-136">The user information is stored in a database.</span></span>  
  
4.  <span data-ttu-id="59ef2-137">L'ID univoco viene restituito all'utente.</span><span class="sxs-lookup"><span data-stu-id="59ef2-137">The unique ID is sent back to the user.</span></span>  
  
5.  <span data-ttu-id="59ef2-138">Viene ricevuta una richiesta di approvazione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-138">An approval request is receive.</span></span> <span data-ttu-id="59ef2-139">Il responsabile dell'approvazione esegue un processo di approvazione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-139">The approval manager executes an approval process.</span></span>  
  
6.  <span data-ttu-id="59ef2-140">Il responsabile dell'approvazione riceve una richiesta di approvazione che avvia un nuovo flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="59ef2-140">An approval request is received by the approval manager, starting a new workflow.</span></span>  
  
7.  <span data-ttu-id="59ef2-141">A seconda del tipo di richiesta (semplice, a quorum o complessa), viene eseguita un'attività diversa.</span><span class="sxs-lookup"><span data-stu-id="59ef2-141">Depending on the type of request (simple, quorum, or complex) a different activity is executed.</span></span>  
  
8.  <span data-ttu-id="59ef2-142">Le attività di invio e ricezione con correlazione vengono usate per inviare la richiesta di approvazione al client per la revisione e per ricevere la risposta.</span><span class="sxs-lookup"><span data-stu-id="59ef2-142">Send and Receive activities with correlation are used to send the approval request to the client for review and receive the response.</span></span>  
  
9. <span data-ttu-id="59ef2-143">Il risultato del flusso di lavoro del processo di approvazione viene inviato al client.</span><span class="sxs-lookup"><span data-stu-id="59ef2-143">The result of the approval process workflow is sent to the client.</span></span>  
  
## <a name="using-the-sample"></a><span data-ttu-id="59ef2-144">Utilizzo dell'esempio</span><span class="sxs-lookup"><span data-stu-id="59ef2-144">Using the Sample</span></span>  
  
##### <a name="to-set-up-the-database"></a><span data-ttu-id="59ef2-145">Per impostare il database</span><span class="sxs-lookup"><span data-stu-id="59ef2-145">To set up the database</span></span>  
  
1.  <span data-ttu-id="59ef2-146">Da un prompt dei comandi di Visual Studio 2010 aperto con privilegi di amministratore, passare alla cartella DocumentApprovalProcess ed eseguire Setup. cmd.</span><span class="sxs-lookup"><span data-stu-id="59ef2-146">From a Visual Studio 2010 command prompt opened with Administrator privileges, navigate to this DocumentApprovalProcess folder and run Setup.cmd.</span></span>  
  
##### <a name="to-set-up-the-application"></a><span data-ttu-id="59ef2-147">Per impostare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="59ef2-147">To set up the application</span></span>  
  
1.  <span data-ttu-id="59ef2-148">Con Visual Studio 2010, aprire il file della soluzione Documentapprovalprocess.</span><span class="sxs-lookup"><span data-stu-id="59ef2-148">Using Visual Studio 2010, open the DocumentApprovalProcess.sln solution file.</span></span>  
  
2.  <span data-ttu-id="59ef2-149">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="59ef2-149">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="59ef2-150">Per eseguire la soluzione, avviare l'applicazione di approvazione Manager facendo clic con il progetto ApprovalManager nel **Esplora soluzioni** e facendo clic su **Debug**->**Start**  nuova istanza di dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="59ef2-150">To run the solution, launch the Approval Manager Application by right-clicking the ApprovalManager project in the **Solution Explorer** and clicking **Debug**->**Start** new instance from the right-click menu.</span></span>  
  
     <span data-ttu-id="59ef2-151">Attendere l'output del responsabile per sapere che è pronta.</span><span class="sxs-lookup"><span data-stu-id="59ef2-151">Wait for the manager’s output to let you know that it is ready.</span></span>  
  
##### <a name="to-run-the-single-approval-scenario"></a><span data-ttu-id="59ef2-152">Per eseguire lo scenario di approvazione singola</span><span class="sxs-lookup"><span data-stu-id="59ef2-152">To run the single approval scenario</span></span>  
  
1.  <span data-ttu-id="59ef2-153">Aprire un prompt dei comandi con l'autorizzazione di amministratore.</span><span class="sxs-lookup"><span data-stu-id="59ef2-153">Open a command prompt with administrator permission.</span></span>  
  
2.  <span data-ttu-id="59ef2-154">Passare alla directory contenente la soluzione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-154">Navigate to the directory that contains the solution.</span></span>  
  
3.  <span data-ttu-id="59ef2-155">Passare alla cartella ApprovalClient\Bin\Debug ed eseguire due istanze di ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="59ef2-155">Navigate to the ApprovalClient\Bin\Debug folder and execute two instances of ApprovalClient.exe.</span></span>  
  
4.  <span data-ttu-id="59ef2-156">Fare clic su **individua**, attendere finché il **sottoscrivere** pulsante è abilitato.</span><span class="sxs-lookup"><span data-stu-id="59ef2-156">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5.  <span data-ttu-id="59ef2-157">Digitare un nome utente e fare clic su **sottoscrivere**.</span><span class="sxs-lookup"><span data-stu-id="59ef2-157">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="59ef2-158">Per un client usare `UserType1` e per l'altro il tipo `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="59ef2-158">For one client, use `UserType1` and the other type `UserType2`.</span></span>  
  
6.  <span data-ttu-id="59ef2-159">Nel client `UserType1` selezionare il tipo di approvazione singola dal menu a discesa e digitare un nome e il contenuto del documento.</span><span class="sxs-lookup"><span data-stu-id="59ef2-159">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="59ef2-160">Fare clic su **Richiedi l'approvazione**.</span><span class="sxs-lookup"><span data-stu-id="59ef2-160">Click **Request Approval**.</span></span>  
  
7.  <span data-ttu-id="59ef2-161">Nel client `UserType2` viene visualizzato un documento in attesa di approvazione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-161">In the `UserType2` client, a document awaiting approval appears.</span></span> <span data-ttu-id="59ef2-162">Selezionarlo e premere **approvare** oppure **rifiutare**.</span><span class="sxs-lookup"><span data-stu-id="59ef2-162">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="59ef2-163">I risultati devono essere visualizzati nel client `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="59ef2-163">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-quorum-approval-scenario"></a><span data-ttu-id="59ef2-164">Per eseguire lo scenario di approvazione a quorum</span><span class="sxs-lookup"><span data-stu-id="59ef2-164">To run the quorum approval scenario</span></span>  
  
1.  <span data-ttu-id="59ef2-165">Aprire un prompt dei comandi con l'autorizzazione di amministratore.</span><span class="sxs-lookup"><span data-stu-id="59ef2-165">Open a command prompt with administrator permission.</span></span>  
  
2.  <span data-ttu-id="59ef2-166">Passare alla directory contenente la soluzione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-166">Navigate to the directory that contains the solution.</span></span>  
  
3.  <span data-ttu-id="59ef2-167">Passare alla cartella ApprovalClient\Bin\Debug ed eseguire tre istanze di ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="59ef2-167">Navigate to the ApprovalClient\Bin\Debug folder and execute three instances of ApprovalClient.exe.</span></span>  
  
4.  <span data-ttu-id="59ef2-168">Fare clic su **individua**, attendere finché il **sottoscrivere** pulsante è abilitato.</span><span class="sxs-lookup"><span data-stu-id="59ef2-168">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5.  <span data-ttu-id="59ef2-169">Digitare un nome utente e fare clic su **sottoscrivere**.</span><span class="sxs-lookup"><span data-stu-id="59ef2-169">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="59ef2-170">Per un client usare `UserType1` e per gli altri due usare il tipo `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="59ef2-170">For one client use `UserType1` and the other two type `UserType2`.</span></span>  
  
6.  <span data-ttu-id="59ef2-171">Nel client `UserType1` selezionare il tipo di approvazione a quorum dal menu a discesa e digitare un nome e il contenuto del documento.</span><span class="sxs-lookup"><span data-stu-id="59ef2-171">In the `UserType1` client, select the quorum approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="59ef2-172">Fare clic su **Richiedi l'approvazione**.</span><span class="sxs-lookup"><span data-stu-id="59ef2-172">Click **Request Approval**.</span></span> <span data-ttu-id="59ef2-173">In questo modo viene richiesto che i due client `UserType2` approvino o rifiutino il documento.</span><span class="sxs-lookup"><span data-stu-id="59ef2-173">This requests that the two `UserType2` clients approve or reject the document.</span></span> <span data-ttu-id="59ef2-174">Mentre entrambi i client `UserType2` devono rispondere, solo un client deve approvare il documento.</span><span class="sxs-lookup"><span data-stu-id="59ef2-174">While both `UserType2` clients must respond, only one client must approve the document for it to be approved.</span></span>  
  
7.  <span data-ttu-id="59ef2-175">Nei client `UserType2` viene visualizzato un documento in attesa di approvazione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-175">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="59ef2-176">Selezionarlo e premere **approvare** oppure **rifiutare**.</span><span class="sxs-lookup"><span data-stu-id="59ef2-176">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="59ef2-177">I risultati devono essere visualizzati nel client `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="59ef2-177">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-complex-approval-scenario"></a><span data-ttu-id="59ef2-178">Per eseguire lo scenario di approvazione complesso</span><span class="sxs-lookup"><span data-stu-id="59ef2-178">To run the complex approval scenario</span></span>  
  
1.  <span data-ttu-id="59ef2-179">Aprire un prompt dei comandi con l'autorizzazione di amministratore.</span><span class="sxs-lookup"><span data-stu-id="59ef2-179">Open a command prompt with administrator permission.</span></span>  
  
2.  <span data-ttu-id="59ef2-180">Passare alla directory contenente la soluzione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-180">Navigate to the directory that contains the solution.</span></span>  
  
3.  <span data-ttu-id="59ef2-181">Passare alla cartella ApprovalClient\Bin\Debug ed eseguire quattro istanze di ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="59ef2-181">Navigate to the ApprovalClient\Bin\Debug folder and execute four instances of ApprovalClient.exe.</span></span>  
  
4.  <span data-ttu-id="59ef2-182">Fare clic su **individua**, attendere finché il **sottoscrivere** pulsante è abilitato.</span><span class="sxs-lookup"><span data-stu-id="59ef2-182">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5.  <span data-ttu-id="59ef2-183">Digitare un nome utente e fare clic su **sottoscrivere**.</span><span class="sxs-lookup"><span data-stu-id="59ef2-183">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="59ef2-184">Per un client usare `UserType1`, per il secondo usare il tipo `UserType2` e per l'ultimo usare `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="59ef2-184">For one client use `UserType1`, in two uses type `UserType2`, and in the last use `UserType3`.</span></span>  
  
6.  <span data-ttu-id="59ef2-185">Nel client `UserType1` selezionare il tipo di approvazione singola dal menu a discesa e digitare un nome e il contenuto del documento.</span><span class="sxs-lookup"><span data-stu-id="59ef2-185">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="59ef2-186">Fare clic su **Richiedi l'approvazione**.</span><span class="sxs-lookup"><span data-stu-id="59ef2-186">Click **Request Approval**.</span></span>  
  
7.  <span data-ttu-id="59ef2-187">Nei client `UserType2` viene visualizzato un documento in attesa di approvazione.</span><span class="sxs-lookup"><span data-stu-id="59ef2-187">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="59ef2-188">Selezionarlo e premere **approvare**, il documento viene passato per il `UserType3` client.</span><span class="sxs-lookup"><span data-stu-id="59ef2-188">Select it and press **approve**, the document is passed to the `UserType3` client.</span></span>  
  
     <span data-ttu-id="59ef2-189">Se il documento viene approvato dal primo quorum `UserType2`, il documento viene passato al client `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="59ef2-189">If the document is approved by the first `UserType2` quorum, the document is passed to the `UserType3` client.</span></span>  
  
8.  <span data-ttu-id="59ef2-190">Approvare o rifiutare il documento dal client `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="59ef2-190">Approve or reject the document from the `UserType3` client.</span></span> <span data-ttu-id="59ef2-191">I risultati devono essere visualizzati nel client `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="59ef2-191">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-clean-up"></a><span data-ttu-id="59ef2-192">Per eseguire la pulizia</span><span class="sxs-lookup"><span data-stu-id="59ef2-192">To clean up</span></span>  
  
1.  <span data-ttu-id="59ef2-193">Da un prompt dei comandi di Visual Studio 2010, passare alla cartella DocumentApprovalProcess ed eseguire Cleanup.</span><span class="sxs-lookup"><span data-stu-id="59ef2-193">From a Visual Studio 2010 command prompt, navigate to the DocumentApprovalProcess folder and run Cleanup.cmd.</span></span>
