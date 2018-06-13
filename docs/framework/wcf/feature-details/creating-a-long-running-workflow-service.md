---
title: Creazione di un servizio flusso di lavoro a esecuzione prolungata
ms.date: 03/30/2017
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
ms.openlocfilehash: 1ddb995b849a15451c36d5d11c95a4904a3e0496
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495707"
---
# <a name="creating-a-long-running-workflow-service"></a>Creazione di un servizio flusso di lavoro a esecuzione prolungata
In questo argomento viene descritto come creare un servizio di flusso di lavoro a esecuzione prolungata. L'esecuzione di tali servizi può durare molto tempo. A un certo punto, è possibile che il flusso di lavoro diventi inattivo a causa dell'attesa di informazioni aggiuntive. In tal caso, il flusso di lavoro viene salvato in modo permanente in un database SQL e rimosso dalla memoria. Quando le informazioni aggiuntive diventano disponibili, l'istanza del flusso di lavoro viene caricata di nuovo in memoria e ne viene continuata l'esecuzione.  In questo scenario viene implementato un sistema di ordini molto semplificato.  Per avviare la procedura di ordine, dal client viene inviato un messaggio iniziale al servizio di flusso di lavoro che, a sua volta, consente la restituzione di un ID ordine al client. A questo punto, a causa dell'attesa di un altro messaggio inviato dal client, il servizio di flusso di lavoro diventa inattivo e viene salvato in modo permanente in un database SQL Server.  Quando dal client viene inviato il messaggio successivo per ordinare un elemento, il servizio di flusso di lavoro viene caricato di nuovo in memoria consentendo il completamento dell'elaborazione dell'ordine. Nell'esempio di codice viene restituita una stringa in cui viene indicato che l'elemento è stato aggiunto all'ordine. L'esempio di codice non è stato ideato per corrispondere a un'applicazione reale della tecnologia, ma piuttosto per fornire un esempio semplice in cui vengono illustrati i servizi di flusso di lavoro a esecuzione prolungata. In questo argomento si presuppone che l'utente sia in grado di creare progetti e soluzioni di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per utilizzare questa procedura dettagliata è necessario aver installato i software seguenti:  
  
1.  Microsoft SQL Server 2008  
  
2.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
3.  Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]  
  
4.  È necessario conoscere WCF e [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], nonché essere in grado di creare progetti e soluzioni.  
  
### <a name="to-setup-the-sql-database"></a>Per impostare il database SQL  
  
1.  Per salvare in modo permanente le istanze del servizio di flusso di lavoro è necessario disporre di Microsoft SQL Server e configurare un database per archiviare le istanze del flusso di lavoro salvate in modo permanente. Eseguire Microsoft SQL Management Studio facendo clic di **avviare** pulsante, la selezione di **tutti i programmi**, **Microsoft SQL Server 2008**, e **Microsoft SQL Management Studio**.  
  
2.  Fare clic su di **Connetti** pulsante per accedere all'istanza di SQL Server  
  
3.  Fare clic con il pulsante destro **database** nella visualizzazione albero e selezionare **Nuovo Database...** Per creare un nuovo database denominato `SQLPersistenceStore`.  
  
4.  Eseguire il file di script SqlWorkflowInstanceStoreSchema.sql presente nella directory C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en del database SQLPersistenceStore per configurare gli schemi del database necessari.  
  
5.  Eseguire il file di script SqlWorkflowInstanceStoreLogic.sql presente nella directory C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en del database SQLPersistenceStore per configurare la logica del database necessaria.  
  
### <a name="to-create-the-web-hosted-workflow-service"></a>Per creare il servizio di flusso di lavoro ospitato dal Web  
  
1.  Creare una soluzione di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] vuota e denominarla `OrderProcessing`.  
  
2.  Aggiungere un nuovo progetto Applicazione di servizi flusso di lavoro WCF denominato `OrderService` alla soluzione.  
  
