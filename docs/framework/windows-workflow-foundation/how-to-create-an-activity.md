---
title: "Procedura: creare un'attività"
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: 8aa6900b26bbe9f77fe0802a7929febe5af61269
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46539616"
---
# <a name="how-to-create-an-activity"></a>Procedura: creare un'attività

Le attività sono l'unità principale del comportamento in [!INCLUDE[wf1](../../../includes/wf1-md.md)]. La logica di esecuzione di un'attività può essere implementata nel codice gestito oppure tramite altre attività. In questo argomento viene illustrato come creare due attività. La prima è un'attività semplice che usa il codice per implementare la propria logica di esecuzione. L'implementazione della seconda attività viene definita tramite altre attività. Queste attività vengono usate nei seguenti passaggi dell'esercitazione.

> [!NOTE]
> Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).

## <a name="create-the-activity-library-project"></a>Creare il progetto di libreria di attività

1.  Aprire Visual Studio e scegli **New** > **Project** dal **File** menu.

2.  Nel **nuovo progetto** finestra di dialogo, sotto il **installati** categoria, seleziona **Visual c#** > **flusso di lavoro** (o **Visual Basic** > **flusso di lavoro**).

    > [!NOTE]
    > Se non viene visualizzato il **flusso di lavoro** categoria del modello, potrebbe essere necessario installare il **Windows Workflow Foundation** componente di Visual Studio. Scegliere il **aperto Visual Studio Installer** collegamento sul lato sinistro delle **nuovo progetto** finestra di dialogo. Il programma di installazione di Visual Studio, selezionare la **singoli componenti** scheda. Quindi, sotto il **attività di sviluppo** categoria, seleziona la **Windows Workflow Foundation** componente. Scegli **Modify** per installare il componente.

3. Selezionare il **libreria di attività** modello di progetto. Tipo di `NumberGuessWorkflowActivities` nella **Name** casella e quindi fare clic su **OK**.

4.  Fare doppio clic su **Activity1.xaml** nelle **Esplora soluzioni** e scegliere **Elimina**. Per confermare scegliere **OK** .

## <a name="create-the-readint-activity"></a>Creare l'attività ReadInt

1.  Scegli **Aggiungi nuovo elemento** dalle **progetto** menu.

2.  Nel **Installed** > **elementi comuni** nodo, seleziona **flusso di lavoro**. Selezionare **attività di codice** dalle **flusso di lavoro** elenco.

3.  Tipo di `ReadInt` nella **Name** casella e quindi fare clic su **Add**.

4.  Sostituire la definizione dell'attività `ReadInt` esistente con la definizione seguente.

     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > L'attività `ReadInt` deriva da <xref:System.Activities.NativeActivity%601> anziché <xref:System.Activities.CodeActivity>, che è l'attività predefinita per il modello di attività codice. L'oggetto <xref:System.Activities.CodeActivity%601> può essere usato se l'attività fornisce un singolo risultato, che viene esposto tramite l'argomento <xref:System.Activities.Activity%601.Result%2A>, ma <xref:System.Activities.CodeActivity%601> non supporta l'uso dei segnalibri, quindi viene usato l'oggetto <xref:System.Activities.NativeActivity%601>.

## <a name="create-the-prompt-activity"></a>Creare l'attività Prompt

1.  Premere **Ctrl**+**MAIUSC**+**B** per compilare il progetto. Nella compilazione del progetto, l'attività `ReadInt` in questo progetto può essere usata per compilare l'attività personalizzata tramite questo passaggio.

2.  Scegli **Aggiungi nuovo elemento** dalle **progetto** menu.

3.  Nel **Installed** > **elementi comuni** nodo, seleziona **flusso di lavoro**. Selezionare **impegno** dalle **flusso di lavoro** elenco.

4.  Tipo di `Prompt` nella **Name** casella e quindi fare clic su **Add**.

5.  Fare doppio clic su **prompt. XAML** nelle **Esplora soluzioni** per visualizzarlo nella finestra di progettazione se non è già visualizzato.

