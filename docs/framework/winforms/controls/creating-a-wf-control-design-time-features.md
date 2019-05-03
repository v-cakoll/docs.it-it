---
title: 'Procedura dettagliata: Creazione di un controllo di Windows Forms che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
ms.openlocfilehash: 70cd08a9d7d03cec4e946d2acb806dbecfe774f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011569"
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a>Procedura dettagliata: Creazione di un controllo di Windows Forms che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione

È possibile migliorare l'esperienza in fase di progettazione per un controllo personalizzato, è sufficiente creare una finestra di progettazione personalizzato associato.

Questa procedura dettagliata illustra come creare una finestra di progettazione personalizzata per un controllo personalizzato. Si implementerà un `MarqueeControl` tipo e una classe della finestra di progettazione associata, chiamato `MarqueeControlRootDesigner`.

Il `MarqueeControl` tipo implementa una visualizzazione simile a un teatro con animate luci e testo lampeggiante.

La finestra di progettazione per questo controllo interagisce con l'ambiente di progettazione per fornire un'esperienza in fase di progettazione personalizzata. Con la finestra di progettazione personalizzata, è possibile assemblare un personalizzato `MarqueeControl` implementazione con luci animate e testo intermittente in molte combinazioni diverse. È possibile usare il controllo assemblato in un formato come qualsiasi altro controllo Windows Form.

Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione del progetto

- Creazione di un progetto di libreria di controlli

- Riferimento al progetto di controllo personalizzato

- Definizione di un controllo personalizzato e la finestra di progettazione personalizzata

- Creazione di un'istanza del controllo personalizzato

- Impostazione del progetto per il debug in fase di progettazione

- Implementazione del controllo personalizzato

- Creazione di un controllo figlio per il controllo personalizzato

- Creare il controllo figlio MarqueeBorder

- Creazione di una finestra di progettazione personalizzata Shadow e le proprietà di filtro

- Gestione delle modifiche dei componenti

- Aggiunta di verbi di progettazione per la finestra di progettazione personalizzata

- Creazione di un UITypeEditor personalizzati

- Test del controllo personalizzato nella finestra di progettazione

Al termine, il controllo personalizzato avrà un aspetto simile al seguente:

![Possibile disposizione di MarqueeControl](./media/demomarqueecontrol.gif "DemoMarqueeControl")

Per il listato di codice completo, vedere [come: Creare un controllo di Windows Form che sfrutta i vantaggi della funzionalità Design-Time](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).

> [!NOTE]
> Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario:

- Autorizzazioni sufficienti per essere in grado di creare ed eseguire progetti di applicazione Windows Form nel computer in cui è installato Visual Studio.

## <a name="creating-the-project"></a>Creazione del progetto

Il primo passaggio consiste nel creare il progetto di applicazione. Si userà questo progetto per compilare l'applicazione che ospita il controllo personalizzato.

### <a name="to-create-the-project"></a>Per creare il progetto

- Creare un progetto Windows Forms Application denominato "MarqueeControlTest" (**File** > **New** > **progetto**  >   **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).

## <a name="creating-a-control-library-project"></a>Creazione di un progetto di libreria di controlli

Il passaggio successivo consiste nel creare il progetto di libreria di controlli. Si creerà un nuovo controllo personalizzato e la finestra di progettazione personalizzata corrispondente.

### <a name="to-create-the-control-library-project"></a>Per creare il progetto di libreria di controlli

1. Aggiungere un progetto libreria di controlli Windows Form alla soluzione. Denominare il progetto "MarqueeControlLibrary."

2. Usando **Esplora soluzioni**, eliminare il controllo del progetto predefinita eliminando il file di origine denominato "UserControl1.cs" o "UserControl1", a seconda del linguaggio che preferisci. Per altre informazioni, vedere [Procedura: Rimuovere, eliminare ed escludere elementi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).

3. Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> voce al `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine un nome di base di "MarqueeControl."

4. Usando **Esplora soluzioni**, creare una nuova cartella nella `MarqueeControlLibrary` progetto. Per altre informazioni, vedere [Procedura: Aggiungere nuovi elementi di progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)). Denominare la nuova cartella "Progettazione".

5. Fare doppio clic il **progettazione** cartella e aggiungere una nuova classe. Assegnare un nome di base di "MarqueeControlRootDesigner." al file di origine

6. È necessario utilizzare i tipi dall'assembly System. Design e quindi aggiungere il riferimento per il `MarqueeControlLibrary` progetto.

    > [!NOTE]
    > Per usare l'assembly System. Design, il progetto deve avere come destinazione la versione completa di .NET Framework, non .NET Framework Client Profile. Per modificare il framework di destinazione, vedere [come: Scegliere una versione di .NET Framework di destinazione](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).

## <a name="referencing-the-custom-control-project"></a>Riferimento al progetto di controllo personalizzato

Si userà il `MarqueeControlTest` progetto per testare il controllo personalizzato. Il progetto di test verrà a conoscenza del controllo personalizzato quando si aggiunge un riferimento al progetto il `MarqueeControlLibrary` assembly.

### <a name="to-reference-the-custom-control-project"></a>Per fare riferimento al progetto di controllo personalizzato

- Nel `MarqueeControlTest` del progetto, aggiungere un riferimento al progetto il `MarqueeControlLibrary` assembly. Assicurarsi di usare il **progetti** scheda il **Aggiungi riferimento** la finestra di dialogo anziché fare riferimento il `MarqueeControlLibrary` assembly direttamente.

## <a name="defining-a-custom-control-and-its-custom-designer"></a>Definizione di un controllo personalizzato e la finestra di progettazione personalizzata
 Il controllo personalizzato deriva dal <xref:System.Windows.Forms.UserControl> classe. In questo modo il controllo includere altri controlli, e offre il controllo sono disponibili numerose funzionalità predefinite.

 Il controllo personalizzato avrà una finestra di progettazione personalizzato associato. In questo modo è possibile creare un'esperienza di progettazione univoco personalizzata appositamente per il controllo personalizzato.

 Associare il controllo con la finestra di progettazione, utilizzare il <xref:System.ComponentModel.DesignerAttribute> classe. Poiché si sta sviluppando l'intero comportamento in fase di progettazione di controlli personalizzati, la finestra di progettazione personalizzata implementerà la <xref:System.ComponentModel.Design.IRootDesigner> interfaccia.

### <a name="to-define-a-custom-control-and-its-custom-designer"></a>Per definire un controllo personalizzato e la finestra di progettazione personalizzata

1. Aprire il `MarqueeControl` file di origine il **Editor di codice**. Nella parte superiore del file, importare gli spazi dei nomi seguenti:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. Aggiungere il <xref:System.ComponentModel.DesignerAttribute> per il `MarqueeControl` dichiarazione di classe. Consente di associare il controllo personalizzato con la finestra di progettazione.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. Aprire il `MarqueeControlRootDesigner` file di origine il **Editor di codice**. Nella parte superiore del file, importare gli spazi dei nomi seguenti:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. Modificare la dichiarazione del `MarqueeControlRootDesigner` da cui ereditare il <xref:System.Windows.Forms.Design.DocumentDesigner> classe. Si applicano i <xref:System.ComponentModel.ToolboxItemFilterAttribute> per specificare l'interazione della finestra di progettazione con il **casella degli strumenti**.

     **Nota** la definizione per il `MarqueeControlRootDesigner` classe è stata inclusa in uno spazio dei nomi "MarqueeControlLibrary". Questa dichiarazione colloca la finestra di progettazione in uno speciale spazio dei nomi riservato per i tipi correlati alla progettazione.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. Definire il costruttore per il `MarqueeControlRootDesigner` classe. Inserire un <xref:System.Diagnostics.Trace.WriteLine%2A> istruzione nel corpo del costruttore. Ciò potrebbe risultare utile a scopo di debug.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="creating-an-instance-of-your-custom-control"></a>Creazione di un'istanza del controllo personalizzato
 Per osservare il comportamento personalizzato in fase di progettazione del controllo, si inserirà un'istanza del controllo nel form in `MarqueeControlTest` progetto.

### <a name="to-create-an-instance-of-your-custom-control"></a>Per creare un'istanza del controllo personalizzato

1. Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> voce al `MarqueeControlTest` progetto. Assegnare al nuovo file di origine un nome di base di "DemoMarqueeControl."

2. Aprire il `DemoMarqueeControl` del file nei **Editor di codice**. Nella parte superiore del file, importare il `MarqueeControlLibrary` dello spazio dei nomi:

```vb
Imports MarqueeControlLibrary
```

```csharp
using MarqueeControlLibrary;
```

1. Modificare la dichiarazione del `DemoMarqueeControl` da cui ereditare il `MarqueeControl` classe.

2. Compilare il progetto.

3. Aprire `Form1` in Progettazione Windows Form.

4. Trovare il **Componenti MarqueeControlTest** scheda le **della casella degli strumenti** e aprirlo. Trascinare un `DemoMarqueeControl` dal **casella degli strumenti** nel form.

5. Compilare il progetto.

## <a name="setting-up-the-project-for-design-time-debugging"></a>Impostazione del progetto per il debug in fase di progettazione

Quando si sviluppa un'esperienza in fase di progettazione personalizzata, sarà necessario eseguire il debug di componenti e dei controlli. È un modo semplice per configurare il progetto per consentire il debug in fase di progettazione. Per altre informazioni, vedere [Procedura dettagliata: Controlli di debug personalizzato Windows Form in fase di progettazione](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).

### <a name="to-set-up-the-project-for-design-time-debugging"></a>Per configurare il progetto per il debug in fase di progettazione

1. Fare doppio clic il `MarqueeControlLibrary` del progetto e selezionare **proprietà**.

2. Nella finestra di dialogo "Pagine delle proprietà MarqueeControlLibrary", selezionare la **Debug** pagina.

3. Nel **azione di avvio** sezione, selezionare **Avvia programma esterno**. Sarà pertanto il debug di un'istanza separata di Visual Studio, fare clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) per cercare l'IDE di Visual Studio. Il nome del file eseguibile è devenv.exe e se è installato nel percorso predefinito, il percorso è %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.

4. Fare clic su OK per chiudere la finestra di dialogo.

5. Fare doppio clic su di `MarqueeControlLibrary` progetto e scegliere "Imposta come progetto di avvio" per abilitare la configurazione di debug.

## <a name="checkpoint"></a>Checkpoint

A questo punto si è pronti per il debug del comportamento in fase di progettazione del controllo personalizzato. Dopo aver determinato che l'ambiente di debug sia configurato correttamente, si testerà l'associazione tra il controllo personalizzato e la finestra di progettazione personalizzata.

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>Per testare l'ambiente di debug e l'associazione della finestra di progettazione

1. Aprire il `MarqueeControlRootDesigner` file di origine il **Editor di codice** e inserire un punto di interruzione nel <xref:System.Diagnostics.Trace.WriteLine%2A> istruzione.

2. Premere F5 per avviare la sessione di debug. Si noti che viene creata una nuova istanza di Visual Studio.

3. Nella nuova istanza di Visual Studio, aprire la soluzione "MarqueeControlTest". È possibile trovare facilmente la soluzione selezionando **progetti recenti** dalle **File** menu. Il file della soluzione "MarqueeControlTest" verrà elencato come più i file usati di recente.

4. Aprire il `DemoMarqueeControl` nella finestra di progettazione. Si noti che l'istanza di debug di Visual Studio acquisisce lo stato attivo e l'esecuzione si arresta in corrispondenza del punto di interruzione. Premere F5 per continuare la sessione di debug.

A questo punto, tutto ciò che è in qui è possibile sviluppare ed eseguire il debug del controllo personalizzato e relativa finestra di progettazione personalizzato associato. Nella parte restante di questa procedura dettagliata si concentrerà sui dettagli di implementazione di funzionalità del controllo e la finestra di progettazione.

## <a name="implementing-your-custom-control"></a>Implementazione del controllo personalizzato

Il `MarqueeControl` è un <xref:System.Windows.Forms.UserControl> con un po' di personalizzazione. Espone due metodi: `Start`, che avvia l'animazione, e `Stop`, che interrompe l'animazione. Perché il `MarqueeControl` contiene controlli figlio che implementano il `IMarqueeWidget` interfaccia `Start` e `Stop` enumerare ogni controllo figlio e chiamare il `StartMarquee` e `StopMarquee` metodi, rispettivamente, per ogni controllo figlio che implementa `IMarqueeWidget`.

L'aspetto del `MarqueeBorder` e `MarqueeText` controlli dipende il layout, in modo `MarqueeControl` esegue l'override di <xref:System.Windows.Forms.Control.OnLayout%2A> metodo e chiama <xref:System.Windows.Forms.Control.PerformLayout%2A> sui controlli figlio di questo tipo.

Questo è l'estensione del `MarqueeControl` personalizzazioni. Le funzionalità di runtime vengono implementate per il `MarqueeBorder` e `MarqueeText` controlli e le funzionalità in fase di progettazione vengono implementati dal `MarqueeBorderDesigner` e `MarqueeControlRootDesigner` classi.

### <a name="to-implement-your-custom-control"></a>Per implementare il controllo personalizzato

1. Aprire il `MarqueeControl` file di origine il **Editor di codice**. Implementare il `Start` e `Stop` metodi.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. Eseguire l'override del metodo <xref:System.Windows.Forms.Control.OnLayout%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="creating-a-child-control-for-your-custom-control"></a>Creazione di un controllo figlio per il controllo personalizzato

Il `MarqueeControl` ospiterà i due tipi di controlli figlio: il `MarqueeBorder` controllo e il `MarqueeText` controllo.

- `MarqueeBorder`: Questo controllo viene disegnato un bordo di "illuminazione" intorno ai relativi bordi. Le luci flash in sequenza, in modo che queste vengono spostate intorno al bordo. La velocità di intermittenza è controllata da una proprietà denominata `UpdatePeriod`. Molte altre proprietà personalizzate determinare altri aspetti dell'aspetto del controllo. Due metodi, denominati `StartMarquee` e `StopMarquee`, controllare l'inizio e la fine dell'animazione.

- `MarqueeText`: Questo controllo viene disegnato una stringa lampeggiante. Ad esempio il `MarqueeBorder` (controllo), la velocità in corrispondenza del quale fa lampeggiare il testo è controllata dal `UpdatePeriod` proprietà. Il `MarqueeText` controllo ha anche il `StartMarquee` e `StopMarquee` metodi in comune con il `MarqueeBorder` controllo.

In fase di progettazione, il `MarqueeControlRootDesigner` consente a questi due tipi di controllo da aggiungere a un `MarqueeControl` in qualsiasi combinazione.

Funzionalità comuni dei due controlli vengono sottoposte a factoring in un'interfaccia denominata `IMarqueeWidget`. In questo modo il `MarqueeControl` per individuare eventuali controlli figlio relative alla selezione e assegnarvi un trattamento speciale.

Per implementare la funzionalità di animazione periodici, si userà <xref:System.ComponentModel.BackgroundWorker> oggetti dal <xref:System.ComponentModel?displayProperty=nameWithType> dello spazio dei nomi. È possibile usare <xref:System.Windows.Forms.Timer> oggetti, ma quando molti `IMarqueeWidget` gli oggetti sono presenti, il singolo thread dell'interfaccia utente potrebbe non essere possibile stare al passo con l'animazione.

### <a name="to-create-a-child-control-for-your-custom-control"></a>Per creare un controllo figlio per il controllo personalizzato

1. Aggiungere un nuovo elemento di classe per il `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine un nome di base di "IMarqueeWidget."

