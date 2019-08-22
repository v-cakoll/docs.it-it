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
ms.openlocfilehash: c8d04725a576c9e24a4b7d4aec1251516a8c544c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666236"
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a>Procedura dettagliata: Creazione di un controllo di Windows Forms che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione

Per migliorare l'esperienza in fase di progettazione per un controllo personalizzato, è possibile creare una finestra di progettazione personalizzata associata.

In questa procedura dettagliata viene illustrato come creare una finestra di progettazione personalizzata per un controllo personalizzato. Verrà implementato un `MarqueeControl` tipo e una classe della finestra di progettazione associata `MarqueeControlRootDesigner`, denominata.

Il `MarqueeControl` tipo implementa una visualizzazione simile a un Marquee del teatro, con luci animate e testo lampeggiante.

La finestra di progettazione per questo controllo interagisce con l'ambiente di progettazione per offrire un'esperienza di progettazione personalizzata. Con la finestra di progettazione personalizzata è possibile assemblare `MarqueeControl` un'implementazione personalizzata con luci animate e testo lampeggiante in molte combinazioni. È possibile utilizzare il controllo assemblato in un form come qualsiasi altro controllo Windows Forms.

Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione del progetto

- Creazione di un progetto libreria di controlli

- Riferimento al progetto di controllo personalizzato

- Definizione di un controllo personalizzato e della relativa finestra di progettazione personalizzata

- Creazione di un'istanza del controllo personalizzato

- Impostazione del progetto per il debug in fase di progettazione

- Implementazione del controllo personalizzato

- Creazione di un controllo figlio per il controllo personalizzato

- Creare il controllo figlio MarqueeBorder

- Creazione di una finestra di progettazione personalizzata per ombreggiare e filtrare le proprietà

- Gestione delle modifiche ai componenti

- Aggiunta di verbi di progettazione alla finestra di progettazione personalizzata

- Creazione di un oggetto UITypeEditor personalizzato

- Test del controllo personalizzato nella finestra di progettazione

Al termine dell'operazione, il controllo personalizzato sarà simile al seguente:

![L'app che visualizza un testo che pronuncia testo e un pulsante di avvio e di arresto.](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

Per il listato di codice completo [, vedere Procedura: Creare un controllo Windows Forms che sfrutta le funzionalità](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))della fase di progettazione.

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario Visual Studio.

## <a name="creating-the-project"></a>Creazione del progetto

Il primo passaggio consiste nel creare il progetto dell'applicazione. Questo progetto verrà usato per compilare l'applicazione che ospita il controllo personalizzato.

Aprire Visual Studio e creare un progetto di applicazione Windows Forms denominato "MarqueeControlTest" (**file** > **nuovo** > **progetto** > **visivo C#**  o **Visual Basic**  >  **Desktop classico** **Applicazione Windows Forms).**  > 

## <a name="creating-a-control-library-project"></a>Creazione di un progetto libreria di controlli

Il passaggio successivo consiste nel creare il progetto di libreria di controlli. Verrà creato un nuovo controllo personalizzato e la relativa finestra di progettazione personalizzata corrispondente.

### <a name="to-create-the-control-library-project"></a>Per creare il progetto di libreria di controlli

1. Aggiungere un progetto libreria di controlli Windows Forms alla soluzione. Denominare il progetto "MarqueeControlLibrary".

2. Utilizzando **Esplora soluzioni**, eliminare il controllo predefinito del progetto eliminando il file di origine denominato "UserControl1.cs" o "UserControl1. vb", a seconda del linguaggio scelto. Per altre informazioni, vedere [Procedura: Rimuovere, eliminare ed escludere elementi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).

3. Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> elemento `MarqueeControlLibrary` al progetto. Assegnare al nuovo file di origine il nome di base "MarqueeControl".

4. Utilizzando **Esplora soluzioni**, creare una nuova cartella nel `MarqueeControlLibrary` progetto. Per altre informazioni, vedere [Procedura: Aggiungere nuovi elementi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))di progetto. Assegnare alla nuova cartella il nome "progettazione".

5. Fare clic con il pulsante destro del mouse sulla cartella **progettazione** e aggiungere una nuova classe. Assegnare al file di origine un nome di base "MarqueeControlRootDesigner".

6. Sarà necessario usare i tipi dall'assembly System. Design, quindi aggiungere questo riferimento al `MarqueeControlLibrary` progetto.

    > [!NOTE]
    > Per usare l'assembly System. Design, il progetto deve avere come destinazione la versione completa del .NET Framework, non il profilo client .NET Framework. Per modificare il Framework di destinazione, [vedere Procedura: Scegliere una versione di .NET Framework di destinazione](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).

## <a name="referencing-the-custom-control-project"></a>Riferimento al progetto di controllo personalizzato

Il `MarqueeControlTest` progetto viene usato per testare il controllo personalizzato. Il progetto di test diventerà in grado di riconoscere il controllo personalizzato quando si aggiunge un `MarqueeControlLibrary` riferimento al progetto all'assembly.

### <a name="to-reference-the-custom-control-project"></a>Per fare riferimento al progetto di controllo personalizzato

