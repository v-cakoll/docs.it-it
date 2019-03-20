---
title: Propagazione di transazioni all'interno e all'esterno di servizi flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: 272e188b448864450621665f80ea0ab8b0037b37
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185688"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="451be-102">Propagazione di transazioni all'interno e all'esterno di servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="451be-102">Flowing Transactions into and out of Workflow Services</span></span>
<span data-ttu-id="451be-103">Servizi e client del flusso di lavoro possono partecipare alle transazioni.</span><span class="sxs-lookup"><span data-stu-id="451be-103">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="451be-104">Affinché un'operazione del servizio diventi parte di una transazione di ambiente, posizionare un'attività <xref:System.ServiceModel.Activities.Receive> all'interno di un'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="451be-104">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="451be-105">Qualsiasi chiamata effettuata da un'attività <xref:System.ServiceModel.Activities.Send> o un'attività <xref:System.ServiceModel.Activities.SendReply> all'interno di <xref:System.ServiceModel.Activities.TransactedReceiveScope> verrà effettuata anche all'interno della transazione di ambiente.</span><span class="sxs-lookup"><span data-stu-id="451be-105">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="451be-106">Un'applicazione client del flusso di lavoro può creare una transazione di ambiente tramite l'attività <xref:System.Activities.Statements.TransactionScope> e chiamare operazioni del servizio utilizzando la transazione di ambiente.</span><span class="sxs-lookup"><span data-stu-id="451be-106">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="451be-107">In questo argomento viene illustrato il processo di creazione di un servizio flusso di lavoro e di un client flusso di lavoro che partecipano a transazioni.</span><span class="sxs-lookup"><span data-stu-id="451be-107">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="451be-108">Se un'istanza del servizio flusso di lavoro viene caricata all'interno di una transazione e il flusso di lavoro contiene un'attività <xref:System.Activities.Statements.Persist>, l'istanza del flusso di lavoro verrà interrotta finché non si verifica il timeout della transazione.</span><span class="sxs-lookup"><span data-stu-id="451be-108">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will hang until the transaction times out.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="451be-109">Ogni volta che si utilizza un oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope>, è consigliabile posizionare tutte le attività Receive del flusso di lavoro all'interno delle attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="451be-109">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="451be-110">Quando si utilizza l'oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope> e i messaggi arrivano nell'ordine non corretto, il flusso di lavoro verrà interrotto quando si tenterà di consegnare il primo messaggio nell'ordine non corretto.</span><span class="sxs-lookup"><span data-stu-id="451be-110">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="451be-111">È necessario assicurarsi che il flusso di lavoro sia sempre in corrispondenza di un punto di interruzione coerente quando il flusso di lavoro è inattivo.</span><span class="sxs-lookup"><span data-stu-id="451be-111">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="451be-112">In questo modo sarà possibile riavviare il flusso di lavoro da un punto di persistenza precedente nel caso in cui il flusso di lavoro venga interrotto.</span><span class="sxs-lookup"><span data-stu-id="451be-112">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="451be-113">Creare una libreria condivisa</span><span class="sxs-lookup"><span data-stu-id="451be-113">Create a shared library</span></span>  
  
1.  <span data-ttu-id="451be-114">Creare una nuova soluzione Visual Studio vuota.</span><span class="sxs-lookup"><span data-stu-id="451be-114">Create a new empty Visual Studio Solution.</span></span>  
  
2.  <span data-ttu-id="451be-115">Aggiungere un nuovo progetto della libreria di classi denominato `Common`.</span><span class="sxs-lookup"><span data-stu-id="451be-115">Add a new class library project called `Common`.</span></span> <span data-ttu-id="451be-116">Aggiungere riferimenti agli assembly riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="451be-116">Add references to the following assemblies:</span></span>  
  
    -   <span data-ttu-id="451be-117">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="451be-117">System.Activities.dll</span></span>  
  
    -   <span data-ttu-id="451be-118">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="451be-118">System.ServiceModel.dll</span></span>  
  
    -   <span data-ttu-id="451be-119">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="451be-119">System.ServiceModel.Activities.dll</span></span>  
  
    -   <span data-ttu-id="451be-120">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="451be-120">System.Transactions.dll</span></span>  
  
