---
title: 'Procedura: eseguire un flusso di lavoro'
description: Questo articolo illustra come creare un host del flusso di lavoro ed eseguire il flusso di lavoro definito in un articolo precedente in questa serie di esercitazioni Windows Workflow Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f814ff82-fe2b-4614-aebb-b768c3e61179
ms.openlocfilehash: 86062dd5147e6e354833928fd98bd1f6b5de9114
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421501"
---
# <a name="how-to-run-a-workflow"></a>Procedura: eseguire un flusso di lavoro
Questo argomento è una continuazione dell'esercitazione introduttiva di Windows Workflow Foundation e illustra come creare un host di flusso di lavoro ed eseguire il flusso di lavoro definito nell'argomento [How to: Create a Workflow](how-to-create-a-workflow.md) precedente.

> [!NOTE]
> Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti. Per completare questo argomento, è necessario completare prima [How to: Create an Activity](how-to-create-an-activity.md) e [How to: Create a Workflow](how-to-create-a-workflow.md).

> [!NOTE]
> Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow-host-project"></a>Per creare il progetto host del flusso di lavoro  
  
1. Aprire la soluzione dall'argomento [procedura: creare un'attività](how-to-create-an-activity.md) con Visual Studio 2012.  
  
2. Fare clic con il pulsante destro del mouse sulla soluzione **WF45GettingStartedTutorial** in **Esplora soluzioni** e scegliere **Aggiungi**, **Nuovo progetto**.  
  
    > [!TIP]
    > Se la finestra **Esplora soluzioni** non è visualizzata, selezionare **Esplora soluzioni** dal menu **Visualizza**.

3. Nel nodo **Modelli installati** selezionare **Visual C#**, **Flusso di lavoro** (oppure **Visual Basic**, **Flusso di lavoro**).

    > [!NOTE]
    > A seconda del linguaggio di programmazione configurato come principale in Visual Studio, il nodo **Visual C#** o **Visual Basic** potrebbe trovarsi all'interno del nodo **Altri linguaggi** nel nodo **Installati**.

     Assicurarsi che nell'elenco a discesa della versione di .NET Framework sia selezionato **.NET Framework 4.5**. Selezionare **Applicazione console flusso di lavoro** dall'elenco **Flusso di lavoro** . Digitare `NumberGuessWorkflowHost` nella casella **Nome** , quindi fare clic su **OK**. In questo modo verrà creata un'applicazione flusso di lavoro iniziale con supporto per l'hosting del flusso di lavoro di base. Il codice host di base viene modificato e usato per eseguire l'applicazione flusso di lavoro.

4. Fare clic con il pulsante destro del mouse sul progetto **NumberGuessWorkflowHost** appena aggiunto in **Esplora soluzioni** e selezionare **Aggiungi riferimento**. Scegliere **Soluzione** nell'elenco **Aggiungi riferimento** , selezionare la casella di controllo accanto a **NumberGuessWorkflowActivities**, quindi scegliere **OK**.

5. Fare clic con il pulsante destro del mouse su **Workflow1.xaml** in **Esplora soluzioni** e scegliere **Elimina**. Fare clic su **OK** per confermare.

### <a name="to-modify-the-workflow-hosting-code"></a>Per modificare il codice host del flusso di lavoro

