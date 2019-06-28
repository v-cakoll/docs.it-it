---
title: Creazione di un servizio flusso di lavoro a esecuzione prolungata
ms.date: 03/30/2017
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
ms.openlocfilehash: 1ca0f2ed4c2ab900191165d100848811e5436c3c
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425411"
---
# <a name="creating-a-long-running-workflow-service"></a>Creazione di un servizio flusso di lavoro a esecuzione prolungata
In questo argomento viene descritto come creare un servizio di flusso di lavoro a esecuzione prolungata. L'esecuzione di tali servizi può durare molto tempo. A un certo punto, è possibile che il flusso di lavoro diventi inattivo a causa dell'attesa di informazioni aggiuntive. In tal caso, il flusso di lavoro viene salvato in modo permanente in un database SQL e rimosso dalla memoria. Quando le informazioni aggiuntive diventano disponibili, l'istanza del flusso di lavoro viene caricata di nuovo in memoria e ne viene continuata l'esecuzione.  In questo scenario viene implementato un sistema di ordini molto semplificato.  Per avviare la procedura di ordine, dal client viene inviato un messaggio iniziale al servizio di flusso di lavoro che, a sua volta, consente la restituzione di un ID ordine al client. A questo punto, a causa dell'attesa di un altro messaggio inviato dal client, il servizio di flusso di lavoro diventa inattivo e viene salvato in modo permanente in un database SQL Server.  Quando dal client viene inviato il messaggio successivo per ordinare un elemento, il servizio di flusso di lavoro viene caricato di nuovo in memoria consentendo il completamento dell'elaborazione dell'ordine. Nell'esempio di codice viene restituita una stringa in cui viene indicato che l'elemento è stato aggiunto all'ordine. L'esempio di codice non è stato ideato per corrispondere a un'applicazione reale della tecnologia, ma piuttosto per fornire un esempio semplice in cui vengono illustrati i servizi di flusso di lavoro a esecuzione prolungata. In questo argomento presuppone che l'utente sappia creare soluzioni e progetti di Visual Studio 2012.

## <a name="prerequisites"></a>Prerequisiti
 Per utilizzare questa procedura dettagliata è necessario aver installato i software seguenti:

1. Microsoft SQL Server 2008

2. Visual Studio 2012

3. Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]

4. Si ha familiarità con WCF e Visual Studio 2012 e in grado di creare progetti e soluzioni.

### <a name="to-setup-the-sql-database"></a>Per impostare il database SQL

1. Per salvare in modo permanente le istanze del servizio di flusso di lavoro è necessario disporre di Microsoft SQL Server e configurare un database per archiviare le istanze del flusso di lavoro salvate in modo permanente. Eseguire Microsoft SQL Management Studio facendo il **avviare** button, selezionando **tutti i programmi**, **Microsoft SQL Server 2008**, e **Microsoft SQL Management Studio**.

2. Scegliere il **Connect** pulsante per accedere all'istanza di SQL Server

3. Fare clic destro **database** nella visualizzazione struttura ad albero e selezionare **Nuovo Database...** Per creare un nuovo database denominato `SQLPersistenceStore`.

4. Eseguire il file di script SqlWorkflowInstanceStoreSchema.sql presente nella directory C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en del database SQLPersistenceStore per configurare gli schemi del database necessari.

5. Eseguire il file di script SqlWorkflowInstanceStoreLogic.sql presente nella directory C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en del database SQLPersistenceStore per configurare la logica del database necessaria.

### <a name="to-create-the-web-hosted-workflow-service"></a>Per creare il servizio di flusso di lavoro ospitato dal Web

1. Creare una soluzione di Visual Studio 2012 vuota, denominarlo `OrderProcessing`.

2. Aggiungere un nuovo progetto Applicazione di servizi flusso di lavoro WCF denominato `OrderService` alla soluzione.

