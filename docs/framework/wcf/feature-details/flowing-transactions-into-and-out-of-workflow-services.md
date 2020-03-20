---
title: Propagazione di transazioni all'interno e all'esterno di servizi flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: fe03047dd931d25ec94bbc5e00c479d1b42397bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185270"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a>Propagazione di transazioni all'interno e all'esterno di servizi flusso di lavoro
Servizi e client del flusso di lavoro possono partecipare alle transazioni.  Affinché un'operazione del servizio diventi parte di una transazione di ambiente, posizionare un'attività <xref:System.ServiceModel.Activities.Receive> all'interno di un'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Qualsiasi chiamata effettuata da un'attività <xref:System.ServiceModel.Activities.Send> o un'attività <xref:System.ServiceModel.Activities.SendReply> all'interno di <xref:System.ServiceModel.Activities.TransactedReceiveScope> verrà effettuata anche all'interno della transazione di ambiente. Un'applicazione client del flusso di lavoro può creare una transazione di ambiente tramite l'attività <xref:System.Activities.Statements.TransactionScope> e chiamare operazioni del servizio utilizzando la transazione di ambiente. In questo argomento viene illustrato il processo di creazione di un servizio flusso di lavoro e di un client flusso di lavoro che partecipano a transazioni.  
  
> [!WARNING]
> Se un'istanza del servizio flusso di lavoro <xref:System.Activities.Statements.Persist> viene caricata all'interno di una transazione e il flusso di lavoro contiene un'attività, l'istanza del flusso di lavoro si bloccherà fino al timeout della transazione.  
  
> [!IMPORTANT]
> Ogni volta che si utilizza un oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope>, è consigliabile posizionare tutte le attività Receive del flusso di lavoro all'interno delle attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>.  
  
> [!IMPORTANT]
> Quando si utilizza l'oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope> e i messaggi arrivano nell'ordine non corretto, il flusso di lavoro verrà interrotto quando si tenterà di consegnare il primo messaggio nell'ordine non corretto. È necessario assicurarsi che il flusso di lavoro sia sempre in corrispondenza di un punto di interruzione coerente quando il flusso di lavoro è inattivo. In questo modo sarà possibile riavviare il flusso di lavoro da un punto di persistenza precedente nel caso in cui il flusso di lavoro venga interrotto.  
  
### <a name="create-a-shared-library"></a>Creare una libreria condivisa  
  
1. Creare una nuova soluzione Visual Studio vuota.  
  
2. Aggiungere un nuovo progetto della libreria di classi denominato `Common`. Aggiungere riferimenti agli assembly riportati di seguito:  
  
    - System.Activities.dll  
  
    - System.ServiceModel.dll  
  
    - System.ServiceModel.Activities.dll  
  
    - System.Transactions.dll  
  
