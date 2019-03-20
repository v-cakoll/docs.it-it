---
title: "Procedura: Accedere a un servizio da un'applicazione flusso di lavoro"
ms.date: 03/30/2017
ms.assetid: 925ef8ea-5550-4c9d-bb7b-209e20c280ad
ms.openlocfilehash: 790f8f24ed8a6c3b7592fb8e78befc8ee5e2214d
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185428"
---
# <a name="how-to-access-a-service-from-a-workflow-application"></a>Procedura: Accedere a un servizio da un'applicazione flusso di lavoro
In questo argomento viene descritto come chiamare un servizio flusso di lavoro da un'applicazione console del flusso di lavoro. Dipende dal completamento del [come: Creare un servizio del flusso di lavoro con attività di messaggistica](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md) argomento. Sebbene in questo argomento viene descritto come chiamare un servizio del flusso di lavoro da un'applicazione flusso di lavoro, gli stessi metodi sono utilizzabile per chiamare qualsiasi servizio Windows Communication Foundation (WCF) da un'applicazione flusso di lavoro.

### <a name="create-a-workflow-console-application-project"></a>Creare un progetto di applicazione console del flusso di lavoro

1.  Start Visual Studio 2012.

2.  Caricare il progetto MyWFService creato nel [come: Creare un servizio del flusso di lavoro con attività di messaggistica](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md) argomento.

3.  Fare clic il **MyWFService** soluzione nel **Esplora soluzioni** e selezionare **Add**, **nuovo progetto**. Selezionare **flusso di lavoro** nel **modelli installati** e **applicazione Console flusso di lavoro** dall'elenco dei tipi di progetto. Assegnare al progetto il nome MyWFClient e utilizzare il percorso predefinito, come illustrato nella figura seguente.

     ![Finestra di dialogo Aggiungi nuovo progetto](./media/how-to-access-a-service-from-a-workflow-application/add-new-project-dialog.jpg)

     Scegliere il **OK** per chiudere la **finestra Aggiungi nuovo progetto**.

4.  Una volta creato il progetto, nella finestra di progettazione verrà aperto il file Workflow1.xaml. Scegliere il **casella degli strumenti** pressione di tab per aprire la casella degli strumenti se non è già aprire e fare clic sulla puntina da disegno per mantenere aperta la finestra Casella degli strumenti.

5.  Premere **Ctrl**+**F5** per compilare e avviare il servizio. Come in precedenza, viene avviato il server di sviluppo ASP.NET e in Internet Explorer viene visualizzata la pagina della Guida relativa a WCF. Tenere presente l'URI di questa pagina, in quanto sarà necessario utilizzarlo nel passaggio successivo.

     ![Visualizzazione di pagina della Guida WCF e URI di inserimento/espulsione](./media/how-to-access-a-service-from-a-workflow-application/ie-wcf-help-page-uri.jpg)

6.  Fare clic il **MyWFClient** del progetto nel **Esplora soluzioni** e selezionare **Add** > **riferimento al servizio**. Scegliere il **Discover** pulsante per la soluzione corrente per tutti i servizi di ricerca. Fare clic sul triangolo accanto a Service1.xamlx nell'elenco dei servizi. Fare clic sul triangolo accanto a Service1 per elencare i contratti implementati dal servizio Service1. Espandere la **Service1** nodo il **Services** elenco. L'operazione Echo viene visualizzato nei **operazioni** elenco come illustrato nella figura seguente.

     ![Finestra di dialogo Aggiungi riferimento al servizio](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference.jpg)

     Mantenere lo spazio dei nomi predefinito e fare clic su **OK** per chiudere la **Aggiungi riferimento al servizio** finestra di dialogo. Verrà visualizzata la finestra di dialogo indicata di seguito.

     ![Aggiungi finestra di dialogo di notifica di riferimento del servizio](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference-dialog.jpg)

     Fare clic su **OK** per chiudere la finestra di dialogo. Premere quindi CTRL+MAIUSC+B per compilare la soluzione. Si noti che nella casella degli strumenti è stata aggiunta una nuova sezione denominata **MyWFClient.ServiceReference1.Activities**. Espandere questa sezione e notare l'attività Eco aggiunta, come illustrato nella figura seguente.

     ![Attività Echo nella casella degli strumenti](./media/how-to-access-a-service-from-a-workflow-application/echo-activity-toolbox.jpg)

7.  Trascinare un'attività <xref:System.Activities.Statements.Sequence> nell'area di progettazione. È sotto la **flusso di controllo** sezione della casella degli strumenti.

8.  Con il <xref:System.Activities.Statements.Sequence> attività in stato attivo, fare clic sui **variabili** collegare e aggiungere una variabile stringa denominata `inString`. Assegnare alla variabile un valore predefinito pari `"Hello, world"` oltre a una variabile stringa denominata `outString` come illustrato nel diagramma seguente.

     ![Aggiunta di una variabile inString](./media/how-to-access-a-service-from-a-workflow-application/add-instring-variable.jpg)

9. Trascinare e rilasciare un' **Echo** attività nel <xref:System.Activities.Statements.Sequence>. Nella finestra Proprietà associare il `inMsg` argomento per il `inString` variabile e il `outMsg` argomento per il `outString` variabile, come illustrato nella figura seguente. Viene passato il valore della variabile `inString` all'operazione e quindi il valore restituito si inserisce nella variabile `outString`.

     ![Associazione degli argomenti alle variabili](./media/how-to-access-a-service-from-a-workflow-application/bind-arguments-variables.jpg)

10. Trascinare e rilasciare un **WriteLine** attività sotto il **Echo** attività per visualizzare la stringa restituita dalla chiamata del servizio. Il **WriteLine** attività si trova nel **primitive** nodo nella casella degli strumenti. Associare il **testo** argomento delle **WriteLine** attività per il `outString` variabile digitando `outString` nella casella di testo il **WriteLine** attività. Il flusso di lavoro viene ora visualizzato come illustrato nella figura seguente.

     ![Flusso di lavoro del client completato](./media/how-to-access-a-service-from-a-workflow-application/complete-client-workflow.jpg)

11. Pulsante destro del mouse sulla soluzione MyWFService e scegliere **Imposta progetti di avvio...** . Selezionare il **progetti di avvio multipli** pulsante di opzione e selezionare **avviare** per ogni progetto nella **azione** colonna come illustrato nella figura seguente.

     ![Opzioni dei progetti di avvio](./media/how-to-access-a-service-from-a-workflow-application/startup-project-options.jpg)

12. Premere CTRL+F5 per avviare il servizio e il client. Il Server di sviluppo ASP.NET ospita il servizio, Internet Explorer viene visualizzata la pagina della Guida WCF e l'applicazione workflow client viene avviato in una finestra della console e Visualizza la stringa restituita dal servizio ("Hello, world").

## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Procedura: Creare un servizio del flusso di lavoro con attività di messaggistica](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)
- [Utilizzo di un servizio WCF da un flusso di lavoro in un progetto Web](https://go.microsoft.com/fwlink/?LinkId=207725)
