---
title: Creazione di un servizio flusso di lavoro a esecuzione prolungata
ms.date: 03/30/2017
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
ms.openlocfilehash: 4ae01201230bf848c045158424db60097d8dd767
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599347"
---
# <a name="create-a-long-running-workflow-service"></a>Creazione di un servizio flusso di lavoro con esecuzione prolungata

In questo argomento viene descritto come creare un servizio di flusso di lavoro a esecuzione prolungata. L'esecuzione di tali servizi può durare molto tempo. A un certo punto, è possibile che il flusso di lavoro diventi inattivo a causa dell'attesa di informazioni aggiuntive. In tal caso, il flusso di lavoro viene salvato in modo permanente in un database SQL e rimosso dalla memoria. Quando le informazioni aggiuntive diventano disponibili, l'istanza del flusso di lavoro viene caricata di nuovo in memoria e ne viene continuata l'esecuzione.  In questo scenario viene implementato un sistema di ordini molto semplificato.  Per avviare la procedura di ordine, dal client viene inviato un messaggio iniziale al servizio di flusso di lavoro che, a sua volta, consente la restituzione di un ID ordine al client. A questo punto, a causa dell'attesa di un altro messaggio inviato dal client, il servizio di flusso di lavoro diventa inattivo e viene salvato in modo permanente in un database SQL Server.  Quando dal client viene inviato il messaggio successivo per ordinare un elemento, il servizio di flusso di lavoro viene caricato di nuovo in memoria consentendo il completamento dell'elaborazione dell'ordine. Nell'esempio di codice viene restituita una stringa in cui viene indicato che l'elemento è stato aggiunto all'ordine. L'esempio di codice non è stato ideato per corrispondere a un'applicazione reale della tecnologia, ma piuttosto per fornire un esempio semplice in cui vengono illustrati i servizi di flusso di lavoro a esecuzione prolungata. In questo argomento si presuppone che si sappia come creare progetti e soluzioni di Visual Studio 2012.

## <a name="prerequisites"></a>Prerequisiti

Per utilizzare questa procedura dettagliata è necessario aver installato i software seguenti:

1. Microsoft SQL Server 2008

2. Visual Studio 2012

3. Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]

4. Si ha familiarità con WCF e Visual Studio 2012 e si sa come creare progetti/soluzioni.

## <a name="set-up-the-sql-database"></a>Configurare il database SQL

1. Per salvare in modo permanente le istanze del servizio di flusso di lavoro è necessario disporre di Microsoft SQL Server e configurare un database per archiviare le istanze del flusso di lavoro salvate in modo permanente. Eseguire Microsoft SQL Management Studio facendo clic sul pulsante **Start** , selezionando **tutti i programmi**, **Microsoft SQL Server 2008**e **Microsoft SQL Management Studio**.

2. Fare clic sul pulsante **Connetti** per accedere all'istanza di SQL Server

3. Fare clic con il pulsante destro del mouse su **database** nella visualizzazione albero e selezionare **nuovo database.** per creare un nuovo database denominato `SQLPersistenceStore` .

4. Eseguire il file di script SqlWorkflowInstanceStoreSchema.sql presente nella directory C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en del database SQLPersistenceStore per configurare gli schemi del database necessari.

5. Eseguire il file di script SqlWorkflowInstanceStoreLogic.sql presente nella directory C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en del database SQLPersistenceStore per configurare la logica del database necessaria.

## <a name="create-the-web-hosted-workflow-service"></a>Creare il servizio del flusso di lavoro ospitato sul Web

1. Creare una soluzione Visual Studio 2012 vuota, denominarla `OrderProcessing` .

2. Aggiungere un nuovo progetto Applicazione di servizi flusso di lavoro WCF denominato `OrderService` alla soluzione.

3. Nella finestra di dialogo Proprietà progetto selezionare la scheda **Web** .

    1. In **azione di avvio** selezionare **pagina specifica** e specificare `Service1.xamlx` .

        ![Proprietà del progetto servizio Web flusso di lavoro](./media/creating-a-long-running-workflow-service/start-action-specific-page-option.png "Creare l'opzione di pagina specifica del servizio del flusso di lavoro ospitato sul Web")

    2. In **Server** selezionare **Usa server Web IIS locale**.

        ![Impostazioni dei server Web locali](./media/creating-a-long-running-workflow-service/use-local-web-server.png "Creare il servizio flusso di lavoro ospitato sul Web: usare l'opzione server Web IIS locale")

        > [!WARNING]
        > Per impostare questa impostazione, è necessario eseguire Visual Studio 2012 in modalità amministratore.

        Questi due passaggi consentono di configurare il progetto del servizio di flusso di lavoro che deve essere ospitato da IIS.

