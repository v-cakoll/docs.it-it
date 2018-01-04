---
title: 'Procedura: creare un flusso di lavoro sequenziale'
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
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6888d13c982f282b0d3d939c1396bfaddd673efc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-sequential-workflow"></a>Procedura: creare un flusso di lavoro sequenziale
I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate. Passaggi in questo argomento per la creazione di un flusso di lavoro che utilizza entrambe le attività predefinite, ad esempio il <xref:System.Activities.Statements.Sequence> attività e le attività personalizzate dal precedente [procedura: creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) argomento. Il flusso di lavoro consente di modellare un gioco per determinare un numero.  
  
> [!NOTE]
>  Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti. Per completare questo argomento, è necessario prima completare [procedura: creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).  
  
> [!NOTE]
>  Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>Per creare il flusso di lavoro  
  
1.  Fare doppio clic su **NumberGuessWorkflowActivities** in **Esplora** e selezionare **Aggiungi**, **nuovo elemento**.  
  
2.  Nel **installato**, **elementi comuni** nodo, seleziona **flusso di lavoro**. Selezionare **attività** dal **flusso di lavoro** elenco.  
  
3.  Tipo `SequentialNumberGuessWorkflow` nel **nome** casella e fare clic su **Aggiungi**.  
  
4.  Trascinare un **sequenza** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta nel area di progettazione del flusso di lavoro.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>Per creare variabili e argomenti del flusso di lavoro  
  
1.  Fare doppio clic su **Sequentialnumberguessworkflow** in **Esplora** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.  
  
2.  Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il **argomenti** riquadro.  
  
3.  Fare clic su **Crea argomento**.  
  
4.  Tipo `MaxNumber` nel **nome** , quindi selezionare **In** dal **direzione** elenco a discesa, seleziona **Int32** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.  
  
5.  Fare clic su **Crea argomento**.  
  
6.  Tipo `Turns` nel **nome** casella che si trova sotto appena aggiunta `MaxNumber` argomento, selezionare **Out** dal **direzione** -elenco a discesa, seleziona  **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.  
  
7.  Fare clic su **argomenti** nel lato inferiore sinistro dell'ActivityDesigner per chiudere la **argomenti** riquadro.  
  
8.  Fare clic su **variabili** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il **variabili** riquadro.  
  
9. Fare clic su **creare variabile**.  
  
    > [!TIP]
    >  Se non **Crea variabile** viene visualizzata, fare clic su di **sequenza** attività nell'area di progettazione del flusso di lavoro per selezionarla.  
  
10. Tipo `Guess` nel **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.  
  
11. Fare clic su **creare variabile**.  
  
12. Tipo `Target` nel **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.  
  
13. Fare clic su **variabili** nel lato inferiore sinistro dell'ActivityDesigner per chiudere la **variabili** riquadro.  
  
### <a name="to-add-the-workflow-activities"></a>Per aggiungere le attività del flusso di lavoro  
  
1.  Trascinare un **assegnare** attività dal **primitive** sezione il **della casella degli strumenti** e rilasciarla il **sequenza** attività. Tipo `Target` nel **a** casella e l'espressione seguente nella **immettere un'espressione c#** o **immettere un'espressione VB** casella.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Se il **della casella degli strumenti** non verrà visualizzata la finestra, selezionare **della casella degli strumenti** dal **vista** menu.  
  
2.  Trascinare un **DoWhile** attività dal **flusso di controllo** sezione il **della casella degli strumenti** e rilasciarla sul flusso di lavoro in modo che si trovi sotto il **assegnare** attività.  
  
3.  Digitare l'espressione seguente nella **DoWhile** dell'attività **condizione** casella valore della proprietà.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     Un'attività <xref:System.Activities.Statements.DoWhile> esegue le proprie attività figlio e successivamente valuta <xref:System.Activities.Statements.DoWhile.Condition%2A>. Se <xref:System.Activities.Statements.DoWhile.Condition%2A> dà come risultato `True`, le attività in <xref:System.Activities.Statements.DoWhile> vengono eseguite nuovamente. In questo esempio, viene valutata l'ipotesi dell'utente e <xref:System.Activities.Statements.DoWhile> continua finché l'ipotesi non è corretta.  
  
4.  Trascinare un **Prompt** attività dal **NumberGuessWorkflowActivities** sezione del **della casella degli strumenti** e rilasciarlo nel **DoWhile** attività nel passaggio precedente.  
  
5.  Nel **finestra proprietà**, tipo `"EnterGuess"` incluse le virgolette nel **BookmarkName** casella valore della proprietà per il **Prompt** attività. Tipo `Guess` nel **risultato** casella valore di proprietà e digitare l'espressione seguente nella **testo** casella della proprietà.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  Se il **finestra proprietà** non è visualizzata, selezionare **finestra proprietà** dal **vista** menu.  
  
6.  Trascinare un **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarlo nel **DoWhile** attività in modo che segua il **Prompt** attività.  
  
    > [!NOTE]
    >  Quando si trascina il **assegnare** attività, nota come finestra di progettazione del flusso di lavoro aggiunge automaticamente un **sequenza** attività per contenere sia il **Prompt** appena aggiunta e attività **Assegnare** attività.  
  
7.  Tipo `Turns` nel **a** casella e `Turns + 1` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella.  
  
8.  Trascinare un **se** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarlo nel **sequenza** attività in modo che segua il aggiunta di **assegnare** attività.  
  
9. Digitare l'espressione seguente nella **se** dell'attività **condizione** casella valore della proprietà.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. Trascinare un'altra **se** attività dal **flusso di controllo** sezione il **della casella degli strumenti** e rilasciarlo nel **quindi** sezione del primo **Se** attività.  
  
11. Digitare l'espressione seguente in appena aggiunta **se** dell'attività **condizione** casella valore della proprietà.  
  
    ```
    Guess < Target  
    ```  
  
12. Trascinare due **WriteLine** le attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarle in modo che uno è il **quindi** sezione di appena aggiunta **se** attività e l'altro è il **Else** sezione.  
  
13. Fare clic sul **WriteLine** attività di **quindi** sezione per selezionarlo, quindi digitare l'espressione seguente nel **testo** casella valore della proprietà.  
  
    ```vb  
    "Your guess is too low."  
    ```  
  
14. Fare clic sul **WriteLine** attività di **Else** sezione per selezionarlo, quindi digitare l'espressione seguente nel **testo** casella valore della proprietà.  
  
    ```vb  
    "Your guess is too high."  
    ```  
  
     Nell'esempio seguente viene illustrato il flusso di lavoro completato.  
  
     ![Flusso di lavoro sequenza completato](../../../docs/framework/windows-workflow-foundation/media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")  
  
### <a name="to-build-the-workflow"></a>Per compilare il flusso di lavoro  
  
1.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
     Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [procedura: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md). Se è già stata completata la [come: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) spostarsi con uno stile diverso del flusso di lavoro e desidera eseguirlo tramite il flusso di lavoro sequenza da questo passaggio, ignorare il [per compilare ed eseguire l'applicazione](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)sezione [procedura: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [Programmazione di Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [Progettazione di flussi di lavoro](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [Esercitazione introduttiva](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [Procedura: Creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [Procedura: Eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
