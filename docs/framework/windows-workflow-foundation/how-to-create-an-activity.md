---
title: "Procedura: creare un'attività"
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
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 26385d91b4201820a5f6ba77b512e7bcfd5372c3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-an-activity"></a>Procedura: creare un'attività
Le attività sono l'unità principale del comportamento in [!INCLUDE[wf1](../../../includes/wf1-md.md)]. La logica di esecuzione di un'attività può essere implementata nel codice gestito oppure tramite altre attività. In questo argomento viene illustrato come creare due attività. La prima è un'attività semplice che usa il codice per implementare la propria logica di esecuzione. L'implementazione della seconda attività viene definita tramite altre attività. Queste attività vengono usate nei seguenti passaggi dell'esercitazione.  
  
> [!NOTE]
>  Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-activity-library-project"></a>Per creare il progetto di libreria di attività  
  
1.  Aprire [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] e scegliere **New**, **progetto** dal **File** menu.  
  
2.  Espandere il **altri tipi di progetto** nodo il **installato**, **modelli** elenco e selezionare **soluzioni di Visual Studio**.  
  
3.  Selezionare **soluzione vuota** dal **soluzioni di Visual Studio** elenco. Assicurarsi che nell'elenco a discesa della versione di .NET Framework sia selezionata l'opzione **.NET Framework 4.5** . Tipo `WF45GettingStartedTutorial` nel **nome** casella e quindi fare clic su **OK**.  
  
4.  Fare doppio clic su **WF45GettingStartedTutorial** in **Esplora** e scegliere **Aggiungi**, **nuovo progetto**.  
  
    > [!TIP]
    >  Se la finestra **Esplora soluzioni** non è visualizzata, scegliere **Esplora soluzioni** dal menu **Visualizza** .  
  
5.  Nel nodo **Modelli installati** selezionare **Visual C#**, **Flusso di lavoro** (oppure **Visual Basic**, **Flusso di lavoro**). Verificare che **.NET Framework 4.5** è selezionata nel [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] elenco a discesa della versione. Selezionare **libreria attività** dal **flusso di lavoro** elenco. Tipo `NumberGuessWorkflowActivities` nel **nome** casella e quindi fare clic su **OK**.  
  
    > [!NOTE]
    >  A seconda del linguaggio di programmazione configurato come linguaggio principale in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], **Visual c#** o **Visual Basic** nodo può trovarsi sotto il **altri linguaggi**nodo il **installato** nodo.  
  
6.  Fare doppio clic su **Activity1** in **Esplora** e scegliere **eliminare**. Per confermare scegliere **OK** .  
  
### <a name="to-create-the-readint-activity"></a>Per creare l'attività ReadInt  
  
1.  Scegliere **Aggiungi nuovo elemento** dal **progetto** menu.  
  
2.  Nel **installato**, **elementi comuni** nodo, seleziona **flusso di lavoro**. Selezionare **attività codice** dal **flusso di lavoro** elenco.  
  
3.  Tipo `ReadInt` nel **nome** casella e quindi fare clic su **Aggiungi**.  
  
4.  Sostituire la definizione dell'attività `ReadInt` esistente con la definizione seguente.  
  
     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]  
  
    > [!NOTE]
    >  L'attività `ReadInt` deriva da <xref:System.Activities.NativeActivity%601> anziché <xref:System.Activities.CodeActivity>, che è l'attività predefinita per il modello di attività codice. L'oggetto <xref:System.Activities.CodeActivity%601> può essere usato se l'attività fornisce un singolo risultato, che viene esposto tramite l'argomento <xref:System.Activities.Activity%601.Result%2A>, ma <xref:System.Activities.CodeActivity%601> non supporta l'uso dei segnalibri, quindi viene usato l'oggetto <xref:System.Activities.NativeActivity%601>.  
  
### <a name="to-create-the-prompt-activity"></a>Per creare l'attività Prompt  
  
1.  Premere CTRL+MAIUSC+B per compilare il progetto. Nella compilazione del progetto, l'attività `ReadInt` in questo progetto può essere usata per compilare l'attività personalizzata tramite questo passaggio.  
  