3. Nella finestra di dialogo proprietà del progetto, selezionare la **Web** scheda.

    1. Sotto **azione di avvio** selezionate **pagina specifica** e specificare `Service1.xamlx`.

         ![Proprietà del flusso di lavoro servizio progetto Web](./media/creating-a-long-running-workflow-service/start-action-specific-page-option.png "creare il servizio del flusso di lavoro ospitati dal web - opzione pagina specifica")

    2. Sotto **i server** selezionate **server Web IIS locale usare**.

         ![Impostazioni del Server Web locale](./media/creating-a-long-running-workflow-service/use-local-web-server.png "creare il servizio del flusso di lavoro ospitati dal web - opzione Usa Server Web IIS locale")

        > [!WARNING]
        >  È necessario eseguire Visual Studio 2012 in modalità amministratore per effettuare tale impostazione.

         Questi due passaggi consentono di configurare il progetto del servizio di flusso di lavoro che deve essere ospitato da IIS.

4. Aprire `Service1.xamlx` se è già aperto ed eliminare quello esistente non **ReceiveRequest** e **SendResponse** attività.

5. Selezionare il **Sequential Service** attività e fare clic sui **variabili** collegare e aggiungere le variabili mostrate nell'illustrazione seguente. In questo modo verranno aggiunte alcune variabili che saranno utilizzate successivamente nel servizio di flusso di lavoro.

    > [!NOTE]
    >  Se CorrelationHandle non è presente nell'elenco a discesa tipo di variabile, selezionare **Cerca tipi** dall'elenco a discesa. Digitare CorrelationHandle nella **nome del tipo** casella, selezionare CorrelationHandle nella casella di riepilogo e fare clic su **OK**.

     ![Aggiungere le variabili](./media/creating-a-long-running-workflow-service/add-variables-sequential-service-activity.gif "aggiungere le variabili per l'attività servizio sequenziale.")

