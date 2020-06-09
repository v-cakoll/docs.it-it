---
title: 'Procedura: creare un servizio flusso di lavoro con attività di messaggistica'
ms.date: 03/30/2017
ms.assetid: 53d094e2-6901-4aa1-88b8-024b27ccf78b
ms.openlocfilehash: b4991fc9f8a6c45cae3943f1506247c42ed2b30b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597124"
---
# <a name="how-to-create-a-workflow-service-with-messaging-activities"></a>Procedura: creare un servizio flusso di lavoro con attività di messaggistica
In questo argomento viene illustrato come creare un semplice servizio flusso di lavoro utilizzando le attività di messaggistica. L'argomento è incentrato sui meccanismi di creazione di un servizio flusso di lavoro in cui il servizio è costituito esclusivamente da attività di messaggistica. In servizi reali i flussi di lavoro contengono molte altre attività. Il servizio implementa un'operazione denominata Echo che acquisisce una stringa e la restituisce al chiamante. Questo è il primo di una serie di due argomenti. Nell'argomento successivo [procedura: accedere a un servizio da un'applicazione flusso di lavoro](how-to-access-a-service-from-a-workflow-application.md) viene illustrato come creare un'applicazione flusso di lavoro in grado di chiamare il servizio creato in questo argomento.  
  
### <a name="to-create-a-workflow-service-project"></a>Per creare un progetto di servizio flusso di lavoro  
  
1. Avviare Visual Studio 2012.  
  
2. Fare clic sul menu **file** , selezionare **nuovo**e quindi **progetto** per visualizzare la **finestra di dialogo nuovo progetto**. Selezionare **flusso di lavoro** dall'elenco dei modelli installati e **dell'applicazione del servizio flusso di lavoro WCF** dall'elenco dei tipi di progetto. Assegnare un nome al progetto `MyWFService` e utilizzare il percorso predefinito, come illustrato nella figura seguente.  
  
     Fare clic sul pulsante **OK** per chiudere la **finestra di dialogo nuovo progetto**.  
  
3. Una volta creato il progetto, nella finestra di progettazione verrà aperto il file Service1.xamlx, come illustrato nella figura seguente.  
  
     ![Screenshot mostra il file Service1. xamlx aperto nella finestra di progettazione.](./media/how-to-create-a-workflow-service-with-messaging-activities/default-workflow-service.jpg)  
  
     Fare clic con il pulsante destro del mouse sull'attività **Servizio sequenziale** e scegliere **Elimina**.  
  
### <a name="to-implement-the-workflow-service"></a>Per implementare il servizio flusso di lavoro  
  
1. Selezionare la scheda **casella degli strumenti** sul lato sinistro della schermata per visualizzare la casella degli strumenti e fare clic sulla puntina da disegno per lasciare aperta la finestra. Espandere la sezione **messaggistica** della casella degli strumenti per visualizzare le attività di messaggistica e i modelli di attività di messaggistica, come illustrato nella figura seguente.  
  
     ![Screenshot che mostra la casella degli strumenti con la sezione della messaggistica espansa.](./media/how-to-create-a-workflow-service-with-messaging-activities/toolbox-messaging-section.jpg)  
  
2. Trascinare e rilasciare un modello **ReceiveAndSendReply** in Progettazione flussi di lavoro. In questo modo viene creata un'attività <xref:System.Activities.Statements.Sequence> con un'attività **Receive** seguita da un' <xref:System.ServiceModel.Activities.SendReply> attività, come illustrato nella figura seguente.  
  
     ![Screenshot che mostra il modello ReceiveAndSendReply.](./media/how-to-create-a-workflow-service-with-messaging-activities/receiveandsendreply-template.jpg)  
  
     La proprietà <xref:System.ServiceModel.Activities.SendReply> dell'attività <xref:System.ServiceModel.Activities.SendReply.Request%2A> è impostata su `Receive`, il nome dell'attività <xref:System.ServiceModel.Activities.Receive> a cui risponde l'attività <xref:System.ServiceModel.Activities.SendReply>.  
  
