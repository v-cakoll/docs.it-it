---
title: 'Procedura: creare un flusso di lavoro del diagramma di flusso'
description: Questo articolo descrive la creazione di un flusso di lavoro che usa sia attività predefinite che le attività personalizzate dell'articolo precedente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: 6b3fa423200f5c5cfece60f07372ce9678fc0072
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419707"
---
# <a name="how-to-create-a-flowchart-workflow"></a>Procedura: creare un flusso di lavoro del diagramma di flusso
I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate. Questo argomento illustra la creazione di un flusso di lavoro che usa sia attività predefinite, ad esempio l' <xref:System.Activities.Statements.Flowchart> attività, che le attività personalizzate dell'argomento [procedura: creare un'attività](how-to-create-an-activity.md) precedente. Il flusso di lavoro consente di modellare un gioco per determinare un numero.  
  
> [!NOTE]
> Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti. Per completare questo argomento, è necessario completare prima di tutto [procedura: creare un'attività](how-to-create-an-activity.md).  
  
> [!NOTE]
> Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>Per creare il flusso di lavoro  
  
1. Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowActivities** in **Esplora soluzioni** e scegliere **Aggiungi**, **nuovo elemento**.  
  
2. Nel nodo **elementi comuni** **installati**selezionare **flusso di lavoro**. Selezionare l'**attività** dall'elenco **Workflow**.  
  
3. Digitare `FlowchartNumberGuessWorkflow` nella casella **nome** e fare clic su **Aggiungi**.  
  
4. Trascinare un'attività **Flowchart** dalla sezione **diagramma** di flusso della **casella degli strumenti** e rilasciarla sull'etichetta **rilasciare l'attività** nell'area di progettazione del flusso di lavoro.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>Per creare variabili e argomenti del flusso di lavoro  
  
1. Fare doppio clic su **FlowchartNumberGuessWorkflow. XAML** in **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.  
  
2. Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **argomenti** .  
  
3. Fare clic su **Crea argomento**.  
  
4. Digitare `MaxNumber` nella casella **nome** , selezionare **nell'elenco a** discesa **direzione** , selezionare **Int32** dall'elenco a discesa tipo di **argomento** , quindi premere INVIO per salvare l'argomento.  
  
5. Fare clic su **Crea argomento**.  
  
6. Digitare `Turns` nella casella **nome** che si trova sotto l'argomento appena aggiunto `MaxNumber` , selezionare **esterno** dall'elenco a discesa **direzione** , selezionare **Int32** dall'elenco a discesa **tipo di argomento** , quindi premere INVIO.  
  
7. Fare clic su **Argomenti** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per chiudere il riquadro **Argomenti**.  
  
8. Fare clic su **variabili** nel lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il riquadro **variabili** .  
  
9. Fare clic su **Crea variabile**.  
  
    > [!TIP]
    > Se non viene visualizzata la casella **Crea variabile** , fare clic sull' <xref:System.Activities.Statements.Flowchart> attività nell'area di progettazione del flusso di lavoro per selezionarla.  
  
10. Digitare `Guess` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.  
  
11. Fare clic su **Crea variabile**.  
  
12. Digitare `Target` nella casella **nome** , selezionare **Int32** dall'elenco a discesa **tipo di variabile** , quindi premere INVIO per salvare la variabile.  
  
13. Fare clic su **Variabili** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per chiudere il riquadro **Variabili**.  
  
### <a name="to-add-the-workflow-activities"></a>Per aggiungere le attività del flusso di lavoro  
  
1. Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e posizionarla sul nodo **iniziale** , che si trova nella parte superiore del diagramma di flusso. Quando l'attività **assign** è sul nodo **iniziale** , vengono visualizzati tre triangoli intorno al nodo **iniziale** . Rilasciare l'attività **assign** sul triangolo che si trova direttamente sotto il nodo **iniziale** . In questo modo i due elementi vengono collegati insieme e l'attività **assign** viene designata come prima attività del diagramma di flusso.  
  
    > [!NOTE]
    > È possibile designare le attività come attività iniziali nel diagramma di flusso anche collegandole manualmente al nodo iniziale. A tale scopo, passare il puntatore del mouse sul nodo **iniziale** , fare clic su uno dei rettangoli visualizzati quando il mouse si trova sul nodo **iniziale** e trascinare la linea di connessione fino all'attività desiderata e rilasciarla su uno dei rettangoli visualizzati. È anche possibile designare un'attività come attività iniziale facendo clic con il pulsante destro del mouse su di essa e scegliendo **Imposta come nodo iniziale**.  
  
2. Digitare `Target` nella casella **a** e l'espressione seguente nella casella **immettere un'espressione C#** o **immettere un'espressione VB** .  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > Se la finestra **Casella degli strumenti** non è visualizzata, selezionare **Casella degli strumenti** dal menu **Visualizza**.  
  
3. Trascinare un'attività **prompt** dalla sezione **NumberGuessWorkflowActivities** della **casella degli strumenti**, rilasciarla sotto l'attività **assign** del passaggio precedente e connettere l'attività **prompt** all'attività **assign** . Esistono tre modi per connettere le due attività. Il primo consiste nel connetterli quando si rilascia l'attività **prompt** sul flusso di lavoro. Quando si trascina l'attività **prompt** sul flusso di lavoro, passare il mouse sull'attività **assign** e rilasciarla su uno dei quattro triangoli visualizzati quando l'attività **prompt** è sull'attività **assign** . Il secondo modo consiste nell'eliminare l'attività **prompt** sul flusso di lavoro nella posizione desiderata. Posizionare quindi il puntatore del mouse sull'attività **assign** e trascinare uno dei rettangoli visualizzati fino all'attività **prompt** . Trascinare il mouse in modo che la linea di connessione dall'attività **assign** si connetta a uno dei rettangoli dell'attività **prompt** , quindi rilasciare il pulsante del mouse. Il terzo modo è molto simile al primo, ad eccezione del fatto che anziché trascinare l'attività **prompt** dalla **casella degli strumenti**, trascinarla dalla relativa posizione nell'area di progettazione del flusso di lavoro, posizionarla sull'attività **assign** e rilasciarla su uno dei triangoli visualizzati.  
  
4. Nella **finestra Proprietà** per l'attività **prompt** digitare, `"EnterGuess"` incluse le virgolette, nella casella del valore della proprietà **BookmarkName** . Digitare `Guess` nella casella valore proprietà **risultato** e digitare l'espressione seguente nella casella della proprietà **testo** .  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    > Se la **finestra Proprietà** non è visualizzata, scegliere **finestra Proprietà** dal menu **Visualizza** .  
  
5. Trascinare un'attività **assign** dalla sezione **primitive** della **casella degli strumenti** e connetterla usando uno dei metodi descritti nel passaggio precedente, in modo che si trovi sotto l'attività **prompt** .  
  
6. Digitare `Turns` nella casella **a** e `Turns + 1` nella casella **immettere un'espressione C#** o **immettere un'espressione VB** .  
  
7. Trascinare un **FlowDecision** dalla sezione **diagramma di flusso** della **casella degli strumenti** e connetterlo sotto l'attività **assign** . Nella **finestra Proprietà**Digitare l'espressione seguente nella casella valore proprietà **condizione** .  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. Trascinare un'altra attività **FlowDecision** dalla **casella degli strumenti** e rilasciarla sotto la prima. Connettere le due attività trascinando dal rettangolo con etichetta **false** nella parte superiore dell'attività **FlowDecision** al rettangolo nella parte superiore della seconda attività **FlowDecision** .  
  
    > [!TIP]
    > Se non vengono visualizzate le etichette **true** e **false** in **FlowDecision**, passare il puntatore del mouse sul **FlowDecision**.  
  
9. Fare clic sulla seconda attività **FlowDecision** per selezionarla. Nella **finestra Proprietà**Digitare l'espressione seguente nella casella valore proprietà **condizione** .  
  
    ```text
    Guess < Target
    ```  
  
10. Trascinare due attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarle in modo che siano affiancate al di sotto delle due attività **FlowDecision** . Connettere la **vera** azione dell'attività **FlowDecision** inferiore all'attività **WriteLine** più a sinistra e l'azione **false** all'attività **WriteLine** più a destra.  
  
11. Fare clic sull'attività **WriteLine** più a sinistra per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** nella **finestra Proprietà**.  
  
    ```text
    "Your guess is too low."  
    ```  
  
12. Connettere il **WriteLine** al lato sinistro dell'attività **prompt** sopra.  
  
13. Fare clic sull'attività **WriteLine** più a destra per selezionarla e digitare l'espressione seguente nella casella del valore della proprietà **Text** nella **finestra Proprietà**.  
  
    ```text
    "Your guess is too high."  
    ```  
  
14. Connettere l'attività **WriteLine** al lato destro dell'attività **prompt** sopra.  
  
     Nell'esempio seguente viene illustrato il flusso di lavoro completato.  
  
     ![Diagramma che mostra un diagramma di flusso Windows Workflow Foundation completato.](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a>Per compilare il flusso di lavoro  
  
1. Premere CTRL+MAIUSC+B per compilare la soluzione.  
  
     Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md). Se è già stato completato il passaggio [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md) con uno stile di flusso di lavoro diverso e si desidera eseguirlo tramite il flusso di lavoro diagramma di flusso da questo passaggio, passare alla sezione [per compilare ed eseguire l'applicazione](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) di [procedura: eseguire un flusso di lavoro](how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Programmazione di Windows Workflow Foundation](programming.md)
- [Progettazione di flussi di lavoro](designing-workflows.md)
- [Esercitazione Introduzione](getting-started-tutorial.md)
- [Procedura: Creare un'attività](how-to-create-an-activity.md)
- [Procedura: Eseguire un flusso di lavoro](how-to-run-a-workflow.md)
