---
title: "Procedura: creare un'attività"
description: 'Questo articolo illustra come creare due attività in Workflow Foundation: una che usa il codice per implementare la logica e una definita tramite altre attività.'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: dae099d102b0c85d09a1ef8bcce56e8a9096bd20
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419590"
---
# <a name="how-to-create-an-activity"></a>Procedura: creare un'attività

Le attività sono l'unità principale del comportamento in [!INCLUDE[wf1](../../../includes/wf1-md.md)]. La logica di esecuzione di un'attività può essere implementata nel codice gestito oppure tramite altre attività. In questo argomento viene illustrato come creare due attività. La prima è un'attività semplice che usa il codice per implementare la propria logica di esecuzione. L'implementazione della seconda attività viene definita tramite altre attività. Queste attività vengono usate nei seguenti passaggi dell'esercitazione.

> [!NOTE]
> Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).

## <a name="create-the-activity-library-project"></a>Creare il progetto di libreria di attività

1. Aprire Visual Studio e scegliere **nuovo**  >  **progetto** dal menu **file** .

2. Nella finestra di dialogo **nuovo progetto** , sotto la categoria **installato** , selezionare flusso di lavoro di **Visual C#**  >  **Workflow** (o **Visual Basic**  >  **flusso di lavoro**).

    > [!NOTE]
    > Se non viene visualizzata la categoria del modello di **flusso di lavoro** , potrebbe essere necessario installare il componente **Windows Workflow Foundation** di Visual Studio. Scegliere il collegamento **apri programma di installazione di Visual Studio** sulla parte sinistra della finestra di dialogo **nuovo progetto** . In Programma di installazione di Visual Studio selezionare la scheda **singoli componenti** . Quindi, nella categoria **attività di sviluppo** selezionare il componente **Windows Workflow Foundation** . Scegliere **modifica** per installare il componente.

3. Selezionare il modello di progetto **libreria attività** . Digitare `NumberGuessWorkflowActivities` nella casella **Nome** e fare clic su **OK**.

4. Fare clic con il pulsante destro del mouse su **Activity1.xaml** in **Esplora soluzioni** e scegliere **Elimina**. Fare clic su **OK** per confermare.

## <a name="create-the-readint-activity"></a>Creare l'attività ReadInt

1. Scegliere **Aggiungi nuovo elemento** dal menu **progetto** .

2. Nel nodo **Installed**  >  **elementi comuni** installati selezionare flusso di **lavoro**. Selezionare **attività codice** dall'elenco **flusso di lavoro** .

3. Digitare `ReadInt` nella casella **Nome** e fare clic su **Aggiungi**.

4. Sostituire la definizione dell'attività `ReadInt` esistente con la definizione seguente.

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > L'attività `ReadInt` deriva da <xref:System.Activities.NativeActivity%601> anziché <xref:System.Activities.CodeActivity>, che è l'attività predefinita per il modello di attività codice. L'oggetto <xref:System.Activities.CodeActivity%601> può essere usato se l'attività fornisce un singolo risultato, che viene esposto tramite l'argomento <xref:System.Activities.Activity%601.Result%2A>, ma <xref:System.Activities.CodeActivity%601> non supporta l'uso dei segnalibri, quindi viene usato l'oggetto <xref:System.Activities.NativeActivity%601>.

## <a name="create-the-prompt-activity"></a>Creare l'attività prompt

1. Premere **CTRL** + **MAIUSC** + **B** per compilare il progetto. Nella compilazione del progetto, l'attività `ReadInt` in questo progetto può essere usata per compilare l'attività personalizzata tramite questo passaggio.

2. Scegliere **Aggiungi nuovo elemento** dal menu **progetto** .

3. Nel nodo **Installed**  >  **elementi comuni** installati selezionare flusso di **lavoro**. Selezionare l'**attività** dall'elenco **Workflow**.

4. Digitare `Prompt` nella casella **Nome** e fare clic su **Aggiungi**.

5. Fare doppio clic su **prompt. XAML** in **Esplora soluzioni** per visualizzarlo nella finestra di progettazione se non è già visualizzato.

