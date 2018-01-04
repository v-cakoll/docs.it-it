---
title: 'Procedura: creare un flusso di lavoro del diagramma di flusso'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b7a8eab16b089597eecc03896f86827aae1ad85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-flowchart-workflow"></a>Procedura: creare un flusso di lavoro del diagramma di flusso
I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate. Passaggi in questo argomento per la creazione di un flusso di lavoro che utilizza entrambe le attività predefinite, ad esempio il <xref:System.Activities.Statements.Flowchart> attività e le attività personalizzate dal precedente [procedura: creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) argomento. Il flusso di lavoro consente di modellare un gioco per determinare un numero.  
  
> [!NOTE]
>  Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti. Per completare questo argomento, è necessario prima completare [procedura: creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).  
  
> [!NOTE]
>  Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>Per creare il flusso di lavoro  
  
1.  Fare doppio clic su **NumberGuessWorkflowActivities** in **Esplora** e selezionare **Aggiungi**, **nuovo elemento**.  
  
2.  Nel **installato**, **elementi comuni** nodo, seleziona **flusso di lavoro**. Selezionare **attività** dal **flusso di lavoro** elenco.  
  
3.  Tipo `FlowchartNumberGuessWorkflow` nel **nome** casella e fare clic su **Aggiungi**.  
  
4.  Trascinare un **diagramma di flusso** attività dal **diagramma di flusso** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta nel area di progettazione del flusso di lavoro.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>Per creare variabili e argomenti del flusso di lavoro  
  
1.  Fare doppio clic su **Flowchartnumberguessworkflow** in **Esplora** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.  
  
2.  Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il **argomenti** riquadro.  
  
3.  Fare clic su **Crea argomento**.  
  
4.  Tipo `MaxNumber` nel **nome** , quindi selezionare **In** dal **direzione** elenco a discesa, seleziona **Int32** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.  
  
5.  Fare clic su **Crea argomento**.  
  
6.  Tipo `Turns` nel **nome** casella che si trova sotto appena aggiunta `MaxNumber` argomento, selezionare **Out** dal **direzione** -elenco a discesa, seleziona  **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.  
  
7.  Fare clic su **argomenti** nel lato inferiore sinistro dell'ActivityDesigner per chiudere la **argomenti** riquadro.  
  
8.  Fare clic su **variabili** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il **variabili** riquadro.  
  
9. Fare clic su **creare variabile**.  
  
    > [!TIP]
    >  Se non **Crea variabile** viene visualizzata, fare clic su di <xref:System.Activities.Statements.Flowchart> attività nell'area di progettazione del flusso di lavoro per selezionarla.  
  
10. Tipo `Guess` nel **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.  
  
11. Fare clic su **creare variabile**.  
  
12. Tipo `Target` nel **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.  
  
13. Fare clic su **variabili** nel lato inferiore sinistro dell'ActivityDesigner per chiudere la **variabili** riquadro.  
  
### <a name="to-add-the-workflow-activities"></a>Per aggiungere le attività del flusso di lavoro  
  
1.  Trascinare un **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e passarla sul **avviare** nodo, nella parte superiore del diagramma di flusso. Quando il **assegnare** attività è posizionato il **avviare** nodo, verranno visualizzati tre triangoli intorno il **avviare** nodo. Eliminare il **assegnare** attività sul triangolo che si trova direttamente sotto il **avviare** nodo. Questo verrà collegare i due elementi e designa il **assegnare** attività come la prima attività nel diagramma di flusso.  
  
    > [!NOTE]
    >  È possibile designare le attività come attività iniziali nel diagramma di flusso anche collegandole manualmente al nodo iniziale. A tale scopo, posizionare il mouse sopra il **avviare** nodo, fare clic su uno dei rettangoli visualizzati quando il mouse è posizionato il **avviare** nodo e trascinare la connessione di riga sull'attività desiderata e rilasciarla su uno di i rettangoli visualizzati. È inoltre possibile designare e attività come attività iniziale facendo clic it e scegliendo **imposta come StartNode**.  
  
2.  Tipo `Target` nel **a** casella e l'espressione seguente nella **immettere un'espressione c#** o **immettere un'espressione VB** casella.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Se il **della casella degli strumenti** non verrà visualizzata la finestra, selezionare **della casella degli strumenti** dal **vista** menu.  
  
