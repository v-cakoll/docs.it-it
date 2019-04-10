---
title: 'Procedura: Creare un flusso di lavoro della macchina a stati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 654621ab7dd74c26a7fddbd985559a713c0e9df3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59294808"
---
# <a name="how-to-create-a-state-machine-workflow"></a>Procedura: Creare un flusso di lavoro della macchina a stati
I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate. In questo argomento illustra la creazione di un flusso di lavoro che vengono usate sia attività incorporate, ad esempio la <xref:System.Activities.Statements.StateMachine> attività e le attività personalizzate dal precedente [come: Creare un'attività](how-to-create-an-activity.md) argomento. Il flusso di lavoro consente di modellare un gioco per determinare un numero.  
  
> [!NOTE]
>  Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti. Per completare questo argomento, è necessario completare prima [come: Creare un'attività](how-to-create-an-activity.md).  
  
> [!NOTE]
>  Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>Per creare il flusso di lavoro  
  
1. Fare doppio clic su **NumberGuessWorkflowActivities** nelle **Esplora soluzioni** e selezionare **Add**, **nuovo elemento**.  
  
2. Nel **Installed**, **elementi comuni** nodo, seleziona **flusso di lavoro**. Selezionare **impegno** dalle **flusso di lavoro** elenco.  
  
3. Tipo di `StateMachineNumberGuessWorkflow` nella **Name** casella e fare clic su **Add**.  
  
4. Trascinare un **StateMachine** attività dal **macchina a stati** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta nel area di progettazione del flusso di lavoro.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>Per creare variabili e argomenti del flusso di lavoro  
  
1. Fare doppio clic su **Statemachinenumberguessworkflow** nelle **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.  
  
2. Fare clic su **argomenti** sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **argomenti** riquadro.  
  
3. Fare clic su **Crea argomento**.  
  
4. Tipo `MaxNumber` nella **nome** , quindi selezionare **nel** dal **direzione** elenco a discesa, seleziona **Int32** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.  
  
5. Fare clic su **Crea argomento**.  
  
6. Tipo `Turns` nella **Name** finestra che si trova sotto appena aggiunta `MaxNumber` argomento, selezionare **Out** dal **direzione** dall'elenco a discesa, seleziona  **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.  
  
7. Fare clic su **argomenti** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **argomenti** riquadro.  
  
8. Fare clic su **variabili** sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **variabili** riquadro.  
  
9. Fare clic su **creare variabile**.  
  
    > [!TIP]
    >  Se nessun **Crea variabile** verrà visualizzata la finestra, fare clic su di <xref:System.Activities.Statements.StateMachine> attività nell'area di progettazione del flusso di lavoro per selezionarla.  
  
10. Tipo di `Guess` nella **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.  
  
11. Fare clic su **creare variabile**.  
  
12. Tipo di `Target` nella **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.  
  
13. Fare clic su **variabili** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **variabili** riquadro.  
  
### <a name="to-add-the-workflow-activities"></a>Per aggiungere le attività del flusso di lavoro  
  
1. Fare clic su **State1** per selezionarlo. Nel **finestra delle proprietà**, modificare il **DisplayName** a `Initialize Target`.  
  
    > [!TIP]
    >  Se il **finestra delle proprietà** non è visualizzato, selezionare **finestra delle proprietà** dal **visualizzazione** menu.  
  
2. Fare doppio clic su appena rinominata **Initialize Target** stato nella finestra di progettazione del flusso di lavoro per espanderlo.  
  
3. Trascinare un **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla il **voce** sezione dello stato. Tipo `Target` nella **al** finestra e l'espressione seguente nella **immettere un'espressione c#** o **immettere un'espressione VB** casella.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Se il **casella degli strumenti** finestra non viene visualizzata, selezionare **della casella degli strumenti** dal **visualizzazione** menu.  
  
4. Tornare al complessiva dello stato di visualizzazione della macchina nella finestra di progettazione del flusso di lavoro facendo clic **StateMachine** sulla barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.  
  
5. Trascinare un **lo stato** attività dalle **macchina a stati** sezione del **della casella degli strumenti** nella finestra di progettazione del flusso di lavoro e passarla sul **Initialize Target** lo stato. Si noti che verranno visualizzati quattro triangoli intorno al **Initialize Target** lo stato quando il nuovo stato viene posizionato sopra di essa. Rilasciare il nuovo stato sul triangolo che si trova immediatamente sotto il **Initialize Target** dello stato. Questo posizionare il nuovo stato sul flusso di lavoro e crea una transizione dal **Initialize Target** stato al nuovo stato.  
  
6. Fare clic su **State1** per selezionarlo, modificare il **DisplayName** a `Enter Guess`, quindi fare doppio clic sullo stato nella finestra di progettazione del flusso di lavoro per espanderlo.  
  
7. Trascinare un **WriteLine** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla il **voce** sezione dello stato.  
  
8. Digitare l'espressione seguente nella **testo** finestra proprietà delle **WriteLine**.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. Trascinare un' **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla il **uscita** sezione dello stato.  
  
10. Tipo `Turns` nella **al** casella e `Turns + 1` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella.  
  
11. Tornare al complessiva dello stato di visualizzazione della macchina nella finestra di progettazione del flusso di lavoro facendo clic **StateMachine** sulla barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.  
  
12. Trascinare un **FinalState** attività dal **macchina a stati** sezione del **della casella degli strumenti**, passarla sul **Enter Guess** sullo stato, quindi rilasciarla nel triangolo che viene visualizzato a destra del **Enter Guess** lo stato in modo che una transizione viene creata tra **Enter Guess** e **FinalState**.  
  
13. È il nome predefinito della transizione **T2**. Fare clic sulla transizione nella finestra di progettazione del flusso di lavoro per selezionarla e impostare relativi **DisplayName** al **Guess Correct**. Quindi fare clic e selezionare il **FinalState**e trascinarla a destra in modo che ci sia spazio per il nome completo della transizione da visualizzare senza sovrapporre uno dei due stati. Ciò faciliterà il completamento dei passaggi rimanenti nell'esercitazione.  
  
14. Fare doppio clic su appena rinominata **Guess Correct** transizione nella finestra di progettazione del flusso di lavoro per espanderlo.  
  
15. Trascinare un **ReadInt** attività dal **NumberGuessWorkflowActivities** sezione del **della casella degli strumenti** e rilasciarla nel **Trigger** sezione della transizione.  
  
16. Nel **finestra delle proprietà** per il **ReadInt** attività, digitare `"EnterGuess"` incluse le virgolette nella **BookmarkName** finestra proprietà di valore e tipo `Guess`nel **risultato** casella del valore proprietà  
  
17. Digitare l'espressione seguente nella **Guess Correct** della transizione **condizione** casella dei valori.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. Tornare al complessiva dello stato di visualizzazione della macchina nella finestra di progettazione del flusso di lavoro facendo clic **StateMachine** sulla barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.  
  
    > [!NOTE]
    >  La transizione si verifica quando viene ricevuto un evento trigger e <xref:System.Activities.Statements.Transition.Condition%2A>, se presente, restituisce `True`. Per questa transizione, se l'utente `Guess` corrispondente generato casualmente `Target`, quindi il controllo passa al **FinalState** e completa il flusso di lavoro.  
  
19. A seconda del fatto che il valore indicato è corretto, il flusso di lavoro deve eseguire la transizione al **FinalState** oppure tornare il **Enter Guess** dello stato per un altro tentativo. Entrambe le transizioni condividono lo stesso trigger di attesa per il tentativo dell'utente sia ricevuta tramite il **ReadInt** attività. Questa transizione è denominata transizione condivisa. Per creare una transizione condivisa, fare clic sul cerchio che indica l'inizio del **Guess Correct** transizione e trascinarlo nello stato desiderato. In questo caso la transizione è una transizione automatica, quindi trascinare il punto iniziale del **Guess Correct** transizione e rilasciarlo indietro nella parte inferiore della **Enter Guess** dello stato. Dopo aver creato la transizione, selezionarla nella finestra di progettazione del flusso di lavoro e impostare relativi **DisplayName** proprietà **Guess Incorrect**.  
  
    > [!NOTE]
    >  Le transizioni condivise possono anche essere create da all'interno di progettazione della transizione facendo **Aggiungi transizione del trigger condivisa** nella parte inferiore della finestra di progettazione di transizione e quindi selezionando lo stato di destinazione desiderato dal  **Gli stati disponibili per la connessione** elenco a discesa.  
  
    > [!NOTE]
    >  Si noti che se <xref:System.Activities.Statements.Transition.Condition%2A> di una transizione restituisce `false` (o tutti gli stati di una transizione trigger condivisa restituiscono `false`), la transizione non si verificherà e tutti i trigger per tutte le transizioni dallo stato verranno rinviati. In questa esercitazione, questa situazione non può verificarsi a causa della modalità con cui le condizioni vengono configurate (esistono azioni specifiche per verificare se il valore indicato è corretto o errato).  
  
20. Fare doppio clic il **Guess Incorrect** transizione nella finestra di progettazione del flusso di lavoro per espanderlo. Si noti che il **Trigger** è già impostato allo stesso **ReadInt** attività che è stata utilizzata per il **Guess Correct** transizione.  
  
21. Digitare l'espressione seguente nella **condizione** casella dei valori.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. Trascinare un' **se** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla nel **azione** sezione della transizione.  
  
23. Digitare l'espressione seguente nella **se** dell'attività **condizione** casella dei valori.  
  
    ```
    Guess < Target  
    ```  
  
24. Trascinare due **WriteLine** le attività eseguite dal **primitive** sezione del **della casella degli strumenti** e rilasciarle in modo che uno è il **quindi** sezione di il **se** attività e l'altro è nel **Else** sezione.  
  
25. Fare clic sui **WriteLine** attività nel **quindi** sezione per selezionarlo, quindi digitare l'espressione seguente nella **testo** casella dei valori.  
  
    ```
    "Your guess is too low."  
    ```  
  
26. Fare clic sui **WriteLine** attività nel **Else** sezione per selezionarlo, quindi digitare l'espressione seguente nella **testo** casella dei valori.  
  
    ```
    "Your guess is too high."  
    ```  
  
27. Tornare al complessiva dello stato di visualizzazione della macchina nella finestra di progettazione del flusso di lavoro facendo clic **StateMachine** sulla barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.  
  
     Nell'esempio seguente viene illustrato il flusso di lavoro completato.  
  
     ![Flusso di lavoro macchina a stati completo](./media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
### <a name="to-build-the-workflow"></a>Per compilare il flusso di lavoro  
  
1. Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
     Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [come: Eseguire un flusso di lavoro](how-to-run-a-workflow.md). Se sono già state completate le [come: Eseguire un flusso di lavoro](how-to-run-a-workflow.md) passaggio con uno stile diverso del flusso di lavoro e si desidera eseguirlo tramite il lavoro macchina a stati da questo passaggio, andare direttamente al [per compilare ed eseguire l'applicazione](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) sezione [come: Eseguire un flusso di lavoro](how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Programmazione di Windows Workflow Foundation](programming.md)
- [Progettazione di flussi di lavoro](designing-workflows.md)
- [Esercitazione introduttiva](getting-started-tutorial.md)
- [Procedura: Creare un'attività](how-to-create-an-activity.md)
- [Procedura: Eseguire un flusso di lavoro](how-to-run-a-workflow.md)
