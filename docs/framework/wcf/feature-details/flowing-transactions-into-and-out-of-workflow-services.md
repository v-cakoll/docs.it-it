---
title: Propagazione di transazioni all'interno e all'esterno di servizi flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: 8b3d3e85b626d033c9ab50e93e3ceb3b86058a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496097"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="05a1b-102">Propagazione di transazioni all'interno e all'esterno di servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="05a1b-102">Flowing Transactions into and out of Workflow Services</span></span>
<span data-ttu-id="05a1b-103">Servizi e client del flusso di lavoro possono partecipare alle transazioni.</span><span class="sxs-lookup"><span data-stu-id="05a1b-103">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="05a1b-104">Affinché un'operazione del servizio diventi parte di una transazione di ambiente, posizionare un'attività <xref:System.ServiceModel.Activities.Receive> all'interno di un'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="05a1b-104">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="05a1b-105">Qualsiasi chiamata effettuata da un'attività <xref:System.ServiceModel.Activities.Send> o un'attività <xref:System.ServiceModel.Activities.SendReply> all'interno di <xref:System.ServiceModel.Activities.TransactedReceiveScope> verrà effettuata anche all'interno della transazione di ambiente.</span><span class="sxs-lookup"><span data-stu-id="05a1b-105">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="05a1b-106">Un'applicazione client del flusso di lavoro può creare una transazione di ambiente tramite l'attività <xref:System.Activities.Statements.TransactionScope> e chiamare operazioni del servizio utilizzando la transazione di ambiente.</span><span class="sxs-lookup"><span data-stu-id="05a1b-106">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="05a1b-107">In questo argomento viene illustrato il processo di creazione di un servizio flusso di lavoro e di un client flusso di lavoro che partecipano a transazioni.</span><span class="sxs-lookup"><span data-stu-id="05a1b-107">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="05a1b-108">Se un'istanza del servizio flusso di lavoro viene caricata all'interno di una transazione e il flusso di lavoro contiene un'attività <xref:System.Activities.Statements.Persist>, l'istanza del flusso di lavoro verrà interrotta finché non si verifica il timeout della transazione.</span><span class="sxs-lookup"><span data-stu-id="05a1b-108">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will hang until the transaction times out.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="05a1b-109">Ogni volta che si utilizza un oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope>, è consigliabile posizionare tutte le attività Receive del flusso di lavoro all'interno delle attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="05a1b-109">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="05a1b-110">Quando si utilizza l'oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope> e i messaggi arrivano nell'ordine non corretto, il flusso di lavoro verrà interrotto quando si tenterà di consegnare il primo messaggio nell'ordine non corretto.</span><span class="sxs-lookup"><span data-stu-id="05a1b-110">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="05a1b-111">È necessario assicurarsi che il flusso di lavoro sia sempre in corrispondenza di un punto di interruzione coerente quando il flusso di lavoro è inattivo.</span><span class="sxs-lookup"><span data-stu-id="05a1b-111">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="05a1b-112">In questo modo sarà possibile riavviare il flusso di lavoro da un punto di persistenza precedente nel caso in cui il flusso di lavoro venga interrotto.</span><span class="sxs-lookup"><span data-stu-id="05a1b-112">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="05a1b-113">Creare una libreria condivisa</span><span class="sxs-lookup"><span data-stu-id="05a1b-113">Create a shared library</span></span>  
  
1.  <span data-ttu-id="05a1b-114">Creare una nuova soluzione Visual Studio vuota.</span><span class="sxs-lookup"><span data-stu-id="05a1b-114">Create a new empty Visual Studio Solution.</span></span>  
  
2.  <span data-ttu-id="05a1b-115">Aggiungere un nuovo progetto della libreria di classi denominato `Common`.</span><span class="sxs-lookup"><span data-stu-id="05a1b-115">Add a new class library project called `Common`.</span></span> <span data-ttu-id="05a1b-116">Aggiungere riferimenti agli assembly riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="05a1b-116">Add references to the following assemblies:</span></span>  
  
    -   <span data-ttu-id="05a1b-117">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="05a1b-117">System.Activities.dll</span></span>  
  
    -   <span data-ttu-id="05a1b-118">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="05a1b-118">System.ServiceModel.dll</span></span>  
  
    -   <span data-ttu-id="05a1b-119">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="05a1b-119">System.ServiceModel.Activities.dll</span></span>  
  
    -   <span data-ttu-id="05a1b-120">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="05a1b-120">System.Transactions.dll</span></span>  
  