4. Aprire `Service1.xamlx` se non è già aperto ed eliminare le attività **ReceiveRequest** e **SendResponse** esistenti.

5. Selezionare l'attività **sequenziale del servizio** e fare clic sul collegamento **variabili** e aggiungere le variabili illustrate nella figura seguente. In questo modo verranno aggiunte alcune variabili che saranno utilizzate successivamente nel servizio di flusso di lavoro.

    > [!NOTE]
    > Se CorrelationHandle non è presente nell'elenco a discesa tipo di variabile, selezionare **Cerca tipi** dall'elenco a discesa. Digitare CorrelationHandle nella casella **nome tipo** , selezionare CorrelationHandle nella casella di riepilogo e fare clic su **OK**.

    ![Aggiungi variabili](./media/creating-a-long-running-workflow-service/add-variables-sequential-service-activity.gif "Aggiungere variabili all'attività sequenziale del servizio.")

6. Trascinare e rilasciare un modello di attività **ReceiveAndSendReply** nell'attività **sequenziale del servizio** . Un messaggio inviato da un client verrà ricevuto da questo set di attività tramite cui, a sua volta, verrà restituita una risposta.

    1. Selezionare l'attività **Receive** e impostare le proprietà evidenziate nella figura seguente.

        ![Impostare le proprietà dell'attività Receive](./media/creating-a-long-running-workflow-service/set-receive-activity-properties.png "Impostare le proprietà dell'attività Receive.")

        La proprietà DisplayName consente di impostare il nome visualizzato per l'attività Receive nella finestra di progettazione. Le proprietà ServiceContractName e OperationName specificano il nome del contratto di servizio e della relativa operazione implementati dall'attività Receive. Per ulteriori informazioni sul modo in cui vengono utilizzati i contratti nei servizi flusso di lavoro, vedere [utilizzo di contratti nel flusso di lavoro](using-contracts-in-workflow.md).

    2. Fare clic sul collegamento **Definisci** nell'attività **ReceiveStartOrder** e impostare le proprietà mostrate nella figura seguente.  Si noti che il pulsante di opzione **parametri** è selezionato, un parametro denominato `p_customerName` è associato alla `customerName` variabile. In questo modo l'attività **Receive** viene configurata in modo da ricevere alcuni dati e associare tali dati alle variabili locali.

        ![Impostazione dei dati ricevuti dall'attività di ricezione](./media/creating-a-long-running-workflow-service/set-properties-for-receive-content.png "Impostare le proprietà per i dati ricevuti dall'attività Receive.")

    3. Selezionare l'attività **SendReplyToReceive** e impostare la proprietà evidenziata mostrata nella figura seguente.

        ![Impostazione delle proprietà dell'attività SendReply](./media/creating-a-long-running-workflow-service/set-properties-for-reply-activities.png "SetReplyProperties")

    4. Fare clic sul collegamento **Definisci** nell'attività **SendReplyToStartOrder** e impostare le proprietà mostrate nella figura seguente. Si noti che il pulsante di opzione **parametri** è selezionato; un parametro denominato `p_orderId` è associato alla `orderId` variabile. Questa impostazione consente di specificare che tramite l'attività SendReplyToStartOrder verrà restituito un valore di tipo stringa al chiamante.

        ![Configurazione dei dati di contenuto dell'attività SendReply](./media/creating-a-long-running-workflow-service/setreplycontent-for-sendreplytostartorder-activity.png "Configurare l'impostazione per l'attività SetReplyToStartOrder.")

    5. Trascinare e rilasciare un'attività Assign tra le attività **Receive** e **SendReply** e impostare le proprietà come illustrato nella figura seguente:

        ![Aggiunta di un'attività di assegnazione](./media/creating-a-long-running-workflow-service/add-an-assign-activity.png "Aggiungere un'attività Assign.")

        In questo modo viene creato un nuovo ID ordine e il valore viene inserito nella variabile orderId.

    6. Selezionare l'attività **ReplyToStartOrder** . Nella finestra Proprietà fare clic sul pulsante con i puntini di sospensione per **CorrelationInitializers**. Selezionare il collegamento **Aggiungi inizializzatore** , immettere `orderIdHandle` nella casella di testo dell'inizializzatore, selezionare inizializzatore di correlazione query per il tipo di correlazione e selezionare p_orderId nella casella a discesa query XPath. Queste impostazioni sono mostrate nella figura seguente. Fare clic su **OK**.  Tale operazione consente di inizializzare una correlazione tra il client e questa istanza del servizio di flusso di lavoro. Quando viene ricevuto un messaggio contenente questo ID ordine, viene indirizzato a questa istanza del servizio di flusso di lavoro.

        ![Aggiunta di un inizializzatore di correlazione](./media/creating-a-long-running-workflow-service/add-correlationinitializers.png "Aggiungere un inizializzatore di correlazione.")

7. Trascinare e rilasciare un'altra attività **ReceiveAndSendReply** alla fine del flusso di lavoro (all'esterno della **sequenza** contenente le prime attività **Receive** e **SendReply** ). Un secondo messaggio inviato dal client verrà ricevuto dal flusso di lavoro tramite cui, a sua volta, verrà fornita una risposta.

    1. Selezionare la **sequenza** che contiene le attività **Receive** e **SendReply** appena aggiunte, quindi fare clic sul pulsante **variabili** . Aggiungere la variabile evidenziata nell'immagine seguente:

        ![Aggiunta di nuove variabili](./media/creating-a-long-running-workflow-service/add-the-itemid-variable.png "Aggiungere la variabile ItemId.")

        Aggiungere anche `orderResult` come **stringa** nell' `Sequence` ambito.

    2. Selezionare l'attività **Receive** e impostare le proprietà mostrate nella figura seguente:

        ![Impostare le proprietà dell'attività Receive](./media/creating-a-long-running-workflow-service/set-receive-activities-properties.png "Impostare le proprietà delle attività di ricezione.")

        > [!NOTE]
        > Non dimenticare di modificare il campo **ServiceContractName** con `../IAddItem` .

    3. Fare clic sul collegamento **Definisci** nell'attività **ReceiveAddItem** e aggiungere i parametri mostrati nella figura seguente: in questo modo l'attività Receive viene configurata in modo da accettare due parametri, l'ID dell'ordine e l'ID dell'elemento ordinato.

        ![Specifica di parametri per la seconda ricezione](./media/creating-a-long-running-workflow-service/add-receive-two-parameters.png "Configurare l'attività Receive per ricevere due parametri.")

    4. Fare clic sul pulsante con i puntini di sospensione **CorrelateOn** e immettere `orderIdHandle` . In **query XPath**fare clic sulla freccia a discesa e selezionare `p_orderId` . In questo modo la correlazione viene configurata sulla seconda attività Receive. Per ulteriori informazioni sulla correlazione, vedere [correlazione](correlation.md).

        ![Impostazione della proprietà CorrelatesOn](./media/creating-a-long-running-workflow-service/correlateson-setting.png "Impostare la proprietà CorrelatesOn.")

    5. Trascinare e rilasciare un'attività **if** immediatamente dopo l'attività **ReceiveAddItem** . Il comportamento di questa attività è uguale a quello di un'istruzione IF.

        1. Impostare la proprietà **Condition** su`itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`

        2. Trascinare e rilasciare un'attività **assign** nella sezione **then** e un'altra nella sezione **else** per impostare le proprietà delle attività **assign** , come illustrato nella figura seguente.

            ![Assegnazione del risultato della chiamata a servizio](./media/creating-a-long-running-workflow-service/assign-result-of-service-call.png "Assegnare il risultato della chiamata al servizio.")

            Se la condizione è `true` la sezione **then** verrà eseguita. Se la condizione è `false` la sezione **else** viene eseguita.

        3. Selezionare l'attività **SendReplyToReceive** e impostare la proprietà **DisplayName** mostrata nella figura seguente.

            ![Impostazione delle proprietà dell'attività SendReply](./media/creating-a-long-running-workflow-service/send-reply-activity-property.png "Impostare la proprietà dell'attività SendReply.")

        4. Fare clic sul collegamento **Definisci** nell'attività **SetReplyToAddItem** e configurarlo come illustrato nella figura seguente. In questo modo viene configurata l'attività **SendReplyToAddItem** per restituire il valore nella `orderResult` variabile.

            ![Impostazione della data binding per l'attività SendReply](./media/creating-a-long-running-workflow-service/set-property-for-sendreplytoadditem.gif "Imposta la proprietà per l'attività SendReplyToAddItem.")

8. Aprire il file Web. config e aggiungere i seguenti elementi nella \<behavior> sezione per abilitare la persistenza del flusso di lavoro.

    ```xml
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />
              <workflowIdle timeToUnload="0"/>
    ```

    > [!WARNING]
    > Assicurarsi di sostituire l'host e il nome dell'istanza di SQL Server nel frammento di codice precedente.

9. Compilare la soluzione.

## <a name="create-a-client-application-to-call-the-workflow-service"></a>Creare un'applicazione client per chiamare il servizio del flusso di lavoro

1. Aggiungere un nuovo progetto di applicazione console denominato `OrderClient` alla soluzione.

2. Aggiungere riferimenti agli assembly seguenti al progetto `OrderClient`

    1. System.ServiceModel.dll

    2. System.ServiceModel.Activities.dll

3. Aggiungere un riferimento al servizio di flusso di lavoro e specificare `OrderService` come spazio dei nomi.

4. Nel metodo `Main()` del progetto client aggiungere il codice seguente:

    ```csharp
    static void Main(string[] args)
    {
       // Send initial message to start the workflow service
       Console.WriteLine("Sending start message");
       StartOrderClient startProxy = new StartOrderClient();
       string orderId = startProxy.StartOrder("Kim Abercrombie");

       // The workflow service is now waiting for the second message to be sent
       Console.WriteLine("Workflow service is idle...");
       Console.WriteLine("Press [ENTER] to send an add item message to reactivate the workflow service...");
       Console.ReadLine();

       // Send the second message
       Console.WriteLine("Sending add item message");
       AddItemClient addProxy = new AddItemClient();
       AddItem item = new AddItem();
       item.p_itemId = "Zune HD";
       item.p_orderId = orderId;

       string orderResult = addProxy.AddItem(item);
       Console.WriteLine("Service returned: " + orderResult);
    }
    ```

5. Compilare la soluzione ed eseguire l'applicazione `OrderClient`. Nel client verrà visualizzato il testo seguente:

    ```output
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...
    ```

6. Per verificare che il servizio del flusso di lavoro sia stato salvato in modo permanente, avviare il SQL Server Management Studio dal menu **Start** , selezionando **tutti i programmi**, **Microsoft SQL Server 2008** **SQL Server Management Studio**.

    1. Nel riquadro a sinistra espandere **database**, **SQLPersistenceStore**, **viste** e fare clic con il pulsante destro del mouse su **System. Activities. DurableInstancing. instances** e scegliere **Seleziona le prime 1000 righe**. Nel riquadro **dei risultati** verificare che sia elencata almeno un'istanza. Se durante l'esecuzione si è verificata un'eccezione potrebbero essere presenti altre istanze di esecuzioni precedenti. È possibile eliminare le righe esistenti facendo clic con il pulsante destro del mouse su **System. Activities. DurableInstancing. Instances** e selezionando **modifica le prime 200 righe**, premendo il pulsante **Esegui** , selezionando tutte le righe nel riquadro risultati e selezionando **Elimina**.  Per verificare che l'istanza visualizzata nel database sia l'istanza creata dall'applicazione, controllare che la visualizzazione delle istanze sia vuota prima di eseguire il client. Quando il client è in esecuzione, eseguire di nuovo la query (Seleziona le prime 1000 righe) e verificare che sia stata aggiunta una nuova istanza.

7. Premere INVIO per inviare il messaggio relativo all'aggiunta di elementi al servizio di flusso di lavoro. Nel client verrà visualizzato il testo seguente:

    ```output
    Sending add item messageService returned: Item added to orderPress any key to continue . . .
    ```

## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](workflow-services.md)
