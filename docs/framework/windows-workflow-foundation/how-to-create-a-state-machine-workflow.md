---
title: 'Procedura: creare un flusso di lavoro della macchina a stati'
description: Questo articolo crea un flusso di lavoro che usa sia le attività predefinite, ad esempio l'attività StateMachine, che le attività personalizzate.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 8a9342c07c15d65df0310c0cb35b4b2c6f2ba686
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419655"
---
# <a name="how-to-create-a-state-machine-workflow"></a>Procedura: creare un flusso di lavoro della macchina a stati
I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate. Questo argomento illustra la creazione di un flusso di lavoro che usa sia attività predefinite, ad esempio l' <xref:System.Activities.Statements.StateMachine> attività, che le attività personalizzate dell'argomento [procedura: creare un'attività](how-to-create-an-activity.md) precedente. Il flusso di lavoro consente di modellare un gioco per determinare un numero.  
  
> [!NOTE]
> Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti. Per completare questo argomento, è necessario completare prima di tutto [procedura: creare un'attività](how-to-create-an-activity.md).  
  
> [!NOTE]
> Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>Per creare il flusso di lavoro  
  
1. Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowActivities** in **Esplora soluzioni** e scegliere **Aggiungi**, **nuovo elemento**.  
  
2. Nel nodo **elementi comuni** **installati**selezionare **flusso di lavoro**. Selezionare l'**attività** dall'elenco **Workflow**.  
  
3. Digitare `StateMachineNumberGuessWorkflow` nella casella **nome** e fare clic su **Aggiungi**.  
  
4. Trascinare un'attività **StateMachine** dalla sezione **macchina a stati** della **casella degli strumenti** e rilasciarla sull'etichetta rilasciare l' **attività** nell'area di progettazione del flusso di lavoro.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>Per creare variabili e argomenti del flusso di lavoro  
  
1. Fare doppio clic su **StateMachineNumberGuessWorkflow. XAML** in **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.  
  
2. Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **argomenti** .  
  
3. Fare clic su **Crea argomento**.  
  
4. Digitare `MaxNumber` nella casella **nome** , selezionare **nell'elenco a** discesa **direzione** , selezionare **Int32** dall'elenco a discesa tipo di **argomento** , quindi premere INVIO per salvare l'argomento.  
  
5. Fare clic su **Crea argomento**.  
  
6. Digitare `Turns` nella casella **nome** che si trova sotto l'argomento appena aggiunto `MaxNumber` , selezionare **esterno** dall'elenco a discesa **direzione** , selezionare **Int32** dall'elenco a discesa **tipo di argomento** , quindi premere INVIO.  
  
7. Fare clic su **Argomenti** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per chiudere il riquadro **Argomenti**.  
  
8. Fare clic su **variabili** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **variabili** .  
  
9. Fare clic su **Crea variabile**.  
  
    > [!TIP]
    > Se non viene visualizzata la casella **Crea variabile** , fare clic sull' <xref:System.Activities.Statements.StateMachine> attività nell'area di progettazione del flusso di lavoro per selezionarla.  
  
10. Digitare `Guess` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.  
  
11. Fare clic su **Crea variabile**.  
  
12. Digitare `Target` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.  
  
13. Fare clic su **Variabili** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per chiudere il riquadro **Variabili**.  
  
### <a name="to-add-the-workflow-activities"></a>Per aggiungere le attività del flusso di lavoro  
  
1. Fare clic su **state1** per selezionarlo. Nella **finestra Proprietà**modificare **DisplayName** in `Initialize Target` .  
  
    > [!TIP]
    > Se la **finestra Proprietà** non è visualizzata, scegliere **finestra Proprietà** dal menu **Visualizza** .  
  
2. Fare doppio clic sullo stato **Initialize Target** appena rinominato nella finestra di progettazione del flusso di lavoro per espanderlo.  
  
3. Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla nella sezione **entry** dello stato. Digitare `Target` nella casella **a** e l'espressione seguente nella casella **immettere un'espressione C#** o **immettere un'espressione VB** .  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > Se la finestra **Casella degli strumenti** non è visualizzata, selezionare **Casella degli strumenti** dal menu **Visualizza**.  
  
4. Tornare alla visualizzazione complessiva della macchina a stati nella finestra di progettazione del flusso di lavoro facendo clic su **StateMachine** nella parte superiore della finestra di progettazione del flusso di lavoro.  
  
5. Trascinare un'attività **stato** dalla sezione **macchina a stati** della **casella degli strumenti** nella finestra di progettazione del flusso di lavoro e posizionarla sullo stato di destinazione dell' **inizializzazione** . Si noti che quattro triangoli verranno visualizzati intorno allo stato di **inizializzazione della destinazione** quando il nuovo stato si trova su di esso. Rilasciare il nuovo stato sul triangolo immediatamente sotto lo stato di **inizializzazione della destinazione** . In questo modo il nuovo stato viene posizionato sul flusso di lavoro e viene creata una transizione dallo stato di **destinazione dell'inizializzazione** al nuovo stato.  
  
6. Fare clic su **state1** per selezionarlo, impostare **DisplayName** su `Enter Guess` , quindi fare doppio clic sullo stato nella finestra di progettazione del flusso di lavoro per espanderlo.  
  
7. Trascinare un'attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla nella sezione **entry** dello stato.  
  
8. Digitare l'espressione seguente nella casella della proprietà **Text** di **WriteLine**.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla nella sezione **uscita** dello stato.  
  
10. Digitare `Turns` nella casella **a** e `Turns + 1` nella casella **immettere un'espressione C#** o **immettere un'espressione VB** .  
  
11. Tornare alla visualizzazione complessiva della macchina a stati nella finestra di progettazione del flusso di lavoro facendo clic su **StateMachine** nella parte superiore della finestra di progettazione del flusso di lavoro.  
  
12. Trascinare un'attività **FinalState** dalla sezione **macchina a stati** della **casella degli strumenti**, posizionarla sopra lo stato **Enter Guess** e rilasciarla sul triangolo visualizzato a destra dello stato **Enter Guess** in modo da creare una transizione tra **Enter Guess** e **FinalState**.  
  
13. Il nome predefinito della transizione è **T2**. Fare clic sulla transizione nella finestra di progettazione del flusso di lavoro per selezionarla e impostare il relativo **DisplayName** su **Guess Correct**. Quindi fare clic e selezionare il **FinalState**e trascinarlo a destra in modo che sia disponibile spazio per il nome di transizione completo da visualizzare senza sovrapporre uno dei due Stati. Ciò faciliterà il completamento dei passaggi rimanenti nell'esercitazione.  
  
14. Fare doppio clic sulla transizione **Guess Correct** appena rinominata nella finestra di progettazione del flusso di lavoro per espanderla.  
  
15. Trascinare un'attività **ReadInt** dalla sezione **NumberGuessWorkflowActivities** della **casella degli strumenti** e rilasciarla nella sezione **trigger** della transizione.  
  
16. Nella **finestra Proprietà** per l'attività **ReadInt** , digitare, `"EnterGuess"` incluse le virgolette, nella casella del valore della proprietà **BookmarkName** e digitare `Guess` nella casella valore proprietà **risultato**  
  
17. Digitare l'espressione seguente nella casella del valore della proprietà **Condition** della transizione **Guess Correct** .  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. Tornare alla visualizzazione complessiva della macchina a stati nella finestra di progettazione del flusso di lavoro facendo clic su **StateMachine** nella parte superiore della finestra di progettazione del flusso di lavoro.  
  
    > [!NOTE]
    > La transizione si verifica quando viene ricevuto un evento trigger e <xref:System.Activities.Statements.Transition.Condition%2A>, se presente, restituisce `True`. Per questa transizione, se l'utente `Guess` corrisponde a generato in modo casuale `Target` , il controllo passa a **FinalState** e il flusso di lavoro viene completato.  
  
19. A seconda del fatto che l'ipotesi sia corretta, il flusso di lavoro deve eseguire la transizione a **FinalState** o di nuovo allo stato **Enter Guess** per un altro tentativo. Entrambe le transizioni condividono lo stesso trigger di attesa per la ricezione dell'ipotesi dell'utente tramite l'attività **ReadInt** . Questa transizione è denominata transizione condivisa. Per creare una transizione condivisa, fare clic sul cerchio che indica l'inizio della transizione **Guess Correct** e trascinarlo nello stato desiderato. In questo caso la transizione è una transizione automatica, quindi trascinare il punto iniziale della transizione **Guess Correct** e rilasciarlo nella parte inferiore dello stato **Enter Guess** . Dopo aver creato la transizione, selezionarla nella finestra di progettazione del flusso di lavoro e impostarne la proprietà **DisplayName** su **Guess uncorrect**.  
  
    > [!NOTE]
    > Le transizioni condivise possono essere create anche dall'interno della finestra di progettazione della transizione facendo clic su **Aggiungi transizione del trigger condiviso** nella parte inferiore della finestra di progettazione della transizione e quindi selezionando lo stato di destinazione desiderato dall'elenco **a discesa stati disponibili per la connessione** .  
  
    > [!NOTE]
    > Si noti che se <xref:System.Activities.Statements.Transition.Condition%2A> di una transizione restituisce `false` (o tutti gli stati di una transizione trigger condivisa restituiscono `false`), la transizione non si verificherà e tutti i trigger per tutte le transizioni dallo stato verranno rinviati. In questa esercitazione, questa situazione non può verificarsi a causa della modalità con cui le condizioni vengono configurate (esistono azioni specifiche per verificare se il valore indicato è corretto o errato).  
  
20. Fare doppio clic sulla transizione **Guess errata** nella finestra di progettazione del flusso di lavoro per espanderla. Si noti che il **trigger** è già impostato sulla stessa attività **ReadInt** utilizzata dalla transizione **Guess Correct** .  
  
21. Digitare l'espressione seguente nella casella del valore della proprietà **Condition** .  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. Trascinare un'attività **if** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla nella sezione **azione** della transizione.  
  
23. Digitare l'espressione seguente nella casella del valore della proprietà **Condition** dell'attività **if** .  
  
    ```text
    Guess < Target
    ```  
  
24. Trascinare due attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarle in modo che una si trovi nella sezione **then** dell'attività **if** e una si trovi nella sezione **else** .  
  
25. Fare clic sull'attività **WriteLine** nella sezione **then** per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** .  
  
    ```text
    "Your guess is too low."  
    ```  
  
26. Fare clic sull'attività **WriteLine** nella sezione **else** per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** .  
  
    ```text
    "Your guess is too high."  
    ```  
  
27. Tornare alla visualizzazione complessiva della macchina a stati nella finestra di progettazione del flusso di lavoro facendo clic su **StateMachine** nella parte superiore della finestra di progettazione del flusso di lavoro.  
  
     Nell'esempio seguente viene illustrato il flusso di lavoro completato.  
  
     ![Illustrazione che mostra il flusso di lavoro della macchina a stati completato.](./media/how-to-create-a-state-machine-workflow/complete-state-machine-workflow.jpg)  
  
### <a name="to-build-the-workflow"></a>Per compilare il flusso di lavoro  
  
1. Premere CTRL+MAIUSC+B per compilare la soluzione.  
  
     Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md). Se è già stato completato il passaggio [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md) con uno stile di flusso di lavoro diverso e si desidera eseguirlo tramite il flusso di lavoro della macchina a stati da questo passaggio, passare alla sezione [per compilare ed eseguire l'applicazione](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) di [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Programmazione di Windows Workflow Foundation](programming.md)
- [Progettazione di flussi di lavoro](designing-workflows.md)
- [Esercitazione Introduzione](getting-started-tutorial.md)
- [Procedura: Creare un'attività](how-to-create-an-activity.md)
- [Procedura: Eseguire un flusso di lavoro](how-to-run-a-workflow.md)