- Nel progetto aggiungere un riferimento `MarqueeControlLibrary` al progetto all'assembly. `MarqueeControlTest` Assicurarsi di usare la scheda **progetti** nella finestra di dialogo **Aggiungi riferimento anziché fare** riferimento direttamente all' `MarqueeControlLibrary` assembly.

## <a name="defining-a-custom-control-and-its-custom-designer"></a>Definizione di un controllo personalizzato e della relativa finestra di progettazione personalizzata
 Il controllo personalizzato deriverà dalla <xref:System.Windows.Forms.UserControl> classe. Ciò consente al controllo di contenere altri controlli e offre al controllo una grande quantità di funzionalità predefinite.

 Al controllo personalizzato verrà associata una finestra di progettazione personalizzata. Questo consente di creare un'esperienza di progettazione univoca personalizzata in modo specifico per il controllo personalizzato.

 Il controllo viene associato alla relativa finestra di progettazione tramite <xref:System.ComponentModel.DesignerAttribute> la classe. Poiché si sta sviluppando l'intero comportamento in fase di progettazione del controllo personalizzato, l' <xref:System.ComponentModel.Design.IRootDesigner> interfaccia verrà implementata dalla finestra di progettazione personalizzata.

### <a name="to-define-a-custom-control-and-its-custom-designer"></a>Per definire un controllo personalizzato e la relativa finestra di progettazione personalizzata

1. Aprire il `MarqueeControl` file di origine nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. Aggiungere la <xref:System.ComponentModel.DesignerAttribute> `MarqueeControl` alla dichiarazione di classe. Il controllo personalizzato verrà associato alla relativa finestra di progettazione.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. Aprire il `MarqueeControlRootDesigner` file di origine nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. Modificare la dichiarazione di `MarqueeControlRootDesigner` in modo che erediti <xref:System.Windows.Forms.Design.DocumentDesigner> dalla classe. Applicare per specificare l'interazione della finestra di progettazione con la **casella degli strumenti.** <xref:System.ComponentModel.ToolboxItemFilterAttribute>

     **Nota** La definizione `MarqueeControlRootDesigner` della classe è stata racchiusa in uno spazio dei nomi denominato "MarqueeControlLibrary. Design". Questa dichiarazione posiziona la finestra di progettazione in uno spazio dei nomi speciale riservato ai tipi correlati alla progettazione.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. Definire il costruttore per la `MarqueeControlRootDesigner` classe. Inserire un' <xref:System.Diagnostics.Trace.WriteLine%2A> istruzione nel corpo del costruttore. Questa operazione sarà utile a scopo di debug.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="creating-an-instance-of-your-custom-control"></a>Creazione di un'istanza del controllo personalizzato
 Per osservare il comportamento personalizzato in fase di progettazione del controllo, si inserirà un'istanza del controllo nel modulo in `MarqueeControlTest` Project.

### <a name="to-create-an-instance-of-your-custom-control"></a>Per creare un'istanza del controllo personalizzato

1. Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> elemento `MarqueeControlTest` al progetto. Assegnare al nuovo file di origine il nome di base "DemoMarqueeControl".

2. Aprire il `DemoMarqueeControl` file nell' **editor di codice**. Nella parte superiore del file importare lo `MarqueeControlLibrary` spazio dei nomi:

```vb
Imports MarqueeControlLibrary
```

```csharp
using MarqueeControlLibrary;
```

1. Modificare la dichiarazione di `DemoMarqueeControl` in modo che erediti `MarqueeControl` dalla classe.

2. Compilare il progetto.

3. Aprire `Form1` in Progettazione Windows Form.

4. Individuare la scheda **Componenti MarqueeControlTest** nella **casella degli strumenti** e aprirla. Trascinare un `DemoMarqueeControl` oggetto dalla **casella degli strumenti** nel form.

5. Compilare il progetto.

## <a name="setting-up-the-project-for-design-time-debugging"></a>Impostazione del progetto per il debug in fase di progettazione

Quando si sviluppa un'esperienza della fase di progettazione personalizzata, sarà necessario eseguire il debug dei controlli e dei componenti. Esiste un modo semplice per configurare il progetto per consentire il debug in fase di progettazione. Per altre informazioni, vedere [Procedura dettagliata: Debug di controlli di Windows Forms personalizzati in](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)fase di progettazione.

### <a name="to-set-up-the-project-for-design-time-debugging"></a>Per configurare il progetto per il debug in fase di progettazione

1. Fare clic con il `MarqueeControlLibrary` pulsante destro del mouse sul progetto e scegliere **proprietà**.

2. Nella finestra di dialogo "pagine delle proprietà di MarqueeControlLibrary" selezionare la pagina **debug** .

3. Nella sezione **azione di avvio** selezionare **Avvia programma esterno**. Verrà eseguito il debug di un'istanza separata di Visual Studio, quindi fare clic sui![puntini di sospensione (il pulsante con i puntini di sospensione (.](./media/visual-studio-ellipsis-button.png)..) nel pulsante finestra proprietà di Visual Studio.) per cercare l'IDE di Visual Studio. Il nome del file eseguibile è devenv. exe e, se è stato installato nel percorso predefinito, il percorso è%Programmi%\Microsoft Visual Studio 9.0 \ Common7\IDE\devenv.exe.