2. Aprire il `IMarqueeWidget` file di origine il **Editor di codice** e modificare la dichiarazione di `class` a `interface`:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. Aggiungere il codice seguente per il `IMarqueeWidget` interfaccia da esporre una proprietà che gestiscono l'animazione e due metodi:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. Aggiungere un nuovo **controllo personalizzato** voce al `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine un nome di base di "MarqueeText."

5. Trascinare un <xref:System.ComponentModel.BackgroundWorker> componente dal **casella degli strumenti** nel `MarqueeText` controllo. Questo componente consentirà il `MarqueeText` controllo aggiornarsi in modo asincrono.

6. Nella finestra Proprietà impostare il <xref:System.ComponentModel.BackgroundWorker> del componente `WorkerReportsProgress` e <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> delle proprietà per `true`. Queste impostazioni consentono il <xref:System.ComponentModel.BackgroundWorker> componente di generare periodicamente il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi e annullare gli aggiornamenti asincroni. Per altre informazioni, vedere [componente BackgroundWorker](backgroundworker-component.md).

7. Aprire il `MarqueeText` file di origine il **Editor di codice**. Nella parte superiore del file, importare gli spazi dei nomi seguenti:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. Modificare la dichiarazione del `MarqueeText` da cui ereditare <xref:System.Windows.Forms.Label> e implementare il `IMarqueeWidget` interfaccia:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. Dichiarare le variabili di istanza che corrispondono alle proprietà esposte e inizializzarli nel costruttore. Il `isLit` campo determina se il testo da disegnare nel colore specificato per il `LightColor` proprietà.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. Implementare l'interfaccia `IMarqueeWidget`.

    Il `StartMarquee` e `StopMarquee` metodi richiamano il <xref:System.ComponentModel.BackgroundWorker> del componente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> e <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> metodi per avviare e arrestare l'animazione.

    Il <xref:System.ComponentModel.CategoryAttribute.Category%2A> e <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> vengono applicati attributi per il `UpdatePeriod` proprietà in modo che venga visualizzato in una sezione personalizzata della finestra proprietà denominata "Testo scorrevole".

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. Implementare le funzioni di accesso di proprietà. Si esporrà ai client le due proprietà: `LightColor` e `DarkColor`. Il <xref:System.ComponentModel.CategoryAttribute.Category%2A> e <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributi vengono applicati a queste proprietà, in modo che le proprietà vengono visualizzate in una sezione personalizzata della finestra proprietà denominata "Testo scorrevole".

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. Implementare i gestori per il <xref:System.ComponentModel.BackgroundWorker> del componente <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi.

    Il <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore dell'evento rimane inattivo per il numero di millisecondi specificato da `UpdatePeriod` genera quindi le <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi, fino a quando il codice si interrompe l'animazione chiamando <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.

    Il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> gestore dell'evento attiva o disattiva il testo compreso tra il relativo stato chiaro e scuro per dare l'impressione di lampeggiante.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. Eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> metodo per consentire l'animazione.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. Premere F6 per compilare la soluzione.