3.  Nella finestra di dialogo proprietà del progetto, selezionare il **Web** scheda.  
  
    1.  In **azione di avvio** selezionare **pagina specifica** e specificare `Service1.xamlx`.  
  
         ![Proprietà Web del progetto servizio flusso di lavoro](../../../../docs/framework/wcf/feature-details/media/startaction.png "StartAction")  
  
    2.  In **server** selezionare **server Web IIS locale usare**.  
  
         ![Impostazioni del Server Web locale](../../../../docs/framework/wcf/feature-details/media/uselocalwebserver.png "UseLocalWebServer")  
  
        > [!WARNING]
        >  Per effettuare tale impostazione, è necessario eseguire [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] in modalità amministratore.  
  
         Questi due passaggi consentono di configurare il progetto del servizio di flusso di lavoro che deve essere ospitato da IIS.  
  
4.  Aprire `Service1.xamlx` se è già aperto non ed eliminare quello esistente **ReceiveRequest** e **SendResponse** attività.  
  
5.  Selezionare il **servizio sequenziale** attività e fare clic su di **variabili** collegare e aggiungere le variabili mostrate nell'illustrazione seguente. In questo modo verranno aggiunte alcune variabili che saranno utilizzate successivamente nel servizio di flusso di lavoro.  
  
    > [!NOTE]
    >  Se CorrelationHandle non è presente nell'elenco a discesa tipo di variabile, selezionare **Cerca tipi** dall'elenco a discesa. Digitare CorrelationHandle nella **nome del tipo** , selezionare CorrelationHandle nella casella di riepilogo e fare clic su **OK**.  
  
     ![Aggiungere variabili](../../../../docs/framework/wcf/feature-details/media/addvariables.gif "AddVariables")  
  