6. Fare clic su **Argomenti** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per visualizzare il riquadro **Argomenti**.

7. Fare clic su **Crea argomento**.

8. Digitare `BookmarkName` nella casella **nome** , selezionare **nell'elenco a** discesa **direzione** , selezionare **stringa** dall'elenco a discesa tipo di **argomento** , quindi premere **invio** per salvare l'argomento.

9. Fare clic su **Crea argomento**.

10. Digitare `Result` nella casella **nome** che si trova sotto l'argomento appena aggiunto `BookmarkName` , selezionare **esterno** dall'elenco a discesa **direzione** , selezionare **Int32** dall'elenco a discesa **tipo di argomento** , quindi premere **invio**.

11. Fare clic su **Crea argomento**.

12. Digitare `Text` nella casella **nome** , selezionare **nell'elenco a** discesa **direzione** , selezionare **stringa** dall'elenco a discesa tipo di **argomento** , quindi premere **invio** per salvare l'argomento.

     Questi tre argomenti vengono associati agli argomenti corrispondenti delle attività <xref:System.Activities.Statements.WriteLine> e `ReadInt` aggiunte all'attività `Prompt` nei passaggi seguenti.

13. Fare clic su **Argomenti** nel riquadro inferiore sinistro dell'area di progettazione dell'attività per chiudere il riquadro **Argomenti**.

14. Trascinare un'attività **Sequence** dalla sezione **flusso di controllo** della **casella degli strumenti** e rilasciarla sull'etichetta **rilasciare** l'attività dell'ActivityDesigner **prompt** .

    > [!TIP]
    > Se la finestra **Casella degli strumenti** non è visualizzata, selezionare **Casella degli strumenti** dal menu **Visualizza**.

15. Trascinare un'attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla sull'etichetta **Drop Activity here** dell'attività **Sequence** .

16. Associare l'argomento **Text** dell'attività **WriteLine** all'argomento **Text** dell'attività **prompt** digitando nella `Text` casella **immettere un'espressione C#** o **immettere un'espressione VB** nella finestra **Proprietà** , quindi premere il tasto **Tab** due volte. Ciò consente di chiudere la finestra dei membri dell'elenco IntelliSense e salva il valore della proprietà spostando la selezione dalla proprietà. Questa proprietà può essere impostata anche digitando `Text` nella casella **immettere un'espressione C#** o **immettere un'espressione VB** nell'attività stessa.

    > [!TIP]
    > Se la **finestra Proprietà** non è visualizzata, scegliere **finestra Proprietà** dal menu **Visualizza** .

17. Trascinare un'attività **ReadInt** dalla sezione **NumberGuessWorkflowActivities** della **casella degli strumenti** e rilasciarla nell'attività **Sequence** in modo che segua l'attività **WriteLine** .

18. Associare l'argomento **BookmarkName** dell'attività **ReadInt** all'argomento **BookmarkName** dell'attività **prompt** digitando `BookmarkName` nella casella **immettere un'espressione VB** a destra dell'argomento **BookmarkName** nella **finestra Proprietà**, quindi premere il tasto **Tab** due volte per chiudere la finestra elenco IntelliSense membri e salvare la proprietà.

19. Associare l'argomento **result** dell'attività **ReadInt** all'argomento **result** dell'attività **prompt** digitando `Result` nella casella **immettere un'espressione VB** a destra dell'argomento **result** nella **finestra Proprietà**, quindi premere il tasto **Tab** due volte.

20. Premere **CTRL** + **MAIUSC** + **B** per compilare la soluzione.

## <a name="next-steps"></a>Passaggi successivi

Per istruzioni su come creare un flusso di lavoro usando queste attività, vedere il passaggio successivo dell'esercitazione [procedura: creare un flusso di lavoro](how-to-create-a-workflow.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [Progettazione e implementazione di attività personalizzate](designing-and-implementing-custom-activities.md)
- [Esercitazione Introduzione](getting-started-tutorial.md)
- [Procedura: Creare un flusso di lavoro](how-to-create-a-workflow.md)
- [Uso di ExpressionTextBox in un ActivityDesigner personalizzato](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