## <a name="create-the-marqueeborder-child-control"></a>Creare il controllo figlio MarqueeBorder

Il `MarqueeBorder` controllo è leggermente più complessa la `MarqueeText` controllo. Include altre proprietà e l'animazione nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo è più complesso. In teoria, è molto simile al `MarqueeText` controllo.

Poiché il `MarqueeBorder` controllo può disporre i controlli figlio, è necessario essere a conoscenza di <xref:System.Windows.Forms.Control.Layout> gli eventi.

### <a name="to-create-the-marqueeborder-control"></a>Per creare il controllo MarqueeBorder

1. Aggiungere un nuovo **controllo personalizzato** voce al `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine un nome di base di "MarqueeBorder."

2. Trascinare un <xref:System.ComponentModel.BackgroundWorker> componente dal **casella degli strumenti** nel `MarqueeBorder` controllo. Questo componente consentirà il `MarqueeBorder` controllo aggiornarsi in modo asincrono.

3. Nella finestra Proprietà impostare il <xref:System.ComponentModel.BackgroundWorker> del componente `WorkerReportsProgress` e <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> delle proprietà per `true`. Queste impostazioni consentono il <xref:System.ComponentModel.BackgroundWorker> componente di generare periodicamente il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi e annullare gli aggiornamenti asincroni. Per altre informazioni, vedere [componente BackgroundWorker](backgroundworker-component.md).

4. Nella finestra Proprietà, fare clic sul pulsante eventi. Collegare i gestori per il <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi.

5. Aprire il `MarqueeBorder` file di origine il **Editor di codice**. Nella parte superiore del file, importare gli spazi dei nomi seguenti:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. Modificare la dichiarazione del `MarqueeBorder` da cui ereditare <xref:System.Windows.Forms.Panel> e implementare il `IMarqueeWidget` interfaccia.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. Dichiarare due enumerazioni per la gestione di `MarqueeBorder` stato del controllo: `MarqueeSpinDirection`, che determina la direzione in cui le luci "attivare" intorno al bordo, e `MarqueeLightShape`, che determina la forma di luci (quadrata o circolare). Inserire queste dichiarazioni prima il `MarqueeBorder` dichiarazione di classe.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. Dichiarare le variabili di istanza che corrispondono alle proprietà esposte e inizializzarli nel costruttore.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. Implementare l'interfaccia `IMarqueeWidget`.

    Il `StartMarquee` e `StopMarquee` metodi richiamano il <xref:System.ComponentModel.BackgroundWorker> del componente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> e <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> metodi per avviare e arrestare l'animazione.

    Poiché il `MarqueeBorder` controllo può contenere i controlli figlio, il `StartMarquee` metodo enumera tutti i controlli figlio e le chiamate `StartMarquee` per quelli che implementano `IMarqueeWidget`. Il `StopMarquee` metodo ha un'implementazione simile.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. Implementare le funzioni di accesso di proprietà. Il `MarqueeBorder` controllo ha diverse proprietà per controllare l'aspetto del controllo.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. Implementare i gestori per il <xref:System.ComponentModel.BackgroundWorker> del componente <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi.

    Il <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore dell'evento rimane inattivo per il numero di millisecondi specificato da `UpdatePeriod` genera quindi le <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi, fino a quando il codice si interrompe l'animazione chiamando <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.

    Il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> gestore dell'evento incrementa la posizione della luce "base", da cui lo stato chiaro/scuro delle altre luci è determinato, e chiama il <xref:System.Windows.Forms.Control.Refresh%2A> metodo in modo che il controllo a ridisegnarsi.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. Implementare i metodi di supporto `IsLit` e `DrawLight`.

    Il `IsLit` metodo determina il colore di una luce in una determinata posizione. Luci sono "acceso" vengono disegnate nel colore specificato per il `LightColor` vengono disegnati nel colore specificato dalla proprietà e quelle "scuro" il `DarkColor` proprietà.

    Il `DrawLight` metodo consente di disegnare una luce utilizzando il colore appropriato, forma e posizione.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. Eseguire l'override di <xref:System.Windows.Forms.Control.OnLayout%2A> e <xref:System.Windows.Forms.Control.OnPaint%2A> metodi.

    Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo disegna le luci lungo i bordi del `MarqueeBorder` controllo.

    Poiché il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo dipende dalle dimensioni del `MarqueeBorder` (controllo), è necessario chiamarlo ogni volta che viene modificato il layout. A tale scopo, eseguire l'override <xref:System.Windows.Forms.Control.OnLayout%2A> e chiamare <xref:System.Windows.Forms.Control.Refresh%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a>Creazione di una finestra di progettazione personalizzata Shadow e le proprietà di filtro

Il `MarqueeControlRootDesigner` classe fornisce l'implementazione per la finestra di progettazione radice. Oltre a questa finestra di progettazione, che opera sul `MarqueeControl`, è necessario una finestra di progettazione associata in modo specifico la `MarqueeBorder` controllo. Questa finestra di progettazione fornisce il comportamento personalizzato che è appropriato nel contesto della finestra di progettazione radice personalizzata.

In particolare, il `MarqueeBorderDesigner` saranno "shadow" e filtrare determinate proprietà di `MarqueeBorder` controllo, alterando l'interazione con l'ambiente di progettazione.

Intercettazione di chiamate alla funzione di accesso alle proprietà del componente è noto come "shadowing". Consente di tenere traccia del valore impostato dall'utente una finestra di progettazione e, facoltativamente, passare il valore per il componente in fase di progettazione.

Per questo esempio, il <xref:System.Windows.Forms.Control.Visible%2A> e <xref:System.Windows.Forms.Control.Enabled%2A> verrà eseguito dalla proprietà il `MarqueeBorderDesigner`, che impedisce all'utente making il `MarqueeBorder` controllo invisibile o disabilitato durante la fase di progettazione.

Finestre di progettazione può anche aggiungere e rimuovere le proprietà. Per questo esempio, il <xref:System.Windows.Forms.Control.Padding%2A> proprietà verrà rimosso in fase di progettazione, poiché il `MarqueeBorder` controllo a livello di codice imposta la spaziatura interna in base alla dimensione delle luci specificato da di `LightSize` proprietà.

La classe base per `MarqueeBorderDesigner` è <xref:System.ComponentModel.Design.ComponentDesigner>, che dispone di metodi che possono modificare gli attributi, proprietà e gli eventi esposti da un controllo in fase di progettazione:

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

Quando si modifica l'interfaccia pubblica di un componente usando questi metodi, devono rispettare queste regole:

- Aggiungere o rimuovere elementi nel `PreFilter` solo metodi

- Modificare gli elementi esistenti nel `PostFilter` solo metodi

- Chiamare sempre per prima l'implementazione di base `PreFilter` metodi

- Chiamare sempre ultima l'implementazione di base `PostFilter` metodi

Rispettano queste regole assicura che tutte le finestre di progettazione in fase di progettazione di una visualizzazione coerente di tutti i componenti in fase di progettazione.

Il <xref:System.ComponentModel.Design.ComponentDesigner> classe fornisce un dizionario per la gestione dei valori delle proprietà nascoste, che elimina la necessità di creare le variabili di istanza specifico.

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>Per creare una finestra di progettazione personalizzata per le proprietà shadow e Applica filtro

1. Fare doppio clic il **progettazione** cartella e aggiungere una nuova classe. Assegnare un nome di base di "MarqueeBorderDesigner." al file di origine

2. Aprire il `MarqueeBorderDesigner` file di origine il **Editor di codice**. Nella parte superiore del file, importare gli spazi dei nomi seguenti:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. Modificare la dichiarazione del `MarqueeBorderDesigner` da cui ereditare <xref:System.Windows.Forms.Design.ParentControlDesigner>.

    Poiché il `MarqueeBorder` controllo può contenere i controlli figlio `MarqueeBorderDesigner` eredita da <xref:System.Windows.Forms.Design.ParentControlDesigner>, che gestisce l'interazione di padre-figlio.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. Sostituire l'implementazione di base di <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. Implementare le proprietà <xref:System.Windows.Forms.Control.Enabled%2A> e <xref:System.Windows.Forms.Control.Visible%2A>. Queste implementazioni di nascondono le proprietà del controllo.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handling-component-changes"></a>Gestione delle modifiche dei componenti
 Il `MarqueeControlRootDesigner` classe fornisce l'esperienza in fase di progettazione personalizzato per il `MarqueeControl` istanze. La maggior parte delle funzionalità in fase di progettazione viene ereditata dal <xref:System.Windows.Forms.Design.DocumentDesigner> classe; il codice verrà implementare due personalizzazioni specifiche: gestione delle modifiche dei componenti e l'aggiunta di verbi di progettazione.

 Come gli utenti nella progettazione loro `MarqueeControl` istanze, la finestra di progettazione radice terrà traccia delle modifiche per il `MarqueeControl` e i relativi controlli figlio. L'ambiente di progettazione offre un servizio utile, <xref:System.ComponentModel.Design.IComponentChangeService>, per rilevamento modifiche apportate allo stato del componente.

 Acquisire un riferimento a questo servizio eseguendo una query con l'ambiente del <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> (metodo). Se la query ha esito positivo, la finestra di progettazione è possibile collegare un gestore per il <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> eventi ed eseguire tutte le attività sono necessari per mantenere uno stato coerente in fase di progettazione.

 Nel caso del `MarqueeControlRootDesigner` (classe), si chiamerà il <xref:System.Windows.Forms.Control.Refresh%2A> metodo in ogni `IMarqueeWidget` oggetto contenuto dalla `MarqueeControl`. Ciò causerà il `IMarqueeWidget` oggetto da aggiornare se stesso in modo appropriato quando si desidera che le proprietà del controllo padre <xref:System.Windows.Forms.Control.Size%2A> vengono modificati.

### <a name="to-handle-component-changes"></a>Gestire le modifiche al componente

1. Aprire il `MarqueeControlRootDesigner` file di origine nel **Editor di codice** ed eseguire l'override di <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> (metodo). Chiamare l'implementazione di base <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> ed eseguire query per il <xref:System.ComponentModel.Design.IComponentChangeService>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. Implementare il <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> gestore dell'evento. Tipo del componente mittente, test e se è un `IMarqueeWidget`, chiamare il <xref:System.Windows.Forms.Control.Refresh%2A> (metodo).

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="adding-designer-verbs-to-your-custom-designer"></a>Aggiunta di verbi di progettazione per la finestra di progettazione personalizzata

Un verbo di progettazione è un comando di menu collegato a un gestore eventi. Verbi di progettazione vengono aggiunti al menu di scelta rapida del componente in fase di progettazione. Per altre informazioni, vedere <xref:System.ComponentModel.Design.DesignerVerb>.

Verranno aggiunti due verbi di progettazione per le finestre di progettazione: **Esegui Test** e **arrestare Test**. Questi verbi modo sarà possibile visualizzare il comportamento in fase di esecuzione del `MarqueeControl` in fase di progettazione. Verranno aggiunto a questi verbi di `MarqueeControlRootDesigner`.

Quando **Esegui Test** viene richiamato, il gestore dell'evento verbo verrà chiamato il `StartMarquee` metodo su di `MarqueeControl`. Quando **Interrompi Test** viene richiamato, il gestore dell'evento verbo verrà chiamato il `StopMarquee` metodo su di `MarqueeControl`. L'implementazione del `StartMarquee` e `StopMarquee` metodi chiamano controlli indipendenti che implementano questi metodi `IMarqueeWidget`, quindi, qualsiasi contenuto `IMarqueeWidget` controlli parteciperà anche il test.

### <a name="to-add-designer-verbs-to-your-custom-designers"></a>Per aggiungere verbi di progettazione per le finestre di progettazione personalizzate

1. Nel `MarqueeControlRootDesigner` classe, aggiungere i gestori eventi denominati `OnVerbRunTest` e `OnVerbStopTest`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. Connettere questi gestori eventi ai verbi di progettazione corrispondente. `MarqueeControlRootDesigner` eredita un <xref:System.ComponentModel.Design.DesignerVerbCollection> dalla relativa classe base. Verranno creati due nuovi <xref:System.ComponentModel.Design.DesignerVerb> degli oggetti e aggiungerli a questa raccolta nel <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> (metodo).

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="creating-a-custom-uitypeeditor"></a>Creazione di un UITypeEditor personalizzati

Quando si crea un'esperienza in fase di progettazione personalizzata per gli utenti, è spesso preferibile creare un'interazione con la finestra proprietà personalizzata. È possibile farlo creando una <xref:System.Drawing.Design.UITypeEditor>. Per altre informazioni, vedere [Procedura: Creare un Editor di tipo UI](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fd3kt7d5(v=vs.120)).

Il `MarqueeBorder` controllo espone diverse proprietà nella finestra Proprietà. Due di queste proprietà, `MarqueeSpinDirection` e `MarqueeLightShape` sono rappresentate dalle enumerazioni. Per illustrare l'utilizzo di un editor di tipi dell'interfaccia utente, il `MarqueeLightShape` della proprietà è associata una <xref:System.Drawing.Design.UITypeEditor> classe.

### <a name="to-create-a-custom-ui-type-editor"></a>Per creare un tipo personalizzato dell'interfaccia utente dell'editor

1. Aprire il `MarqueeBorder` file di origine il **Editor di codice**.

2. Nella definizione del `MarqueeBorder` classe, dichiarare una classe denominata `LightShapeEditor` che deriva da <xref:System.Drawing.Design.UITypeEditor>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. Dichiarare un <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> variabile di istanza denominato `editorService`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. Eseguire l'override del metodo <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> . Questa implementazione restituisce <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, che indica l'ambiente di progettazione come visualizzare il `LightShapeEditor`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. Eseguire l'override del metodo <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> . Questa implementazione esegue una query all'ambiente di progettazione un <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> oggetto. Se ha esito positivo, viene creato un `LightShapeSelectionControl`. Il <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> metodo viene richiamato per iniziare il `LightShapeEditor`. Il valore restituito da questa chiamata viene restituito all'ambiente di progettazione.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a>Creazione di un controllo di visualizzazione per il UITypeEditor personalizzati

1. Il `MarqueeLightShape` proprietà supporta due tipi di forme chiare: `Square` e `Circle`. Si creerà un controllo personalizzato usato esclusivamente allo scopo di visualizzare graficamente i valori nella finestra Proprietà. Questo controllo personalizzato userà il <xref:System.Drawing.Design.UITypeEditor> per interagire con la finestra Proprietà.

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>Per creare un controllo di visualizzazione per l'interfaccia utente personalizzata dell'editor di tipo

1. Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> voce al `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine un nome di base di "LightShapeSelectionControl."