4. Fare clic su OK per chiudere la finestra di dialogo.

5. Fare clic con il `MarqueeControlLibrary` pulsante destro del mouse sul progetto e scegliere "Imposta come progetto di avvio" per abilitare questa configurazione di debug.

## <a name="checkpoint"></a>Checkpoint

A questo punto è possibile eseguire il debug del comportamento in fase di progettazione del controllo personalizzato. Una volta stabilito che l'ambiente di debug è stato configurato correttamente, verrà eseguito il test dell'associazione tra il controllo personalizzato e la finestra di progettazione personalizzata.

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>Per testare l'ambiente di debug e l'associazione della finestra di progettazione

1. Aprire il `MarqueeControlRootDesigner` file di origine nell' **Editor del codice** e inserire <xref:System.Diagnostics.Trace.WriteLine%2A> un punto di interruzione nell'istruzione.

2. Premere F5 per avviare la sessione di debug. Si noti che viene creata una nuova istanza di Visual Studio.

3. Nella nuova istanza di Visual Studio aprire la soluzione "MarqueeControlTest". È possibile trovare facilmente la soluzione selezionando **progetti recenti** dal menu **file** . Il file di soluzione "MarqueeControlTest. sln" verrà elencato come file usato più di recente.

4. Aprire la `DemoMarqueeControl` nella finestra di progettazione. Si noti che l'istanza di debug di Visual Studio acquisisce lo stato attivo e l'esecuzione si arresta in corrispondenza del punto di interruzione. Premere F5 per continuare la sessione di debug.

A questo punto, è possibile sviluppare ed eseguire il debug del controllo personalizzato e della finestra di progettazione personalizzata associata. Il resto di questa procedura dettagliata si concentrerà sui dettagli dell'implementazione delle funzionalità del controllo e della finestra di progettazione.

## <a name="implementing-your-custom-control"></a>Implementazione del controllo personalizzato

`MarqueeControl` È un<xref:System.Windows.Forms.UserControl> oggetto con un po' di personalizzazione. Espone due metodi: `Start`, che avvia l'animazione Marquee e `Stop`, che interrompe l'animazione. `StartMarquee` `IMarqueeWidget` `StopMarquee` `Stop` `Start` Poiché contiene i controlli figlio che implementano l'interfaccia ed enumerano ogni controllo figlio e chiamano rispettivamente i metodi e in ogni controllo figlio `MarqueeControl` che implementa `IMarqueeWidget`.

`MarqueeBorder` L'aspetto dei controlli e `MarqueeText` dipende dal layout, quindi `MarqueeControl` esegue l'override del metodo <xref:System.Windows.Forms.Control.OnLayout%2A> e chiama <xref:System.Windows.Forms.Control.PerformLayout%2A> i controlli figlio di questo tipo.

Si tratta dell'extent delle `MarqueeControl` personalizzazioni. Le funzionalità della fase di esecuzione sono implementate `MarqueeBorder` dai `MarqueeText` controlli e e le `MarqueeBorderDesigner` funzionalità della fase di progettazione vengono implementate dalle `MarqueeControlRootDesigner` classi e.

### <a name="to-implement-your-custom-control"></a>Per implementare il controllo personalizzato

1. Aprire il `MarqueeControl` file di origine nell' **editor di codice**. Implementare i `Start` metodi `Stop` e.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. Eseguire l'override del metodo <xref:System.Windows.Forms.Control.OnLayout%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="creating-a-child-control-for-your-custom-control"></a>Creazione di un controllo figlio per il controllo personalizzato

Ospiterà due tipi di controllo figlio: il `MarqueeBorder` controllo e il `MarqueeText` controllo. `MarqueeControl`

- `MarqueeBorder`: Questo controllo disegna un bordo di "luci" intorno ai bordi. Le spie lampeggiano in sequenza, quindi sembrano spostarsi intorno al bordo. La velocità con cui lampeggia la luce viene controllata da una proprietà denominata `UpdatePeriod`. Diverse altre proprietà personalizzate determinano altri aspetti dell'aspetto del controllo. Due metodi, denominati `StartMarquee` e `StopMarquee`, controllano quando l'animazione viene avviata e arrestata.

- `MarqueeText`: Questo controllo disegna una stringa lampeggiante. Analogamente `MarqueeBorder` al controllo, la velocità di lampeggio del testo viene controllata `UpdatePeriod` dalla proprietà. Il `MarqueeText` controllo dispone anche dei `StartMarquee` metodi `StopMarquee` e in comune con il `MarqueeBorder` controllo.

In fase di progettazione, `MarqueeControlRootDesigner` consente di aggiungere questi due tipi di controllo a un `MarqueeControl` oggetto in qualsiasi combinazione.

Le funzionalità comuni dei due controlli vengono fattorizzate in un'interfaccia denominata `IMarqueeWidget`. In questo modo `MarqueeControl` , l'oggetto può individuare eventuali controlli figlio correlati a Marquee e assegnare loro un trattamento speciale.