6. Trascinare e rilasciare un **ReceiveAndSendReply** modello di attività nel **Sequential Service** attività. Un messaggio inviato da un client verrà ricevuto da questo set di attività tramite cui, a sua volta, verrà restituita una risposta.

    1. Selezionare il **ricezione** attività e impostare le proprietà evidenziate nella figura seguente.

         ![Impostare le proprietà di attività di ricezione](./media/creating-a-long-running-workflow-service/set-receive-activity-properties.png "impostare le proprietà dell'attività Receive.")

         La proprietà DisplayName consente di impostare il nome visualizzato per l'attività Receive nella finestra di progettazione. Le proprietà ServiceContractName e OperationName specificano il nome del contratto di servizio e della relativa operazione implementati dall'attività Receive. Per altre informazioni sulle modalità di utilizzo dei contratti nei servizi del flusso di lavoro, vedere [uso di contratti nel flusso di lavoro](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).

    2. Fare clic su di **definire...**  collegare il **ReceiveStartOrder** attività e impostare le proprietà mostrate nell'illustrazione seguente.  Si noti che il **parametri** pulsante di opzione è selezionato, un parametro denominato `p_customerName` è associato il `customerName` variabile. Ciò consente di configurare il **ricezione** attività per ricevere dati e associarli a variabili locali.

         ![Impostazione dei dati ricevuti dall'attività Receive](./media/creating-a-long-running-workflow-service/set-properties-for-receive-content.png "impostare le proprietà per i dati ricevuti dall'attività Receive.")

    3. Selezionare il **SendReplyToReceive** attività e impostare la proprietà evidenziata mostrata nell'illustrazione seguente.

         ![Impostazione delle proprietà dell'attività SendReply](./media/creating-a-long-running-workflow-service/set-properties-for-reply-activities.png "SetReplyProperties")

    4. Fare clic su di **definire...**  collegare il **SendReplyToStartOrder** attività e impostare le proprietà mostrate nell'illustrazione seguente. Si noti che il **parametri** pulsante di opzione è selezionato mentre un parametro denominato `p_orderId` è associato il `orderId` variabile. Questa impostazione consente di specificare che tramite l'attività SendReplyToStartOrder verrà restituito un valore di tipo stringa al chiamante.

         ![Configurare i dati di contenuto attività SendReply](./media/creating-a-long-running-workflow-service/setreplycontent-for-sendreplytostartorder-activity.png "configurare le impostazioni delle attività SetReplyToStartOrder.")

    5. Trascinare e rilasciare un'attività Assign tra le **Receive** e **SendReply** attività e impostare le proprietà come illustrato nella figura seguente:

         ![Aggiunta di un'attività assign](./media/creating-a-long-running-workflow-service/add-an-assign-activity.png "aggiungere un'attività assign.")

         In questo modo viene creato un nuovo ID ordine e il valore viene inserito nella variabile orderId.

    6. Selezionare il **ReplyToStartOrder** attività. Nella finestra Proprietà fare clic sul pulsante con i puntini **CorrelationInitializers**. Selezionare il **Aggiungi inizializzatore** collegare, immettere `orderIdHandle` nella casella di testo dell'inizializzatore, selezionare l'inizializzatore correlazione Query per il tipo di correlazione e scegliere p_orderId nella casella a discesa query XPATH. Queste impostazioni sono mostrate nell'immagine seguente. Fare clic su **OK**.  Tale operazione consente di inizializzare una correlazione tra il client e questa istanza del servizio di flusso di lavoro. Quando viene ricevuto un messaggio contenente questo ID ordine, viene indirizzato a questa istanza del servizio di flusso di lavoro.

         ![Aggiunta di un inizializzatore di correlazione](./media/creating-a-long-running-workflow-service/add-correlationinitializers.png "aggiungere un inizializzatore di correlazione.")

7. Trascinare e rilasciare un'altra **ReceiveAndSendReply** attività alla fine del flusso di lavoro (all'esterno di **sequenza** che contiene il primo **ricezione** e  **SendReply** attività). Un secondo messaggio inviato dal client verrà ricevuto dal flusso di lavoro tramite cui, a sua volta, verrà fornita una risposta.

    1. Selezionare il **sequenza** che contiene appena aggiunta **ricezione** e **SendReply** le attività e fare clic sul **variabili** pulsante. Aggiungere la variabile evidenziata nell'immagine seguente:

         ![Aggiunta di nuove variabili](./media/creating-a-long-running-workflow-service/add-the-itemid-variable.png "aggiungere la variabile di ItemId.")
         
         Aggiungere inoltre `orderResult` come **stringa** nel `Sequence` ambito.

    2. Selezionare il **ricezione** attività e impostare le proprietà mostrate nell'illustrazione seguente:

         ![Impostare le proprietà dell'attività Receive](./media/creating-a-long-running-workflow-service/set-receive-activities-properties.png "impostare le proprietà di attività di ricezione.")
         
         > [!NOTE]
         >  Non dimenticare di modificare **ServiceContractName** campo `../IAddItem`.

    3. Fare clic su di **definire...**  link nel **ReceiveAddItem** attività e aggiungere i parametri riportati nella figura seguente: questa impostazione configura l'attività di ricezione per accettare due parametri, l'ID dell'ordine e l'ID dell'elemento da ordinare.

         ![Specifica dei parametri per la seconda ricezione](./media/creating-a-long-running-workflow-service/add-receive-two-parameters.png "configurare l'attività di ricezione per ricevere due parametri.")

    4. Scegliere il **CorrelateOn** puntini di sospensione sul pulsante e immettere `orderIdHandle`. Sotto **le query XPath**, fare clic sulla freccia a discesa e selezionare `p_orderId`. In questo modo la correlazione viene configurata sulla seconda attività Receive. Per altre informazioni sulla correlazione, vedere [correlazione](../../../../docs/framework/wcf/feature-details/correlation.md).

         ![Impostazione della proprietà CorrelatesOn](./media/creating-a-long-running-workflow-service/correlateson-setting.png "impostare la proprietà CorrelatesOn.")

    5. Trascinare e rilasciare un' **se** attività immediatamente dopo il **ReceiveAddItem** attività. Il comportamento di questa attività è uguale a quello di un'istruzione IF.

        1. Impostare il **condizione** proprietà `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`

        2. Trascinare e rilasciare un' **assegnare** attività nel **quindi** sezione e un altro nel **Else** sezione impostazione delle proprietà del **assegnare** attività come illustrato nella figura seguente.

             ![Assegnazione del risultato della chiamata al servizio](./media/creating-a-long-running-workflow-service/assign-result-of-service-call.png "assegnare il risultato della chiamata al servizio.")

             Se la condizione è `true` il **quindi** sezione verrà eseguita. Se la condizione è `false` il **Else** sezione viene eseguita.

        3. Selezionare il **SendReplyToReceive** attività e impostare le **DisplayName** proprietà illustrato nella figura seguente.

             ![Impostazione delle proprietà dell'attività SendReply](./media/creating-a-long-running-workflow-service/send-reply-activity-property.png "impostare le proprietà dell'attività SendReply.")

        4. Fare clic su di **definire...**  collegare il **SetReplyToAddItem** attività e configurarlo come mostrato nella figura seguente. Ciò consente di configurare il **SendReplyToAddItem** attività per restituire il valore nel `orderResult` variabile.

             ![Impostazione del data binding per l'attività SendReply](./media/creating-a-long-running-workflow-service/set-property-for-sendreplytoadditem.gif "impostare proprietà per l'attività SendReplyToAddItem.")

8. Aprire il file Web. config e aggiungere gli elementi seguenti nel \<comportamento > sezione abilitare la persistenza del flusso di lavoro.

    ```xml
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />
              <workflowIdle timeToUnload="0"/>
    ```

    > [!WARNING]
    >  Assicurarsi di sostituire l'host e il nome dell'istanza di SQL Server nel frammento di codice precedente.

9. Compilare la soluzione.

### <a name="to-create-a-client-application-to-call-the-workflow-service"></a>Per creare un'applicazione client e chiamare il servizio di flusso di lavoro

1. Aggiungere un nuovo progetto di applicazione console denominato `OrderClient` alla soluzione.

2. Aggiungere riferimenti agli assembly seguenti al progetto `OrderClient`

    1. System.ServiceModel.dll

    2. System.ServiceModel.Activities.dll

3. Aggiungere un riferimento al servizio di flusso di lavoro e specificare `OrderService` come spazio dei nomi.

4. Nel metodo `Main()` del progetto client aggiungere il codice seguente:

    ```
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

    ```Output
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...
    ```

6. Per verificare che il servizio del flusso di lavoro è stata resa persistente, avviare SQL Server Management Studio visitando la **avviare** menu, se si seleziona **tutti i programmi**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**.

    1. Nel riquadro a sinistra espandere, **database**, **SQLPersistenceStore**, **viste** e fare clic destro **System.Activities.DurableInstancing.Instances**  e selezionare **seleziona le prime 1000 righe**. Nel **risultati** riquadro verificare sia presente almeno un'istanza elencata. Se durante l'esecuzione si è verificata un'eccezione potrebbero essere presenti altre istanze di esecuzioni precedenti. È possibile eliminare le righe esistenti facendo clic con il pulsante destro **System.Activities.DurableInstancing.Instances** e selezionando **modifica le prime 200 righe**, premendo il **Execute** pulsante, selezionando tutte le righe nel riquadro dei risultati e selezionando **Elimina**.  Per verificare che l'istanza visualizzata nel database sia l'istanza creata dall'applicazione, controllare che la visualizzazione delle istanze sia vuota prima di eseguire il client. Quando il client è in esecuzione, eseguire di nuovo la query (Seleziona le prime 1000 righe) e verificare che sia stata aggiunta una nuova istanza.

7. Premere INVIO per inviare il messaggio relativo all'aggiunta di elementi al servizio di flusso di lavoro. Nel client verrà visualizzato il testo seguente:

    ```Output
    Sending add item messageService returned: Item added to orderPress any key to continue . . .
    ```

## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