3. Nel <xref:System.ServiceModel.Activities.Receive> tipo di attività `Echo` nella casella di testo denominata **OperationName**. In questo modo viene definito il nome dell'operazione implementata dal servizio.  
  
     ![Screenshot che mostra dove specificare il nome dell'operazione.](./media/how-to-create-a-workflow-service-with-messaging-activities/define-operation-name.jpg)  
  
4. Con l' <xref:System.ServiceModel.Activities.Receive> attività selezionata, aprire la finestra Proprietà, se non è già aperta, scegliendo **finestra Proprietà**dal menu **Visualizza** . Nella **finestra Proprietà** scorrere verso il basso fino a visualizzare **CanCreateInstance** e fare clic sulla casella di controllo come illustrato nella figura seguente. Questa impostazione consente all'host del servizio flusso di lavoro di creare, se necessario, una nuova istanza del servizio dopo la ricezione di un messaggio.  
  
     ![Screenshot che mostra la proprietà CanCreateInstance.](./media/how-to-create-a-workflow-service-with-messaging-activities/cancreateinstance-property.jpg)  
  
5. Selezionare l' <xref:System.Activities.Statements.Sequence> attività e fare clic sul pulsante **variabili** nell'angolo inferiore sinistro della finestra di progettazione. Verrà visualizzato l'editor delle variabili. Fare clic sul collegamento **Crea variabile** per aggiungere una variabile per archiviare la stringa inviata all'operazione. Assegnare un nome alla variabile `msg` e impostare il tipo di **variabile** su String, come illustrato nella figura seguente.  
  
     ![Screenshot che illustra come aggiungere una variabile.](./media/how-to-create-a-workflow-service-with-messaging-activities/add-variable-msg-string.jpg)  
  
     Fare di nuovo clic sul pulsante **variabili** per chiudere l'editor delle variabili.  
  
6. Fare clic su **Definisci.** collegamento nella casella di testo **contenuto** dell' <xref:System.ServiceModel.Activities.Receive> attività per visualizzare la finestra di dialogo **Definizione contenuto** . Selezionare il pulsante di opzione **parametri** , fare clic sul collegamento **Aggiungi nuovo parametro** , digitare `inMsg` nella casella di testo **nome** , selezionare **stringa** nella casella di riepilogo a discesa **tipo** e digitare `msg` nella casella di testo **assegna a** , come illustrato nella figura seguente.  
  
     ![Screenshot che mostra l'aggiunta di contenuto dei parametri.](./media/how-to-create-a-workflow-service-with-messaging-activities/adding-parameters-content.jpg)  
  
     In questo modo viene specificato che l'attività Receive riceve il parametro stringa e che i dati sono associati alla variabile `msg`. Fare clic su **OK** per chiudere la finestra di dialogo **Definizione contenuto** .  
  
7. Fare clic sul collegamento **Definisci** nella casella **contenuto** nell' <xref:System.ServiceModel.Activities.SendReply> attività per visualizzare la finestra di dialogo **Definizione contenuto** . Selezionare il pulsante di opzione **parametri** , fare clic sul collegamento **Aggiungi nuovo parametro** , digitare nella casella di `outMsg` testo **nome** , selezionare **stringa** nell'elenco a discesa **tipo** e `msg` nella casella di testo **valore** , come illustrato nella figura seguente.  
  
     ![Screenshot che illustra come aggiungere il parametro outMsg.](./media/how-to-create-a-workflow-service-with-messaging-activities/outmsg-parameters-content.jpg)  
  
     In questo modo viene specificato che l'attività <xref:System.ServiceModel.Activities.SendReply> invia un messaggio o un tipo di contratto messaggio e che i dati sono associati alla variabile `msg`. Poiché si tratta di un'attività <xref:System.ServiceModel.Activities.SendReply>, i dati in `msg` vengono usati per popolare il messaggio inviato in risposta al client da parte dell'attività. Fare clic su **OK** per chiudere la finestra di dialogo **Definizione contenuto** .  
  
8. Salvare e compilare la soluzione facendo clic sul menu **Compila** e selezionando **Compila soluzione**.  
  
## <a name="configure-the-workflow-service-project"></a>Configurare il progetto di servizio flusso di lavoro  
 Il servizio flusso di lavoro è completo. Contenuto della sezione viene illustrato come configurare la soluzione del servizio flusso di lavoro per agevolarne l'hosting e l'esecuzione. Questa soluzione utilizza il server di sviluppo ASP.NET per ospitare il servizio.  
  
#### <a name="to-set-project-start-up-options"></a>Per impostare le opzioni di avvio del progetto  
  
1. Nella **Esplora soluzioni**fare clic con il pulsante destro del mouse su **MyWFService** e scegliere **proprietà** per visualizzare la finestra di dialogo **Proprietà progetto** .  
  
2. Selezionare la scheda **Web** e selezionare la **pagina specifica** in **azione di avvio** e digitare `Service1.xamlx` nella casella di testo, come illustrato nella figura seguente.  
  
     ![Screenshot che mostra la finestra di dialogo delle proprietà del progetto.](./media/how-to-create-a-workflow-service-with-messaging-activities/project-properties-dialog.jpg)  
  
     In questo modo, il servizio definito in Service1.xamlx viene ospitato nel server di sviluppo ASP.NET.  
  
3. Premere CTRL+F5 per avviare il servizio. L'icona del server di sviluppo ASP.NET verrà visualizzata nel lato inferiore destro del desktop, come illustrato nella figura seguente.  
  
     ![Screenshot che mostra l'icona di ASP.NET Developer Server.](./media/how-to-create-a-workflow-service-with-messaging-activities/asp-net-dev-server-icon.jpg)  
  
     In Internet Explorer verrà inoltre visualizzata la pagina della Guida del servizio WCF relativa al servizio.  
  
     ![Screenshot che mostra la pagina della guida del servizio WCF.](./media/how-to-create-a-workflow-service-with-messaging-activities/wcf-service-help-page.jpg)  
  
4. Continuare con l'argomento [procedura: accedere a un servizio da un'applicazione flusso di lavoro](how-to-access-a-service-from-a-workflow-application.md) per creare un client del flusso di lavoro che chiama il servizio.  
  
## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](workflow-services.md)
- [Panoramica dell'hosting dei servizi flusso di lavoro](hosting-workflow-services-overview.md)
- [Attività di messaggistica](messaging-activities.md)
