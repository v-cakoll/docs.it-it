---
title: 'Procedura: creare un flusso di lavoro sequenziale'
description: Questo articolo crea un flusso di lavoro che usa sia le attività predefinite, ad esempio l'attività Sequence, che le attività personalizzate.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: f80ac471fdcc425504b11b5fb17effa888aa9590
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419694"
---
# <a name="how-to-create-a-sequential-workflow"></a>Procedura: creare un flusso di lavoro sequenziale

I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate. Questo argomento illustra la creazione di un flusso di lavoro che usa sia attività predefinite, ad esempio l' <xref:System.Activities.Statements.Sequence> attività, che le attività personalizzate dell'argomento [procedura: creare un'attività](how-to-create-an-activity.md) precedente. Il flusso di lavoro consente di modellare un gioco per determinare un numero.

> [!NOTE]
> Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti. Per completare questo argomento, è necessario completare prima di tutto [procedura: creare un'attività](how-to-create-an-activity.md).

> [!NOTE]
> Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).

## <a name="to-create-the-workflow"></a>Per creare il flusso di lavoro

1. Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowActivities** in **Esplora soluzioni** e scegliere **Aggiungi**, **nuovo elemento**.

2. Nel nodo **elementi comuni** **installati**selezionare **flusso di lavoro**. Selezionare l'**attività** dall'elenco **Workflow**.

3. Digitare `SequentialNumberGuessWorkflow` nella casella **nome** e fare clic su **Aggiungi**.

4. Trascinare un'attività **Sequence** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla sull'etichetta rilasciare l' **attività** nell'area di progettazione del flusso di lavoro.

## <a name="to-create-the-workflow-variables-and-arguments"></a>Per creare variabili e argomenti del flusso di lavoro

1. Fare doppio clic su **SequentialNumberGuessWorkflow. XAML** in **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.

2. Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **argomenti** .

3. Fare clic su **Crea argomento**.

4. Digitare `MaxNumber` nella casella **nome** , selezionare **nell'elenco a** discesa **direzione** , selezionare **Int32** dall'elenco a discesa tipo di **argomento** , quindi premere INVIO per salvare l'argomento.

5. Fare clic su **Crea argomento**.

6. Digitare `Turns` nella casella **nome** che si trova sotto l'argomento appena aggiunto `MaxNumber` , selezionare **esterno** dall'elenco a discesa **direzione** , selezionare **Int32** dall'elenco a discesa **tipo di argomento** , quindi premere INVIO.

7. Fare clic su **Argomenti** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per chiudere il riquadro **Argomenti**.

8. Fare clic su **variabili** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **variabili** .

9. Fare clic su **Crea variabile**.

    > [!TIP]
    > Se non viene visualizzata la casella **Crea variabile** , fare clic sull'attività **Sequence** nell'area di progettazione del flusso di lavoro per selezionarla.

10. Digitare `Guess` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.

11. Fare clic su **Crea variabile**.

12. Digitare `Target` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.

13. Fare clic su **Variabili** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per chiudere il riquadro **Variabili**.

## <a name="to-add-the-workflow-activities"></a>Per aggiungere le attività del flusso di lavoro

1. Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla nell'attività **Sequence** . Digitare `Target` nella casella **a** e l'espressione seguente nella casella **immettere un'espressione C#** o **immettere un'espressione VB** .

    ```vb
    New System.Random().Next(1, MaxNumber + 1)
    ```

    ```csharp
    new System.Random().Next(1, MaxNumber + 1)
    ```

    > [!TIP]
    > Se la finestra **Casella degli strumenti** non è visualizzata, selezionare **Casella degli strumenti** dal menu **Visualizza**.

2. Trascinare un'attività **DoWhile** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla nel flusso di lavoro in modo che si trovi sotto l'attività **assign** .

3. Digitare l'espressione seguente nella casella del valore della proprietà **Condition** dell'attività **DoWhile** .

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

     Un'attività <xref:System.Activities.Statements.DoWhile> esegue le proprie attività figlio e successivamente valuta <xref:System.Activities.Statements.DoWhile.Condition%2A>. Se <xref:System.Activities.Statements.DoWhile.Condition%2A> dà come risultato `True`, le attività in <xref:System.Activities.Statements.DoWhile> vengono eseguite nuovamente. In questo esempio, viene valutata l'ipotesi dell'utente e <xref:System.Activities.Statements.DoWhile> continua finché l'ipotesi non è corretta.

4. Trascinare un'attività **prompt** dalla sezione **NumberGuessWorkflowActivities** della **casella degli strumenti** e rilasciarla nell'attività **DoWhile** del passaggio precedente.

5. Nella **finestra Proprietà**Digitare `"EnterGuess"` includendo le virgolette nella casella del valore della proprietà **BookmarkName** per l'attività **prompt** . Digitare `Guess` nella casella valore proprietà **risultato** e digitare l'espressione seguente nella casella della proprietà **testo** .

    ```vb
    "Please enter a number between 1 and " & MaxNumber
    ```

    ```csharp
    "Please enter a number between 1 and " + MaxNumber
    ```

    > [!TIP]
    > Se la **finestra Proprietà** non è visualizzata, scegliere **finestra Proprietà** dal menu **Visualizza** .

6. Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla nell'attività **DoWhile** in modo che segua l'attività **prompt** .

    > [!NOTE]
    > Quando si rilascia l'attività **assign** , si noti come la finestra di progettazione del flusso di lavoro aggiunge automaticamente un'attività **Sequence** in modo che contenga sia l'attività **prompt** che l'attività **assign** appena aggiunta.

7. Digitare `Turns` nella casella **a** e `Turns + 1` nella casella **immettere un'espressione C#** o **immettere un'espressione VB** .

8. Trascinare un'attività **if** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla nell'attività **Sequence** in modo che segua l'attività **assign** appena aggiunta.

9. Digitare l'espressione seguente nella casella del valore della proprietà **Condition** dell'attività **if** .

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

10. Trascinare un'altra attività **if** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla nella sezione **then** della prima attività **if** .

11. Digitare l'espressione seguente nella casella del valore della proprietà **Condition** dell'attività **if** appena aggiunta.

    ```text
    Guess < Target
    ```

12. Trascinare due attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarle in modo che una si trovi nella sezione **then** dell'attività **if** appena aggiunta e una si trovi nella sezione **else** .

13. Fare clic sull'attività **WriteLine** nella sezione **then** per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** .

    ```text
    "Your guess is too low."
    ```

14. Fare clic sull'attività **WriteLine** nella sezione **else** per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** .

    ```text
    "Your guess is too high."
    ```

     Nell'esempio seguente viene illustrato il flusso di lavoro completato:

     ![Screenshot che illustra il flusso di lavoro sequenziale completato.](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)

## <a name="to-build-the-workflow"></a>Per compilare il flusso di lavoro

1. Premere CTRL+MAIUSC+B per compilare la soluzione.

     Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md). Se è già stato completato il passaggio [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md) con uno stile di flusso di lavoro diverso e si desidera eseguirlo tramite il flusso di lavoro sequenziale da questo passaggio, passare alla sezione [per compilare ed eseguire l'applicazione](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) di [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Programmazione di Windows Workflow Foundation](programming.md)
- [Progettazione di flussi di lavoro](designing-workflows.md)
- [Esercitazione Introduzione](getting-started-tutorial.md)
- [Procedura: Creare un'attività](how-to-create-an-activity.md)
- [Procedura: Eseguire un flusso di lavoro](how-to-run-a-workflow.md)