3. Aggiungere una nuova classe denominata `PrintTransactionInfo` al progetto `Common`. Questa classe è derivata da <xref:System.Activities.NativeActivity> ed esegue l'overload del metodo <xref:System.Activities.NativeActivity.Execute%2A>.  
  
    ```csharp
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
  
     Si tratta di un'attività nativa che visualizza informazioni sulla transazione di ambiente e viene utilizzata sia nei flussi di lavoro del servizio che del client utilizzati nel presente argomento. Compilare la soluzione per rendere disponibile questa attività nella sezione **Comune** della **Casella degli strumenti**.  
  
### <a name="implement-the-workflow-service"></a>Implementare il servizio di flusso di lavoro  
  
1. Aggiungere un nuovo servizio `WorkflowService` flusso `Common` di lavoro WCF, denominato al progetto. A tale scopo, `Common` fare clic con il pulsante destro del mouse sul progetto, scegliere **Aggiungi**, **Nuovo elemento ...**, Selezionare Flusso di **lavoro** in **Modelli installati** e selezionare Servizio flusso di **lavoro WCF**.  
  
     ![Aggiunta di un servizio flusso di lavoro](./media/flowing-transactions-into-and-out-of-workflow-services/add-workflow-service.jpg)  
  
2. Eliminare le attività `ReceiveRequest` e `SendResponse` predefinite.  
  
3. Trascinare e rilasciare un'attività <xref:System.Activities.Statements.WriteLine> nell'attività `Sequential Service`. Impostare la proprietà Text su `"Workflow Service starting ..."` come illustrato nell'esempio seguente.  
  
     ! [Aggiunta di un'attività WriteLine all'attività Sequential Service(./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg)  
  
4. Trascinare e rilasciare un'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope> dopo l'attività <xref:System.Activities.Statements.WriteLine>. L'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope> è disponibile nella sezione **Messaggistica** della **Casella degli strumenti**. L'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope> è composta da due sezioni **Richiesta** e **Corpo**. La **Request** sezione Richiesta <xref:System.ServiceModel.Activities.Receive> contiene l'attività. La sezione **Corpo** contiene le attività da eseguire all'interno di una transazione dopo la ricezione di un messaggio.  
  
     ![Aggiunta di un'attività TransactedReceiveScope](./media/flowing-transactions-into-and-out-of-workflow-services/transactedreceivescope-activity.jpg)  
  
5. Selezionare <xref:System.ServiceModel.Activities.TransactedReceiveScope> l'attività e fare clic sul pulsante **Variabili.** Aggiungere le variabili seguenti.  
  
     ![Aggiunta di variabili a TransactedReceiveScope](./media/flowing-transactions-into-and-out-of-workflow-services/add-transactedreceivescope-variables.jpg)  
  
    > [!NOTE]
    > È possibile eliminare la variabile relativa ai dati, presente per impostazione predefinita. È possibile utilizzare anche la variabile dell'handle esistente.  
  
6. Trascinare un'attività <xref:System.ServiceModel.Activities.Receive> all'interno <xref:System.ServiceModel.Activities.TransactedReceiveScope> della sezione **Richiesta** dell'attività. Impostare le proprietà seguenti:  
  
    |Proprietà|valore|  
    |--------------|-----------|  
    |CanCreateInstance|True (controllare la casella di controllo)|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     Il flusso di lavoro dovrebbe risultare analogo al seguente:  
  
     ![Aggiunta di un'attività Receive](./media/flowing-transactions-into-and-out-of-workflow-services/add-receive-activity.jpg)  
  
7. Fare clic sul collegamento <xref:System.ServiceModel.Activities.Receive> **Definisci...** nell'attività e definire le impostazioni seguenti:  
  
     ![Impostazione delle impostazioni dei messaggi per l'attività Receive](./media/flowing-transactions-into-and-out-of-workflow-services/receive-message-settings.jpg)  
  
8. Trascinare e rilasciare un'attività <xref:System.Activities.Statements.Sequence> nella sezione Corpo di <xref:System.ServiceModel.Activities.TransactedReceiveScope>. All'interno dell'attività <xref:System.Activities.Statements.Sequence>, trascinare e rilasciare due attività <xref:System.Activities.Statements.WriteLine> e impostare le proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> come illustrato nella tabella seguente.  
  
    |Attività|valore|  
    |--------------|-----------|  
    |WriteLine 1|"Servizio: Ricezione completato"|  
    |WriteLine 2|"Service: Received = " + requestMessage|  
  
     Il flusso di lavoro dovrebbe risultare analogo al seguente:  
  
     ![Sequenza dopo l'aggiunta di attività WriteLineSequence after adding WriteLine activities](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-writelines.jpg)  
  
9. Trascinare `PrintTransactionInfo` l'attività dopo <xref:System.Activities.Statements.WriteLine> la seconda attività <xref:System.ServiceModel.Activities.TransactedReceiveScope> nel **corpo** dell'attività.  
  
     ![Sequenza dopo l'aggiunta di PrintTransactionInfoSequence after adding PrintTransactionInfo](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-printtransactioninfo.jpg )  
  
10. Trascinare e rilasciare un'attività <xref:System.Activities.Statements.Assign> dopo l'attività `PrintTransactionInfo` e impostarne le proprietà in base alla tabella seguente.  
  
    |Proprietà|valore|  
    |--------------|-----------|  
    |A|replyMessage|  
    |valore|"Service: Sending reply".|  
  
11. Trascinare un'attività <xref:System.Activities.Statements.WriteLine> dopo l'attività <xref:System.Activities.Statements.Assign> e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su "Service: Begin reply".  
  
     Il flusso di lavoro dovrebbe risultare analogo al seguente:  
  
     ![Dopo avere aggiunto Assign e WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-sbr-writeline.jpg)  
  
12. Fare clic <xref:System.ServiceModel.Activities.Receive> con il pulsante destro del <xref:System.Activities.Statements.WriteLine> mouse sull'attività e selezionare **Crea SendReply** e incollarla dopo l'ultima attività. Fare clic sul collegamento `SendReplyToReceive` **Definisci...** nell'attività e apportare le impostazioni seguenti.  
  
     ![Impostazioni del messaggio di risposta](./media/flowing-transactions-into-and-out-of-workflow-services/reply-message-settings.jpg)  
  
13. Trascinare un'attività <xref:System.Activities.Statements.WriteLine> `SendReplyToReceive` dopo l'attività <xref:System.Activities.Statements.WriteLine.Text%2A> e impostarne la proprietà su "Servizio: Rispondi inviato".  
  
14. Trascinare un'attività <xref:System.Activities.Statements.WriteLine> nella parte inferiore del flusso di lavoro e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su "Service: Workflow ends, press ENTER to exit".  
  
     Il flusso di lavoro del servizio completato dovrebbe risultare analogo al seguente:  
  
     ![Flusso di lavoro del servizio completato](./media/flowing-transactions-into-and-out-of-workflow-services/service-complete-workflow.jpg)  
  
### <a name="implement-the-workflow-client"></a>Implementare il client flusso di lavoro  
  
1. Aggiungere una nuova applicazione flusso di lavoro WCF, denominata `WorkflowClient`, al progetto `Common`. A tale scopo, `Common` fare clic con il pulsante destro del mouse sul progetto, selezionare **Aggiungi**, **Nuovo elemento ...**, Selezionare Flusso di **lavoro** in **Modelli installati** e selezionare **Attività**.  
  
     ![Aggiungere un progetto di attività](./media/flowing-transactions-into-and-out-of-workflow-services/add-activity-project.jpg)  
  
2. Trascinare e rilasciare un'attività <xref:System.Activities.Statements.Sequence> sull'area di progettazione.  
  
3. All'interno dell'attività <xref:System.Activities.Statements.Sequence>, trascinare un'attività <xref:System.Activities.Statements.WriteLine> e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su `"Client: Workflow starting"`. Il flusso di lavoro dovrebbe risultare analogo al seguente:  
  
     ![Aggiungere un'attività WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-activity.jpg)  
  
4. Trascinare un'attività <xref:System.Activities.Statements.TransactionScope> dopo l'attività <xref:System.Activities.Statements.WriteLine>.  Selezionare l'attività <xref:System.Activities.Statements.TransactionScope>, fare clic sul pulsante Variabili e aggiungere le variabili seguenti.  
  
     ![Aggiungere variabili a TransactionScope](./media/flowing-transactions-into-and-out-of-workflow-services/transactionscope-variables.jpg)  
  
5. Trascinare e rilasciare un'attività <xref:System.Activities.Statements.Sequence> nel corpo dell'attività <xref:System.Activities.Statements.TransactionScope>.  
  
6. Trascinare e rilasciare un'attività `PrintTransactionInfo` all'interno dell'attività <xref:System.Activities.Statements.Sequence>.  
  
7. Trascinare e <xref:System.Activities.Statements.WriteLine> rilasciare `PrintTransactionInfo` un'attività <xref:System.Activities.Statements.WriteLine.Text%2A> dopo l'attività e impostarne la proprietà su "Client: Inizio invio". Il flusso di lavoro dovrebbe risultare analogo al seguente:  
  
     ![Aggiunta di un client: attività di invio inizialeAdding Client: Beginning Send activities](./media/flowing-transactions-into-and-out-of-workflow-services/client-add-cbs-writeline.jpg)  
  
8. Trascinare un'attività <xref:System.ServiceModel.Activities.Send> dopo l'attività <xref:System.Activities.Statements.Assign> e impostare le proprietà seguenti:  
  
    |Proprietà|valore|  
    |--------------|-----------|  
    |EndpointConfigurationName|workflowServiceEndpoint|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     Il flusso di lavoro dovrebbe risultare analogo al seguente:  
  
     ![Impostazione delle proprietà dell'attività Send](./media/flowing-transactions-into-and-out-of-workflow-services/client-send-activity-settings.jpg)  
  
9. Fare clic sul collegamento **Definisci...** e definire le seguenti impostazioni:  
  
     ![Impostazioni del messaggio dell'attività Send](./media/flowing-transactions-into-and-out-of-workflow-services/send-message-settings.jpg)  
  
10. Fare clic <xref:System.ServiceModel.Activities.Send> con il pulsante destro del mouse sull'attività e selezionare **Crea ReceiveReply**. L'attività <xref:System.ServiceModel.Activities.ReceiveReply> sarà posizionata automaticamente dopo l'attività <xref:System.ServiceModel.Activities.Send>.  
  
11. Fare clic sul collegamento Definisci nell'attività ReceiveReplyForSend e configurare le impostazioni seguenti:  
  
     ![Configurazione delle impostazioni del messaggio per ReceiveForSend](./media/flowing-transactions-into-and-out-of-workflow-services/client-reply-message-settings.jpg)  
  
12. Trascinare un'attività <xref:System.Activities.Statements.WriteLine> tra le attività <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.ReceiveReply> e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su "Client: Send complete".  
  
13. Trascinare e rilasciare un'attività <xref:System.Activities.Statements.WriteLine> dopo l'attività <xref:System.ServiceModel.Activities.ReceiveReply> e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su "Client side: Reply received = " + replyMessage  
  
14. Trascinare un'attività `PrintTransactionInfo` dopo l'attività <xref:System.Activities.Statements.WriteLine>.  
  
15. Trascinare un'attività <xref:System.Activities.Statements.WriteLine> alla fine del flusso di lavoro e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su "Client workflow ends". Il flusso di lavoro client completato viene visualizzato come illustrato del diagramma seguente.  
  
     ![Flusso di lavoro client completato](./media/flowing-transactions-into-and-out-of-workflow-services/client-complete-workflow.jpg)  
  
16. Compilare la soluzione.  
  
### <a name="create-the-service-application"></a>Creare l'applicazione di servizio  
  
1. Aggiungere un nuovo progetto Applicazione console denominato `Service` alla soluzione. Aggiungere riferimenti agli assembly riportati di seguito:  
  
    1. System.Activities.dll  
  
    2. System.ServiceModel.dll  
  
    3. System.ServiceModel.Activities.dll  
  
2. Aprire il file Program.cs generato e il codice seguente:  
  
    ```csharp
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
  
3. Aggiungere il file app.config seguente al progetto.  
  
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
  
### <a name="create-the-client-application"></a>Creare l'applicazione client  
  
1. Aggiungere un nuovo progetto Applicazione console denominato `Client` alla soluzione. Aggiungere un riferimento a System.Activities.dll.  
  
2. Aprire il file program.cs e aggiungere il codice seguente.  
  
    ```csharp
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
  
## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Panoramica sulle transazioni di Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/transactions-overview.md)
