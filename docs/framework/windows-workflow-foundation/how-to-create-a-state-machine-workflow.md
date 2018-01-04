---
title: 'Procedura: creare un flusso di lavoro della macchina a stati'
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
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 95ba37b123b57ba9f86fefb55a860fb2122ccd3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-state-machine-workflow"></a>Procedura: creare un flusso di lavoro della macchina a stati
I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate. Passaggi in questo argomento per la creazione di un flusso di lavoro che utilizza entrambe le attività predefinite, ad esempio il <xref:System.Activities.Statements.StateMachine> attività e le attività personalizzate dal precedente [procedura: creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) argomento. Il flusso di lavoro consente di modellare un gioco per determinare un numero.  
  
> [!NOTE]
>  Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti. Per completare questo argomento, è necessario prima completare [procedura: creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).  
  
> [!NOTE]
>  Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>Per creare il flusso di lavoro  
  
1.  Fare doppio clic su **NumberGuessWorkflowActivities** in **Esplora** e selezionare **Aggiungi**, **nuovo elemento**.  
  
2.  Nel **installato**, **elementi comuni** nodo, seleziona **flusso di lavoro**. Selezionare **attività** dal **flusso di lavoro** elenco.  
  
3.  Tipo `StateMachineNumberGuessWorkflow` nel **nome** casella e fare clic su **Aggiungi**.  
  
4.  Trascinare un **StateMachine** attività dal **macchina a stati** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta nel finestra di progettazione del flusso di lavoro.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>Per creare variabili e argomenti del flusso di lavoro  
  
1.  Fare doppio clic su **Statemachinenumberguessworkflow** in **Esplora** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.  
  
2.  Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il **argomenti** riquadro.  
  
3.  Fare clic su **Crea argomento**.  
  
4.  Tipo `MaxNumber` nel **nome** , quindi selezionare **In** dal **direzione** elenco a discesa, seleziona **Int32** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.  
  
5.  Fare clic su **Crea argomento**.  
  
6.  Tipo `Turns` nel **nome** casella che si trova sotto appena aggiunta `MaxNumber` argomento, selezionare **Out** dal **direzione** -elenco a discesa, seleziona  **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.  
  
7.  Fare clic su **argomenti** nel lato inferiore sinistro dell'ActivityDesigner per chiudere la **argomenti** riquadro.  
  
8.  Fare clic su **variabili** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il **variabili** riquadro.  
  
9. Fare clic su **creare variabile**.  
  
    > [!TIP]
    >  Se non **Crea variabile** viene visualizzata, fare clic su di <xref:System.Activities.Statements.StateMachine> attività nell'area di progettazione del flusso di lavoro per selezionarla.  
  
10. Tipo `Guess` nel **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.  
  
11. Fare clic su **creare variabile**.  
  
12. Tipo `Target` nel **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.  
  
13. Fare clic su **variabili** nel lato inferiore sinistro dell'ActivityDesigner per chiudere la **variabili** riquadro.  
  
### <a name="to-add-the-workflow-activities"></a>Per aggiungere le attività del flusso di lavoro  
  
1.  Fare clic su **State1** per selezionarlo. Nel **finestra proprietà**, modificare il **DisplayName** a `Initialize Target`.  
  
    > [!TIP]
    >  Se il **finestra proprietà** non è visualizzata, selezionare **finestra proprietà** dal **vista** menu.  
  
2.  Fare doppio clic su appena rinominata **Initialize Target** dello stato nella finestra di progettazione del flusso di lavoro per espanderlo.  
  
3.  Trascinare un **assegnare** attività dal **primitive** sezione il **della casella degli strumenti** e rilasciarla il **voce** sezione dello stato. Tipo `Target` nel **a** casella e l'espressione seguente nella **immettere un'espressione c#** o **immettere un'espressione VB** casella.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Se il **della casella degli strumenti** non verrà visualizzata la finestra, selezionare **della casella degli strumenti** dal **vista** menu.  
  
4.  Tornare a generale dello stato di visualizzazione nella finestra di progettazione del flusso di lavoro della macchina, fare clic su **StateMachine** della barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.  
  
5.  Trascinare un **stato** attività dal **macchina a stati** sezione del **della casella degli strumenti** nella finestra di progettazione del flusso di lavoro e passarla sul **Initialize Target** stato. Si noti che verranno visualizzati quattro triangoli intorno il **Initialize Target** lo stato quando il nuovo stato è su di esso. Rilasciare il nuovo stato sul triangolo che si trova immediatamente sotto il **Initialize Target** dello stato. Si inserisce il nuovo stato sul flusso di lavoro e si crea una transizione dal **Initialize Target** dello stato per il nuovo stato.  
  
6.  Fare clic su **State1** per selezionarlo, modificare il **DisplayName** a `Enter Guess`, quindi fare doppio clic su stato nella finestra di progettazione del flusso di lavoro per espanderlo.  
  
7.  Trascinare un **WriteLine** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla il **voce** sezione dello stato.  
  
8.  Digitare l'espressione seguente nella **testo** casella della proprietà del **WriteLine**.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. Trascinare un **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciare il **uscita** sezione dello stato.  
  
10. Tipo `Turns` nel **a** casella e `Turns + 1` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella.  
  
11. Tornare a generale dello stato di visualizzazione nella finestra di progettazione del flusso di lavoro della macchina, fare clic su **StateMachine** della barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.  
  
12. Trascinare un **FinalState** attività dal **macchina a stati** sezione del **della casella degli strumenti**, passarlo sul **Enter Guess** stato e l'eliminazione nel triangolo che viene visualizzato a destra del **Enter Guess** stato in modo che una transizione viene creata tra **Enter Guess** e **FinalState**.  
  