2. Trascinare due <xref:System.Windows.Forms.Panel> dei controlli il **casella degli strumenti** nel `LightShapeSelectionControl`. Denominarle `squarePanel` e `circlePanel`. Disporli fianco a fianco. Impostare il <xref:System.Windows.Forms.Control.Size%2A> proprietà di entrambi <xref:System.Windows.Forms.Panel> controlli alla (60, 60). Impostare il <xref:System.Windows.Forms.Control.Location%2A> proprietà del `squarePanel` controllo (8, 10). Impostare il <xref:System.Windows.Forms.Control.Location%2A> proprietà del `circlePanel` controllo (80, 10). Infine, impostare il <xref:System.Windows.Forms.Control.Size%2A> proprietà del `LightShapeSelectionControl` a (150, 80).

3. Aprire il `LightShapeSelectionControl` file di origine il **Editor di codice**. Nella parte superiore del file, importare il <xref:System.Windows.Forms.Design?displayProperty=nameWithType> dello spazio dei nomi:

```vb
Imports System.Windows.Forms.Design
```

```csharp
using System.Windows.Forms.Design;
```

1. Implementare <xref:System.Windows.Forms.Control.Click> gestori eventi per il `squarePanel` e `circlePanel` controlli. Tali metodi richiamano <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> per terminare l'oggetto personalizzato <xref:System.Drawing.Design.UITypeEditor> sessione di modifica.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