3.  <span data-ttu-id="05a1b-121">Aggiungere una nuova classe denominata `PrintTransactionInfo` al progetto `Common`.</span><span class="sxs-lookup"><span data-stu-id="05a1b-121">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="05a1b-122">Questa classe è derivata da <xref:System.Activities.NativeActivity> ed esegue l'overload del metodo <xref:System.Activities.NativeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="05a1b-122">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
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
  
     <span data-ttu-id="05a1b-123">Si tratta di un'attività nativa che visualizza informazioni sulla transazione di ambiente e viene utilizzata sia nei flussi di lavoro del servizio che del client utilizzati nel presente argomento.</span><span class="sxs-lookup"><span data-stu-id="05a1b-123">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="05a1b-124">Compilare la soluzione per rendere disponibile in questa attività il **comuni** sezione la **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="05a1b-124">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="05a1b-125">Implementare il servizio di flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="05a1b-125">Implement the workflow service</span></span>  
  
1.  <span data-ttu-id="05a1b-126">Aggiungere un nuovo servizio di flusso di lavoro WCF, denominato `WorkflowService` per il `Common` progetto.</span><span class="sxs-lookup"><span data-stu-id="05a1b-126">Add a new WCF Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="05a1b-127">Per eseguire questa operazione destra il `Common` progetto, selezionare **Aggiungi**, **nuovo elemento...** Selezionare **flusso di lavoro** in **modelli installati** e selezionare **servizio flusso di lavoro WCF**.</span><span class="sxs-lookup"><span data-stu-id="05a1b-127">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     <span data-ttu-id="05a1b-128">![Aggiunta di un servizio flusso di lavoro](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")</span><span class="sxs-lookup"><span data-stu-id="05a1b-128">![Adding a Workflow Service](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")</span></span>  
  