1. Fare doppio clic su **Program.cs** o **Module1.vb** in **Esplora soluzioni** per visualizzare il codice.

    > [!TIP]
    > Se la finestra **Esplora soluzioni** non è visualizzata, selezionare **Esplora soluzioni** dal menu **Visualizza**.

     Poiché questo progetto viene creato usando il modello **Applicazione console flusso di lavoro** , **Program.cs** o **Module1.vb** contiene il seguente codice host del flusso di lavoro di base.

    ```vb
    ' Create and cache the workflow definition.
    Dim workflow1 As Activity = New Workflow1()
    WorkflowInvoker.Invoke(workflow1)
    ```

    ```csharp
    // Create and cache the workflow definition.
    Activity workflow1 = new Workflow1();
    WorkflowInvoker.Invoke(workflow1);
    ```

     Questo codice host generato usa <xref:System.Activities.WorkflowInvoker>. <xref:System.Activities.WorkflowInvoker> offre un modo semplice per richiamare un flusso di lavoro come se fosse una chiamata a un metodo e può essere usato solo per i flussi di lavoro che non usano la persistenza. <xref:System.Activities.WorkflowApplication> fornisce un modello più dettagliato per l'esecuzione di flussi di lavoro che include la notifica degli eventi del ciclo di vita, il controllo di esecuzione, la ripresa del segnalibro e la persistenza. In questo esempio vengono usati i segnalibri e l'oggetto <xref:System.Activities.WorkflowApplication> viene usato per ospitare il flusso di lavoro. Aggiungere la seguente istruzione `using` o **Imports** all'inizio del file **Program.cs** o **Module1.vb** dopo le istruzioni **using** o **Imports** esistenti.

    ```vb
    Imports NumberGuessWorkflowActivities
    Imports System.Threading
    ```

    ```csharp
    using NumberGuessWorkflowActivities;
    using System.Threading;
    ```

     Sostituire le righe di codice che usano l'oggetto <xref:System.Activities.WorkflowInvoker> con il seguente codice host <xref:System.Activities.WorkflowApplication> di base. In questo codice host di esempio vengono illustrati i passaggi di base per ospitare e richiamare un flusso di lavoro, ma non è contenuta ancora la funzionalità per eseguire correttamente il flusso di lavoro da questo argomento. Nei seguenti passaggi il codice di base viene modificato e vengono aggiunte funzionalità aggiuntive fino a quando l'applicazione non viene completata.

    > [!NOTE]
    > Sostituire `Workflow1` in questi esempi con `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, a seconda del flusso di lavoro completato nel passaggio precedente [How to: Create a Workflow](how-to-create-a-workflow.md) . Se non si sostituisce `Workflow1` , si verificheranno degli errori di compilazione quando si tenterà di compilare o eseguire il flusso di lavoro.

     [!code-csharp[CFX_WF_GettingStarted#4](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#4)]
     [!code-vb[CFX_WF_GettingStarted#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#4)]

     Questo codice crea un oggetto <xref:System.Activities.WorkflowApplication>, sottoscrive tre eventi del ciclo di vita del flusso di lavoro, avvia il flusso di lavoro con una chiamata al metodo <xref:System.Activities.WorkflowApplication.Run%2A>, quindi attende il completamento del flusso di lavoro. Quando il flusso di lavoro viene completato, l'oggetto <xref:System.Threading.AutoResetEvent> viene impostato e l'applicazione host viene completata.

### <a name="to-set-input-arguments-of-a-workflow"></a>Per impostare gli argomenti di input di un flusso di lavoro

1. Aggiungere la seguente istruzione all'inizio del file **Program.cs** o **Module1.vb** dopo le istruzioni `using` o `Imports` esistenti.

     [!code-csharp[CFX_WF_GettingStarted#5](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#5)]
     [!code-vb[CFX_WF_GettingStarted#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#5)]

2. Sostituire la riga di codice che crea il nuovo oggetto <xref:System.Activities.WorkflowApplication> con il codice seguente che crea e passa un dizionario di parametri al flusso di lavoro quando viene creato.

    > [!NOTE]
    > Sostituire `Workflow1` in questi esempi con `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, a seconda del flusso di lavoro completato nel passaggio precedente [How to: Create a Workflow](how-to-create-a-workflow.md) . Se non si sostituisce `Workflow1` , si verificheranno degli errori di compilazione quando si tenterà di compilare o eseguire il flusso di lavoro.

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     Questo dizionario contiene un elemento con una chiave di `MaxNumber`. Le chiavi nel dizionario di input corrispondono agli argomenti di input sull'attività radice del flusso di lavoro. `MaxNumber` viene usato dal flusso di lavoro per determinare il limite superiore del numero generato casualmente.

### <a name="to-retrieve-output-arguments-of-a-workflow"></a>Per recuperare gli argomenti di output di un flusso di lavoro