2. Dichiarare un <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> variabile di istanza denominato `editorService`.

```vb
Private editorService As IWindowsFormsEditorService
```

```csharp
private IWindowsFormsEditorService editorService;
```

1. Dichiarare un `MarqueeLightShape` variabile di istanza denominato `lightShapeValue`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

2. Nel `LightShapeSelectionControl` costruttore, collegare il <xref:System.Windows.Forms.Control.Click> gestori eventi per il `squarePanel` e `circlePanel` controlli <xref:System.Windows.Forms.Control.Click> gli eventi. Definire anche un overload del costruttore che assegna il `MarqueeLightShape` valore dall'ambiente di progettazione per il `lightShapeValue` campo.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

3. Nel <xref:System.ComponentModel.Component.Dispose%2A> metodo, scollegare il <xref:System.Windows.Forms.Control.Click> gestori eventi.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

4. In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**. Aprire il file LightShapeSelectionControl.Designer.cs o LightShapeSelectionControl.Designer.vb e rimuovere la definizione predefinita del <xref:System.ComponentModel.Component.Dispose%2A> (metodo).

5. Implementare la proprietà `LightShape`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

6. Eseguire l'override del metodo <xref:System.Windows.Forms.Control.OnPaint%2A> . Questa implementazione verrà disegnato un quadrato pieno e un cerchio. Disegnando un bordo intorno a una forma o l'altro verrà anche evidenziati i il valore selezionato.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="testing-your-custom-control-in-the-designer"></a>Test del controllo personalizzato nella finestra di progettazione