2.  <span data-ttu-id="05a1b-129">Eliminare le attività `ReceiveRequest` e `SendResponse` predefinite.</span><span class="sxs-lookup"><span data-stu-id="05a1b-129">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3.  <span data-ttu-id="05a1b-130">Trascinare un'attività <xref:System.Activities.Statements.WriteLine> nell'attività `Sequential Service`.</span><span class="sxs-lookup"><span data-stu-id="05a1b-130">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="05a1b-131">Impostare la proprietà Text su `"Workflow Service starting ..."` come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="05a1b-131">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="05a1b-132">![Aggiunta di un'attività WriteLine](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")</span><span class="sxs-lookup"><span data-stu-id="05a1b-132">![Adding a WriteLine activity](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")</span></span>  
  
4.  <span data-ttu-id="05a1b-133">Trascinare un'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope> dopo l'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="05a1b-133">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="05a1b-134">Il <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività, vedere il **messaggistica** sezione del **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="05a1b-134">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="05a1b-135">Il <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività è costituita da due sezioni **richiesta** e **corpo**.</span><span class="sxs-lookup"><span data-stu-id="05a1b-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="05a1b-136">Il **richiesta** sezione sono contenuti il <xref:System.ServiceModel.Activities.Receive> attività.</span><span class="sxs-lookup"><span data-stu-id="05a1b-136">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="05a1b-137">Il **corpo** sezione contiene le attività da eseguire all'interno di una transazione dopo è stato ricevuto un messaggio.</span><span class="sxs-lookup"><span data-stu-id="05a1b-137">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     <span data-ttu-id="05a1b-138">![Aggiunta di un'attività TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")</span><span class="sxs-lookup"><span data-stu-id="05a1b-138">![Adding a TransactedReceiveScope activity](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")</span></span>  
  
5.  <span data-ttu-id="05a1b-139">Selezionare il <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività e fare clic su di **variabili** pulsante.</span><span class="sxs-lookup"><span data-stu-id="05a1b-139">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="05a1b-140">Aggiungere le variabili seguenti.</span><span class="sxs-lookup"><span data-stu-id="05a1b-140">Add the following variables.</span></span>  
  
     <span data-ttu-id="05a1b-141">![Aggiunta di variabili a TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")</span><span class="sxs-lookup"><span data-stu-id="05a1b-141">![Adding Variables to the TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05a1b-142">È possibile eliminare la variabile relativa ai dati, presente per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="05a1b-142">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="05a1b-143">È possibile utilizzare anche la variabile dell'handle esistente.</span><span class="sxs-lookup"><span data-stu-id="05a1b-143">You can also use the existing handle variable.</span></span>  
  
6.  <span data-ttu-id="05a1b-144">Trascinare e rilasciare un <xref:System.ServiceModel.Activities.Receive> attività all'interno di **richiesta** sezione del <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività.</span><span class="sxs-lookup"><span data-stu-id="05a1b-144">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="05a1b-145">Impostare le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="05a1b-145">Set the following properties:</span></span>  
  
    |<span data-ttu-id="05a1b-146">Proprietà</span><span class="sxs-lookup"><span data-stu-id="05a1b-146">Property</span></span>|<span data-ttu-id="05a1b-147">Valore</span><span class="sxs-lookup"><span data-stu-id="05a1b-147">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="05a1b-148">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="05a1b-148">CanCreateInstance</span></span>|<span data-ttu-id="05a1b-149">True (controllare la casella di controllo)</span><span class="sxs-lookup"><span data-stu-id="05a1b-149">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="05a1b-150">OperationName</span><span class="sxs-lookup"><span data-stu-id="05a1b-150">OperationName</span></span>|<span data-ttu-id="05a1b-151">StartSample</span><span class="sxs-lookup"><span data-stu-id="05a1b-151">StartSample</span></span>|  
    |<span data-ttu-id="05a1b-152">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="05a1b-152">ServiceContractName</span></span>|<span data-ttu-id="05a1b-153">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="05a1b-153">ITransactionSample</span></span>|  
  
     <span data-ttu-id="05a1b-154">Il flusso di lavoro dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="05a1b-154">The workflow should look like this:</span></span>  
  
     <span data-ttu-id="05a1b-155">![Aggiunta di un'attività Receive](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")</span><span class="sxs-lookup"><span data-stu-id="05a1b-155">![Adding a Receive activity](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")</span></span>  
  
7.  <span data-ttu-id="05a1b-156">Fare clic su di **definire...**  collegare il <xref:System.ServiceModel.Activities.Receive> attività e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05a1b-156">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     <span data-ttu-id="05a1b-157">![Configurazione delle impostazioni di messaggio per l'attività Receive](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="05a1b-157">![Setting message settings for the Recieve activity](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")</span></span>  
  
8.  <span data-ttu-id="05a1b-158">Trascinare un'attività <xref:System.Activities.Statements.Sequence> nella sezione Corpo di <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="05a1b-158">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="05a1b-159">All'interno dell'attività <xref:System.Activities.Statements.Sequence>, trascinare due attività <xref:System.Activities.Statements.WriteLine> e impostare le proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="05a1b-159">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="05a1b-160">Attività</span><span class="sxs-lookup"><span data-stu-id="05a1b-160">Activity</span></span>|<span data-ttu-id="05a1b-161">Valore</span><span class="sxs-lookup"><span data-stu-id="05a1b-161">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="05a1b-162">WriteLine 1</span><span class="sxs-lookup"><span data-stu-id="05a1b-162">1st WriteLine</span></span>|<span data-ttu-id="05a1b-163">"Servizio: ricezione completato"</span><span class="sxs-lookup"><span data-stu-id="05a1b-163">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="05a1b-164">WriteLine 2</span><span class="sxs-lookup"><span data-stu-id="05a1b-164">2nd WriteLine</span></span>|<span data-ttu-id="05a1b-165">"Service: Received = " + requestMessage</span><span class="sxs-lookup"><span data-stu-id="05a1b-165">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="05a1b-166">Il flusso di lavoro dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="05a1b-166">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="05a1b-167">![Aggiunta di attività WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")</span><span class="sxs-lookup"><span data-stu-id="05a1b-167">![Adding WriteLine activities](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")</span></span>  
  
9. <span data-ttu-id="05a1b-168">Trascinare e rilasciare il `PrintTransactionInfo` attività dopo la seconda <xref:System.Activities.Statements.WriteLine> attività il **corpo** nel <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività.</span><span class="sxs-lookup"><span data-stu-id="05a1b-168">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     <span data-ttu-id="05a1b-169">![Dopo avere aggiunto PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")</span><span class="sxs-lookup"><span data-stu-id="05a1b-169">![After adding PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")</span></span>  
  
10. <span data-ttu-id="05a1b-170">Trascinare un'attività <xref:System.Activities.Statements.Assign> dopo l'attività `PrintTransactionInfo` e impostarne le proprietà in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="05a1b-170">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="05a1b-171">Proprietà</span><span class="sxs-lookup"><span data-stu-id="05a1b-171">Property</span></span>|<span data-ttu-id="05a1b-172">Valore</span><span class="sxs-lookup"><span data-stu-id="05a1b-172">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="05a1b-173">A</span><span class="sxs-lookup"><span data-stu-id="05a1b-173">To</span></span>|<span data-ttu-id="05a1b-174">replyMessage</span><span class="sxs-lookup"><span data-stu-id="05a1b-174">replyMessage</span></span>|  
    |<span data-ttu-id="05a1b-175">Valore</span><span class="sxs-lookup"><span data-stu-id="05a1b-175">Value</span></span>|<span data-ttu-id="05a1b-176">"Service: Sending reply".</span><span class="sxs-lookup"><span data-stu-id="05a1b-176">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="05a1b-177">Trascinare un'attività <xref:System.Activities.Statements.WriteLine> dopo l'attività <xref:System.Activities.Statements.Assign> e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su "Service: Begin reply".</span><span class="sxs-lookup"><span data-stu-id="05a1b-177">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="05a1b-178">Il flusso di lavoro dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="05a1b-178">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="05a1b-179">![Dopo avere aggiunto Assign e WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")</span><span class="sxs-lookup"><span data-stu-id="05a1b-179">![After adding Assign and WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")</span></span>  
  
12. <span data-ttu-id="05a1b-180">Fare clic destro la <xref:System.ServiceModel.Activities.Receive> attività e selezionare **crea SendReply** e incollarla dopo l'ultimo <xref:System.Activities.Statements.WriteLine> attività.</span><span class="sxs-lookup"><span data-stu-id="05a1b-180">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="05a1b-181">Fare clic su di **definire...**  collegare il `SendReplyToReceive` attività e configurare le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="05a1b-181">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     <span data-ttu-id="05a1b-182">![Impostazioni del messaggio di risposta](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="05a1b-182">![Reply message settings](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")</span></span>  
  
13. <span data-ttu-id="05a1b-183">Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività dopo il `SendReplyToReceive` attività e impostare ha <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà per "servizio: Reply sent."</span><span class="sxs-lookup"><span data-stu-id="05a1b-183">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="05a1b-184">Trascinare un'attività <xref:System.Activities.Statements.WriteLine> nella parte inferiore del flusso di lavoro e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su "Service: Workflow ends, press ENTER to exit".</span><span class="sxs-lookup"><span data-stu-id="05a1b-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="05a1b-185">Il flusso di lavoro del servizio completato dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="05a1b-185">The completed service workflow should look like this:</span></span>  
  
     <span data-ttu-id="05a1b-186">![Completamento del flusso di lavoro di servizio](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")</span><span class="sxs-lookup"><span data-stu-id="05a1b-186">![Complete Service Workflow](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")</span></span>  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="05a1b-187">Implementare il client flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="05a1b-187">Implement the workflow client</span></span>  
  
1.  <span data-ttu-id="05a1b-188">Aggiungere una nuova applicazione flusso di lavoro WCF, denominata `WorkflowClient`, al progetto `Common`.</span><span class="sxs-lookup"><span data-stu-id="05a1b-188">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="05a1b-189">Per eseguire questa operazione destra il `Common` progetto, selezionare **Aggiungi**, **nuovo elemento...** Selezionare **flusso di lavoro** in **modelli installati** e selezionare **attività**.</span><span class="sxs-lookup"><span data-stu-id="05a1b-189">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     <span data-ttu-id="05a1b-190">![Aggiungere un progetto di attività](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")</span><span class="sxs-lookup"><span data-stu-id="05a1b-190">![Add an Activity project](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")</span></span>  
  
2.  <span data-ttu-id="05a1b-191">Trascinare un'attività <xref:System.Activities.Statements.Sequence> sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="05a1b-191">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3.  <span data-ttu-id="05a1b-192">All'interno dell'attività <xref:System.Activities.Statements.Sequence>, trascinare un'attività <xref:System.Activities.Statements.WriteLine> e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su `"Client: Workflow starting"`.</span><span class="sxs-lookup"><span data-stu-id="05a1b-192">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="05a1b-193">Il flusso di lavoro dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="05a1b-193">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="05a1b-194">![Aggiungere un'attività WriteLine](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")</span><span class="sxs-lookup"><span data-stu-id="05a1b-194">![Add a WriteLine activity](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")</span></span>  
  
4.  <span data-ttu-id="05a1b-195">Trascinare un'attività <xref:System.Activities.Statements.TransactionScope> dopo l'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="05a1b-195">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="05a1b-196">Selezionare l'attività <xref:System.Activities.Statements.TransactionScope>, fare clic sul pulsante Variabili e aggiungere le variabili seguenti.</span><span class="sxs-lookup"><span data-stu-id="05a1b-196">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     <span data-ttu-id="05a1b-197">![Aggiungere variabili a TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")</span><span class="sxs-lookup"><span data-stu-id="05a1b-197">![Add variables to the TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")</span></span>  
  
5.  <span data-ttu-id="05a1b-198">Trascinare un'attività <xref:System.Activities.Statements.Sequence> nel corpo dell'attività <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="05a1b-198">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6.  <span data-ttu-id="05a1b-199">Trascinare un'attività `PrintTransactionInfo` all'interno dell'attività <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="05a1b-199">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7.  <span data-ttu-id="05a1b-200">Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività dopo il `PrintTransactionInfo` attività e impostare il relativo <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà su "Client: Beginning Send".</span><span class="sxs-lookup"><span data-stu-id="05a1b-200">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="05a1b-201">Il flusso di lavoro dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="05a1b-201">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="05a1b-202">![Aggiunta di attività](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")</span><span class="sxs-lookup"><span data-stu-id="05a1b-202">![Adding activities](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")</span></span>  
  
8.  <span data-ttu-id="05a1b-203">Trascinare un'attività <xref:System.ServiceModel.Activities.Send> dopo l'attività <xref:System.Activities.Statements.Assign> e impostare le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="05a1b-203">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="05a1b-204">Proprietà</span><span class="sxs-lookup"><span data-stu-id="05a1b-204">Property</span></span>|<span data-ttu-id="05a1b-205">Valore</span><span class="sxs-lookup"><span data-stu-id="05a1b-205">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="05a1b-206">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="05a1b-206">EndpointConfigurationName</span></span>|<span data-ttu-id="05a1b-207">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="05a1b-207">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="05a1b-208">OperationName</span><span class="sxs-lookup"><span data-stu-id="05a1b-208">OperationName</span></span>|<span data-ttu-id="05a1b-209">StartSample</span><span class="sxs-lookup"><span data-stu-id="05a1b-209">StartSample</span></span>|  
    |<span data-ttu-id="05a1b-210">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="05a1b-210">ServiceContractName</span></span>|<span data-ttu-id="05a1b-211">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="05a1b-211">ITransactionSample</span></span>|  
  
     <span data-ttu-id="05a1b-212">Il flusso di lavoro dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="05a1b-212">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="05a1b-213">![L'impostazione di proprietà dell'attività Send](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")</span><span class="sxs-lookup"><span data-stu-id="05a1b-213">![Setting the Send activity properties](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")</span></span>  
  
9. <span data-ttu-id="05a1b-214">Fare clic su di **definire...**  collegare e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05a1b-214">Click the **Define...** link and make the following settings:</span></span>  
  
     <span data-ttu-id="05a1b-215">![Impostazioni del messaggio attività Send](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="05a1b-215">![Send activity message settings](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")</span></span>  
  
10. <span data-ttu-id="05a1b-216">Fare clic destro la <xref:System.ServiceModel.Activities.Send> attività e selezionare **crea ReceiveReply**.</span><span class="sxs-lookup"><span data-stu-id="05a1b-216">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="05a1b-217">L'attività <xref:System.ServiceModel.Activities.ReceiveReply> sarà posizionata automaticamente dopo l'attività <xref:System.ServiceModel.Activities.Send>.</span><span class="sxs-lookup"><span data-stu-id="05a1b-217">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="05a1b-218">Fare clic sul collegamento Definisci nell'attività ReceiveReplyForSend e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="05a1b-218">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     <span data-ttu-id="05a1b-219">![L'impostazione di impostazioni del messaggio ReceiveForSend](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="05a1b-219">![Setting the ReceiveForSend message settings](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")</span></span>  
  
12. <span data-ttu-id="05a1b-220">Trascinare un'attività <xref:System.Activities.Statements.WriteLine> tra le attività <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.ReceiveReply> e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su "Client: Send complete".</span><span class="sxs-lookup"><span data-stu-id="05a1b-220">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="05a1b-221">Trascinare un'attività <xref:System.Activities.Statements.WriteLine> dopo l'attività <xref:System.ServiceModel.Activities.ReceiveReply> e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su "Client side: Reply received = " + replyMessage</span><span class="sxs-lookup"><span data-stu-id="05a1b-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="05a1b-222">Trascinare un'attività `PrintTransactionInfo` dopo l'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="05a1b-222">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="05a1b-223">Trascinare un'attività <xref:System.Activities.Statements.WriteLine> alla fine del flusso di lavoro e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su "Client workflow ends".</span><span class="sxs-lookup"><span data-stu-id="05a1b-223">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="05a1b-224">Il flusso di lavoro client completato viene visualizzato come illustrato del diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="05a1b-224">The completed client workflow should look like the following diagram.</span></span>  
  
     <span data-ttu-id="05a1b-225">![Il workfliow client completate](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")</span><span class="sxs-lookup"><span data-stu-id="05a1b-225">![The completed client workfliow](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")</span></span>  
  
16. <span data-ttu-id="05a1b-226">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="05a1b-226">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="05a1b-227">Creare l'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="05a1b-227">Create the Service application</span></span>  
  
1.  <span data-ttu-id="05a1b-228">Aggiungere un nuovo progetto Applicazione console denominato `Service` alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="05a1b-228">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="05a1b-229">Aggiungere riferimenti agli assembly riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="05a1b-229">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="05a1b-230">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="05a1b-230">System.Activities.dll</span></span>  
  
    2.  <span data-ttu-id="05a1b-231">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="05a1b-231">System.ServiceModel.dll</span></span>  
  
    3.  <span data-ttu-id="05a1b-232">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="05a1b-232">System.ServiceModel.Activities.dll</span></span>  
  
2.  <span data-ttu-id="05a1b-233">Aprire il file Program.cs generato e il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="05a1b-233">Open the generated Program.cs file and the following code:</span></span>  
  
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
  
3.  <span data-ttu-id="05a1b-234">Aggiungere il file app.config seguente al progetto.</span><span class="sxs-lookup"><span data-stu-id="05a1b-234">Add the following app.config file to the project.</span></span>  
  
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
  
### <a name="create-the-client-application"></a><span data-ttu-id="05a1b-235">Creare l'applicazione client</span><span class="sxs-lookup"><span data-stu-id="05a1b-235">Create the client application</span></span>  
  
1.  <span data-ttu-id="05a1b-236">Aggiungere un nuovo progetto Applicazione console denominato `Client` alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="05a1b-236">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="05a1b-237">Aggiungere un riferimento a System.Activities.dll.</span><span class="sxs-lookup"><span data-stu-id="05a1b-237">Add a reference to System.Activities.dll.</span></span>  
  
2.  <span data-ttu-id="05a1b-238">Aprire il file program.cs e aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="05a1b-238">Open the program.cs file and add the following code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="05a1b-239">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05a1b-239">See Also</span></span>  
 [<span data-ttu-id="05a1b-240">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="05a1b-240">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="05a1b-241">Panoramica delle transazioni di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="05a1b-241">Windows Communication Foundation Transactions Overview</span></span>](../../../../docs/framework/wcf/feature-details/transactions-overview.md)  
 [<span data-ttu-id="05a1b-242">Uso di TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="05a1b-242">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)
