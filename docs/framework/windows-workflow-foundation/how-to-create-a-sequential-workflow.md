---
title: 'Procedura: Creare un flusso di lavoro sequenziale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: 33a4d6f7db140023bc33839fec7d5e28b7f5fe51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547306"
---
# <a name="how-to-create-a-sequential-workflow"></a>Procedura: Creare un flusso di lavoro sequenziale
I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate. In questo argomento illustra la creazione di un flusso di lavoro che vengono usate sia attività incorporate, ad esempio la <xref:System.Activities.Statements.Sequence> attività e le attività personalizzate dal precedente [come: Creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) argomento. Il flusso di lavoro consente di modellare un gioco per determinare un numero.  
  
> [!NOTE]
>  Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti. Per completare questo argomento, è necessario completare prima [come: Creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).  
  
> [!NOTE]
>  Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>Per creare il flusso di lavoro  
  
1.  Fare doppio clic su **NumberGuessWorkflowActivities** nelle **Esplora soluzioni** e selezionare **Add**, **nuovo elemento**.  
  
2.  Nel **Installed**, **elementi comuni** nodo, seleziona **flusso di lavoro**. Selezionare **impegno** dalle **flusso di lavoro** elenco.  
  
3.  Tipo di `SequentialNumberGuessWorkflow` nella **Name** casella e fare clic su **Add**.  
  
4.  Trascinare un **sequenza** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta nel area di progettazione del flusso di lavoro.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>Per creare variabili e argomenti del flusso di lavoro  
  
1.  Fare doppio clic su **sequentialnumberguessworkflow. XAML** nelle **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.  
  
2.  Fare clic su **argomenti** sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **argomenti** riquadro.  
  
3.  Fare clic su **Crea argomento**.  
  
4.  Tipo `MaxNumber` nella **nome** , quindi selezionare **nel** dal **direzione** elenco a discesa, seleziona **Int32** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.  
  
5.  Fare clic su **Crea argomento**.  
  
6.  Tipo `Turns` nella **Name** finestra che si trova sotto appena aggiunta `MaxNumber` argomento, selezionare **Out** dal **direzione** dall'elenco a discesa, seleziona  **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.  
  
7.  Fare clic su **argomenti** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **argomenti** riquadro.  
  
8.  Fare clic su **variabili** sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **variabili** riquadro.  
  
9. Fare clic su **creare variabile**.  
  
    > [!TIP]
    >  Se nessun **Crea variabile** verrà visualizzata la finestra, fare clic sui **sequenza** attività nell'area di progettazione del flusso di lavoro per selezionarla.  
  
10. Tipo di `Guess` nella **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.  
  
11. Fare clic su **creare variabile**.  
  
12. Tipo di `Target` nella **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.  
  
13. Fare clic su **variabili** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **variabili** riquadro.  
  
### <a name="to-add-the-workflow-activities"></a>Per aggiungere le attività del flusso di lavoro  
  
1.  Trascinare un' **assegnare** attività dalle **primitive** sezione del **della casella degli strumenti** e rilasciarla sul **sequenza** attività. Tipo `Target` nella **al** finestra e l'espressione seguente nella **immettere un'espressione c#** o **immettere un'espressione VB** casella.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Se il **casella degli strumenti** finestra non viene visualizzata, selezionare **della casella degli strumenti** dal **visualizzazione** menu.  
  
2.  Trascinare un **DoWhile** attività dalle **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla sul flusso di lavoro in modo che si trovi sotto il **assegnare** attività.  
  
3.  Digitare l'espressione seguente nella **DoWhile** dell'attività **condizione** casella dei valori.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     Un'attività <xref:System.Activities.Statements.DoWhile> esegue le proprie attività figlio e successivamente valuta <xref:System.Activities.Statements.DoWhile.Condition%2A>. Se <xref:System.Activities.Statements.DoWhile.Condition%2A> dà come risultato `True`, le attività in <xref:System.Activities.Statements.DoWhile> vengono eseguite nuovamente. In questo esempio, viene valutata l'ipotesi dell'utente e <xref:System.Activities.Statements.DoWhile> continua finché l'ipotesi non è corretta.  
  
4.  Trascinare un **dei messaggi di richiesta** attività dal **NumberGuessWorkflowActivities** sezione del **della casella degli strumenti** e rilasciarla nel **DoWhile** attività nel passaggio precedente.  
  
5.  Nel **finestra delle proprietà**, tipo `"EnterGuess"` incluse le virgolette nella **BookmarkName** casella dei valori per i **dei messaggi di richiesta** attività. Tipo di `Guess` nella **risultato** casella del valore proprietà e digitare l'espressione seguente nella **testo** finestra delle proprietà.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  Se il **finestra delle proprietà** non è visualizzato, selezionare **finestra delle proprietà** dal **visualizzazione** menu.  
  
6.  Trascinare un **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla nel **DoWhile** attività in modo che segua il **Dei messaggi di richiesta** attività.  
  
    > [!NOTE]
    >  Quando si rilascia il **assegnare** attività, nota come la finestra di progettazione del flusso di lavoro aggiunge automaticamente un **sequenza** attività per contenere sia il **Prompt** appena aggiunto e attività **Assegnare** attività.  
  
7.  Tipo `Turns` nella **al** casella e `Turns + 1` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella.  
  
8.  Trascinare un **se** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla nel **sequenza** attività in modo che segua il aggiunti di recente **assegnare** attività.  
  
9. Digitare l'espressione seguente nella **se** dell'attività **condizione** casella dei valori.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. Trascinare un altro **se** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla nel **quindi** sezione del primo **Se** attività.  
  
11. Digitare l'espressione seguente nella nuova **se** dell'attività **condizione** casella dei valori.  
  
    ```
    Guess < Target  
    ```  
  
12. Trascinare due **WriteLine** le attività eseguite dal **primitive** sezione del **della casella degli strumenti** e rilasciarle in modo che uno è il **quindi** sezione di appena aggiunta **se** attività e l'altro è nel **Else** sezione.  
  
13. Fare clic sui **WriteLine** attività nel **quindi** sezione per selezionarlo, quindi digitare l'espressione seguente nella **testo** casella dei valori.  
  
    ```vb  
    "Your guess is too low."  
    ```  
  
14. Fare clic sui **WriteLine** attività nel **Else** sezione per selezionarlo, quindi digitare l'espressione seguente nella **testo** casella dei valori.  
  
    ```vb  
    "Your guess is too high."  
    ```  
  
     Nell'esempio seguente viene illustrato il flusso di lavoro completato.  
  
     ![Flusso di lavoro sequenza completo](../../../docs/framework/windows-workflow-foundation/media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")  
  
### <a name="to-build-the-workflow"></a>Per compilare il flusso di lavoro  
  
1.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
     Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [come: Eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md). Se sono già state completate le [come: Eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) passaggio con uno stile diverso del flusso di lavoro e si desidera eseguirlo tramite il flusso di lavoro sequenza da questo passaggio, andare direttamente al [per compilare ed eseguire l'applicazione](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) sezione [come: Eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Programmazione di Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/programming.md)
- [Progettazione di flussi di lavoro](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)
- [Esercitazione introduttiva](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
- [Procedura: Creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)
- [Procedura: Eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