A questo punto, è possibile compilare il `MarqueeControlLibrary` progetto. Testare l'implementazione mediante la creazione di un controllo da cui eredita il `MarqueeControl` classe e usarlo in un form.

### <a name="to-create-a-custom-marqueecontrol-implementation"></a>Per creare un'implementazione personalizzata di MarqueeControl

1. Aprire `DemoMarqueeControl` in Progettazione Windows Form. Questo modo viene creata un'istanza del `DemoMarqueeControl` tipo e lo visualizza in un'istanza del `MarqueeControlRootDesigner` tipo.

2. Nel **casella degli strumenti**, aprire il **componenti MarqueeControlLibrary** scheda. Verrà visualizzato il `MarqueeBorder` e `MarqueeText` controlli disponibili per la selezione.

3. Trascinare un'istanza di `MarqueeBorder` sul controllo il `DemoMarqueeControl` nell'area di progettazione. Ancorare il `MarqueeBorder` nel controllo padre.

4. Trascinare un'istanza di `MarqueeText` sul controllo il `DemoMarqueeControl` nell'area di progettazione.

5. Compilare la soluzione.

6. Fare doppio clic sui `DemoMarqueeControl` e nel menu di scelta rapida selezionare il **eseguire Test** opzione per avviare l'animazione. Fare clic su **Interrompi Test** per interrompere l'animazione.