3.  Trascinare un **prompt dei comandi** attività dal **NumberGuessWorkflowActivities** sezione del **della casella degli strumenti**, rilasciarlo di sotto di **assegnare** attività dal precedente passaggio e collegare il **Prompt** attività per il **assegnare** attività. Esistono tre modi per connettere le due attività. La prima consiste nel connetterle quando si elimina il **Prompt** attività del flusso di lavoro. Mentre si trascina il **prompt dei comandi** attività al flusso di lavoro, posizionarla sopra il **assegnare** attività e rilasciarla su uno dei quattro triangoli visualizzati quando il **Prompt** attività è posizionato il **assegnare** attività. Il secondo modo consiste nel rilasciare il **Prompt** attività sul flusso di lavoro nella posizione desiderata. Quindi, posizionare il mouse sopra il **assegnare** attività e trascinare uno dei rettangoli visualizzati fino al **prompt dei comandi** attività. Trascinare il mouse in modo che la linea di connessione dal **assegnare** attività si connette a uno dei rettangoli del **Prompt** attività e quindi rilasciare il pulsante del mouse. Il terzo modo è molto simile al primo, tranne il fatto che invece di trascinare il **Prompt** attività dal **della casella degli strumenti**, si trascina dalla relativa posizione nell'area di progettazione del flusso di lavoro, posizionarla sopra il  **Assegnare** , attività e rilasciarlo su uno dei triangoli visualizzati.  
  
4.  Nel **finestra proprietà** per il **Prompt** attività, digitare `"EnterGuess"` incluse le virgolette nel **BookmarkName** casella valore della proprietà. Tipo `Guess` nel **risultato** casella valore di proprietà e digitare l'espressione seguente nella **testo** casella della proprietà.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  Se il **finestra proprietà** non è visualizzata, selezionare **finestra proprietà** dal **vista** menu.  
  
5.  Trascinare un **assegnare** attività dal **primitive** sezione il **della casella degli strumenti** e connetterla usando uno dei metodi descritti nel passaggio precedente, in modo che si trovi sotto il  **Prompt dei comandi** attività.  
  
6.  Tipo `Turns` nel **a** casella e `Turns + 1` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella.  
  
7.  Trascinare un **FlowDecision** dal **diagramma di flusso** sezione il **della casella degli strumenti** e connetterla sotto il **assegnare** attività. Nel **finestra proprietà**, digitare l'espressione seguente nella **condizione** casella valore della proprietà.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8.  Trascinare un'altra **FlowDecision** attività di **della casella degli strumenti** e rilasciarlo sotto il primo. Connettere le due attività trascinando dal rettangolo con etichetta **False** in alto **FlowDecision** attività per il rettangolo nella parte superiore del secondo **FlowDecision**attività.  
  
    > [!TIP]
    >  Se non viene visualizzato il **True** e **False** etichette del **FlowDecision**, posizionare il mouse sopra il **FlowDecision**.  
  
9. Fare clic sul secondo **FlowDecision** attività per selezionarlo. Nel **finestra proprietà**, digitare l'espressione seguente nella **condizione** casella valore della proprietà.  
  
    ```
    Guess < Target  
    ```  
  
10. Trascinare due **WriteLine** le attività dal **primitive** sezione la **della casella degli strumenti** e rilasciarle in modo che siano affiancate sotto le due **FlowDecision**  attività. Connettere il **True** azione della parte inferiore **FlowDecision** attività più a sinistra **WriteLine** attività e il **False** azione per il all'estrema destra **WriteLine** attività.  
  
11. Fare clic su quello all'estrema sinistra **WriteLine** attività per selezionarla e digitare l'espressione seguente nella **testo** nella casella valore della proprietà di **finestra proprietà**.  
  
    ```
    "Your guess is too low."  
    ```  
  
12. Connettere il **WriteLine** sul lato sinistro del **prompt dei comandi** attività sopra di esso.  
  
13. Fare clic su all'estrema destra **WriteLine** attività per selezionarla e digitare l'espressione seguente nella **testo** nella casella valore della proprietà di **finestra proprietà**.  
  
    ```
    "Your guess is too high."  
    ```  
  
14. Connettere il **WriteLine** attività sul lato destro del **prompt dei comandi** attività sopra di esso.  
  
     Nell'esempio seguente viene illustrato il flusso di lavoro completato.  
  
     ![Windows Workflow Foundation completato](../../../docs/framework/windows-workflow-foundation/media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")  
  
### <a name="to-build-the-workflow"></a>Per compilare il flusso di lavoro  
  
1.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
     Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [procedura: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md). Se è già stata completata la [come: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) spostarsi con uno stile diverso del flusso di lavoro e desidera eseguirlo tramite il flusso di lavoro di diagramma di flusso tramite questo passaggio, ignorare il [per compilare ed eseguire l'applicazione](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)sezione [procedura: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [Programmazione di Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [Progettazione di flussi di lavoro](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [Esercitazione introduttiva](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [Procedura: Creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [Procedura: Eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