3.  <span data-ttu-id="451be-121">Aggiungere una nuova classe denominata `PrintTransactionInfo` al progetto `Common`.</span><span class="sxs-lookup"><span data-stu-id="451be-121">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="451be-122">Questa classe è derivata da <xref:System.Activities.NativeActivity> ed esegue l'overload del metodo <xref:System.Activities.NativeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="451be-122">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
    ```  
    using System;  
    using System;  
    using System.Activities;  
    using System.Transactions;  
  
    namespace Common  
    {  
        public class PrintTransactionInfo : NativeActivity  
        {  
            protected override void Execute(NativeActivityContext context)  
            {  
                RuntimeTransactionHandle rth = context.Properties.Find(typeof(RuntimeTransactionHandle).FullName) as RuntimeTransactionHandle;  
  
                if (rth == null)  
                {  
                    Console.WriteLine("There is no ambient RuntimeTransactionHandle");  
                }  
  
                Transaction t = rth.GetCurrentTransaction(context);  
  
                if (t == null)  
                {  
                    Console.WriteLine("There is no ambient transaction");  
                }  
                else  
                {  
                    Console.WriteLine("Transaction: {0} is {1}", t.TransactionInformation.DistributedIdentifier, t.TransactionInformation.Status);  
                }  
            }  
        }  
  
    }  
    ```  
  
     <span data-ttu-id="451be-123">Si tratta di un'attività nativa che visualizza informazioni sulla transazione di ambiente e viene utilizzata sia nei flussi di lavoro del servizio che del client utilizzati nel presente argomento.</span><span class="sxs-lookup"><span data-stu-id="451be-123">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="451be-124">Compilare la soluzione per rendere disponibile in questa attività il **comuni** sezione il **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="451be-124">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="451be-125">Implementare il servizio di flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="451be-125">Implement the workflow service</span></span>  
  
1.  <span data-ttu-id="451be-126">Aggiungere un nuovo servizio di flusso di lavoro WCF, denominato `WorkflowService` per il `Common` progetto.</span><span class="sxs-lookup"><span data-stu-id="451be-126">Add a new WCF Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="451be-127">Per eseguire questa operazione, a destra il `Common` progetto, scegliere **Add**, **nuovo elemento...** , Selezionare **flusso di lavoro** sotto **modelli installati** e selezionare **servizio del flusso di lavoro WCF**.</span><span class="sxs-lookup"><span data-stu-id="451be-127">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     ![Aggiunta di un servizio flusso di lavoro](./media/flowing-transactions-into-and-out-of-workflow-services/add-workflow-service.jpg)  
  
