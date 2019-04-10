---
title: 'Procedura: Creare un servizio di flusso di lavoro con attività di messaggistica'
ms.date: 03/30/2017
ms.assetid: 53d094e2-6901-4aa1-88b8-024b27ccf78b
ms.openlocfilehash: f5bb8df5936be1890bf744300daa7ccb68e341e3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337773"
---
# <a name="how-to-create-a-workflow-service-with-messaging-activities"></a>Procedura: Creare un servizio di flusso di lavoro con attività di messaggistica
In questo argomento viene illustrato come creare un semplice servizio flusso di lavoro utilizzando le attività di messaggistica. L'argomento è incentrato sui meccanismi di creazione di un servizio flusso di lavoro in cui il servizio è costituito esclusivamente da attività di messaggistica. In servizi reali i flussi di lavoro contengono molte altre attività. Il servizio implementa un'operazione denominata Echo che acquisisce una stringa e la restituisce al chiamante. Questo è il primo di una serie di due argomenti. Argomento successivo [How To: Accedere a un servizio da un flusso di lavoro applicazione](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) viene illustrato come creare un'applicazione flusso di lavoro che possa chiamare il servizio creato in questo argomento.  
  
### <a name="to-create-a-workflow-service-project"></a>Per creare un progetto di servizio flusso di lavoro  
  
1. Start Visual Studio 2012.  
  
2. Fare clic sui **File** dal menu **New**e quindi **progetto** per visualizzare il **finestra Nuovo progetto**. Selezionare **flusso di lavoro** dall'elenco dei modelli installati e **applicazione di servizio del flusso di lavoro WCF** dall'elenco dei tipi di progetto. Denominare il progetto `MyWFService` e usare il percorso predefinito, come illustrato nella figura seguente.  
  
     Scegliere il **OK** per chiudere la **finestra Nuovo progetto**.  
  
3. Una volta creato il progetto, nella finestra di progettazione verrà aperto il file Service1.xamlx, come illustrato nella figura seguente.  
  
     ![Schermata mostra il file Service1.xamlx aperto nella finestra di progettazione.](./media/how-to-create-a-workflow-service-with-messaging-activities/default-workflow-service.jpg)  
  
     Fare doppio clic su attività con etichettata **Sequential Service** e selezionare **eliminare**.  
  
### <a name="to-implement-the-workflow-service"></a>Per implementare il servizio flusso di lavoro  
  
1. Selezionare il **casella degli strumenti** scheda sul lato sinistro della schermata per visualizzare la casella degli strumenti fare clic sulla puntina da disegno per mantenere aperta la finestra. Espandere la **messaggistica** sezione della casella degli strumenti per visualizzare le attività di messaggistica e i relativi modelli, come mostrato nella figura seguente.  
  
     ![Screenshot che mostra la casella degli strumenti con sezione messaggi espansa.](./media/how-to-create-a-workflow-service-with-messaging-activities/toolbox-messaging-section.jpg)  
  
2. Trascinare e rilasciare un **ReceiveAndSendReply** modello alla finestra di progettazione del flusso di lavoro. Ciò consente di creare un <xref:System.Activities.Statements.Sequence> attività con un **Receive** seguita da un <xref:System.ServiceModel.Activities.SendReply> attività come illustrato nella figura seguente.  
  
     ![Screenshot che mostra il modello ReceiveAndSendReply.](./media/how-to-create-a-workflow-service-with-messaging-activities/receiveandsendreply-template.jpg)  
  
     La proprietà <xref:System.ServiceModel.Activities.SendReply> dell'attività <xref:System.ServiceModel.Activities.SendReply.Request%2A> è impostata su `Receive`, il nome dell'attività <xref:System.ServiceModel.Activities.Receive> a cui risponde l'attività <xref:System.ServiceModel.Activities.SendReply>.  
  
