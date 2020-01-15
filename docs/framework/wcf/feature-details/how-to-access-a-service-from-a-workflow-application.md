---
title: "Procedura: accesso a un servizio da un'applicazione flusso di lavoro"
ms.date: 03/30/2017
ms.assetid: 925ef8ea-5550-4c9d-bb7b-209e20c280ad
ms.openlocfilehash: c524dc07106f039d9dc6c17ee6fb966321b6da24
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964523"
---
# <a name="how-to-access-a-service-from-a-workflow-application"></a>Procedura: accesso a un servizio da un'applicazione flusso di lavoro
In questo argomento viene descritto come chiamare un servizio flusso di lavoro da un'applicazione console del flusso di lavoro. Dipende dal completamento dell'argomento [procedura: creare un servizio del flusso di lavoro con attività di messaggistica](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md) . Anche se in questo argomento viene descritto come chiamare un servizio del flusso di lavoro da un'applicazione flusso di lavoro, è possibile utilizzare gli stessi metodi per chiamare qualsiasi servizio Windows Communication Foundation (WCF) da un'applicazione flusso di lavoro.

### <a name="create-a-workflow-console-application-project"></a>Creare un progetto di applicazione console del flusso di lavoro

1. Start Visual Studio 2012.

2. Caricare il progetto MyWFService creato nell'argomento [procedura: creare un servizio flusso di lavoro con attività di messaggistica](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md) .

3. Fare clic con il pulsante destro del mouse sulla soluzione **MyWFService** nel **Esplora soluzioni** e scegliere **Aggiungi**, **nuovo progetto**. Selezionare **flusso di lavoro** in **modelli installati** e **applicazione console flusso di lavoro** dall'elenco dei tipi di progetto. Assegnare al progetto il nome MyWFClient e utilizzare il percorso predefinito, come illustrato nella figura seguente.

     ![Finestra di dialogo Aggiungi nuovo progetto](./media/how-to-access-a-service-from-a-workflow-application/add-new-project-dialog.jpg)

     Fare clic sul pulsante **OK** per chiudere la **finestra di dialogo Aggiungi nuovo progetto**.

4. Una volta creato il progetto, nella finestra di progettazione verrà aperto il file Workflow1.xaml. Fare clic sulla scheda **casella degli strumenti** per aprire la casella degli strumenti, se non è già aperta, e fare clic sulla puntina da disegno per lasciare aperta la finestra casella degli strumenti.

5. Premere **Ctrl**+**F5** per compilare e avviare il servizio. Come in precedenza, viene avviato il server di sviluppo ASP.NET e in Internet Explorer viene visualizzata la pagina della Guida relativa a WCF. Tenere presente l'URI di questa pagina, in quanto sarà necessario utilizzarlo nel passaggio successivo.

     ![Visualizzazione dell'URI e della pagina della Guida WCF](./media/how-to-access-a-service-from-a-workflow-application/ie-wcf-help-page-uri.jpg)

6. Fare clic con il pulsante destro del mouse sul progetto **MyWFClient** nel **Esplora soluzioni** e scegliere **Aggiungi** > **riferimento al servizio**. Fare clic sul pulsante **Discover (individua** ) per cercare tutti i servizi nella soluzione corrente. Fare clic sul triangolo accanto a Service1.xamlx nell'elenco dei servizi. Fare clic sul triangolo accanto a Service1 per elencare i contratti implementati dal servizio Service1. Espandere il nodo **Service1** nell'elenco **dei servizi** . L'operazione Echo viene visualizzata nell'elenco **operazioni** , come illustrato nella figura seguente.

     ![Finestra di dialogo Aggiungi riferimento al servizio](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference.jpg)

     Lasciare lo spazio dei nomi predefinito e fare clic su **OK** per chiudere la finestra di dialogo **Aggiungi riferimento al servizio** . Verrà visualizzata la finestra di dialogo indicata di seguito.

     ![Finestra di dialogo Aggiungi riferimento al servizio notifica](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference-dialog.jpg)

     Fare clic su **OK** per chiudere la finestra di dialogo. Premere quindi CTRL+MAIUSC+B per compilare la soluzione. Si noti che nella casella degli strumenti è stata aggiunta una nuova sezione denominata **MyWFClient. ServiceReference1. Activities**. Espandere questa sezione e notare l'attività Eco aggiunta, come illustrato nella figura seguente.

     ![Attività Echo nella casella degli strumenti](./media/how-to-access-a-service-from-a-workflow-application/echo-activity-toolbox.jpg)

7. Trascinare un'attività <xref:System.Activities.Statements.Sequence> nell'area di progettazione. Si trova nella sezione **flusso di controllo** della casella degli strumenti.

8. Con l'attività <xref:System.Activities.Statements.Sequence> in stato attivo, fare clic sul collegamento **variabili** e aggiungere una variabile di stringa denominata `inString`. Assegnare alla variabile un valore predefinito di `"Hello, world"` e una variabile di stringa denominata `outString`, come illustrato nel diagramma seguente.

     ![Aggiunta di una variabile inString](./media/how-to-access-a-service-from-a-workflow-application/add-instring-variable.jpg)

9. Trascinare e rilasciare un'attività **echo** nell'<xref:System.Activities.Statements.Sequence>. Nella finestra Proprietà associare l'argomento `inMsg` alla variabile `inString` e l'argomento `outMsg` alla variabile `outString`, come illustrato nella figura seguente. Viene passato il valore della variabile `inString` all'operazione e quindi il valore restituito si inserisce nella variabile `outString`.

     ![Associazione degli argomenti alle variabili](./media/how-to-access-a-service-from-a-workflow-application/bind-arguments-variables.jpg)

10. Trascinare e rilasciare un'attività **WriteLine** al di sotto dell'attività **echo** per visualizzare la stringa restituita dalla chiamata al servizio. L'attività **WriteLine** si trova nel nodo **primitive** della casella degli strumenti. Associare l'argomento **Text** dell'attività **writeline** alla variabile `outString` digitando `outString` nella casella di testo nell'attività **WriteLine** . Il flusso di lavoro viene ora visualizzato come illustrato nella figura seguente.

     ![Flusso di lavoro del client completo](./media/how-to-access-a-service-from-a-workflow-application/complete-client-workflow.jpg)

11. Fare clic con il pulsante destro del mouse sulla soluzione MyWFService e selezionare **Imposta progetti di avvio...** . Selezionare il pulsante di opzione **progetti di avvio multipli** e selezionare **Avvia** per ogni progetto nella colonna **azione** , come illustrato nella figura seguente.

     ![Opzioni dei progetti di avvio](./media/how-to-access-a-service-from-a-workflow-application/startup-project-options.jpg)

12. Premere CTRL+F5 per avviare il servizio e il client. Il Server di sviluppo ASP.NET ospita il servizio, Internet Explorer visualizza la pagina della Guida WCF e l'applicazione flusso di lavoro client viene avviata in una finestra della console e visualizza la stringa restituita dal servizio ("Hello, World").

## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Procedura: Creare un servizio flusso di lavoro con attività di messaggistica](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)
- [Utilizzo di un servizio WCF da un flusso di lavoro in un progetto Web](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