2.  Scegliere **Aggiungi nuovo elemento** dal **progetto** menu.  
  
3.  Nel **installato**, **elementi comuni** nodo, seleziona **flusso di lavoro**. Selezionare **attività** dal **flusso di lavoro** elenco.  
  
4.  Tipo `Prompt` nel **nome** casella e quindi fare clic su **Aggiungi**.  
  
5.  Fare doppio clic su **prompt** in **Esplora** da visualizzare nella finestra di progettazione se non è già visualizzato.  
  
6.  Fare clic su **argomenti** nel lato inferiore sinistro della finestra di progettazione di attività per visualizzare il **argomenti** riquadro.  
  
7.  Fare clic su **Crea argomento**.  
  
8.  Tipo `BookmarkName` nel **nome** , quindi selezionare **In** dal **direzione** elenco a discesa, seleziona **stringa** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.  
  
9. Fare clic su **Crea argomento**.  
  
10. Tipo `Result` nel **nome** casella che si trova sotto appena aggiunta `BookmarkName` argomento, selezionare **Out** dal **direzione** elenco a discesa, seleziona **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.  
  
11. Fare clic su **Crea argomento**.  
  
12. Tipo `Text` nel **nome** , quindi selezionare **In** dal **direzione** elenco a discesa, seleziona **stringa** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.  
  
     Questi tre argomenti vengono associati agli argomenti corrispondenti delle attività <xref:System.Activities.Statements.WriteLine> e `ReadInt` aggiunte all'attività `Prompt` nei passaggi seguenti.  
  
13. Fare clic su **argomenti** nel lato inferiore sinistro dell'ActivityDesigner per chiudere la **argomenti** riquadro.  
  
14. Trascinare un **sequenza** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta del **Prompt** ActivityDesigner.  
  
    > [!TIP]
    >  Se il **della casella degli strumenti** non verrà visualizzata la finestra, selezionare **della casella degli strumenti** dal **vista** menu.  
  
15. Trascinare un **WriteLine** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta del **Sequenza** attività.  
  
16. Associare il **testo** argomento del **WriteLine** attività per il **testo** argomento del **Prompt** attività digitando `Text` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella il **proprietà** finestra e quindi la scheda tasto due volte. Ciò consente di chiudere la finestra dei membri dell'elenco IntelliSense e salva il valore della proprietà spostando la selezione dalla proprietà. Questa proprietà può essere impostata anche digitando `Text` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella nell'attività stessa.  
  
    > [!TIP]
    >  Se il **finestra proprietà** non è visualizzata, selezionare **finestra proprietà** dal **vista** menu.  
  
17. Trascinare un **ReadInt** attività dal **NumberGuessWorkflowActivities** sezione il **della casella degli strumenti** e rilasciarlo nel **sequenza** attività in modo che segua il **WriteLine** attività.  
  
18. Associare il **BookmarkName** argomento del **ReadInt** attività per il **BookmarkName** argomento del **Prompt** attività digitando `BookmarkName` nel **immettere un'espressione VB** casella a destra del **BookmarkName** argomento in di **finestra proprietà**e quindi premere il tasto TAB due a volte per chiudere la finestra di IntelliSense elenco membri e salvare la proprietà.  
  
19. Associare il **risultato** argomento del **ReadInt** attività per il **risultato** argomento del **Prompt** attività digitando `Result` nel **immettere un'espressione VB** casella a destra del **risultato** argomento in di **finestra proprietà**e quindi premere il tasto TAB due volte.  
  
20. Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
     Per istruzioni su come creare un flusso di lavoro utilizzando queste attività, vedere il passaggio successivo dell'esercitazione, [procedura: creare un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Activities.CodeActivity>  
 <xref:System.Activities.NativeActivity%601>  
 [Progettazione e implementazione di attività personalizzate](../../../docs/framework/windows-workflow-foundation/designing-and-implementing-custom-activities.md)  
 [Esercitazione introduttiva](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [Procedura: Creare un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)  
 [Utilizzo di ExpressionTextBox in un ActivityDesigner personalizzato](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