Per implementare la funzionalità di animazione periodica, si <xref:System.ComponentModel.BackgroundWorker> utilizzeranno oggetti <xref:System.ComponentModel?displayProperty=nameWithType> dello spazio dei nomi. È possibile usare <xref:System.Windows.Forms.Timer> gli oggetti, ma quando `IMarqueeWidget` sono presenti molti oggetti, il singolo thread dell'interfaccia utente potrebbe non essere in grado di tenere il passo con l'animazione.

### <a name="to-create-a-child-control-for-your-custom-control"></a>Per creare un controllo figlio per il controllo personalizzato

1. Aggiungere un nuovo elemento di classe al `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine il nome di base "IMarqueeWidget".

2. Aprire il `IMarqueeWidget` file di origine nell' **editor di codice** e modificare la Dichiarazione `class` da `interface`a:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. Aggiungere il codice seguente all' `IMarqueeWidget` interfaccia per esporre due metodi e una proprietà che modificano l'animazione Marquee:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. Aggiungere un nuovo elemento di **controllo personalizzato** al `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine il nome di base "MarqueeText".

5. Trascinare un <xref:System.ComponentModel.BackgroundWorker> componente dalla `MarqueeText` **casella degli strumenti** nel controllo. Questo componente consentirà `MarqueeText` al controllo di aggiornarsi in modo asincrono.

6. Nella <xref:System.ComponentModel.BackgroundWorker> finestra Proprietà impostare le proprietà `WorkerReportsProgress` e <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> del componente su `true`. Queste impostazioni consentono al <xref:System.ComponentModel.BackgroundWorker> componente di generare periodicamente l' <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento e di annullare gli aggiornamenti asincroni. Per ulteriori informazioni, vedere [BackgroundWorker Component](backgroundworker-component.md).

7. Aprire il `MarqueeText` file di origine nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. Modificare la dichiarazione di `MarqueeText` in modo che <xref:System.Windows.Forms.Label> erediti da e per `IMarqueeWidget` implementare l'interfaccia:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. Dichiarare le variabili di istanza che corrispondono alle proprietà esposte e inizializzarle nel costruttore. Il `isLit` campo determina se il testo deve essere disegnato nel colore specificato `LightColor` dalla proprietà.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. Implementare l'interfaccia `IMarqueeWidget`.

    I `StartMarquee` `StopMarquee` metodie<xref:System.ComponentModel.BackgroundWorker> richiamano i metodi <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> e del componente per avviare e arrestare l'animazione. <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>

    Gli <xref:System.ComponentModel.CategoryAttribute.Category%2A> <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>attributie vengono applicati alla ProprietàinmodochevenganovisualizzatiinunasezionepersonalizzatadelfinestraProprietàdenominato"Marquee".`UpdatePeriod`

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. Implementare le funzioni di accesso alle proprietà. Si esporrà due proprietà ai client: `LightColor` e `DarkColor`. Gli <xref:System.ComponentModel.CategoryAttribute.Category%2A> attributi <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> e vengono applicati a queste proprietà, quindi le proprietà vengono visualizzate in una sezione personalizzata del finestra Proprietà denominato "Marquee".

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. Implementare i gestori per <xref:System.ComponentModel.BackgroundWorker> gli eventi <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> del componente.

    Il <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore eventi dorme per il numero di millisecondi specificato da `UpdatePeriod` genera l' <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento, <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>fino a quando il codice non interrompe l'animazione chiamando.

    Il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> gestore eventi alterna il testo tra lo stato chiaro e scuro per dare l'impressione di lampeggiare.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. Eseguire l' <xref:System.Windows.Forms.Control.OnPaint%2A> override del metodo per abilitare l'animazione.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. Premere F6 per compilare la soluzione.

## <a name="create-the-marqueeborder-child-control"></a>Creare il controllo figlio MarqueeBorder

Il `MarqueeBorder` controllo è leggermente più sofisticato `MarqueeText` del controllo. Dispone di più proprietà e l'animazione nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo è più complessa. In linea di base, è molto simile al `MarqueeText` controllo.

Poiché il `MarqueeBorder` controllo può avere controlli figlio, deve essere in grado di <xref:System.Windows.Forms.Control.Layout> riconoscere gli eventi.

### <a name="to-create-the-marqueeborder-control"></a>Per creare il controllo MarqueeBorder