7. Aprire **Form1** nella visualizzazione Progettazione.

8. Inserire due <xref:System.Windows.Forms.Button> controlli nel form. Denominarle `startButton` e `stopButton`e modificare il <xref:System.Windows.Forms.Control.Text%2A> valori della proprietà da **Start** e **Arresta**rispettivamente.

9. Implementare <xref:System.Windows.Forms.Control.Click> gestori eventi per entrambi <xref:System.Windows.Forms.Button> controlli.

10. Nel **casella degli strumenti**, aprire il **Componenti MarqueeControlTest** scheda. Verrà visualizzato il `DemoMarqueeControl` disponibili per la selezione.

11. Trascinare un'istanza di `DemoMarqueeControl` nella **Form1** nell'area di progettazione.

12. Nel <xref:System.Windows.Forms.Control.Click> richiamare i gestori eventi, il `Start` e `Stop` metodi su di `DemoMarqueeControl`.

```vb
Private Sub startButton_Click(sender As Object, e As System.EventArgs)
    Me.demoMarqueeControl1.Start()
End Sub 'startButton_Click

Private Sub stopButton_Click(sender As Object, e As System.EventArgs)
Me.demoMarqueeControl1.Stop()
End Sub 'stopButton_Click
```

```csharp
private void startButton_Click(object sender, System.EventArgs e)
{
    this.demoMarqueeControl1.Start();
}

private void stopButton_Click(object sender, System.EventArgs e)
{
    this.demoMarqueeControl1.Stop();
}
```

1. Impostare il `MarqueeControlTest` il progetto come progetto di avvio ed eseguirlo. Verrà visualizzata la forma di `DemoMarqueeControl`. Scegliere il **avviare** per avviare l'animazione. Verrà visualizzato il testo il lampeggiamento e lo spostamento del bordo delle luci.

## <a name="next-steps"></a>Passaggi successivi

Il `MarqueeControlLibrary` illustra un'implementazione semplice di controlli personalizzati e finestre di progettazione associate. È possibile rendere più sofisticati in questo esempio in diversi modi:

- Modificare i valori delle proprietà per il `DemoMarqueeControl` nella finestra di progettazione. Aggiungere più `MarqueBorder` controlla e ancorarli nelle relative istanze padre per creare un effetto annidato. Esperimento con impostazioni diverse per il `UpdatePeriod` e le proprietà correlate alla luce.

- Creare altre implementazioni di `IMarqueeWidget`. È possibile, ad esempio, creare un "neon segno" lampeggiante o un'animazione con più immagini.

- Personalizzare ulteriormente l'esperienza in fase di progettazione. È possibile provare a più proprietà di shadowing <xref:System.Windows.Forms.Control.Enabled%2A> e <xref:System.Windows.Forms.Control.Visible%2A>,. bat e aggiungere nuove proprietà. Aggiungere nuovo verbi di progettazione per semplificare le attività comuni, ad esempio ancorare i controlli figlio.

- Licenza di `MarqueeControl`. Per altre informazioni, vedere [Procedura: Concedere in licenza componenti e controlli](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120)).

- Controllare il modo in cui vengono serializzati i controlli e la modalità di generazione di codice per loro. Per altre informazioni, vedere [Dynamic Source Code Generation and Compilation](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
- [Procedura: Creare un controllo di Windows Form che sfrutta i vantaggi della funzionalità Design-Time](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))
- [Estensione del supporto in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Finestre di progettazione personalizzate](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h51z5c0x(v=vs.120))
