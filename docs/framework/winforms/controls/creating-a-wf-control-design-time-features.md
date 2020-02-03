---
title: Creare un controllo che sfrutta i vantaggi delle funzionalità della fase di progettazione di Visual Studio
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7166b4203c54ab31f1d929c85cf1e6481ff120f8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744071"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a>Procedura dettagliata: creare un controllo che sfrutti le funzionalità della fase di progettazione

Per migliorare l'esperienza in fase di progettazione per un controllo personalizzato, è possibile creare una finestra di progettazione personalizzata associata.

Questo articolo illustra come creare una finestra di progettazione personalizzata per un controllo personalizzato. Verrà implementato un tipo di `MarqueeControl` e una classe della finestra di progettazione associata denominata `MarqueeControlRootDesigner`.

Il tipo di `MarqueeControl` implementa una visualizzazione simile a un Marquee del teatro con luci animate e testo lampeggiante.

La finestra di progettazione per questo controllo interagisce con l'ambiente di progettazione per offrire un'esperienza di progettazione personalizzata. Con la finestra di progettazione personalizzata è possibile assemblare un'implementazione di `MarqueeControl` personalizzata con luci animate e testo lampeggiante in molte combinazioni. È possibile utilizzare il controllo assemblato in un form come qualsiasi altro controllo Windows Forms.

Al termine di questa procedura dettagliata, il controllo personalizzato sarà simile al seguente:

![L'app che visualizza un testo che pronuncia testo e un pulsante di avvio e di arresto.](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

Per il listato di codice completo, vedere [procedura: creare un controllo Windows Forms che sfrutta le funzionalità della fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-project"></a>Creare il progetto

Il primo passaggio consiste nel creare il progetto dell'applicazione. Questo progetto verrà usato per compilare l'applicazione che ospita il controllo personalizzato.

In Visual Studio creare un nuovo progetto di applicazione Windows Forms e denominarlo **MarqueeControlTest**.

## <a name="create-the-control-library-project"></a>Creare il progetto di libreria di controlli

1. Aggiungere un progetto libreria di controlli Windows Forms alla soluzione. Denominare il progetto **MarqueeControlLibrary**.

2. Utilizzando **Esplora soluzioni**, eliminare il controllo predefinito del progetto eliminando il file di origine denominato "UserControl1.cs" o "UserControl1. vb", a seconda del linguaggio scelto.

3. Aggiungere un nuovo elemento <xref:System.Windows.Forms.UserControl> al progetto `MarqueeControlLibrary`. Assegnare al nuovo file di origine un nome di base di **MarqueeControl**.

4. Utilizzando **Esplora soluzioni**, creare una nuova cartella nel progetto `MarqueeControlLibrary`.

5. Fare clic con il pulsante destro del mouse sulla cartella **progettazione** e aggiungere una nuova classe. Denominarlo **MarqueeControlRootDesigner**.

6. È necessario usare i tipi dall'assembly System. Design, quindi aggiungere questo riferimento al progetto `MarqueeControlLibrary`.

## <a name="reference-the-custom-control-project"></a>Fare riferimento al progetto di controllo personalizzato

Si userà il progetto `MarqueeControlTest` per testare il controllo personalizzato. Il progetto di test diventerà in grado di riconoscere il controllo personalizzato quando si aggiunge un riferimento al progetto all'assembly `MarqueeControlLibrary`.

Nel progetto `MarqueeControlTest` aggiungere un riferimento al progetto nell'assembly `MarqueeControlLibrary`. Assicurarsi di usare la scheda **progetti** nella finestra di dialogo **Aggiungi riferimento anziché fare** riferimento direttamente all'assembly `MarqueeControlLibrary`.

## <a name="define-a-custom-control-and-its-custom-designer"></a>Definire un controllo personalizzato e la relativa finestra di progettazione personalizzata

Il controllo personalizzato deriverà dalla classe <xref:System.Windows.Forms.UserControl>. Ciò consente al controllo di contenere altri controlli e offre al controllo una grande quantità di funzionalità predefinite.

Al controllo personalizzato verrà associata una finestra di progettazione personalizzata. Questo consente di creare un'esperienza di progettazione univoca personalizzata in modo specifico per il controllo personalizzato.

Il controllo viene associato alla relativa finestra di progettazione tramite la classe <xref:System.ComponentModel.DesignerAttribute>. Poiché si sta sviluppando l'intero comportamento in fase di progettazione del controllo personalizzato, la finestra di progettazione personalizzata implementerà l'interfaccia <xref:System.ComponentModel.Design.IRootDesigner>.

### <a name="to-define-a-custom-control-and-its-custom-designer"></a>Per definire un controllo personalizzato e la relativa finestra di progettazione personalizzata

1. Aprire il file di origine `MarqueeControl` nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. Aggiungere la <xref:System.ComponentModel.DesignerAttribute> alla dichiarazione della classe `MarqueeControl`. Il controllo personalizzato verrà associato alla relativa finestra di progettazione.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. Aprire il file di origine `MarqueeControlRootDesigner` nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. Modificare la dichiarazione di `MarqueeControlRootDesigner` per ereditare dalla classe <xref:System.Windows.Forms.Design.DocumentDesigner>. Applicare la <xref:System.ComponentModel.ToolboxItemFilterAttribute> per specificare l'interazione della finestra di progettazione con la **casella degli strumenti**.

   > [!NOTE]
   > La definizione per la classe `MarqueeControlRootDesigner` è stata racchiusa in uno spazio dei nomi denominato MarqueeControlLibrary. Design. Questa dichiarazione posiziona la finestra di progettazione in uno spazio dei nomi speciale riservato ai tipi correlati alla progettazione.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. Definire il costruttore per la classe `MarqueeControlRootDesigner`. Inserire un'istruzione <xref:System.Diagnostics.Trace.WriteLine%2A> nel corpo del costruttore. Questa operazione sarà utile per il debug.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a>Creare un'istanza del controllo personalizzato

1. Aggiungere un nuovo elemento <xref:System.Windows.Forms.UserControl> al progetto `MarqueeControlTest`. Assegnare al nuovo file di origine un nome di base di **DemoMarqueeControl**.

2. Aprire il file di `DemoMarqueeControl` nell' **editor di codice**. Nella parte superiore del file importare lo spazio dei nomi `MarqueeControlLibrary`:

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. Modificare la dichiarazione di `DemoMarqueeControl` per ereditare dalla classe `MarqueeControl`.

4. Compilazione del progetto.

5. Aprire Form1 nella Progettazione Windows Form.

6. Individuare la scheda **Componenti MarqueeControlTest** nella **casella degli strumenti** e aprirla. Trascinare un `DemoMarqueeControl` dalla **casella degli strumenti** nel form.

7. Compilazione del progetto.

## <a name="set-up-the-project-for-design-time-debugging"></a>Configurare il progetto per il debug in fase di progettazione

Quando si sviluppa un'esperienza della fase di progettazione personalizzata, sarà necessario eseguire il debug dei controlli e dei componenti. Esiste un modo semplice per configurare il progetto per consentire il debug in fase di progettazione. Per ulteriori informazioni, vedere [procedura dettagliata: debug di controlli di Windows Forms personalizzati in fase di progettazione](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).

1. Fare clic con il pulsante destro del mouse sul progetto `MarqueeControlLibrary` e scegliere **Proprietà**.

2. Nella finestra di dialogo **pagine delle proprietà di MarqueeControlLibrary** selezionare la pagina **debug** .

3. Nella sezione **azione di avvio** selezionare **Avvia programma esterno**. Si eseguirà il debug di un'istanza separata di Visual Studio, quindi fare clic sui puntini di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante Finestra Proprietà di Visual Studio](./media/visual-studio-ellipsis-button.png)) per cercare l'IDE di Visual Studio. Il nome del file eseguibile è devenv. exe e, se è stato installato nel percorso predefinito, il percorso è *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\\\<edition > \Common7\IDE\devenv.exe*.

4. Fare clic su **OK** per chiudere la finestra di dialogo.

5. Fare clic con il pulsante destro del mouse sul progetto MarqueeControlLibrary e selezionare **Imposta come progetto di avvio** per abilitare questa configurazione di debug.

## <a name="checkpoint"></a>Punto di controllo

A questo punto è possibile eseguire il debug del comportamento in fase di progettazione del controllo personalizzato. Una volta stabilito che l'ambiente di debug è configurato correttamente, si verificherà l'associazione tra il controllo personalizzato e la finestra di progettazione personalizzata.

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>Per testare l'ambiente di debug e l'associazione della finestra di progettazione

1. Aprire il file di origine MarqueeControlRootDesigner nell' **editor di codice** e inserire un punto di interruzione nell'istruzione <xref:System.Diagnostics.Trace.WriteLine%2A>.

2. Premere **F5** per avviare la sessione di debug.

   Viene creata una nuova istanza di Visual Studio.

3. Nella nuova istanza di Visual Studio aprire la soluzione MarqueeControlTest. È possibile trovare facilmente la soluzione selezionando **progetti recenti** dal menu **file** . Il file della soluzione MarqueeControlTest. sln verrà elencato come file usato più di recente.

4. Aprire il `DemoMarqueeControl` nella finestra di progettazione.

   L'istanza di debug di Visual Studio ottiene lo stato attivo e l'esecuzione si arresta in corrispondenza del punto di interruzione. Premere **F5** per continuare la sessione di debug.

A questo punto, è possibile sviluppare ed eseguire il debug del controllo personalizzato e della finestra di progettazione personalizzata associata. Il resto di questo articolo è incentrato sui dettagli dell'implementazione delle funzionalità del controllo e della finestra di progettazione.

## <a name="implement-the-custom-control"></a>Implementare il controllo personalizzato

Il `MarqueeControl` è un <xref:System.Windows.Forms.UserControl> con un po' di personalizzazione. Espone due metodi: `Start`, che avvia l'animazione Marquee e `Stop`, che interrompe l'animazione. Poiché il `MarqueeControl` contiene controlli figlio che implementano l'interfaccia `IMarqueeWidget`, `Start` e `Stop` enumerano ogni controllo figlio e chiamano rispettivamente i metodi `StartMarquee` e `StopMarquee` in ogni controllo figlio che implementa `IMarqueeWidget`.

L'aspetto dei controlli `MarqueeBorder` e `MarqueeText` dipende dal layout. `MarqueeControl` esegue l'override del metodo <xref:System.Windows.Forms.Control.OnLayout%2A> e chiama <xref:System.Windows.Forms.Control.PerformLayout%2A> sui controlli figlio di questo tipo.

Questo è l'ambito delle personalizzazioni del `MarqueeControl`. Le funzionalità della fase di esecuzione vengono implementate dai controlli `MarqueeBorder` e `MarqueeText` e le funzionalità della fase di progettazione vengono implementate dalle classi `MarqueeBorderDesigner` e `MarqueeControlRootDesigner`.

### <a name="to-implement-your-custom-control"></a>Per implementare il controllo personalizzato

1. Aprire il file di origine `MarqueeControl` nell' **editor di codice**. Implementare i metodi `Start` e `Stop`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. Eseguire l'override del metodo <xref:System.Windows.Forms.Control.OnLayout%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a>Creare un controllo figlio per il controllo personalizzato

Nel `MarqueeControl` vengono ospitati due tipi di controllo figlio: il controllo `MarqueeBorder` e il controllo `MarqueeText`.

- `MarqueeBorder`: questo controllo disegna un bordo di "luci" intorno ai bordi. Le spie lampeggiano in sequenza, quindi sembrano spostarsi intorno al bordo. La velocità con cui lampeggia la luce viene controllata da una proprietà denominata `UpdatePeriod`. Diverse altre proprietà personalizzate determinano altri aspetti dell'aspetto del controllo. Due metodi, denominati `StartMarquee` e `StopMarquee`, controllano quando l'animazione viene avviata e arrestata.

- `MarqueeText`: questo controllo disegna una stringa lampeggiante. Analogamente al controllo `MarqueeBorder`, la velocità di lampeggio del testo viene controllata dalla proprietà `UpdatePeriod`. Il controllo `MarqueeText` dispone anche dei metodi `StartMarquee` e `StopMarquee` in comune con il controllo `MarqueeBorder`.

In fase di progettazione, il `MarqueeControlRootDesigner` consente l'aggiunta di questi due tipi di controllo a una `MarqueeControl` in qualsiasi combinazione.

Le funzionalità comuni dei due controlli vengono fattorizzate in un'interfaccia denominata `IMarqueeWidget`. Ciò consente all'`MarqueeControl` di individuare tutti i controlli figlio correlati a Marquee e di offrire loro un trattamento speciale.

Per implementare la funzionalità di animazione periodica, si utilizzeranno <xref:System.ComponentModel.BackgroundWorker> oggetti dello spazio dei nomi <xref:System.ComponentModel?displayProperty=nameWithType>. È possibile usare gli oggetti <xref:System.Windows.Forms.Timer>, ma quando sono presenti molti `IMarqueeWidget` oggetti, il singolo thread dell'interfaccia utente potrebbe non essere in grado di rimanere al passo con l'animazione.

### <a name="to-create-a-child-control-for-your-custom-control"></a>Per creare un controllo figlio per il controllo personalizzato

1. Aggiungere un nuovo elemento di classe al progetto `MarqueeControlLibrary`. Assegnare al nuovo file di origine il nome di base "IMarqueeWidget".

2. Aprire il file di origine `IMarqueeWidget` nell' **editor di codice** e modificare la dichiarazione da `class` a `interface`:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. Aggiungere il codice seguente all'interfaccia `IMarqueeWidget` per esporre due metodi e una proprietà che modificano l'animazione Marquee:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. Aggiungere un nuovo elemento di **controllo personalizzato** al progetto `MarqueeControlLibrary`. Assegnare al nuovo file di origine il nome di base "MarqueeText".

5. Trascinare un componente <xref:System.ComponentModel.BackgroundWorker> dalla **casella degli strumenti** nel controllo `MarqueeText`. Questo componente consente all'`MarqueeText` controllo di aggiornarsi in modo asincrono.

6. Nella finestra **Proprietà** impostare le proprietà `WorkerReportsProgress` e <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> del componente <xref:System.ComponentModel.BackgroundWorker> su **true**. Queste impostazioni consentono al componente <xref:System.ComponentModel.BackgroundWorker> di generare periodicamente l'evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> e di annullare gli aggiornamenti asincroni.

   Per ulteriori informazioni, vedere [BackgroundWorker Component](backgroundworker-component.md).

7. Aprire il file di origine `MarqueeText` nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. Modificare la dichiarazione di `MarqueeText` in modo da ereditare da <xref:System.Windows.Forms.Label> e implementare l'interfaccia `IMarqueeWidget`:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. Dichiarare le variabili di istanza che corrispondono alle proprietà esposte e inizializzarle nel costruttore. Il campo `isLit` determina se il testo deve essere disegnato nel colore specificato dalla proprietà `LightColor`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. Implementare l'interfaccia `IMarqueeWidget`.

    I metodi `StartMarquee` e `StopMarquee` richiamano i metodi <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> e <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> del componente <xref:System.ComponentModel.BackgroundWorker> per avviare e arrestare l'animazione.

    Gli attributi <xref:System.ComponentModel.CategoryAttribute.Category%2A> e <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> vengono applicati alla proprietà `UpdatePeriod` in modo che venga visualizzata in una sezione personalizzata della Finestra Proprietà denominata "Marquee".

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. Implementare le funzioni di accesso alle proprietà. Si esporrà due proprietà ai client: `LightColor` e `DarkColor`. Gli attributi <xref:System.ComponentModel.CategoryAttribute.Category%2A> e <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> vengono applicati a queste proprietà, quindi le proprietà vengono visualizzate in una sezione personalizzata del Finestra Proprietà denominato "Marquee".

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. Implementare i gestori per gli eventi <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> del componente <xref:System.ComponentModel.BackgroundWorker>.

    Il gestore dell'evento <xref:System.ComponentModel.BackgroundWorker.DoWork> dorme per il numero di millisecondi specificato da `UpdatePeriod` quindi genera l'evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>, fino a quando il codice non interrompe l'animazione chiamando <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.

    Il gestore dell'evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> alterna il testo tra lo stato chiaro e scuro per dare l'impressione di lampeggiare.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. Eseguire l'override del metodo <xref:System.Windows.Forms.Control.OnPaint%2A> per abilitare l'animazione.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. Premere **F6** per compilare la soluzione.

## <a name="create-the-marqueeborder-child-control"></a>Creare il controllo figlio MarqueeBorder

Il controllo `MarqueeBorder` è leggermente più sofisticato rispetto al controllo `MarqueeText`. Dispone di più proprietà e l'animazione nel metodo <xref:System.Windows.Forms.Control.OnPaint%2A> è più complessa. In linea di base, è molto simile al controllo `MarqueeText`.

Poiché il controllo `MarqueeBorder` può avere controlli figlio, deve essere in grado di riconoscere <xref:System.Windows.Forms.Control.Layout> eventi.

### <a name="to-create-the-marqueeborder-control"></a>Per creare il controllo MarqueeBorder

1. Aggiungere un nuovo elemento di **controllo personalizzato** al progetto `MarqueeControlLibrary`. Assegnare al nuovo file di origine il nome di base "MarqueeBorder".

2. Trascinare un componente <xref:System.ComponentModel.BackgroundWorker> dalla **casella degli strumenti** nel controllo `MarqueeBorder`. Questo componente consente all'`MarqueeBorder` controllo di aggiornarsi in modo asincrono.

3. Nella finestra **Proprietà** impostare le proprietà `WorkerReportsProgress` e <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> del componente <xref:System.ComponentModel.BackgroundWorker> su **true**. Queste impostazioni consentono al componente <xref:System.ComponentModel.BackgroundWorker> di generare periodicamente l'evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> e di annullare gli aggiornamenti asincroni. Per ulteriori informazioni, vedere [BackgroundWorker Component](backgroundworker-component.md).

4. Nella finestra **Proprietà** selezionare il pulsante **eventi** . Alleghi i gestori per gli eventi <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>.

5. Aprire il file di origine `MarqueeBorder` nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. Modificare la dichiarazione di `MarqueeBorder` in modo da ereditare da <xref:System.Windows.Forms.Panel> e implementare l'interfaccia `IMarqueeWidget`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. Dichiarare due enumerazioni per la gestione dello stato del controllo `MarqueeBorder`: `MarqueeSpinDirection`, che determina la direzione in cui le luci "ruotano" intorno al bordo e `MarqueeLightShape`, che determina la forma delle luci (quadrati o circolari). Inserire queste dichiarazioni prima della dichiarazione della classe `MarqueeBorder`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. Dichiarare le variabili di istanza che corrispondono alle proprietà esposte e inizializzarle nel costruttore.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. Implementare l'interfaccia `IMarqueeWidget`.

    I metodi `StartMarquee` e `StopMarquee` richiamano i metodi <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> e <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> del componente <xref:System.ComponentModel.BackgroundWorker> per avviare e arrestare l'animazione.

    Poiché il controllo `MarqueeBorder` può contenere controlli figlio, il metodo `StartMarquee` enumera tutti i controlli figlio e chiama `StartMarquee` su quelli che implementano `IMarqueeWidget`. Il metodo `StopMarquee` ha un'implementazione simile.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. Implementare le funzioni di accesso alle proprietà. Il controllo `MarqueeBorder` dispone di diverse proprietà per controllarne l'aspetto.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. Implementare i gestori per gli eventi <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> del componente <xref:System.ComponentModel.BackgroundWorker>.

    Il gestore dell'evento <xref:System.ComponentModel.BackgroundWorker.DoWork> dorme per il numero di millisecondi specificato da `UpdatePeriod` quindi genera l'evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>, fino a quando il codice non interrompe l'animazione chiamando <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.

    Il gestore dell'evento <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> incrementa la posizione della luce "base", da cui viene determinato lo stato chiaro/scuro degli altri indicatori e chiama il metodo <xref:System.Windows.Forms.Control.Refresh%2A> per fare in modo che il controllo venga ridisegnato.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. Implementare i metodi helper `IsLit` e `DrawLight`.

    Il metodo `IsLit` determina il colore di una luce in una determinata posizione. Le luci con "lit" vengono disegnate nel colore specificato dalla proprietà `LightColor` e quelle "scure" vengono disegnate nel colore specificato dalla proprietà `DarkColor`.

    Il metodo `DrawLight` disegna una luce usando il colore, la forma e la posizione appropriati.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. Eseguire l'override dei metodi <xref:System.Windows.Forms.Control.OnLayout%2A> e <xref:System.Windows.Forms.Control.OnPaint%2A>.

    Il metodo <xref:System.Windows.Forms.Control.OnPaint%2A> disegna le luci lungo i bordi del controllo `MarqueeBorder`.

    Poiché il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo dipende dalle dimensioni del controllo `MarqueeBorder`, è necessario chiamarlo ogni volta che viene modificato il layout. A tale scopo, eseguire l'override <xref:System.Windows.Forms.Control.OnLayout%2A> e chiamare <xref:System.Windows.Forms.Control.Refresh%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a>Creare una finestra di progettazione personalizzata per nascondere e filtrare le proprietà

La classe `MarqueeControlRootDesigner` fornisce l'implementazione per la finestra di progettazione radice. Oltre a questa finestra di progettazione, che opera sulla `MarqueeControl`, sarà necessaria una finestra di progettazione personalizzata associata in modo specifico al controllo `MarqueeBorder`. Questa finestra di progettazione fornisce un comportamento personalizzato appropriato nel contesto della finestra di progettazione radice personalizzata.

In particolare, il `MarqueeBorderDesigner` "Shadow" e filtrare determinate proprietà nel controllo `MarqueeBorder`, modificando l'interazione con l'ambiente di progettazione.

L'intercettazione delle chiamate alla funzione di accesso delle proprietà di un componente è nota come "shadowing". Consente a una finestra di progettazione di tenere traccia del valore impostato dall'utente e, facoltativamente, di passare il valore al componente in fase di progettazione.

Per questo esempio, le proprietà <xref:System.Windows.Forms.Control.Visible%2A> e <xref:System.Windows.Forms.Control.Enabled%2A> verranno nascoste dal `MarqueeBorderDesigner`, evitando che l'utente renda invisibile o disabilitato il controllo `MarqueeBorder` durante la fase di progettazione.

Le finestre di progettazione possono inoltre aggiungere e rimuovere proprietà. Per questo esempio, la proprietà <xref:System.Windows.Forms.Control.Padding%2A> verrà rimossa in fase di progettazione, perché il controllo `MarqueeBorder` imposta a livello di codice la spaziatura interna in base alla dimensione delle luci specificate dalla proprietà `LightSize`.

La classe base per `MarqueeBorderDesigner` è <xref:System.ComponentModel.Design.ComponentDesigner>, che include metodi che possono modificare gli attributi, le proprietà e gli eventi esposti da un controllo in fase di progettazione:

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

Quando si modifica l'interfaccia pubblica di un componente usando questi metodi, attenersi alle regole seguenti:

- Aggiungere o rimuovere elementi solo nei metodi di `PreFilter`

- Modificare gli elementi esistenti solo nei metodi di `PostFilter`

- Chiamare sempre prima l'implementazione di base nei metodi `PreFilter`

- Chiamare sempre l'implementazione di base per ultima nei metodi `PostFilter`

Rispettando queste regole si garantisce che tutte le finestre di progettazione nell'ambiente in fase di progettazione dispongano di una visualizzazione coerente di tutti i componenti progettati.

La classe <xref:System.ComponentModel.Design.ComponentDesigner> fornisce un dizionario per la gestione dei valori delle proprietà nascoste, che consente di evitare la necessità di creare variabili di istanza specifiche.

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>Per creare una finestra di progettazione personalizzata per nascondere e filtrare le proprietà

1. Fare clic con il pulsante destro del mouse sulla cartella **progettazione** e aggiungere una nuova classe. Assegnare al file di origine un nome di base di **MarqueeBorderDesigner**.

2. Aprire il file di origine MarqueeBorderDesigner nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. Modificare la dichiarazione di `MarqueeBorderDesigner` in modo da ereditare da <xref:System.Windows.Forms.Design.ParentControlDesigner>.

    Poiché il controllo `MarqueeBorder` può contenere controlli figlio, `MarqueeBorderDesigner` eredita da <xref:System.Windows.Forms.Design.ParentControlDesigner>, che gestisce l'interazione padre-figlio.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. Eseguire l'override dell'implementazione di base di <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. Implementare le proprietà <xref:System.Windows.Forms.Control.Enabled%2A> e <xref:System.Windows.Forms.Control.Visible%2A>. Queste implementazioni nascondono le proprietà del controllo.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a>Gestire le modifiche ai componenti

La classe `MarqueeControlRootDesigner` fornisce l'esperienza in fase di progettazione personalizzata per le istanze di `MarqueeControl`. La maggior parte della funzionalità in fase di progettazione viene ereditata dalla classe <xref:System.Windows.Forms.Design.DocumentDesigner>. Il codice implementa due personalizzazioni specifiche, ovvero la gestione delle modifiche dei componenti e l'aggiunta di verbi di progettazione.

Quando gli utenti progettano le istanze di `MarqueeControl`, la finestra di progettazione radice tiene traccia delle modifiche apportate al `MarqueeControl` e ai relativi controlli figlio. L'ambiente in fase di progettazione offre un comodo servizio, <xref:System.ComponentModel.Design.IComponentChangeService>, per tenere traccia delle modifiche apportate allo stato del componente.

Per acquisire un riferimento a questo servizio, è possibile eseguire una query sull'ambiente con il metodo <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>. Se la query ha esito positivo, la finestra di progettazione può allineare un gestore per l'evento <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> ed eseguire tutte le attività necessarie per mantenere uno stato coerente in fase di progettazione.

Nel caso della classe `MarqueeControlRootDesigner`, si chiamerà il metodo <xref:System.Windows.Forms.Control.Refresh%2A> per ogni `IMarqueeWidget` oggetto contenuto nel `MarqueeControl`. In questo modo l'oggetto `IMarqueeWidget` verrà ridisegnato in modo appropriato quando vengono modificate le proprietà come <xref:System.Windows.Forms.Control.Size%2A> del padre.

### <a name="to-handle-component-changes"></a>Per gestire le modifiche ai componenti

1. Aprire il file di origine `MarqueeControlRootDesigner` nell' **editor di codice** ed eseguire l'override del metodo <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>. Chiamare l'implementazione di base di <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> ed eseguire una query per l'<xref:System.ComponentModel.Design.IComponentChangeService>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. Implementare il gestore dell'evento <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>. Testare il tipo del componente di invio e, se si tratta di un `IMarqueeWidget`, chiamare il relativo metodo <xref:System.Windows.Forms.Control.Refresh%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a>Aggiungere verbi di progettazione alla finestra di progettazione personalizzata

Un verbo di progettazione è un comando di menu collegato a un gestore evento. I verbi della finestra di progettazione vengono aggiunti al menu di scelta rapida di un componente in fase di progettazione. Per altre informazioni, vedere <xref:System.ComponentModel.Design.DesignerVerb>.

Si aggiungeranno due verbi di progettazione alle finestre di progettazione: **Esegui test** e **Interrompi test**. Questi verbi consentiranno di visualizzare il comportamento della fase di esecuzione del `MarqueeControl` in fase di progettazione. Questi verbi verranno aggiunti al `MarqueeControlRootDesigner`.

Quando viene richiamato **Esegui test** , il gestore dell'evento verb chiamerà il metodo `StartMarquee` sul `MarqueeControl`. Quando **stop test** viene richiamato, il gestore dell'evento verb chiamerà il metodo `StopMarquee` sul `MarqueeControl`. L'implementazione dei metodi `StartMarquee` e `StopMarquee` chiama questi metodi sui controlli contenuti che implementano `IMarqueeWidget`, quindi anche tutti i controlli `IMarqueeWidget` contenuti parteciperanno al test.

### <a name="to-add-designer-verbs-to-your-custom-designers"></a>Per aggiungere verbi di progettazione alle finestre di progettazione personalizzate

1. Nella classe `MarqueeControlRootDesigner` aggiungere i gestori eventi denominati `OnVerbRunTest` e `OnVerbStopTest`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. Connettere questi gestori eventi ai verbi della finestra di progettazione corrispondente. `MarqueeControlRootDesigner` eredita una <xref:System.ComponentModel.Design.DesignerVerbCollection> dalla relativa classe base. Si creeranno due nuovi oggetti <xref:System.ComponentModel.Design.DesignerVerb> e li si aggiungeranno a questa raccolta nel metodo <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a>Creare un oggetto UITypeEditor personalizzato

Quando si crea un'esperienza di progettazione personalizzata per gli utenti, è spesso consigliabile creare un'interazione personalizzata con l'Finestra Proprietà. A tale scopo, è possibile creare un <xref:System.Drawing.Design.UITypeEditor>.

Il controllo `MarqueeBorder` espone diverse proprietà nell'Finestra Proprietà. Due di queste proprietà, `MarqueeSpinDirection` e `MarqueeLightShape` sono rappresentate dalle enumerazioni. Per illustrare l'uso di un editor di tipi dell'interfaccia utente, la proprietà `MarqueeLightShape` avrà una classe <xref:System.Drawing.Design.UITypeEditor> associata.

### <a name="to-create-a-custom-ui-type-editor"></a>Per creare un editor di tipo personalizzato dell'interfaccia utente

1. Aprire il file di origine `MarqueeBorder` nell' **editor di codice**.

2. Nella definizione della classe `MarqueeBorder` dichiarare una classe denominata `LightShapeEditor` che deriva da <xref:System.Drawing.Design.UITypeEditor>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. Dichiarare una variabile di istanza <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> denominata `editorService`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. Eseguire l'override del metodo <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> . Questa implementazione restituisce <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, che indica all'ambiente di progettazione come visualizzare l'`LightShapeEditor`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. Eseguire l'override del metodo <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> . Questa implementazione esegue una query nell'ambiente di progettazione per un oggetto <xref:System.Windows.Forms.Design.IWindowsFormsEditorService>. Se ha esito positivo, viene creato un `LightShapeSelectionControl`. Viene richiamato il metodo <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> per avviare l'`LightShapeEditor`. Il valore restituito da questa chiamata viene restituito all'ambiente di progettazione.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a>Creare un controllo di visualizzazione per l'oggetto UITypeEditor personalizzato

La proprietà `MarqueeLightShape` supporta due tipi di forme chiare: `Square` e `Circle`. Si creerà un controllo personalizzato usato esclusivamente per visualizzare graficamente questi valori nel Finestra Proprietà. Questo controllo personalizzato verrà usato dal <xref:System.Drawing.Design.UITypeEditor> per interagire con l'Finestra Proprietà.

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>Per creare un controllo di visualizzazione per l'editor di tipo dell'interfaccia utente personalizzata

1. Aggiungere un nuovo elemento <xref:System.Windows.Forms.UserControl> al progetto `MarqueeControlLibrary`. Assegnare al nuovo file di origine un nome di base di **LightShapeSelectionControl**.

2. Trascinare due controlli <xref:System.Windows.Forms.Panel> dalla **casella degli strumenti** nel `LightShapeSelectionControl`. Assegnare loro un nome `squarePanel` e `circlePanel`. Disponerli affiancati. Impostare la proprietà <xref:System.Windows.Forms.Control.Size%2A> di entrambi i controlli <xref:System.Windows.Forms.Panel> su **(60, 60)** . Impostare la proprietà <xref:System.Windows.Forms.Control.Location%2A> del controllo `squarePanel` su **(8, 10)** . Impostare la proprietà <xref:System.Windows.Forms.Control.Location%2A> del controllo `circlePanel` su **(80, 10)** . Infine, impostare la proprietà <xref:System.Windows.Forms.Control.Size%2A> della `LightShapeSelectionControl` su **(150, 80)** .

3. Aprire il file di origine `LightShapeSelectionControl` nell' **editor di codice**. Nella parte superiore del file importare lo spazio dei nomi <xref:System.Windows.Forms.Design?displayProperty=nameWithType>:

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. Implementare <xref:System.Windows.Forms.Control.Click> gestori eventi per i controlli `squarePanel` e `circlePanel`. Questi metodi richiamano <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> per terminare la sessione di modifica <xref:System.Drawing.Design.UITypeEditor> personalizzata.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. Dichiarare una variabile di istanza <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> denominata `editorService`.

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. Dichiarare una variabile di istanza `MarqueeLightShape` denominata `lightShapeValue`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. Nel costruttore di `LightShapeSelectionControl`, alleghi i gestori eventi <xref:System.Windows.Forms.Control.Click> agli eventi <xref:System.Windows.Forms.Control.Click> `squarePanel` e `circlePanel` Controls. Definire anche un overload del costruttore che assegna il valore `MarqueeLightShape` dall'ambiente di progettazione al campo `lightShapeValue`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. Nel metodo <xref:System.ComponentModel.Component.Dispose%2A> scollegare i gestori eventi di <xref:System.Windows.Forms.Control.Click>.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**. Aprire il file LightShapeSelectionControl.Designer.cs o LightShapeSelectionControl. designer. vb e rimuovere la definizione predefinita del metodo <xref:System.ComponentModel.Component.Dispose%2A>.

10. Implementare la proprietà `LightShape`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. Eseguire l'override del metodo <xref:System.Windows.Forms.Control.OnPaint%2A> . Questa implementazione trarrà un quadrato e un cerchio pieni. Verrà inoltre evidenziato il valore selezionato disegnando un bordo intorno a una forma o l'altro.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a>Testare il controllo personalizzato nella finestra di progettazione

A questo punto, è possibile compilare il progetto `MarqueeControlLibrary`. Testare l'implementazione creando un controllo che eredita dalla classe `MarqueeControl` e usandolo in un form.

### <a name="to-create-a-custom-marqueecontrol-implementation"></a>Per creare un'implementazione MarqueeControl personalizzata

1. Aprire `DemoMarqueeControl` in Progettazione Windows Form. In questo modo viene creata un'istanza del tipo di `DemoMarqueeControl` e viene visualizzata in un'istanza del tipo di `MarqueeControlRootDesigner`.

2. Nella **casella degli strumenti**aprire la scheda **componenti di MarqueeControlLibrary** . Si noterà che i controlli `MarqueeBorder` e `MarqueeText` sono disponibili per la selezione.

3. Trascinare un'istanza del controllo `MarqueeBorder` nell'area di progettazione del `DemoMarqueeControl`. Ancorare questo controllo `MarqueeBorder` al controllo padre.

4. Trascinare un'istanza del controllo `MarqueeText` nell'area di progettazione del `DemoMarqueeControl`.

5. Compila la soluzione.

6. Fare clic con il pulsante destro del mouse sul `DemoMarqueeControl` e scegliere l'opzione **Esegui test** dal menu di scelta rapida per avviare l'animazione. Fare clic su **Interrompi test** per arrestare l'animazione.

7. Aprire **Form1** nella visualizzazione Progettazione.

8. Inserire due controlli <xref:System.Windows.Forms.Button> nel form. Assegnare loro un nome `startButton` e `stopButton`e modificare i valori delle proprietà <xref:System.Windows.Forms.Control.Text%2A> rispettivamente per **avviare** e **arrestare**.

9. Implementare <xref:System.Windows.Forms.Control.Click> gestori eventi per entrambi i controlli <xref:System.Windows.Forms.Button>.

10. Nella **casella degli strumenti**aprire la scheda **componenti di MarqueeControlTest** . Il `DemoMarqueeControl` sarà disponibile per la selezione.

11. Trascinare un'istanza di `DemoMarqueeControl` nell'area di progettazione **Form1** .

12. Nei gestori eventi <xref:System.Windows.Forms.Control.Click> richiamare i metodi `Start` e `Stop` sul `DemoMarqueeControl`.

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

13. Impostare il progetto `MarqueeControlTest` come progetto di avvio ed eseguirlo. Viene visualizzato il modulo che Visualizza il `DemoMarqueeControl`. Selezionare il pulsante **Avvia** per avviare l'animazione. Si noterà che il testo lampeggia e le luci si spostano attorno al bordo.

## <a name="next-steps"></a>Passaggi successivi

Il `MarqueeControlLibrary` illustra una semplice implementazione di controlli personalizzati e finestre di progettazione associate. Questo esempio può essere reso più sofisticato in diversi modi:

- Modificare i valori delle proprietà per il `DemoMarqueeControl` nella finestra di progettazione. Aggiungere altri controlli `MarqueBorder` e ancorarli all'interno delle istanze padre per creare un effetto annidato. Provare a usare impostazioni diverse per la `UpdatePeriod` e le proprietà correlate alla luce.

- Creare implementazioni personalizzate di `IMarqueeWidget`. È possibile, ad esempio, creare un segno "neon" lampeggiante o un segno animato con più immagini.

- Personalizzare ulteriormente l'esperienza in fase di progettazione. È possibile provare ad ombreggiare più proprietà rispetto a <xref:System.Windows.Forms.Control.Enabled%2A> e <xref:System.Windows.Forms.Control.Visible%2A>ed è possibile aggiungere nuove proprietà. Aggiungere nuovi verbi di progettazione per semplificare attività comuni come l'ancoraggio dei controlli figlio.

- Concedere in licenza il `MarqueeControl`.

- Controllare la modalità di serializzazione dei controlli e il modo in cui viene generato il codice. Per altre informazioni, vedere [generazione e compilazione di codice sorgente dinamico](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