3. Nel <xref:System.ServiceModel.Activities.Receive> tipo di attività `Echo` nella casella di testo etichettato **OperationName**. In questo modo viene definito il nome dell'operazione implementata dal servizio.  
  
     ![Screenshot che mostra la posizione in cui specificare il nome dell'operazione.](./media/how-to-create-a-workflow-service-with-messaging-activities/define-operation-name.jpg)  
  
4. Con il <xref:System.ServiceModel.Activities.Receive> attività selezionata, aprire la finestra proprietà se non è già aperto, fare clic il **View** menu e selezionando **finestra proprietà**. Nel **finestra delle proprietà** scorrere verso il basso fino a visualizzare **CanCreateInstance** e fare clic sulla casella di controllo, come illustrato nella figura seguente. Questa impostazione consente all'host del servizio flusso di lavoro di creare, se necessario, una nuova istanza del servizio dopo la ricezione di un messaggio.  
  
     ![Screenshot che mostra la proprietà CanCreateInstance.](./media/how-to-create-a-workflow-service-with-messaging-activities/cancreateinstance-property.jpg)  
  
5. Selezionare il <xref:System.Activities.Statements.Sequence> attività e scegliere il **variabili** pulsante nell'angolo inferiore sinistro della finestra di progettazione. Verrà visualizzato l'editor delle variabili. Scegliere il **Crea variabile** collegamento per aggiungere una variabile per archiviare la stringa inviata all'operazione. Rinominare la variabile `msg` e impostare relativi **variabile** digitare alla stringa, come illustrato nella figura seguente.  
  
     ![Screenshot che mostra come aggiungere una variabile.](./media/how-to-create-a-workflow-service-with-messaging-activities/add-variable-msg-string.jpg)  
  
     Scegliere il **variabili** pulsante per chiudere l'editor delle variabili.  
  
6. Fare clic su di **definire...** clic sul collegamento nella **contenuto** casella di testo il <xref:System.ServiceModel.Activities.Receive> attività per visualizzare il **definizione contenuto** finestra di dialogo. Selezionare il **parametri** pulsante di opzione, fare clic sui **Aggiungi nuovo parametro** collegare, digitare `inMsg` nel **nome** casella di testo, seleziona **stringa**nel **tipo** elenco a discesa casella di riepilogo e digitare `msg` nel **assegna a** casella di testo, come illustrato nella figura seguente.  
  
     ![Screenshot che mostra l'aggiunta di parametri del contenuto.](./media/how-to-create-a-workflow-service-with-messaging-activities/adding-parameters-content.jpg)  
  
     In questo modo viene specificato che l'attività Receive riceve il parametro stringa e che i dati sono associati alla variabile `msg`. Fare clic su **OK** per chiudere la **definizione del contenuto** finestra di dialogo.  
  
7. Fare clic su di **definire...**  clic sul collegamento nella **contenuto** nella casella il <xref:System.ServiceModel.Activities.SendReply> attività per visualizzare il **definizione contenuto** finestra di dialogo. Selezionare il **parametri** pulsante di opzione, fare clic sul **Aggiungi nuovo parametro** collegare, digitare `outMsg` nel **nome** casella di testo, seleziona **stringa**nel **tipo** casella di riepilogo a discesa, e `msg` nel **valore** casella di testo, come illustrato nella figura seguente.  
  
     ![Screenshot che mostra come aggiungere il parametro outMsg.](./media/how-to-create-a-workflow-service-with-messaging-activities/outmsg-parameters-content.jpg)  
  
     In questo modo viene specificato che l'attività <xref:System.ServiceModel.Activities.SendReply> invia un messaggio o un tipo di contratto messaggio e che i dati sono associati alla variabile `msg`. Poiché si tratta di un'attività <xref:System.ServiceModel.Activities.SendReply>, i dati in `msg` vengono usati per popolare il messaggio inviato in risposta al client da parte dell'attività. Fare clic su **OK** per chiudere la **definizione del contenuto** finestra di dialogo.  
  
8. Salvare e compilare la soluzione scegliendo il **compilare** dal menu e selezionando **Compila soluzione**.  
  
## <a name="configure-the-workflow-service-project"></a>Configurare il progetto di servizio flusso di lavoro  
 Il servizio flusso di lavoro è completo. Contenuto della sezione viene illustrato come configurare la soluzione del servizio flusso di lavoro per agevolarne l'hosting e l'esecuzione. Questa soluzione utilizza il server di sviluppo ASP.NET per ospitare il servizio.  
  
#### <a name="to-set-project-start-up-options"></a>Per impostare le opzioni di avvio del progetto  
  
1. Nel **Esplora soluzioni**, fare doppio clic su **MyWFService** e selezionare **proprietà** per visualizzare il **le proprietà del progetto** finestra di dialogo.  
  
2. Selezionare il **Web** scheda e selezionare **pagina specifica** sotto **azione di avvio** e digitare `Service1.xamlx` nella casella di testo, come illustrato nella figura seguente.  
  
     ![Screenshot che mostra la finestra di dialogo Proprietà progetto.](./media/how-to-create-a-workflow-service-with-messaging-activities/project-properties-dialog.jpg)  
  
     In questo modo, il servizio definito in Service1.xamlx viene ospitato nel server di sviluppo ASP.NET.  
  
3. Premere CTRL+F5 per avviare il servizio. L'icona del server di sviluppo ASP.NET verrà visualizzata nel lato inferiore destro del desktop, come illustrato nella figura seguente.  
  
     ![Screenshot che mostra l'icona di Server di sviluppo ASP.NET.](./media/how-to-create-a-workflow-service-with-messaging-activities/asp-net-dev-server-icon.jpg)  
  
     In Internet Explorer verrà inoltre visualizzata la pagina della Guida del servizio WCF relativa al servizio.  
  
     ![Screenshot che mostra la pagina della Guida del servizio WCF.](./media/how-to-create-a-workflow-service-with-messaging-activities/wcf-service-help-page.jpg)  
  
4. Continuare con la [come: Accedere a un servizio da un flusso di lavoro applicazione](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) argomento per creare un client flusso di lavoro che chiami questo servizio.  
  
## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Panoramica dell'hosting dei servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)
- [Attività di messaggistica](../../../../docs/framework/wcf/feature-details/messaging-activities.md)