6.  Fare clic su **argomenti** sul lato sinistro inferiore dell'ActivityDesigner per visualizzare i **argomenti** riquadro.

7.  Fare clic su **Crea argomento**.

8.  Tipo `BookmarkName` nella **nome** , quindi selezionare **nel** dal **direzione** elenco a discesa, seleziona **stringa** dal **Tipo di argomento** elenco a discesa e quindi premere **invio** per salvare l'argomento.

9. Fare clic su **Crea argomento**.

10. Tipo `Result` nella **Name** casella sotto appena aggiunta `BookmarkName` argomento, selezionare **Out** dal **direzione** elenco a discesa, seleziona **Int32** dalle **tipo di argomento** elenco a discesa e quindi premere **invio**.

11. Fare clic su **Crea argomento**.

12. Tipo `Text` nella **nome** , quindi selezionare **nel** dal **direzione** elenco a discesa, seleziona **stringa** dal **Tipo di argomento** elenco a discesa e quindi premere **invio** per salvare l'argomento.

     Questi tre argomenti vengono associati agli argomenti corrispondenti delle attività <xref:System.Activities.Statements.WriteLine> e `ReadInt` aggiunte all'attività `Prompt` nei passaggi seguenti.

13. Fare clic su **argomenti** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **argomenti** riquadro.

14. Trascinare un **sequenza** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta del **Dei messaggi di richiesta** ActivityDesigner.

    > [!TIP]
    > Se il **casella degli strumenti** finestra non viene visualizzata, selezionare **della casella degli strumenti** dal **visualizzazione** menu.

15. Trascinare un **WriteLine** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta del **Sequenza** attività.

16. Associare il **testo** argomento del **WriteLine** attività per il **testo** argomento del **Prompt** attività digitando `Text` nel **immettere un'espressione c#** oppure **immettere un'espressione VB** nella casella il **proprietà** finestra e quindi premere il **scheda** chiave due volte. Ciò consente di chiudere la finestra dei membri dell'elenco IntelliSense e salva il valore della proprietà spostando la selezione dalla proprietà. Questa proprietà può essere impostata anche digitando `Text` nella **immettere un'espressione c#** oppure **immettere un'espressione VB** casella nell'attività stessa.

    > [!TIP]
    > Se il **finestra delle proprietà** non è visualizzato, selezionare **finestra delle proprietà** dal **visualizzazione** menu.

17. Trascinare un **ReadInt** attività dal **NumberGuessWorkflowActivities** sezione del **della casella degli strumenti** e rilasciarla nel **sequenza** attività in modo che segua il **WriteLine** attività.

18. Associare il **BookmarkName** argomento del **ReadInt** attività per il **BookmarkName** argomento del **Prompt** attività digitando `BookmarkName` nel **immettere un'espressione VB** a destra della casella il **BookmarkName** argomento nel **finestra proprietà**e quindi premere il **Scheda** due volte per chiudere la finestra di membri di elenco IntelliSense e salvare la proprietà della chiave.

19. Associare il **risultato** argomento del **ReadInt** attività per il **risultato** argomento del **Prompt** attività digitando `Result` nel **immettere un'espressione VB** casella a destra del **risultato** argomento in di **finestra proprietà**e quindi premere il **scheda** tasto due volte.

20. Premere **Ctrl**+**MAIUSC**+**B** per compilare la soluzione.

## <a name="next-steps"></a>Passaggi successivi

Per istruzioni su come creare un flusso di lavoro tramite queste attività, vedere il passaggio successivo dell'esercitazione [procedura: creare un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [Progettazione e implementazione di attività personalizzate](../../../docs/framework/windows-workflow-foundation/designing-and-implementing-custom-activities.md)
- [Esercitazione introduttiva](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
- [Procedura: Creare un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)
- [Uso di ExpressionTextBox in un ActivityDesigner personalizzato](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)