2.  <span data-ttu-id="451be-129">Eliminare le attività `ReceiveRequest` e `SendResponse` predefinite.</span><span class="sxs-lookup"><span data-stu-id="451be-129">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3.  <span data-ttu-id="451be-130">Trascinare e rilasciare un'attività <xref:System.Activities.Statements.WriteLine> nell'attività `Sequential Service`.</span><span class="sxs-lookup"><span data-stu-id="451be-130">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="451be-131">Impostare la proprietà Text su `"Workflow Service starting ..."` come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="451be-131">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="451be-132">! [Aggiunta di un'attività WriteLine a activity(./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg) il servizio sequenziale</span><span class="sxs-lookup"><span data-stu-id="451be-132">![Adding a WriteLine activity to the Sequential Service activity(./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg)</span></span>  
  
4.  <span data-ttu-id="451be-133">Trascinare e rilasciare un'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope> dopo l'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="451be-133">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="451be-134">Il <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività sono reperibili nel **messaggistica** sezione del **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="451be-134">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="451be-135">Il <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività è costituita da due sezioni **richiedere** e **corpo**.</span><span class="sxs-lookup"><span data-stu-id="451be-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="451be-136">Il **richiedere** sezione sono contenute le <xref:System.ServiceModel.Activities.Receive> attività.</span><span class="sxs-lookup"><span data-stu-id="451be-136">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="451be-137">Il **corpo** sezione contiene le attività da eseguire all'interno di una transazione dopo che è stato ricevuto un messaggio.</span><span class="sxs-lookup"><span data-stu-id="451be-137">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     ![Aggiunta di un'attività TransactedReceiveScope](./media/flowing-transactions-into-and-out-of-workflow-services/transactedreceivescope-activity.jpg)  
  
5.  <span data-ttu-id="451be-139">Selezionare il <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività e scegliere il **variabili** pulsante.</span><span class="sxs-lookup"><span data-stu-id="451be-139">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="451be-140">Aggiungere le variabili seguenti.</span><span class="sxs-lookup"><span data-stu-id="451be-140">Add the following variables.</span></span>  
  
     ![Aggiunta di variabili a TransactedReceiveScope](./media/flowing-transactions-into-and-out-of-workflow-services/add-transactedreceivescope-variables.jpg)  
  
    > [!NOTE]
    >  <span data-ttu-id="451be-142">È possibile eliminare la variabile relativa ai dati, presente per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="451be-142">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="451be-143">È possibile utilizzare anche la variabile dell'handle esistente.</span><span class="sxs-lookup"><span data-stu-id="451be-143">You can also use the existing handle variable.</span></span>  
  
6.  <span data-ttu-id="451be-144">Trascinare e rilasciare un <xref:System.ServiceModel.Activities.Receive> attività all'interno di **richiesta** sezione del <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività.</span><span class="sxs-lookup"><span data-stu-id="451be-144">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="451be-145">Impostare le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="451be-145">Set the following properties:</span></span>  
  
    |<span data-ttu-id="451be-146">Proprietà</span><span class="sxs-lookup"><span data-stu-id="451be-146">Property</span></span>|<span data-ttu-id="451be-147">Value</span><span class="sxs-lookup"><span data-stu-id="451be-147">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="451be-148">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="451be-148">CanCreateInstance</span></span>|<span data-ttu-id="451be-149">True (controllare la casella di controllo)</span><span class="sxs-lookup"><span data-stu-id="451be-149">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="451be-150">OperationName</span><span class="sxs-lookup"><span data-stu-id="451be-150">OperationName</span></span>|<span data-ttu-id="451be-151">StartSample</span><span class="sxs-lookup"><span data-stu-id="451be-151">StartSample</span></span>|  
    |<span data-ttu-id="451be-152">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="451be-152">ServiceContractName</span></span>|<span data-ttu-id="451be-153">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="451be-153">ITransactionSample</span></span>|  
  
     <span data-ttu-id="451be-154">Il flusso di lavoro dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="451be-154">The workflow should look like this:</span></span>  
  
     ![Aggiunta di un'attività Receive](./media/flowing-transactions-into-and-out-of-workflow-services/add-receive-activity.jpg)  
  
7.  <span data-ttu-id="451be-156">Fare clic su di **definire...**  collegare il <xref:System.ServiceModel.Activities.Receive> attività e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="451be-156">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     ![Configurazione delle impostazioni del messaggio per l'attività Receive](./media/flowing-transactions-into-and-out-of-workflow-services/receive-message-settings.jpg)  
  
8.  <span data-ttu-id="451be-158">Trascinare e rilasciare un'attività <xref:System.Activities.Statements.Sequence> nella sezione Corpo di <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="451be-158">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="451be-159">All'interno dell'attività <xref:System.Activities.Statements.Sequence>, trascinare e rilasciare due attività <xref:System.Activities.Statements.WriteLine> e impostare le proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="451be-159">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="451be-160">Attività</span><span class="sxs-lookup"><span data-stu-id="451be-160">Activity</span></span>|<span data-ttu-id="451be-161">Value</span><span class="sxs-lookup"><span data-stu-id="451be-161">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="451be-162">WriteLine 1</span><span class="sxs-lookup"><span data-stu-id="451be-162">1st WriteLine</span></span>|<span data-ttu-id="451be-163">"Service: Ricezione completato"</span><span class="sxs-lookup"><span data-stu-id="451be-163">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="451be-164">WriteLine 2</span><span class="sxs-lookup"><span data-stu-id="451be-164">2nd WriteLine</span></span>|<span data-ttu-id="451be-165">"Service: Received = " + requestMessage</span><span class="sxs-lookup"><span data-stu-id="451be-165">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="451be-166">Il flusso di lavoro dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="451be-166">The workflow should now look like this:</span></span>  
  
     ![Sequenza dopo l'aggiunta di attività WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-writelines.jpg)  
  
9. <span data-ttu-id="451be-168">Trascinare e rilasciare il `PrintTransactionInfo` attività dopo la seconda <xref:System.Activities.Statements.WriteLine> attività nel **corpo** nel <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività.</span><span class="sxs-lookup"><span data-stu-id="451be-168">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     ![Sequenziare dopo avere aggiunto PrintTransactionInfo](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-printtransactioninfo.jpg )  
  
10. <span data-ttu-id="451be-170">Trascinare e rilasciare un'attività <xref:System.Activities.Statements.Assign> dopo l'attività `PrintTransactionInfo` e impostarne le proprietà in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="451be-170">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="451be-171">Proprietà</span><span class="sxs-lookup"><span data-stu-id="451be-171">Property</span></span>|<span data-ttu-id="451be-172">Value</span><span class="sxs-lookup"><span data-stu-id="451be-172">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="451be-173">A</span><span class="sxs-lookup"><span data-stu-id="451be-173">To</span></span>|<span data-ttu-id="451be-174">replyMessage</span><span class="sxs-lookup"><span data-stu-id="451be-174">replyMessage</span></span>|  
    |<span data-ttu-id="451be-175">Valore</span><span class="sxs-lookup"><span data-stu-id="451be-175">Value</span></span>|<span data-ttu-id="451be-176">"Service: Invio risposta".</span><span class="sxs-lookup"><span data-stu-id="451be-176">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="451be-177">Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività dopo il <xref:System.Activities.Statements.Assign> attività e set relativo <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà su "Service: Begin reply".</span><span class="sxs-lookup"><span data-stu-id="451be-177">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="451be-178">Il flusso di lavoro dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="451be-178">The workflow should now look like this:</span></span>  
  
     ![Dopo avere aggiunto Assign e WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-sbr-writeline.jpg)  
  
12. <span data-ttu-id="451be-180">Fare clic il <xref:System.ServiceModel.Activities.Receive> attività e selezionare **crea SendReply** e incollarlo dopo l'ultimo <xref:System.Activities.Statements.WriteLine> attività.</span><span class="sxs-lookup"><span data-stu-id="451be-180">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="451be-181">Fare clic su di **definire...**  collegare il `SendReplyToReceive` attività e configurare le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="451be-181">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     ![Impostazioni del messaggio di risposta](./media/flowing-transactions-into-and-out-of-workflow-services/reply-message-settings.jpg)  
  
13. <span data-ttu-id="451be-183">Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività dopo il `SendReplyToReceive` attività e set ha <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà su "Service: Risposta inviata."</span><span class="sxs-lookup"><span data-stu-id="451be-183">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="451be-184">Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività nella parte inferiore del flusso di lavoro e set relativo <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà su "Service: Flusso di lavoro termina, premere INVIO per uscire."</span><span class="sxs-lookup"><span data-stu-id="451be-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="451be-185">Il flusso di lavoro del servizio completato dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="451be-185">The completed service workflow should look like this:</span></span>  
  
     ![Flusso di lavoro del servizio completato](./media/flowing-transactions-into-and-out-of-workflow-services/service-complete-workflow.jpg)  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="451be-187">Implementare il client flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="451be-187">Implement the workflow client</span></span>  
  
1.  <span data-ttu-id="451be-188">Aggiungere una nuova applicazione flusso di lavoro WCF, denominata `WorkflowClient`, al progetto `Common`.</span><span class="sxs-lookup"><span data-stu-id="451be-188">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="451be-189">Per eseguire questa operazione, a destra il `Common` progetto, scegliere **Add**, **nuovo elemento...** , Selezionare **flusso di lavoro** sotto **modelli installati** e selezionare **attività**.</span><span class="sxs-lookup"><span data-stu-id="451be-189">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     ![Aggiungere un progetto di attività](./media/flowing-transactions-into-and-out-of-workflow-services/add-activity-project.jpg)  
  
2.  <span data-ttu-id="451be-191">Trascinare e rilasciare un'attività <xref:System.Activities.Statements.Sequence> sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="451be-191">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3.  <span data-ttu-id="451be-192">All'interno dell'attività <xref:System.Activities.Statements.Sequence>, trascinare un'attività <xref:System.Activities.Statements.WriteLine> e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su `"Client: Workflow starting"`.</span><span class="sxs-lookup"><span data-stu-id="451be-192">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="451be-193">Il flusso di lavoro dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="451be-193">The workflow should now look like this:</span></span>  
  
     ![Aggiungere un'attività WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-activity.jpg)  
  
4.  <span data-ttu-id="451be-195">Trascinare un'attività <xref:System.Activities.Statements.TransactionScope> dopo l'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="451be-195">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="451be-196">Selezionare l'attività <xref:System.Activities.Statements.TransactionScope>, fare clic sul pulsante Variabili e aggiungere le variabili seguenti.</span><span class="sxs-lookup"><span data-stu-id="451be-196">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     ![Aggiungere variabili a TransactionScope](./media/flowing-transactions-into-and-out-of-workflow-services/transactionscope-variables.jpg)  
  
5.  <span data-ttu-id="451be-198">Trascinare e rilasciare un'attività <xref:System.Activities.Statements.Sequence> nel corpo dell'attività <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="451be-198">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6.  <span data-ttu-id="451be-199">Trascinare e rilasciare un'attività `PrintTransactionInfo` all'interno dell'attività <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="451be-199">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7.  <span data-ttu-id="451be-200">Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività dopo il `PrintTransactionInfo` attività e set relativo <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà su "Client: Inizio invio".</span><span class="sxs-lookup"><span data-stu-id="451be-200">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="451be-201">Il flusso di lavoro dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="451be-201">The workflow should now look like this:</span></span>  
  
     ![Aggiunta del Client: Iniziare le attività Send](./media/flowing-transactions-into-and-out-of-workflow-services/client-add-cbs-writeline.jpg)  
  
8.  <span data-ttu-id="451be-203">Trascinare un'attività <xref:System.ServiceModel.Activities.Send> dopo l'attività <xref:System.Activities.Statements.Assign> e impostare le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="451be-203">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="451be-204">Proprietà</span><span class="sxs-lookup"><span data-stu-id="451be-204">Property</span></span>|<span data-ttu-id="451be-205">Value</span><span class="sxs-lookup"><span data-stu-id="451be-205">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="451be-206">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="451be-206">EndpointConfigurationName</span></span>|<span data-ttu-id="451be-207">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="451be-207">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="451be-208">OperationName</span><span class="sxs-lookup"><span data-stu-id="451be-208">OperationName</span></span>|<span data-ttu-id="451be-209">StartSample</span><span class="sxs-lookup"><span data-stu-id="451be-209">StartSample</span></span>|  
    |<span data-ttu-id="451be-210">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="451be-210">ServiceContractName</span></span>|<span data-ttu-id="451be-211">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="451be-211">ITransactionSample</span></span>|  
  
     <span data-ttu-id="451be-212">Il flusso di lavoro dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="451be-212">The workflow should now look like this:</span></span>  
  
     ![Impostazione delle proprietà dell'attività Send](./media/flowing-transactions-into-and-out-of-workflow-services/client-send-activity-settings.jpg)  
  
9. <span data-ttu-id="451be-214">Fare clic su di **definire...**  collegare e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="451be-214">Click the **Define...** link and make the following settings:</span></span>  
  
     ![Impostazioni del messaggio dell'attività Send](./media/flowing-transactions-into-and-out-of-workflow-services/send-message-settings.jpg)  
  
10. <span data-ttu-id="451be-216">Fare clic il <xref:System.ServiceModel.Activities.Send> attività e selezionare **crea ReceiveReply**.</span><span class="sxs-lookup"><span data-stu-id="451be-216">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="451be-217">L'attività <xref:System.ServiceModel.Activities.ReceiveReply> sarà posizionata automaticamente dopo l'attività <xref:System.ServiceModel.Activities.Send>.</span><span class="sxs-lookup"><span data-stu-id="451be-217">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="451be-218">Fare clic sul collegamento Definisci nell'attività ReceiveReplyForSend e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="451be-218">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     ![Configurazione delle impostazioni del messaggio per ReceiveForSend](./media/flowing-transactions-into-and-out-of-workflow-services/client-reply-message-settings.jpg)  
  
12. <span data-ttu-id="451be-220">Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività tra il <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.ReceiveReply> attività e set relativo <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà su "Client: Invia completo".</span><span class="sxs-lookup"><span data-stu-id="451be-220">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="451be-221">Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività dopo il <xref:System.ServiceModel.Activities.ReceiveReply> attività e set relativo <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà "lato Client: Risposta ricevuta = "+ replyMessage</span><span class="sxs-lookup"><span data-stu-id="451be-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="451be-222">Trascinare un'attività `PrintTransactionInfo` dopo l'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="451be-222">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="451be-223">Trascinare un'attività <xref:System.Activities.Statements.WriteLine> alla fine del flusso di lavoro e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su "Client workflow ends".</span><span class="sxs-lookup"><span data-stu-id="451be-223">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="451be-224">Il flusso di lavoro client completato viene visualizzato come illustrato del diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="451be-224">The completed client workflow should look like the following diagram.</span></span>  
  
     ![Flusso di lavoro del client completato](./media/flowing-transactions-into-and-out-of-workflow-services/client-complete-workflow.jpg)  
  
16. <span data-ttu-id="451be-226">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="451be-226">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="451be-227">Creare l'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="451be-227">Create the Service application</span></span>  
  
1.  <span data-ttu-id="451be-228">Aggiungere un nuovo progetto Applicazione console denominato `Service` alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="451be-228">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="451be-229">Aggiungere riferimenti agli assembly riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="451be-229">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="451be-230">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="451be-230">System.Activities.dll</span></span>  
  
    2.  <span data-ttu-id="451be-231">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="451be-231">System.ServiceModel.dll</span></span>  
  
    3.  <span data-ttu-id="451be-232">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="451be-232">System.ServiceModel.Activities.dll</span></span>  
  
2.  <span data-ttu-id="451be-233">Aprire il file Program.cs generato e il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="451be-233">Open the generated Program.cs file and the following code:</span></span>  
  
    ```  
    static void Main()  
          {  
              Console.WriteLine("Building the server.");  
              using (WorkflowServiceHost host = new WorkflowServiceHost(new DeclarativeServiceWorkflow(), new Uri("net.tcp://localhost:8000/TransactedReceiveService/Declarative")))  
              {                
                  //Start the server  
                  host.Open();  
                  Console.WriteLine("Service started.");  
  
                  Console.WriteLine();  
                  Console.ReadLine();  
                  //Shutdown  
                  host.Close();  
              };         
          }  
    ```  
  
3.  <span data-ttu-id="451be-234">Aggiungere il file app.config seguente al progetto.</span><span class="sxs-lookup"><span data-stu-id="451be-234">Add the following app.config file to the project.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <!-- Copyright © Microsoft Corporation.  All rights reserved. -->  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding transactionFlow="true" />  
                </netTcpBinding>  
            </bindings>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="create-the-client-application"></a><span data-ttu-id="451be-235">Creare l'applicazione client</span><span class="sxs-lookup"><span data-stu-id="451be-235">Create the client application</span></span>  
  
1.  <span data-ttu-id="451be-236">Aggiungere un nuovo progetto Applicazione console denominato `Client` alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="451be-236">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="451be-237">Aggiungere un riferimento a System.Activities.dll.</span><span class="sxs-lookup"><span data-stu-id="451be-237">Add a reference to System.Activities.dll.</span></span>  
  
2.  <span data-ttu-id="451be-238">Aprire il file program.cs e aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="451be-238">Open the program.cs file and add the following code.</span></span>  
  
    ```  
    class Program  
        {  
  
            private static AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
            static void Main(string[] args)  
            {  
                //Build client  
                Console.WriteLine("Building the client.");  
                WorkflowApplication client = new WorkflowApplication(new DeclarativeClientWorkflow());  
                client.Completed = Program.Completed;  
                client.Aborted = Program.Aborted;  
                client.OnUnhandledException = Program.OnUnhandledException;  
  
                //Wait for service to start  
                Console.WriteLine("Press ENTER once service is started.");  
                Console.ReadLine();  
  
                //Start the client              
                Console.WriteLine("Starting the client.");  
                client.Run();  
                syncEvent.WaitOne();  
  
                //Sample complete  
                Console.WriteLine();  
                Console.WriteLine("Client complete. Press ENTER to exit.");  
                Console.ReadLine();  
            }  
  
            private static void Completed(WorkflowApplicationCompletedEventArgs e)  
            {  
                Program.syncEvent.Set();  
            }  
  
            private static void Aborted(WorkflowApplicationAbortedEventArgs e)  
            {  
                Console.WriteLine("Client Aborted: {0}", e.Reason);  
                Program.syncEvent.Set();  
            }  
  
            private static UnhandledExceptionAction OnUnhandledException(WorkflowApplicationUnhandledExceptionEventArgs e)  
            {  
                Console.WriteLine("Client had an unhandled exception: {0}", e.UnhandledException);  
                return UnhandledExceptionAction.Cancel;  
            }  
        }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="451be-239">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="451be-239">See also</span></span>

- [<span data-ttu-id="451be-240">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="451be-240">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="451be-241">Panoramica delle transazioni di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="451be-241">Windows Communication Foundation Transactions Overview</span></span>](../../../../docs/framework/wcf/feature-details/transactions-overview.md)