1. Aggiungere un nuovo elemento di **controllo personalizzato** al `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine il nome di base "MarqueeBorder".

2. Trascinare un <xref:System.ComponentModel.BackgroundWorker> componente dalla `MarqueeBorder` **casella degli strumenti** nel controllo. Questo componente consentirà `MarqueeBorder` al controllo di aggiornarsi in modo asincrono.

3. Nella <xref:System.ComponentModel.BackgroundWorker> finestra Proprietà impostare le proprietà `WorkerReportsProgress` e <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> del componente su `true`. Queste impostazioni consentono al <xref:System.ComponentModel.BackgroundWorker> componente di generare periodicamente l' <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento e di annullare gli aggiornamenti asincroni. Per ulteriori informazioni, vedere [BackgroundWorker Component](backgroundworker-component.md).

4. Nella Finestra Proprietà fare clic sul pulsante eventi. Associazione di gestori per gli <xref:System.ComponentModel.BackgroundWorker.DoWork> eventi <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> e.

5. Aprire il `MarqueeBorder` file di origine nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. Modificare la dichiarazione di `MarqueeBorder` in modo che <xref:System.Windows.Forms.Panel> erediti da e per `IMarqueeWidget` implementare l'interfaccia.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. Dichiarare due enumerazioni per la gestione `MarqueeBorder` dello stato del controllo `MarqueeSpinDirection`:, che determina la direzione in cui le luci "ruotano" intorno al bordo `MarqueeLightShape`, e, che determina la forma delle luci (quadrati o circolari). Inserire queste dichiarazioni prima della Dichiarazione `MarqueeBorder` di classe.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. Dichiarare le variabili di istanza che corrispondono alle proprietà esposte e inizializzarle nel costruttore.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. Implementare l'interfaccia `IMarqueeWidget`.

    I `StartMarquee` `StopMarquee` metodie<xref:System.ComponentModel.BackgroundWorker> richiamano i metodi <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> e del componente per avviare e arrestare l'animazione. <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>

    Poiché il `MarqueeBorder` controllo può contenere controlli figlio, il `StartMarquee` metodo enumera tutti i controlli figlio e chiama `StartMarquee` su quelli che implementano `IMarqueeWidget`. Il `StopMarquee` metodo ha un'implementazione simile.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. Implementare le funzioni di accesso alle proprietà. Il `MarqueeBorder` controllo dispone di diverse proprietà per il controllo dell'aspetto.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. Implementare i gestori per <xref:System.ComponentModel.BackgroundWorker> gli eventi <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> del componente.

    Il <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore eventi dorme per il numero di millisecondi specificato da `UpdatePeriod` genera l' <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento, <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>fino a quando il codice non interrompe l'animazione chiamando.

    Il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> gestore eventi incrementa la posizione della luce "base", da cui viene determinato lo stato chiaro/scuro degli altri indicatori e chiama il <xref:System.Windows.Forms.Control.Refresh%2A> metodo per fare in modo che il controllo venga ridisegnato.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. Implementare i metodi helper, `IsLit` e. `DrawLight`

    Il `IsLit` metodo determina il colore di una luce in una determinata posizione. Le luci con "lit" vengono disegnate nel colore specificato dalla `LightColor` proprietà e quelle "scure" vengono disegnate nel colore specificato `DarkColor` dalla proprietà.

    Il `DrawLight` metodo disegna una luce usando il colore, la forma e la posizione appropriati.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. Eseguire l' <xref:System.Windows.Forms.Control.OnLayout%2A> override <xref:System.Windows.Forms.Control.OnPaint%2A> dei metodi e.

    Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo disegna le luci lungo i bordi `MarqueeBorder` del controllo.

    Poiché il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo dipende dalle dimensioni `MarqueeBorder` del controllo, è necessario chiamarlo ogni volta che viene modificato il layout. Per ottenere questo risultato, <xref:System.Windows.Forms.Control.OnLayout%2A> eseguire l' <xref:System.Windows.Forms.Control.Refresh%2A>override di e chiamare.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a>Creazione di una finestra di progettazione personalizzata per ombreggiare e filtrare le proprietà

La `MarqueeControlRootDesigner` classe fornisce l'implementazione per la finestra di progettazione radice. Oltre a questa finestra di progettazione, che opera su `MarqueeControl`, sarà necessaria una finestra di progettazione personalizzata associata in modo specifico al `MarqueeBorder` controllo. Questa finestra di progettazione fornisce un comportamento personalizzato appropriato nel contesto della finestra di progettazione radice personalizzata.

In particolare, `MarqueeBorderDesigner` la funzione "Shadow" e filtra alcune proprietà `MarqueeBorder` del controllo, modificando l'interazione con l'ambiente di progettazione.

L'intercettazione delle chiamate alla funzione di accesso delle proprietà di un componente è nota come "shadowing". Consente a una finestra di progettazione di tenere traccia del valore impostato dall'utente e, facoltativamente, di passare il valore al componente in fase di progettazione.

Per questo esempio, le <xref:System.Windows.Forms.Control.Visible%2A> proprietà <xref:System.Windows.Forms.Control.Enabled%2A> e verranno nascoste da `MarqueeBorderDesigner`, che impedisce all'utente di rendere il `MarqueeBorder` controllo invisibile o disabilitato in fase di progettazione.

Le finestre di progettazione possono inoltre aggiungere e rimuovere proprietà. Per questo esempio, la <xref:System.Windows.Forms.Control.Padding%2A> proprietà verrà rimossa in fase di progettazione, perché `MarqueeBorder` il controllo imposta a livello di codice la spaziatura interna in base alla dimensione delle `LightSize` luci specificate dalla proprietà.

La classe base per `MarqueeBorderDesigner` è <xref:System.ComponentModel.Design.ComponentDesigner>, che dispone di metodi che possono modificare gli attributi, le proprietà e gli eventi esposti da un controllo in fase di progettazione:

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

Quando si modifica l'interfaccia pubblica di un componente usando questi metodi, è necessario attenersi alle regole seguenti:

- Aggiungere o rimuovere elementi solo nei `PreFilter` metodi

- Modificare gli elementi esistenti solo `PostFilter` nei metodi

- Chiamare sempre prima l'implementazione di base nei `PreFilter` metodi

- Chiamare sempre l'implementazione di base per ultima `PostFilter` nei metodi

Rispettando queste regole si garantisce che tutte le finestre di progettazione nell'ambiente in fase di progettazione dispongano di una visualizzazione coerente di tutti i componenti progettati.

La <xref:System.ComponentModel.Design.ComponentDesigner> classe fornisce un dizionario per la gestione dei valori delle proprietà nascoste, che consente di evitare la necessità di creare variabili di istanza specifiche.

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>Per creare una finestra di progettazione personalizzata per nascondere e filtrare le proprietà

1. Fare clic con il pulsante destro del mouse sulla cartella **progettazione** e aggiungere una nuova classe. Assegnare al file di origine un nome di base "MarqueeBorderDesigner".

2. Aprire il `MarqueeBorderDesigner` file di origine nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. Modificare la dichiarazione di `MarqueeBorderDesigner` in modo da <xref:System.Windows.Forms.Design.ParentControlDesigner>ereditare da.

    Poiché il `MarqueeBorder` controllo può contenere controlli figlio, `MarqueeBorderDesigner` eredita da <xref:System.Windows.Forms.Design.ParentControlDesigner>, che gestisce l'interazione padre-figlio.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. Eseguire l'override dell'implementazione <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>di base di.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. Implementare le proprietà <xref:System.Windows.Forms.Control.Enabled%2A> e <xref:System.Windows.Forms.Control.Visible%2A>. Queste implementazioni nascondono le proprietà del controllo.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handling-component-changes"></a>Gestione delle modifiche ai componenti
 La `MarqueeControlRootDesigner` classe fornisce l'esperienza della fase di progettazione personalizzata per `MarqueeControl` le istanze di. La maggior parte della funzionalità in fase di progettazione viene ereditata dalla <xref:System.Windows.Forms.Design.DocumentDesigner> classe. il codice implementa due personalizzazioni specifiche: gestione delle modifiche dei componenti e aggiunta di verbi di progettazione.

 Quando gli utenti progettano le `MarqueeControl` istanze, la finestra `MarqueeControl` di progettazione radice tiene traccia delle modifiche apportate a e ai relativi controlli figlio. L'ambiente in fase di progettazione offre un comodo servizio <xref:System.ComponentModel.Design.IComponentChangeService>,, per tenere traccia delle modifiche apportate allo stato del componente.

 Per acquisire un riferimento a questo servizio, è possibile eseguire una query sull' <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> ambiente con il metodo. Se la query ha esito positivo, la finestra di progettazione può allineare un gestore per l' <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> evento ed eseguire tutte le attività necessarie per mantenere uno stato coerente in fase di progettazione.

 Nel caso della `MarqueeControlRootDesigner` classe, si chiamerà il <xref:System.Windows.Forms.Control.Refresh%2A> metodo su `MarqueeControl`ogni `IMarqueeWidget` oggetto contenuto da. In questo modo l' `IMarqueeWidget` oggetto verrà ridisegnato in modo appropriato quando <xref:System.Windows.Forms.Control.Size%2A> vengono modificate le proprietà come l'elemento padre.

### <a name="to-handle-component-changes"></a>Per gestire le modifiche ai componenti

1. Aprire il `MarqueeControlRootDesigner` file di origine nell' **Editor del codice** ed eseguire <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> l'override del metodo. Chiamare l'implementazione di base <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> di ed eseguire una <xref:System.ComponentModel.Design.IComponentChangeService>query per l'oggetto.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. Implementare il <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> gestore eventi. Testare il tipo del componente di invio e, se è un `IMarqueeWidget`, chiamare il <xref:System.Windows.Forms.Control.Refresh%2A> relativo metodo.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="adding-designer-verbs-to-your-custom-designer"></a>Aggiunta di verbi di progettazione alla finestra di progettazione personalizzata

Un verbo di progettazione è un comando di menu collegato a un gestore eventi. I verbi della finestra di progettazione vengono aggiunti al menu di scelta rapida di un componente in fase di progettazione. Per altre informazioni, vedere <xref:System.ComponentModel.Design.DesignerVerb>.

Si aggiungeranno due verbi di progettazione alle finestre di progettazione: **Eseguire** test e **arrestare il test**. Questi verbi consentiranno di visualizzare il comportamento `MarqueeControl` in fase di esecuzione di in fase di progettazione. Questi verbi verranno aggiunti a `MarqueeControlRootDesigner`.

Quando viene richiamato **Esegui test** , il gestore dell'evento verb chiamerà `StartMarquee` il metodo su `MarqueeControl`. Quando **stop test** viene richiamato, il gestore dell'evento verb chiamerà `StopMarquee` il metodo su `MarqueeControl`. L'implementazione dei `StartMarquee` metodi e `StopMarquee` chiama questi metodi sui controlli contenuti che implementano `IMarqueeWidget`, quindi anche tutti `IMarqueeWidget` i controlli contenuti parteciperanno al test.

### <a name="to-add-designer-verbs-to-your-custom-designers"></a>Per aggiungere verbi di progettazione alle finestre di progettazione personalizzate

1. Nella classe `MarqueeControlRootDesigner` aggiungere i gestori eventi denominati `OnVerbRunTest` e `OnVerbStopTest`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. Connettere questi gestori eventi ai verbi della finestra di progettazione corrispondente. `MarqueeControlRootDesigner`eredita un <xref:System.ComponentModel.Design.DesignerVerbCollection> oggetto dalla relativa classe di base. Si creeranno due nuovi <xref:System.ComponentModel.Design.DesignerVerb> oggetti che vengono aggiunti a questa raccolta <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> nel metodo.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="creating-a-custom-uitypeeditor"></a>Creazione di un oggetto UITypeEditor personalizzato

Quando si crea un'esperienza di progettazione personalizzata per gli utenti, è spesso consigliabile creare un'interazione personalizzata con l'Finestra Proprietà. A tale scopo, è possibile creare <xref:System.Drawing.Design.UITypeEditor>un oggetto. Per altre informazioni, vedere [Procedura: Creare un editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fd3kt7d5(v=vs.120))di tipo dell'interfaccia utente.

Il `MarqueeBorder` controllo espone diverse proprietà nell'finestra Proprietà. Due di queste proprietà `MarqueeSpinDirection` e `MarqueeLightShape` sono rappresentate dalle enumerazioni. Per illustrare l'uso di un editor di tipi dell'interfaccia `MarqueeLightShape` utente, alla proprietà sarà <xref:System.Drawing.Design.UITypeEditor> associata una classe.

### <a name="to-create-a-custom-ui-type-editor"></a>Per creare un editor di tipo personalizzato dell'interfaccia utente

1. Aprire il `MarqueeBorder` file di origine nell' **editor di codice**.

2. Nella definizione della `MarqueeBorder` classe dichiarare una classe denominata `LightShapeEditor` che deriva da <xref:System.Drawing.Design.UITypeEditor>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. Dichiarare una <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> variabile di istanza `editorService`denominata.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. Eseguire l'override del metodo <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> . Questa implementazione restituisce <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, che indica all'ambiente di progettazione come `LightShapeEditor`visualizzare.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. Eseguire l'override del metodo <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> . Questa implementazione esegue una query nell'ambiente di <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> progettazione di un oggetto. Se ha esito positivo, `LightShapeSelectionControl`viene creato un oggetto. Il <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> metodo viene richiamato per `LightShapeEditor`avviare. Il valore restituito da questa chiamata viene restituito all'ambiente di progettazione.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a>Creazione di un controllo di visualizzazione per l'oggetto UITypeEditor personalizzato

1. La `MarqueeLightShape` proprietà supporta due tipi di forme chiare: `Square` e `Circle`. Si creerà un controllo personalizzato usato esclusivamente per visualizzare graficamente questi valori nel Finestra Proprietà. Questo controllo personalizzato verrà usato dal <xref:System.Drawing.Design.UITypeEditor> per interagire con l'finestra Proprietà.

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>Per creare un controllo di visualizzazione per l'editor di tipo dell'interfaccia utente personalizzata

1. Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> elemento `MarqueeControlLibrary` al progetto. Assegnare al nuovo file di origine il nome di base "LightShapeSelectionControl".

2. Trascinare due <xref:System.Windows.Forms.Panel> controlli dalla `LightShapeSelectionControl` **casella degli strumenti** in. Denominarli `circlePanel`e. `squarePanel` Disponerli affiancati. Impostare la <xref:System.Windows.Forms.Control.Size%2A> proprietà di entrambi <xref:System.Windows.Forms.Panel> i controlli su (60, 60). Impostare la <xref:System.Windows.Forms.Control.Location%2A> proprietà `squarePanel` del controllo su (8, 10). Impostare la <xref:System.Windows.Forms.Control.Location%2A> proprietà `circlePanel` del controllo su (80, 10). Infine, impostare la <xref:System.Windows.Forms.Control.Size%2A> proprietà `LightShapeSelectionControl` di su (150, 80).

3. Aprire il `LightShapeSelectionControl` file di origine nell' **editor di codice**. Nella parte superiore del file importare lo <xref:System.Windows.Forms.Design?displayProperty=nameWithType> spazio dei nomi:

```vb
Imports System.Windows.Forms.Design
```

```csharp
using System.Windows.Forms.Design;
```

1. Implementare <xref:System.Windows.Forms.Control.Click> i gestori eventi per i `squarePanel` controlli `circlePanel` e. Questi metodi richiamano <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> per terminare <xref:System.Drawing.Design.UITypeEditor> la sessione di modifica personalizzata.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

2. Dichiarare una <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> variabile di istanza `editorService`denominata.

```vb
Private editorService As IWindowsFormsEditorService
```

```csharp
private IWindowsFormsEditorService editorService;
```

1. Dichiarare una `MarqueeLightShape` variabile di istanza `lightShapeValue`denominata.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

2. <xref:System.Windows.Forms.Control.Click> `squarePanel` `circlePanel` Nel costruttore, alleghi i gestori eventi<xref:System.Windows.Forms.Control.Click> agli eventi dei controlli e. `LightShapeSelectionControl` Definire anche un overload del costruttore che assegna il `MarqueeLightShape` valore dall'ambiente `lightShapeValue` di progettazione al campo.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

3. Nel metodo scollegare i <xref:System.Windows.Forms.Control.Click> gestori eventi. <xref:System.ComponentModel.Component.Dispose%2A>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

4. In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**. Aprire il file LightShapeSelectionControl.designer.cs o LightShapeSelectionControl. designer. vb e rimuovere la definizione predefinita del <xref:System.ComponentModel.Component.Dispose%2A> metodo.

5. Implementare la proprietà `LightShape`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

6. Eseguire l'override del metodo <xref:System.Windows.Forms.Control.OnPaint%2A> . Questa implementazione trarrà un quadrato e un cerchio pieni. Verrà inoltre evidenziato il valore selezionato disegnando un bordo intorno a una forma o l'altro.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="testing-your-custom-control-in-the-designer"></a>Test del controllo personalizzato nella finestra di progettazione

A questo punto, è possibile compilare il `MarqueeControlLibrary` progetto. Testare l'implementazione creando un controllo che eredita dalla `MarqueeControl` classe e usandolo in un form.

### <a name="to-create-a-custom-marqueecontrol-implementation"></a>Per creare un'implementazione MarqueeControl personalizzata

1. Aprire `DemoMarqueeControl` in Progettazione Windows Form. In questo modo viene creata un' `DemoMarqueeControl` istanza del tipo e viene visualizzata in un'istanza `MarqueeControlRootDesigner` del tipo.

2. Nella **casella degli strumenti**aprire la scheda **componenti di MarqueeControlLibrary** . Si noterà che i `MarqueeBorder` controlli `MarqueeText` e sono disponibili per la selezione.

3. Trascinare un'istanza del `MarqueeBorder` controllo `DemoMarqueeControl` nell'area di progettazione. Ancorare `MarqueeBorder` questo controllo al controllo padre.

4. Trascinare un'istanza del `MarqueeText` controllo `DemoMarqueeControl` nell'area di progettazione.

5. Compilare la soluzione.

6. Fare clic con il `DemoMarqueeControl` pulsante destro del mouse su e dal menu di scelta rapida selezionare l'opzione **Esegui test** per avviare l'animazione. Fare clic su **Interrompi test** per arrestare l'animazione.

7. Aprire **Form1** nella visualizzazione Progettazione.

8. Posizionare due <xref:System.Windows.Forms.Button> controlli nel form. Assegnare loro `startButton` un `stopButton`nome e, quindi <xref:System.Windows.Forms.Control.Text%2A> modificare i valori delle proprietà rispettivamente per **avviare** e **arrestare**.

9. Implementare <xref:System.Windows.Forms.Control.Click> i gestori eventi per entrambi <xref:System.Windows.Forms.Button> i controlli.

10. Nella **casella degli strumenti**aprire la scheda **componenti di MarqueeControlTest** . La `DemoMarqueeControl` selezione sarà disponibile.

11. Trascinare un'istanza di `DemoMarqueeControl` nell'area di progettazione **Form1** .

12. Nei gestori `Start` `Stop` eventi, richiamare i metodi e su `DemoMarqueeControl`. <xref:System.Windows.Forms.Control.Click>

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

1. Impostare il `MarqueeControlTest` progetto come progetto di avvio ed eseguirlo. Viene visualizzato il modulo che visualizza `DemoMarqueeControl`il. Fare clic sul pulsante **Start** per avviare l'animazione. Si noterà che il testo lampeggia e le luci si spostano attorno al bordo.

## <a name="next-steps"></a>Passaggi successivi

`MarqueeControlLibrary` Viene illustrata una semplice implementazione di controlli personalizzati e finestre di progettazione associate. Questo esempio può essere reso più sofisticato in diversi modi:

- Modificare i valori delle proprietà di `DemoMarqueeControl` nella finestra di progettazione. Aggiungere altri `MarqueBorder` controlli e ancorarli all'interno delle istanze padre per creare un effetto annidato. Provare a usare impostazioni diverse per `UpdatePeriod` e le proprietà correlate alla luce.

- Creare implementazioni personalizzate di `IMarqueeWidget`. È possibile, ad esempio, creare un segno "neon" lampeggiante o un segno animato con più immagini.

- Personalizzare ulteriormente l'esperienza in fase di progettazione. È possibile provare ad ombreggiare più proprietà <xref:System.Windows.Forms.Control.Enabled%2A> rispetto <xref:System.Windows.Forms.Control.Visible%2A>a e e aggiungere nuove proprietà. Aggiungere nuovi verbi di progettazione per semplificare attività comuni come l'ancoraggio dei controlli figlio.

- Concedere in `MarqueeControl`licenza il. Per altre informazioni, vedere [Procedura: Componenti e controlli](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))delle licenze.

- Controllare la modalità di serializzazione dei controlli e il modo in cui viene generato il codice. Per altre informazioni, vedere [generazione e compilazione di codice sorgente dinamico](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
- [Procedura: Creazione di un controllo Windows Forms che sfrutta le funzionalità della fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))
- [Estensione del supporto in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Finestre di progettazione personalizzate](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h51z5c0x(v=vs.120))