6.  Trascinare e rilasciare un **ReceiveAndSendReply** il modello di attività nel **servizio sequenziale** attività. Un messaggio inviato da un client verrà ricevuto da questo set di attività tramite cui, a sua volta, verrà restituita una risposta.  
  
    1.  Selezionare il **ricezione** attività e impostare le proprietà evidenziate nella figura seguente.  
  
         ![Impostare le proprietà di attività Receive](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties.png "SetReceiveProperties")  
  
         La proprietà DisplayName consente di impostare il nome visualizzato per l'attività Receive nella finestra di progettazione. Le proprietà ServiceContractName e OperationName specificano il nome del contratto di servizio e della relativa operazione implementati dall'attività Receive. Per ulteriori informazioni sulle modalità di utilizzo contratti nei servizi del flusso di lavoro, vedere [uso di contratti nel flusso di lavoro](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).  
  
    2.  Fare clic su di **definire...**  collegare il **ReceiveStartOrder** attività e impostare le proprietà mostrate nell'illustrazione seguente.  Si noti che il **parametri** pulsante di opzione è selezionata, un parametro denominato `p_customerName` è associato il `customerName` variabile. In questo modo il **ricezione** attività per la ricezione di alcuni dati e associarli a variabili locali.  
  
         ![Impostazione dei dati ricevuti dall'attività Receive](../../../../docs/framework/wcf/feature-details/media/setreceivecontent.png "SetReceiveContent")  
  
    3.  Selezionare il **SendReplyToReceive** attività e impostare la proprietà evidenziata mostrata nella figura seguente.  
  
         ![Impostazione delle proprietà dell'attività SendReply](../../../../docs/framework/wcf/feature-details/media/setreplyproperties.png "SetReplyProperties")  
  
    4.  Fare clic su di **definire...**  collegare il **SendReplyToStartOrder** attività e impostare le proprietà mostrate nell'illustrazione seguente. Si noti che il **parametri** pulsante di opzione è selezionata, mentre un parametro denominato `p_orderId` è associato il `orderId` variabile. Questa impostazione consente di specificare che tramite l'attività SendReplyToStartOrder verrà restituito un valore di tipo stringa al chiamante.  
  
         ![Configurazione dei dati di contenuto dell'attività SendReply](../../../../docs/framework/wcf/feature-details/media/setreplycontent.png "SetReplyContent")  
  
    5.  Trascinare e rilasciare un'attività Assign tra le **ricezione** e **SendReply** le attività e impostare le proprietà, come illustrato nella figura seguente:  
  
         ![Aggiunta di un'attività assign](../../../../docs/framework/wcf/feature-details/media/addassign.png "AddAssign")  
  
         In questo modo viene creato un nuovo ID ordine e il valore viene inserito nella variabile orderId.  
  
    6.  Selezionare il **ReplyToStartOrder** attività. Nella finestra Proprietà fare clic sul pulsante con puntini di sospensione per **CorrelationInitializers**. Selezionare il **aggiungere inizializzatore** collegare, immettere `orderIdHandle` nella casella di testo dell'inizializzatore, selezionare l'inizializzatore correlazione Query per il tipo di correlazione, quindi scegliere p_orderId nella casella a discesa query XPATH. Queste impostazioni sono mostrate nell'immagine seguente. Fare clic su **OK**.  Tale operazione consente di inizializzare una correlazione tra il client e questa istanza del servizio di flusso di lavoro. Quando viene ricevuto un messaggio contenente questo ID ordine, viene indirizzato a questa istanza del servizio di flusso di lavoro.  
  
         ![Aggiunta di un inizializzatore di correlazione](../../../../docs/framework/wcf/feature-details/media/addcorrelationinitializers.png "AddCorrelationInitializers")  
  
7.  Trascinare e rilasciare un altro **ReceiveAndSendReply** attività alla fine del flusso di lavoro (all'esterno di **sequenza** contenente le prime **ricezione** e  **SendReply** attività). Un secondo messaggio inviato dal client verrà ricevuto dal flusso di lavoro tramite cui, a sua volta, verrà fornita una risposta.  
  
    1.  Selezionare il **sequenza** contenente appena aggiunta **ricezione** e **SendReply** le attività e fare clic su di **variabili** pulsante. Aggiungere la variabile evidenziata nell'immagine seguente:  
  
         ![Aggiunta di nuove variabili](../../../../docs/framework/wcf/feature-details/media/addorderitemidvariable.png "AddOrderItemIdVariable")  
  
    2.  Selezionare il **ricezione** attività e impostare le proprietà mostrate nell'illustrazione seguente:  
  
         ![Impostare le proprietà dell'attività Receive](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties2.png "SetReceiveProperties2")  
  
    3.  Fare clic su di **definire...**  collegare il **ReceiveAddItem** attività e aggiungere i parametri riportati nella figura seguente: questa impostazione configura l'attività di ricezione per accettare due parametri, l'ID dell'ordine e l'ID dell'elemento da ordinare.  
  
         ![Specificare i parametri per la seconda ricevano](../../../../docs/framework/wcf/feature-details/media/addreceive2parameters.png "AddReceive2Parameters")  
  
    4.  Fare clic su di **CorrelateOn** i puntini di sospensione pulsante e immettere `orderIdHandle`. In **query XPath**fare clic sulla freccia a discesa e selezionare `p_orderId`. In questo modo la correlazione viene configurata sulla seconda attività Receive. Per ulteriori informazioni sulla correlazione, vedere [correlazione](../../../../docs/framework/wcf/feature-details/correlation.md).  
  
         ![Impostazione della proprietà CorrelatesOn](../../../../docs/framework/wcf/feature-details/media/correlateson.png "CorrelatesOn")  
  
    5.  Trascinare e rilasciare un **se** attività immediatamente dopo il **ReceiveAddItem** attività. Il comportamento di questa attività è uguale a quello di un'istruzione IF.  
  
        1.  Impostare il **condizione** proprietà `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`  
  
        2.  Trascinare e rilasciare un **assegnare** attività per il **quindi** sezione e un'altra nella **Else** sezione impostata le proprietà del **assegnare** attività, come illustrato nella figura seguente.  
  
             ![Assegnazione del risultato della chiamata al servizio](../../../../docs/framework/wcf/feature-details/media/resultassign.png "ResultAssign")  
  
             Se la condizione è `true` il **quindi** sezione verrà eseguita. Se la condizione è `false` il **Else** sezione viene eseguita.  
  
        3.  Selezionare il **SendReplyToReceive** attività e impostare il **DisplayName** proprietà illustrata nella figura seguente.  
  
             ![Impostazione delle proprietà dell'attività SendReply](../../../../docs/framework/wcf/feature-details/media/setreply2properties.png "SetReply2Properties")  
  
        4.  Fare clic su di **definire...**  collegare il **SetReplyToAddItem** attività e configurarlo come mostrato nella figura seguente. In questo modo il **SendReplyToAddItem** attività per restituire il valore di `orderResult` variabile.  
  
             ![Impostazione del data binding per l'attività SendReply](../../../../docs/framework/wcf/feature-details/media/replytoadditemcontent.gif "ReplyToAddItemContent")  
  
8.  Aprire il file Web. config e aggiungere gli elementi seguenti nel \<comportamento > sezione per abilitare la persistenza del flusso di lavoro.  
  
    ```xml  
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />  
              <workflowIdle timeToUnload="0"/>  
    ```  
  
    > [!WARNING]
    >  Assicurarsi di sostituire l'host e il nome dell'istanza di SQL Server nel frammento di codice precedente.  
  
9. Compilare la soluzione.  
  
### <a name="to-create-a-client-application-to-call-the-workflow-service"></a>Per creare un'applicazione client e chiamare il servizio di flusso di lavoro  
  
1.  Aggiungere un nuovo progetto di applicazione console denominato `OrderClient` alla soluzione.  
  
2.  Aggiungere riferimenti agli assembly seguenti al progetto `OrderClient`  
  
    1.  System.ServiceModel.dll  
  
    2.  System.ServiceModel.Activities.dll  
  
3.  Aggiungere un riferimento al servizio di flusso di lavoro e specificare `OrderService` come spazio dei nomi.  
  
4.  Nel metodo `Main()` del progetto client aggiungere il codice seguente:  
  
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
  
5.  Compilare la soluzione ed eseguire l'applicazione `OrderClient`. Nel client verrà visualizzato il testo seguente:  
  
    ```Output  
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...  
    ```  
  
6.  Per verificare che il servizio del flusso di lavoro è stata resa persistente, avviare SQL Server Management Studio visitando il **avviare** dal menu selezionando **tutti i programmi**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**.  
  
    1.  Nel riquadro di sinistra espandere **database**, **SQLPersistenceStore**, **viste** e fare clic destro **System.Activities.DurableInstancing.Instances**  e selezionare **seleziona le prime 1000 righe**. Nel **risultati** riquadro verificare venga visualizzato almeno un'istanza elencata. Se durante l'esecuzione si è verificata un'eccezione potrebbero essere presenti altre istanze di esecuzioni precedenti. È possibile eliminare righe esistenti facendo clic **System.Activities.DurableInstancing.Instances** e selezionando **modifica le prime 200 righe**, premendo il **Execute** pulsante Selezionare tutte le righe nel riquadro dei risultati e **eliminare**.  Per verificare che l'istanza visualizzata nel database sia l'istanza creata dall'applicazione, controllare che la visualizzazione delle istanze sia vuota prima di eseguire il client. Quando il client è in esecuzione, eseguire di nuovo la query (Seleziona le prime 1000 righe) e verificare che sia stata aggiunta una nuova istanza.  
  
7.  Premere INVIO per inviare il messaggio relativo all'aggiunta di elementi al servizio di flusso di lavoro. Nel client verrà visualizzato il testo seguente:  
  
    ```Output  
    Sending add item messageService returned: Item added to orderPress any key to continue . . .  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