13. Il nome predefinito della transizione è **T2**. Fare clic sulla transizione nella finestra di progettazione del flusso di lavoro per selezionarla e impostare il relativo **DisplayName** a **Guess Correct**. Quindi fare clic e selezionare il **FinalState**e trascinarla a destra, in modo che vi sia spazio per il nome completo della transizione da visualizzare senza sovrapporre uno dei due stati. Ciò faciliterà il completamento dei passaggi rimanenti nell'esercitazione.  
  
14. Fare doppio clic su appena rinominata **Guess Correct** transizione nella finestra di progettazione del flusso di lavoro per espanderlo.  
  
15. Trascinare un **ReadInt** attività dal **NumberGuessWorkflowActivities** sezione il **della casella degli strumenti** e rilasciarlo nel **Trigger** sezione della transizione.  
  
16. Nel **finestra proprietà** per il **ReadInt** attività, digitare `"EnterGuess"` incluse le virgolette nel **BookmarkName** casella valore della proprietà e tipo `Guess`nel **risultato** casella Valore proprietà  
  
17. Digitare l'espressione seguente nella **Guess Correct** della transizione **condizione** casella valore della proprietà.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. Tornare a generale dello stato di visualizzazione nella finestra di progettazione del flusso di lavoro della macchina, fare clic su **StateMachine** della barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.  
  
    > [!NOTE]
    >  La transizione si verifica quando viene ricevuto un evento trigger e <xref:System.Activities.Statements.Transition.Condition%2A>, se presente, restituisce `True`. Per questa transizione, se l'utente `Guess` corrispondente generato casualmente `Target`, quindi il controllo passa al **FinalState** e completa il flusso di lavoro.  
  
19. A seconda che la stima sia corretta, il flusso di lavoro deve eseguire la transizione al **FinalState** o di **Enter Guess** dello stato per un altro tentativo. Entrambe le transizioni condividono lo stesso trigger di attesa che l'ipotesi dell'utente deve essere ricevuto tramite il **ReadInt** attività. Questa transizione è denominata transizione condivisa. Per creare una transizione condivisa, fare clic sul cerchio che indica l'inizio del **Guess Correct** transizione e trascinarlo nello stato desiderato. In questo caso la transizione è una transizione automatica, quindi trascinare il punto iniziale del **Guess Correct** transizione e rilasciarlo indietro nella parte inferiore del **Enter Guess** stato. Dopo aver creato la transizione, selezionarla nella finestra di progettazione del flusso di lavoro e impostare il relativo **DisplayName** proprietà **Guess Incorrect**.  
  
    > [!NOTE]
    >  Le transizioni condivise possono anche essere create dalla finestra di progettazione della transizione facendo **Aggiungi transizione del trigger condivisa** nella parte inferiore della finestra di progettazione di transizione e selezionando lo stato di destinazione desiderato dal  **Gli stati disponibili per la connessione** elenco a discesa.  
  
    > [!NOTE]
    >  Si noti che se <xref:System.Activities.Statements.Transition.Condition%2A> di una transizione restituisce `false` (o tutti gli stati di una transizione trigger condivisa restituiscono `false`), la transizione non si verificherà e tutti i trigger per tutte le transizioni dallo stato verranno rinviati. In questa esercitazione, questa situazione non può verificarsi a causa della modalità con cui le condizioni vengono configurate (esistono azioni specifiche per verificare se il valore indicato è corretto o errato).  
  
20. Fare doppio clic su di **Guess Incorrect** transizione nella finestra di progettazione del flusso di lavoro per espanderlo. Si noti che il **Trigger** è già impostato sullo stesso **ReadInt** attività che è stato utilizzato il **Guess Correct** transizione.  
  
21. Digitare l'espressione seguente nella **condizione** casella valore della proprietà.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. Trascinare un **se** attività dal **flusso di controllo** sezione il **della casella degli strumenti** e rilasciarlo nel **azione** sezione della transizione.  
  
23. Digitare l'espressione seguente nella **se** dell'attività **condizione** casella valore della proprietà.  
  
    ```
    Guess < Target  
    ```  
  
24. Trascinare due **WriteLine** le attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarle in modo che uno è il **quindi** sezione di il **se** attività e l'altro è il **Else** sezione.  
  
25. Fare clic sul **WriteLine** attività di **quindi** sezione per selezionarlo, quindi digitare l'espressione seguente nel **testo** casella valore della proprietà.  
  
    ```
    "Your guess is too low."  
    ```  
  
26. Fare clic sul **WriteLine** attività di **Else** sezione per selezionarlo, quindi digitare l'espressione seguente nel **testo** casella valore della proprietà.  
  
    ```
    "Your guess is too high."  
    ```  
  
27. Tornare a generale dello stato di visualizzazione nella finestra di progettazione del flusso di lavoro della macchina, fare clic su **StateMachine** della barra di navigazione visualizzato nella parte superiore della finestra di progettazione del flusso di lavoro.  
  
     Nell'esempio seguente viene illustrato il flusso di lavoro completato.  
  
     ![Flusso di lavoro macchina a stati completato](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
### <a name="to-build-the-workflow"></a>Per compilare il flusso di lavoro  
  
1.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
     Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [procedura: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md). Se è già stata completata la [come: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) spostarsi con uno stile diverso del flusso di lavoro e desidera eseguirlo tramite il flusso di lavoro macchina da questo passaggio, ignorare il [per compilare ed eseguire l'applicazione](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) sezione [procedura: eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [Programmazione di Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [Progettazione di flussi di lavoro](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [Esercitazione introduttiva](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [Procedura: Creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [Procedura: Eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
