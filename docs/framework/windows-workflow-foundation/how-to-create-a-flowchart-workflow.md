---
title: 'Procedura: Creare un flusso di lavoro del diagramma di flusso'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: 15cf94d5ea191435723f754f35e43d65632142e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311201"
---
# <a name="how-to-create-a-flowchart-workflow"></a>Procedura: Creare un flusso di lavoro del diagramma di flusso
I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate. In questo argomento illustra la creazione di un flusso di lavoro che vengono usate sia attività incorporate, ad esempio la <xref:System.Activities.Statements.Flowchart> attività e le attività personalizzate dal precedente [come: Creare un'attività](how-to-create-an-activity.md) argomento. Il flusso di lavoro consente di modellare un gioco per determinare un numero.  
  
> [!NOTE]
>  Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti. Per completare questo argomento, è necessario completare prima [come: Creare un'attività](how-to-create-an-activity.md).  
  
> [!NOTE]
>  Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>Per creare il flusso di lavoro  
  
1. Fare doppio clic su **NumberGuessWorkflowActivities** nelle **Esplora soluzioni** e selezionare **Add**, **nuovo elemento**.  
  
2. Nel **Installed**, **elementi comuni** nodo, seleziona **flusso di lavoro**. Selezionare **impegno** dalle **flusso di lavoro** elenco.  
  
3. Tipo di `FlowchartNumberGuessWorkflow` nella **Name** casella e fare clic su **Add**.  
  
4. Trascinare un **diagramma di flusso** attività dal **diagramma di flusso** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta nel area di progettazione del flusso di lavoro.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>Per creare variabili e argomenti del flusso di lavoro  
  
1. Fare doppio clic su **Flowchartnumberguessworkflow** nelle **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.  
  
2. Fare clic su **argomenti** sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **argomenti** riquadro.  
  
3. Fare clic su **Crea argomento**.  
  
4. Tipo `MaxNumber` nella **nome** , quindi selezionare **nel** dal **direzione** elenco a discesa, seleziona **Int32** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.  
  
5. Fare clic su **Crea argomento**.  
  
6. Tipo `Turns` nella **Name** finestra che si trova sotto appena aggiunta `MaxNumber` argomento, selezionare **Out** dal **direzione** dall'elenco a discesa, seleziona  **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.  
  
7. Fare clic su **argomenti** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **argomenti** riquadro.  
  
8. Fare clic su **variabili** sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **variabili** riquadro.  
  
9. Fare clic su **creare variabile**.  
  
    > [!TIP]
    >  Se nessun **Crea variabile** verrà visualizzata la finestra, fare clic su di <xref:System.Activities.Statements.Flowchart> attività nell'area di progettazione del flusso di lavoro per selezionarla.  
  
10. Tipo di `Guess` nella **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.  
  
11. Fare clic su **creare variabile**.  
  
12. Tipo di `Target` nella **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.  
  
13. Fare clic su **variabili** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **variabili** riquadro.  
  
### <a name="to-add-the-workflow-activities"></a>Per aggiungere le attività del flusso di lavoro  
  
1. Trascinare un' **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e passarla sul **avviare** nodo, ovvero all'inizio del diagramma di flusso. Quando la **assegnare** attività è posizionato sulle **avviare** nodo, verranno visualizzati tre triangoli intorno al **avviare** nodo. Eliminare il **assegnare** attività sul triangolo che si trova direttamente sotto il **avviare** nodo. Questo verrà collegare i due elementi e designa il **assegnare** attività come la prima attività nel diagramma di flusso.  
  
    > [!NOTE]
    >  È possibile designare le attività come attività iniziali nel diagramma di flusso anche collegandole manualmente al nodo iniziale. A tale scopo, posizionare il mouse sopra il **avviare** nodo, fare clic su uno dei rettangoli visualizzati quando il mouse è posizionato sopra il **avviare** nodo e quindi trascinare la connessione di riga sull'attività desiderata e rilasciarla su uno dei i rettangoli visualizzati. È inoltre possibile specificare un'attività come attività iniziale facendo clic su it e scegliendo **imposta come StartNode**.  
  
2. Tipo `Target` nella **al** finestra e l'espressione seguente nella **immettere un'espressione c#** o **immettere un'espressione VB** casella.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Se il **casella degli strumenti** finestra non viene visualizzata, selezionare **della casella degli strumenti** dal **visualizzazione** menu.  
  
3. Trascinare un **dei messaggi di richiesta** attività dalle **NumberGuessWorkflowActivities** sezione del **della casella degli strumenti**, rilasciarla sotto il **assegnare** attività dal precedente passaggio e connettere il **dei messaggi di richiesta** attività per il **assegnare** attività. Esistono tre modi per connettere le due attività. Il primo modo consiste nel connetterle quando si rilascia il **dei messaggi di richiesta** attività del flusso di lavoro. Mentre si trascina il **dei messaggi di richiesta** attività al flusso di lavoro, passarlo sulle **assegnare** attività e rilasciarlo su uno dei quattro triangoli visualizzati quando il **Prompt** attività è tramite il **assegnare** attività. Il secondo modo consiste nell'eliminare la **dei messaggi di richiesta** attività sul flusso di lavoro nella posizione desiderata. Quindi, posizionare il mouse sopra il **assegnare** attività e trascinare uno dei rettangoli visualizzati fino al **dei messaggi di richiesta** attività. Trascinare il puntatore del mouse in modo che la linea di connessione dal **assegnare** attività si connette a uno dei rettangoli delle **dei messaggi di richiesta** attività e quindi rilasciare il pulsante del mouse. Il terzo modo è molto simile al primo modo, con la differenza che invece di trascinare il **dei messaggi di richiesta** attività dalle **della casella degli strumenti**, si trascina dalla relativa posizione nell'area di progettazione del flusso di lavoro, passarlo sul  **Assegnare** attività e rilasciarlo su uno dei triangoli visualizzati.  
  
4. Nel **finestra delle proprietà** per il **dei messaggi di richiesta** attività, digitare `"EnterGuess"` incluse le virgolette nella **BookmarkName** casella dei valori. Tipo di `Guess` nella **risultato** casella del valore proprietà e digitare l'espressione seguente nella **testo** finestra delle proprietà.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  Se il **finestra delle proprietà** non è visualizzato, selezionare **finestra delle proprietà** dal **visualizzazione** menu.  
  
5. Trascinare un' **assegnare** attività dalle **primitive** sezione del **della casella degli strumenti** e connetterla usando uno dei metodi descritti nel passaggio precedente in modo che si trovi sotto il  **Messaggio di richiesta** attività.  
  
6. Tipo `Turns` nella **al** casella e `Turns + 1` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella.  
  
7. Trascinare un **FlowDecision** dalle **diagramma di flusso** sezione del **della casella degli strumenti** e connetterla sotto il **assegnare** attività. Nel **finestra delle proprietà**, digitare l'espressione seguente nella **condizione** casella dei valori.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. Trascinare un'altra **FlowDecision** attività dalle **della casella degli strumenti** e rilasciarlo sotto il primo elemento. Connettere le due attività trascinando dal rettangolo con etichetta **False** in alto **FlowDecision** attività per il rettangolo nella parte superiore della seconda **FlowDecision**attività.  
  
    > [!TIP]
    >  Se non viene visualizzato il **True** e **False** etichette nel **FlowDecision**, posizionare il mouse sopra il **FlowDecision**.  
  
9. Fare clic sul secondo **FlowDecision** attività per selezionarla. Nel **finestra delle proprietà**, digitare l'espressione seguente nella **condizione** casella dei valori.  
  
    ```
    Guess < Target  
    ```  
  
10. Trascinare due **WriteLine** le attività eseguite dal **primitive** sezione la **della casella degli strumenti** e rilasciarle in modo che siano affiancate sotto le due **FlowDecision**  attività. Connettere il **True** azione della parte inferiore **FlowDecision** attività più a sinistra **WriteLine** attività e il **False** azione per il all'estrema destra **WriteLine** attività.  
  
11. Fare clic su più a sinistra **WriteLine** attività per selezionarla e digitare l'espressione seguente nel **testo** casella di valore della proprietà di **finestra proprietà**.  
  
    ```
    "Your guess is too low."  
    ```  
  
12. Connettere il **WriteLine** a sinistra del **dei messaggi di richiesta** attività che si trova.  
  
13. Fare clic all'estrema destra **WriteLine** attività per selezionarla e digitare l'espressione seguente nella **testo** casella di valore della proprietà il **finestra proprietà**.  
  
    ```
    "Your guess is too high."  
    ```  
  
14. Connettere il **WriteLine** attività sul lato destro delle **dei messaggi di richiesta** attività sopra di esso.  
  
     Nell'esempio seguente viene illustrato il flusso di lavoro completato.  
  
     ![Windows Workflow Foundation completato](./media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")  
  
### <a name="to-build-the-workflow"></a>Per compilare il flusso di lavoro  
  
1. Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
     Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [come: Eseguire un flusso di lavoro](how-to-run-a-workflow.md). Se sono già state completate le [come: Eseguire un flusso di lavoro](how-to-run-a-workflow.md) passaggio con uno stile diverso del flusso di lavoro e si desidera eseguirlo tramite il flusso di lavoro del diagramma di flusso da questo passaggio, andare direttamente al [per compilare ed eseguire l'applicazione](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) sezione [come: Eseguire un flusso di lavoro](how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Programmazione di Windows Workflow Foundation](programming.md)
- [Progettazione di flussi di lavoro](designing-workflows.md)
- [Esercitazione introduttiva](getting-started-tutorial.md)
- [Procedura: Creare un'attività](how-to-create-an-activity.md)
- [Procedura: Eseguire un flusso di lavoro](how-to-run-a-workflow.md)