1. Modificare il gestore <xref:System.Activities.WorkflowApplication.Completed%2A> per recuperare e visualizzare il numero di turni usati dal flusso di lavoro.

     [!code-csharp[CFX_WF_GettingStarted#7](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#7)]
     [!code-vb[CFX_WF_GettingStarted#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#7)]

### <a name="to-resume-a-bookmark"></a>Per riprendere un segnalibro

1. Aggiungere il seguente codice all'inizio del metodo `Main` subito dopo la dichiarazione <xref:System.Threading.AutoResetEvent> esistente.

     [!code-csharp[CFX_WF_GettingStarted#8](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#8)]
     [!code-vb[CFX_WF_GettingStarted#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#8)]

2. Aggiungere il seguente gestore <xref:System.Activities.WorkflowApplication.Idle%2A> subito dopo i tre gestori del ciclo di vita del flusso di lavoro esistenti in `Main`.

     [!code-csharp[CFX_WF_GettingStarted#9](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#9)]
     [!code-vb[CFX_WF_GettingStarted#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#9)]

     Ogni volta che il flusso di lavoro diventa inattivo in attesa del tentativo successivo, questo gestore viene chiamato e l'oggetto `idleAction` <xref:System.Threading.AutoResetEvent> viene impostato. Il codice nel passaggio seguente usa `idleEvent` e `syncEvent` per determinare se il flusso di lavoro è in attesa della prossimo tentativo o viene completato.

    > [!NOTE]
    > In questo esempio l'applicazione host usa eventi di reimpostazione automatica nei gestori <xref:System.Activities.WorkflowApplication.Completed%2A> e <xref:System.Activities.WorkflowApplication.Idle%2A> per sincronizzare l'applicazione host con lo stato di avanzamento del flusso di lavoro. Non è necessario bloccare e attendere l'inattività del flusso di lavoro prima di riprendere un segnalibro, ma in questo esempio gli eventi di sincronizzazione sono obbligatori affinché l'host sappia se il flusso di lavoro viene completato o se è in attesa di più input dell'utente usando l'oggetto <xref:System.Activities.Bookmark>. Per ulteriori informazioni, vedere [segnalibri](bookmarks.md).

3. Rimuovere la chiamata al metodo `WaitOne`e sostituirla con codice per raccogliere l'input dell'utente e riprendere l'oggetto <xref:System.Activities.Bookmark>.

     Rimuovere la seguente riga di codice.

     [!code-csharp[CFX_WF_GettingStarted#10](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#10)]
     [!code-vb[CFX_WF_GettingStarted#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#10)]

     Sostituirla con l'esempio seguente.

     [!code-csharp[CFX_WF_GettingStarted#11](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#11)]
     [!code-vb[CFX_WF_GettingStarted#11](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#11)]

## <a name="to-build-and-run-the-application"></a><a name="BKMK_ToRunTheApplication"></a>Per compilare ed eseguire l'applicazione

1. Fare clic con il pulsante destro del mouse su **NumberGuessWorkflowHost** in **Esplora soluzioni** e selezionare **Imposta come progetto di avvio**.

2. Premere CTRL+F5 per compilare ed eseguire l'applicazione. Provare a determinare il numero con meno tentativi possibili.

     Per provare l'applicazione con uno degli altri stili del flusso di lavoro, sostituire `Workflow1` nel codice che crea <xref:System.Activities.WorkflowApplication> con `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, a seconda dello stile del flusso di lavoro desiderato.

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     Per istruzioni sull'aggiunta di persistenza a un'applicazione flusso di lavoro, vedere l'argomento successivo, [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md).

## <a name="example"></a>Esempio
 L'esempio seguente è l'elenco di codice per il metodo `Main` .

> [!NOTE]
> Sostituire `Workflow1` in questi esempi con `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, a seconda del flusso di lavoro completato nel passaggio precedente [How to: Create a Workflow](how-to-create-a-workflow.md) . Se non si sostituisce `Workflow1` , si verificheranno degli errori di compilazione quando si tenterà di compilare o eseguire il flusso di lavoro.

 [!code-csharp[CFX_WF_GettingStarted#12](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#12)]
 [!code-vb[CFX_WF_GettingStarted#12](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#12)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.WorkflowApplication>
- <xref:System.Activities.Bookmark>
- [Programmazione di Windows Workflow Foundation](programming.md)
- [Esercitazione Introduzione](getting-started-tutorial.md)
- [Procedura: Creare un flusso di lavoro](how-to-create-a-workflow.md)
- [Procedura: Creare ed eseguire un flusso di lavoro con esecuzione prolungata](how-to-create-and-run-a-long-running-workflow.md)
- [Attesa per l'input in un flusso di lavoro](waiting-for-input-in-a-workflow.md)
- [Hosting dei flussi di lavoro](hosting-workflows.md)
