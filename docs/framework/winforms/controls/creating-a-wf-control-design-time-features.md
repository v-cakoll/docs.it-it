---
title: Creare un controllo che sfrutta i vantaggi delle funzionalità della fase di progettazione di Visual Studio
description: Informazioni su come creare una finestra di progettazione personalizzata per un controllo personalizzato in Windows Forms che sfrutta le funzionalità della fase di progettazione.
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
ms.openlocfilehash: 03c04578ecb01b689f58d41a46eef5793fb1182c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613910"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a>Procedura dettagliata: creare un controllo che sfrutti le funzionalità della fase di progettazione

Per migliorare l'esperienza in fase di progettazione per un controllo personalizzato, è possibile creare una finestra di progettazione personalizzata associata.

Questo articolo illustra come creare una finestra di progettazione personalizzata per un controllo personalizzato. Verranno implementati un `MarqueeControl` tipo e una classe della finestra di progettazione associata denominata `MarqueeControlRootDesigner` .

Il `MarqueeControl` tipo implementa una visualizzazione simile a un Marquee del teatro con luci animate e testo lampeggiante.

La finestra di progettazione per questo controllo interagisce con l'ambiente di progettazione per offrire un'esperienza di progettazione personalizzata. Con la finestra di progettazione personalizzata è possibile assemblare un' `MarqueeControl` implementazione personalizzata con luci animate e testo lampeggiante in molte combinazioni. È possibile utilizzare il controllo assemblato in un form come qualsiasi altro controllo Windows Forms.

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

3. Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> elemento al `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine un nome di base di **MarqueeControl**.

4. Utilizzando **Esplora soluzioni**, creare una nuova cartella nel `MarqueeControlLibrary` progetto.

5. Fare clic con il pulsante destro del mouse sulla cartella **progettazione** e aggiungere una nuova classe. Denominarlo **MarqueeControlRootDesigner**.

6. È necessario usare i tipi dall'assembly System. Design, quindi aggiungere questo riferimento al `MarqueeControlLibrary` progetto.

## <a name="reference-the-custom-control-project"></a>Fare riferimento al progetto di controllo personalizzato

Il progetto viene usato `MarqueeControlTest` per testare il controllo personalizzato. Il progetto di test diventerà in grado di riconoscere il controllo personalizzato quando si aggiunge un riferimento al progetto all' `MarqueeControlLibrary` assembly.

Nel `MarqueeControlTest` progetto aggiungere un riferimento al progetto all' `MarqueeControlLibrary` assembly. Assicurarsi di usare la scheda **progetti** nella finestra di dialogo **Aggiungi riferimento anziché fare** riferimento direttamente all' `MarqueeControlLibrary` assembly.

## <a name="define-a-custom-control-and-its-custom-designer"></a>Definire un controllo personalizzato e la relativa finestra di progettazione personalizzata

Il controllo personalizzato deriverà dalla <xref:System.Windows.Forms.UserControl> classe. Ciò consente al controllo di contenere altri controlli e offre al controllo una grande quantità di funzionalità predefinite.

Al controllo personalizzato verrà associata una finestra di progettazione personalizzata. Questo consente di creare un'esperienza di progettazione univoca personalizzata in modo specifico per il controllo personalizzato.

Il controllo viene associato alla relativa finestra di progettazione tramite la <xref:System.ComponentModel.DesignerAttribute> classe. Poiché si sta sviluppando l'intero comportamento in fase di progettazione del controllo personalizzato, l'interfaccia verrà implementata dalla finestra di progettazione personalizzata <xref:System.ComponentModel.Design.IRootDesigner> .

### <a name="to-define-a-custom-control-and-its-custom-designer"></a>Per definire un controllo personalizzato e la relativa finestra di progettazione personalizzata

1. Aprire il `MarqueeControl` file di origine nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. Aggiungere la <xref:System.ComponentModel.DesignerAttribute> alla `MarqueeControl` dichiarazione di classe. Il controllo personalizzato verrà associato alla relativa finestra di progettazione.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. Aprire il `MarqueeControlRootDesigner` file di origine nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. Modificare la dichiarazione di `MarqueeControlRootDesigner` in modo che erediti dalla <xref:System.Windows.Forms.Design.DocumentDesigner> classe. Applicare <xref:System.ComponentModel.ToolboxItemFilterAttribute> per specificare l'interazione della finestra di progettazione con la **casella degli strumenti**.

   > [!NOTE]
   > La definizione della `MarqueeControlRootDesigner` classe è stata racchiusa in uno spazio dei nomi denominato MarqueeControlLibrary. Design. Questa dichiarazione posiziona la finestra di progettazione in uno spazio dei nomi speciale riservato ai tipi correlati alla progettazione.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. Definire il costruttore per la `MarqueeControlRootDesigner` classe. Inserire un' <xref:System.Diagnostics.Trace.WriteLine%2A> istruzione nel corpo del costruttore. Questa operazione sarà utile per il debug.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a>Creare un'istanza del controllo personalizzato

1. Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> elemento al `MarqueeControlTest` progetto. Assegnare al nuovo file di origine un nome di base di **DemoMarqueeControl**.

2. Aprire il `DemoMarqueeControl` file nell' **editor di codice**. Nella parte superiore del file importare lo `MarqueeControlLibrary` spazio dei nomi:

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. Modificare la dichiarazione di `DemoMarqueeControl` in modo che erediti dalla `MarqueeControl` classe.

4. Compilare il progetto.

5. Aprire Form1 nella Progettazione Windows Form.

6. Individuare la scheda **Componenti MarqueeControlTest** nella **casella degli strumenti** e aprirla. Trascinare un oggetto `DemoMarqueeControl` dalla **casella degli strumenti** nel form.

7. Compilare il progetto.

## <a name="set-up-the-project-for-design-time-debugging"></a>Configurare il progetto per il debug in fase di progettazione

Quando si sviluppa un'esperienza della fase di progettazione personalizzata, sarà necessario eseguire il debug dei controlli e dei componenti. Esiste un modo semplice per configurare il progetto per consentire il debug in fase di progettazione. Per ulteriori informazioni, vedere [procedura dettagliata: debug di controlli di Windows Forms personalizzati in fase di progettazione](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).

1. Fare clic con il pulsante destro del mouse sul `MarqueeControlLibrary` progetto e scegliere **Proprietà**.

2. Nella finestra di dialogo **pagine delle proprietà di MarqueeControlLibrary** selezionare la pagina **debug** .

3. Nella sezione **azione di avvio** selezionare **Avvia programma esterno**. Verrà eseguito il debug di un'istanza separata di Visual Studio, quindi fare clic sui puntini di sospensione ( ![ il pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio ](./media/visual-studio-ellipsis-button.png) ) per cercare l'IDE di Visual Studio. Il nome del file eseguibile è devenv.exe e, se è stato installato nel percorso predefinito, il percorso è *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019 \\ \<edition>\Common7\IDE\devenv.exe*.

4. Selezionare **OK** per chiudere la finestra di dialogo.

5. Fare clic con il pulsante destro del mouse sul progetto MarqueeControlLibrary e selezionare **Imposta come progetto di avvio** per abilitare questa configurazione di debug.

## <a name="checkpoint"></a>Checkpoint

A questo punto è possibile eseguire il debug del comportamento in fase di progettazione del controllo personalizzato. Una volta stabilito che l'ambiente di debug è configurato correttamente, si verificherà l'associazione tra il controllo personalizzato e la finestra di progettazione personalizzata.

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>Per testare l'ambiente di debug e l'associazione della finestra di progettazione

1. Aprire il file di origine MarqueeControlRootDesigner nell' **editor di codice** e inserire un punto di interruzione nell' <xref:System.Diagnostics.Trace.WriteLine%2A> istruzione.

2. Premere **F5** per avviare la sessione di debug.

   Viene creata una nuova istanza di Visual Studio.

3. Nella nuova istanza di Visual Studio aprire la soluzione MarqueeControlTest. È possibile trovare facilmente la soluzione selezionando **progetti recenti** dal menu **file** . Il file della soluzione MarqueeControlTest. sln verrà elencato come file usato più di recente.

4. Aprire la `DemoMarqueeControl` nella finestra di progettazione.

   L'istanza di debug di Visual Studio ottiene lo stato attivo e l'esecuzione si arresta in corrispondenza del punto di interruzione. Premere **F5** per continuare la sessione di debug.

A questo punto, è possibile sviluppare ed eseguire il debug del controllo personalizzato e della finestra di progettazione personalizzata associata. Il resto di questo articolo è incentrato sui dettagli dell'implementazione delle funzionalità del controllo e della finestra di progettazione.

## <a name="implement-the-custom-control"></a>Implementare il controllo personalizzato

`MarqueeControl`È un oggetto <xref:System.Windows.Forms.UserControl> con un po' di personalizzazione. Espone due metodi: `Start` , che avvia l'animazione Marquee e `Stop` , che interrompe l'animazione. Poiché `MarqueeControl` contiene i controlli figlio che implementano l' `IMarqueeWidget` interfaccia `Start` ed `Stop` enumerano ogni controllo figlio e chiamano `StartMarquee` rispettivamente i `StopMarquee` metodi e in ogni controllo figlio che implementa `IMarqueeWidget` .

L'aspetto dei `MarqueeBorder` controlli e `MarqueeText` dipende dal layout, quindi `MarqueeControl` esegue l'override del <xref:System.Windows.Forms.Control.OnLayout%2A> metodo e chiama i <xref:System.Windows.Forms.Control.PerformLayout%2A> controlli figlio di questo tipo.

Si tratta dell'extent delle `MarqueeControl` personalizzazioni. Le funzionalità della fase di esecuzione sono implementate `MarqueeBorder` dai `MarqueeText` controlli e e le funzionalità della fase di progettazione vengono implementate `MarqueeBorderDesigner` dalle `MarqueeControlRootDesigner` classi e.

### <a name="to-implement-your-custom-control"></a>Per implementare il controllo personalizzato

1. Aprire il `MarqueeControl` file di origine nell' **editor di codice**. Implementare i `Start` `Stop` metodi e.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. Eseguire l'override del metodo <xref:System.Windows.Forms.Control.OnLayout%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a>Creare un controllo figlio per il controllo personalizzato

`MarqueeControl`Ospiterà due tipi di controllo figlio: il `MarqueeBorder` controllo e il `MarqueeText` controllo.

- `MarqueeBorder`: Questo controllo disegna un bordo di "luci" intorno ai bordi. Le spie lampeggiano in sequenza, quindi sembrano spostarsi intorno al bordo. La velocità con cui lampeggia la luce viene controllata da una proprietà denominata `UpdatePeriod` . Diverse altre proprietà personalizzate determinano altri aspetti dell'aspetto del controllo. Due metodi, denominati `StartMarquee` e `StopMarquee` , controllano quando l'animazione viene avviata e arrestata.

- `MarqueeText`: Questo controllo disegna una stringa lampeggiante. Analogamente al `MarqueeBorder` controllo, la velocità di lampeggio del testo viene controllata dalla `UpdatePeriod` Proprietà. Il `MarqueeText` controllo dispone anche dei `StartMarquee` `StopMarquee` metodi e in comune con il `MarqueeBorder` controllo.

In fase di progettazione, `MarqueeControlRootDesigner` consente di aggiungere questi due tipi di controllo a un oggetto `MarqueeControl` in qualsiasi combinazione.

Le funzionalità comuni dei due controlli vengono fattorizzate in un'interfaccia denominata `IMarqueeWidget` . `MarqueeControl`In questo modo, l'oggetto può individuare eventuali controlli figlio correlati a Marquee e assegnare loro un trattamento speciale.

Per implementare la funzionalità di animazione periodica, si utilizzeranno <xref:System.ComponentModel.BackgroundWorker> oggetti dello <xref:System.ComponentModel?displayProperty=nameWithType> spazio dei nomi. È possibile usare <xref:System.Windows.Forms.Timer> gli oggetti, ma quando `IMarqueeWidget` sono presenti molti oggetti, il singolo thread dell'interfaccia utente potrebbe non essere in grado di tenere il passo con l'animazione.

### <a name="to-create-a-child-control-for-your-custom-control"></a>Per creare un controllo figlio per il controllo personalizzato

1. Aggiungere un nuovo elemento di classe al `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine il nome di base "IMarqueeWidget".

2. Aprire il `IMarqueeWidget` file di origine nell' **editor di codice** e modificare la dichiarazione da `class` a `interface` :

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. Aggiungere il codice seguente all' `IMarqueeWidget` interfaccia per esporre due metodi e una proprietà che modificano l'animazione Marquee:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. Aggiungere un nuovo elemento di **controllo personalizzato** al `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine il nome di base "MarqueeText".

5. Trascinare un <xref:System.ComponentModel.BackgroundWorker> componente dalla **casella degli strumenti** nel `MarqueeText` controllo. Questo componente consentirà al `MarqueeText` controllo di aggiornarsi in modo asincrono.

6. Nella finestra **Proprietà** impostare le <xref:System.ComponentModel.BackgroundWorker> proprietà e del componente `WorkerReportsProgress` <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> su **true**. Queste impostazioni consentono al <xref:System.ComponentModel.BackgroundWorker> componente di generare periodicamente l' <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento e di annullare gli aggiornamenti asincroni.

   Per ulteriori informazioni, vedere [BackgroundWorker Component](backgroundworker-component.md).

7. Aprire il `MarqueeText` file di origine nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. Modificare la dichiarazione di `MarqueeText` in modo che erediti da <xref:System.Windows.Forms.Label> e per implementare l' `IMarqueeWidget` interfaccia:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. Dichiarare le variabili di istanza che corrispondono alle proprietà esposte e inizializzarle nel costruttore. Il `isLit` campo determina se il testo deve essere disegnato nel colore specificato dalla `LightColor` Proprietà.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. Implementare l'interfaccia `IMarqueeWidget`.

    I `StartMarquee` `StopMarquee` metodi e richiamano i <xref:System.ComponentModel.BackgroundWorker> metodi e del componente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> per avviare e arrestare l'animazione.

    Gli <xref:System.ComponentModel.CategoryAttribute.Category%2A> <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributi e vengono applicati alla `UpdatePeriod` Proprietà in modo che vengano visualizzati in una sezione personalizzata del finestra Proprietà denominato "Marquee".

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. Implementare le funzioni di accesso alle proprietà. Si esporrà due proprietà ai client: `LightColor` e `DarkColor` . Gli <xref:System.ComponentModel.CategoryAttribute.Category%2A> <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributi e vengono applicati a queste proprietà, quindi le proprietà vengono visualizzate in una sezione personalizzata del finestra Proprietà denominato "Marquee".

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. Implementare i gestori per gli <xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.BackgroundWorker.DoWork> eventi e del componente <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> .

    Il <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore eventi dorme per il numero di millisecondi specificato da `UpdatePeriod` genera l' <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento, fino a quando il codice non interrompe l'animazione chiamando <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> .

    Il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> gestore eventi alterna il testo tra lo stato chiaro e scuro per dare l'impressione di lampeggiare.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. Eseguire l'override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo per abilitare l'animazione.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. Premere **F6** per compilare la soluzione.

## <a name="create-the-marqueeborder-child-control"></a>Creare il controllo figlio MarqueeBorder

Il `MarqueeBorder` controllo è leggermente più sofisticato del `MarqueeText` controllo. Dispone di più proprietà e l'animazione nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo è più complessa. In linea di base, è molto simile al `MarqueeText` controllo.

Poiché il `MarqueeBorder` controllo può avere controlli figlio, deve essere in grado di riconoscere <xref:System.Windows.Forms.Control.Layout> gli eventi.

### <a name="to-create-the-marqueeborder-control"></a>Per creare il controllo MarqueeBorder

1. Aggiungere un nuovo elemento di **controllo personalizzato** al `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine il nome di base "MarqueeBorder".

2. Trascinare un <xref:System.ComponentModel.BackgroundWorker> componente dalla **casella degli strumenti** nel `MarqueeBorder` controllo. Questo componente consentirà al `MarqueeBorder` controllo di aggiornarsi in modo asincrono.

3. Nella finestra **Proprietà** impostare le <xref:System.ComponentModel.BackgroundWorker> proprietà e del componente `WorkerReportsProgress` <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> su **true**. Queste impostazioni consentono al <xref:System.ComponentModel.BackgroundWorker> componente di generare periodicamente l' <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento e di annullare gli aggiornamenti asincroni. Per ulteriori informazioni, vedere [BackgroundWorker Component](backgroundworker-component.md).

4. Nella finestra **Proprietà** selezionare il pulsante **eventi** . Associazione di gestori per gli <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> eventi e.

5. Aprire il `MarqueeBorder` file di origine nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. Modificare la dichiarazione di `MarqueeBorder` in modo che erediti da <xref:System.Windows.Forms.Panel> e per implementare l' `IMarqueeWidget` interfaccia.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. Dichiarare due enumerazioni per la gestione `MarqueeBorder` dello stato del controllo: `MarqueeSpinDirection` , che determina la direzione in cui le luci "ruotano" intorno al bordo, e `MarqueeLightShape` , che determina la forma delle luci (quadrati o circolari). Inserire queste dichiarazioni prima della `MarqueeBorder` dichiarazione di classe.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. Dichiarare le variabili di istanza che corrispondono alle proprietà esposte e inizializzarle nel costruttore.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. Implementare l'interfaccia `IMarqueeWidget`.

    I `StartMarquee` `StopMarquee` metodi e richiamano i <xref:System.ComponentModel.BackgroundWorker> metodi e del componente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> per avviare e arrestare l'animazione.

    Poiché il `MarqueeBorder` controllo può contenere controlli figlio, il `StartMarquee` metodo enumera tutti i controlli figlio e chiama `StartMarquee` su quelli che implementano `IMarqueeWidget` . Il `StopMarquee` metodo ha un'implementazione simile.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. Implementare le funzioni di accesso alle proprietà. Il `MarqueeBorder` controllo dispone di diverse proprietà per il controllo dell'aspetto.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. Implementare i gestori per gli <xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.BackgroundWorker.DoWork> eventi e del componente <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> .

    Il <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore eventi dorme per il numero di millisecondi specificato da `UpdatePeriod` genera l' <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> evento, fino a quando il codice non interrompe l'animazione chiamando <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> .

    Il <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> gestore eventi incrementa la posizione della luce "base", da cui viene determinato lo stato chiaro/scuro degli altri indicatori e chiama il <xref:System.Windows.Forms.Control.Refresh%2A> metodo per fare in modo che il controllo venga ridisegnato.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. Implementare i metodi helper, `IsLit` e `DrawLight` .

    Il `IsLit` metodo determina il colore di una luce in una determinata posizione. Le luci con "lit" vengono disegnate nel colore specificato dalla `LightColor` proprietà e quelle "scure" vengono disegnate nel colore specificato dalla `DarkColor` Proprietà.

    Il `DrawLight` metodo disegna una luce usando il colore, la forma e la posizione appropriati.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. Eseguire l'override dei metodi <xref:System.Windows.Forms.Control.OnLayout%2A> e <xref:System.Windows.Forms.Control.OnPaint%2A>.

    Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo disegna le luci lungo i bordi del `MarqueeBorder` controllo.

    Poiché il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo dipende dalle dimensioni del `MarqueeBorder` controllo, è necessario chiamarlo ogni volta che viene modificato il layout. Per ottenere questo risultato, eseguire l'override di <xref:System.Windows.Forms.Control.OnLayout%2A> e chiamare <xref:System.Windows.Forms.Control.Refresh%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a>Creare una finestra di progettazione personalizzata per nascondere e filtrare le proprietà

La `MarqueeControlRootDesigner` classe fornisce l'implementazione per la finestra di progettazione radice. Oltre a questa finestra di progettazione, che opera su `MarqueeControl` , è necessaria una finestra di progettazione personalizzata associata in modo specifico al `MarqueeBorder` controllo. Questa finestra di progettazione fornisce un comportamento personalizzato appropriato nel contesto della finestra di progettazione radice personalizzata.

In particolare, la `MarqueeBorderDesigner` funzione "Shadow" e filtra alcune proprietà del `MarqueeBorder` controllo, modificando l'interazione con l'ambiente di progettazione.

L'intercettazione delle chiamate alla funzione di accesso delle proprietà di un componente è nota come "shadowing". Consente a una finestra di progettazione di tenere traccia del valore impostato dall'utente e, facoltativamente, di passare il valore al componente in fase di progettazione.

Per questo esempio, le <xref:System.Windows.Forms.Control.Visible%2A> <xref:System.Windows.Forms.Control.Enabled%2A> proprietà e verranno nascoste da `MarqueeBorderDesigner` , che impedisce all'utente di rendere il `MarqueeBorder` controllo invisibile o disabilitato in fase di progettazione.

Le finestre di progettazione possono inoltre aggiungere e rimuovere proprietà. Per questo esempio, la <xref:System.Windows.Forms.Control.Padding%2A> proprietà verrà rimossa in fase di progettazione, perché il `MarqueeBorder` controllo imposta a livello di codice la spaziatura interna in base alla dimensione delle luci specificate dalla `LightSize` Proprietà.

La classe base per `MarqueeBorderDesigner` è <xref:System.ComponentModel.Design.ComponentDesigner> , che dispone di metodi che possono modificare gli attributi, le proprietà e gli eventi esposti da un controllo in fase di progettazione:

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

Quando si modifica l'interfaccia pubblica di un componente usando questi metodi, attenersi alle regole seguenti:

- Aggiungere o rimuovere elementi solo nei `PreFilter` metodi

- Modificare gli elementi esistenti `PostFilter` solo nei metodi

- Chiamare sempre prima l'implementazione di base nei `PreFilter` metodi

- Chiamare sempre l'implementazione di base per ultima nei `PostFilter` metodi

Rispettando queste regole si garantisce che tutte le finestre di progettazione nell'ambiente in fase di progettazione dispongano di una visualizzazione coerente di tutti i componenti progettati.

La <xref:System.ComponentModel.Design.ComponentDesigner> classe fornisce un dizionario per la gestione dei valori delle proprietà nascoste, che consente di evitare la necessità di creare variabili di istanza specifiche.

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>Per creare una finestra di progettazione personalizzata per nascondere e filtrare le proprietà

1. Fare clic con il pulsante destro del mouse sulla cartella **progettazione** e aggiungere una nuova classe. Assegnare al file di origine un nome di base di **MarqueeBorderDesigner**.

2. Aprire il file di origine MarqueeBorderDesigner nell' **editor di codice**. Nella parte superiore del file importare gli spazi dei nomi seguenti:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. Modificare la dichiarazione di `MarqueeBorderDesigner` in modo da ereditare da <xref:System.Windows.Forms.Design.ParentControlDesigner> .

    Poiché il `MarqueeBorder` controllo può contenere controlli figlio, `MarqueeBorderDesigner` eredita da <xref:System.Windows.Forms.Design.ParentControlDesigner> , che gestisce l'interazione padre-figlio.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. Eseguire l'override dell'implementazione di base di <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. Implementare le proprietà <xref:System.Windows.Forms.Control.Enabled%2A> e <xref:System.Windows.Forms.Control.Visible%2A>. Queste implementazioni nascondono le proprietà del controllo.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a>Gestire le modifiche ai componenti

La `MarqueeControlRootDesigner` classe fornisce l'esperienza della fase di progettazione personalizzata per le `MarqueeControl` istanze di. La maggior parte della funzionalità in fase di progettazione viene ereditata dalla <xref:System.Windows.Forms.Design.DocumentDesigner> classe. Il codice implementa due personalizzazioni specifiche, ovvero la gestione delle modifiche dei componenti e l'aggiunta di verbi di progettazione.

Quando gli utenti progettano le `MarqueeControl` istanze, la finestra di progettazione radice tiene traccia delle modifiche apportate a `MarqueeControl` e ai relativi controlli figlio. L'ambiente in fase di progettazione offre un comodo servizio, <xref:System.ComponentModel.Design.IComponentChangeService> , per tenere traccia delle modifiche apportate allo stato del componente.

Per acquisire un riferimento a questo servizio, è possibile eseguire una query sull'ambiente con il <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> metodo. Se la query ha esito positivo, la finestra di progettazione può allineare un gestore per l' <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> evento ed eseguire tutte le attività necessarie per mantenere uno stato coerente in fase di progettazione.

Nel caso della `MarqueeControlRootDesigner` classe, si chiamerà il <xref:System.Windows.Forms.Control.Refresh%2A> metodo su ogni `IMarqueeWidget` oggetto contenuto da `MarqueeControl` . In questo modo l' `IMarqueeWidget` oggetto verrà ridisegnato in modo appropriato quando vengono modificate le proprietà come l'elemento padre <xref:System.Windows.Forms.Control.Size%2A> .

### <a name="to-handle-component-changes"></a>Per gestire le modifiche ai componenti

1. Aprire il `MarqueeControlRootDesigner` file di origine nell' **Editor del codice** ed eseguire l'override del <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> metodo. Chiamare l'implementazione di base di <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> ed eseguire una query per l'oggetto <xref:System.ComponentModel.Design.IComponentChangeService> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. Implementare il <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> gestore eventi. Testare il tipo del componente di invio e, se è un `IMarqueeWidget` , chiamare il relativo <xref:System.Windows.Forms.Control.Refresh%2A> metodo.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a>Aggiungere verbi di progettazione alla finestra di progettazione personalizzata

Un verbo di progettazione è un comando di menu collegato a un gestore evento. I verbi della finestra di progettazione vengono aggiunti al menu di scelta rapida di un componente in fase di progettazione. Per altre informazioni, vedere <xref:System.ComponentModel.Design.DesignerVerb>.

Si aggiungeranno due verbi di progettazione alle finestre di progettazione: **Esegui test** e **Interrompi test**. Questi verbi consentiranno di visualizzare il comportamento in fase di esecuzione di in fase di `MarqueeControl` progettazione. Questi verbi verranno aggiunti a `MarqueeControlRootDesigner` .

Quando viene richiamato **Esegui test** , il gestore dell'evento verb chiamerà il `StartMarquee` metodo su `MarqueeControl` . Quando **stop test** viene richiamato, il gestore dell'evento verb chiamerà il `StopMarquee` metodo su `MarqueeControl` . L'implementazione dei `StartMarquee` metodi e `StopMarquee` chiama questi metodi sui controlli contenuti che implementano `IMarqueeWidget` , quindi anche tutti `IMarqueeWidget` i controlli contenuti parteciperanno al test.

### <a name="to-add-designer-verbs-to-your-custom-designers"></a>Per aggiungere verbi di progettazione alle finestre di progettazione personalizzate

1. Nella `MarqueeControlRootDesigner` classe aggiungere i gestori eventi denominati `OnVerbRunTest` e `OnVerbStopTest` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. Connettere questi gestori eventi ai verbi della finestra di progettazione corrispondente. `MarqueeControlRootDesigner`eredita un oggetto <xref:System.ComponentModel.Design.DesignerVerbCollection> dalla relativa classe di base. Si creeranno due nuovi <xref:System.ComponentModel.Design.DesignerVerb> oggetti che vengono aggiunti a questa raccolta nel <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> metodo.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a>Creare un oggetto UITypeEditor personalizzato

Quando si crea un'esperienza di progettazione personalizzata per gli utenti, è spesso consigliabile creare un'interazione personalizzata con l'Finestra Proprietà. A tale scopo, è possibile creare un oggetto <xref:System.Drawing.Design.UITypeEditor> .

Il `MarqueeBorder` controllo espone diverse proprietà nell'finestra Proprietà. Due di queste proprietà `MarqueeSpinDirection` e `MarqueeLightShape` sono rappresentate dalle enumerazioni. Per illustrare l'uso di un editor di tipi dell'interfaccia utente, alla `MarqueeLightShape` proprietà sarà associata una <xref:System.Drawing.Design.UITypeEditor> classe.

### <a name="to-create-a-custom-ui-type-editor"></a>Per creare un editor di tipo personalizzato dell'interfaccia utente

1. Aprire il `MarqueeBorder` file di origine nell' **editor di codice**.

2. Nella definizione della `MarqueeBorder` classe dichiarare una classe denominata `LightShapeEditor` che deriva da <xref:System.Drawing.Design.UITypeEditor> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. Dichiarare una <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> variabile di istanza denominata `editorService` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. Eseguire l'override del metodo <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> . Questa implementazione restituisce <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown> , che indica all'ambiente di progettazione come visualizzare `LightShapeEditor` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. Eseguire l'override del metodo <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> . Questa implementazione esegue una query nell'ambiente di progettazione di un <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> oggetto. Se ha esito positivo, viene creato un oggetto `LightShapeSelectionControl` . Il <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> metodo viene richiamato per avviare `LightShapeEditor` . Il valore restituito da questa chiamata viene restituito all'ambiente di progettazione.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a>Creare un controllo di visualizzazione per l'oggetto UITypeEditor personalizzato

La `MarqueeLightShape` proprietà supporta due tipi di forme chiare: `Square` e `Circle` . Si creerà un controllo personalizzato usato esclusivamente per visualizzare graficamente questi valori nel Finestra Proprietà. Questo controllo personalizzato verrà usato dal <xref:System.Drawing.Design.UITypeEditor> per interagire con l'finestra Proprietà.

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>Per creare un controllo di visualizzazione per l'editor di tipo dell'interfaccia utente personalizzata

1. Aggiungere un nuovo <xref:System.Windows.Forms.UserControl> elemento al `MarqueeControlLibrary` progetto. Assegnare al nuovo file di origine un nome di base di **LightShapeSelectionControl**.

2. Trascinare due <xref:System.Windows.Forms.Panel> controlli dalla **casella degli strumenti** in `LightShapeSelectionControl` . Denominarli `squarePanel` e `circlePanel` . Disponerli affiancati. Impostare la <xref:System.Windows.Forms.Control.Size%2A> proprietà di entrambi i <xref:System.Windows.Forms.Panel> controlli su **(60, 60)**. Impostare la <xref:System.Windows.Forms.Control.Location%2A> proprietà del `squarePanel` controllo su **(8, 10)**. Impostare la <xref:System.Windows.Forms.Control.Location%2A> proprietà del `circlePanel` controllo su **(80, 10)**. Infine, impostare la <xref:System.Windows.Forms.Control.Size%2A> proprietà di `LightShapeSelectionControl` su **(150, 80)**.

3. Aprire il `LightShapeSelectionControl` file di origine nell' **editor di codice**. Nella parte superiore del file importare lo <xref:System.Windows.Forms.Design?displayProperty=nameWithType> spazio dei nomi:

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. Implementare <xref:System.Windows.Forms.Control.Click> i gestori eventi per i `squarePanel` `circlePanel` controlli e. Questi metodi richiamano <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> per terminare la <xref:System.Drawing.Design.UITypeEditor> sessione di modifica personalizzata.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. Dichiarare una <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> variabile di istanza denominata `editorService` .

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. Dichiarare una `MarqueeLightShape` variabile di istanza denominata `lightShapeValue` .

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. Nel `LightShapeSelectionControl` costruttore, alleghi i <xref:System.Windows.Forms.Control.Click> gestori eventi agli eventi dei `squarePanel` `circlePanel` controlli e <xref:System.Windows.Forms.Control.Click> . Definire anche un overload del costruttore che assegna il `MarqueeLightShape` valore dall'ambiente di progettazione al `lightShapeValue` campo.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. Nel <xref:System.ComponentModel.Component.Dispose%2A> Metodo scollegare i <xref:System.Windows.Forms.Control.Click> gestori eventi.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**. Aprire il file LightShapeSelectionControl.Designer.cs o LightShapeSelectionControl. designer. vb e rimuovere la definizione predefinita del <xref:System.ComponentModel.Component.Dispose%2A> metodo.

10. Implementare la proprietà `LightShape`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. Eseguire l'override del metodo <xref:System.Windows.Forms.Control.OnPaint%2A> . Questa implementazione trarrà un quadrato e un cerchio pieni. Verrà inoltre evidenziato il valore selezionato disegnando un bordo intorno a una forma o l'altro.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a>Testare il controllo personalizzato nella finestra di progettazione

A questo punto, è possibile compilare il `MarqueeControlLibrary` progetto. Testare l'implementazione creando un controllo che eredita dalla `MarqueeControl` classe e usandolo in un form.

### <a name="to-create-a-custom-marqueecontrol-implementation"></a>Per creare un'implementazione MarqueeControl personalizzata

1. Aprire `DemoMarqueeControl` in Progettazione Windows Form. In questo modo viene creata un'istanza del `DemoMarqueeControl` tipo e viene visualizzata in un'istanza del `MarqueeControlRootDesigner` tipo.

2. Nella **casella degli strumenti**aprire la scheda **componenti di MarqueeControlLibrary** . Si noterà che i `MarqueeBorder` controlli e sono `MarqueeText` disponibili per la selezione.

3. Trascinare un'istanza del `MarqueeBorder` controllo nell'area di `DemoMarqueeControl` progettazione. Ancorare questo `MarqueeBorder` controllo al controllo padre.

4. Trascinare un'istanza del `MarqueeText` controllo nell'area di `DemoMarqueeControl` progettazione.

5. Compilare la soluzione.

6. Fare clic con il pulsante destro del mouse su `DemoMarqueeControl` e dal menu di scelta rapida selezionare l'opzione **Esegui test** per avviare l'animazione. Fare clic su **Interrompi test** per arrestare l'animazione.

7. Aprire **Form1** nella visualizzazione progettazione.

8. Posizionare due <xref:System.Windows.Forms.Button> controlli nel form. Assegnare loro `startButton` un nome e `stopButton` , quindi modificare i <xref:System.Windows.Forms.Control.Text%2A> valori delle proprietà rispettivamente per **avviare** e **arrestare**.

9. Implementare <xref:System.Windows.Forms.Control.Click> i gestori eventi per entrambi i <xref:System.Windows.Forms.Button> controlli.

10. Nella **casella degli strumenti**aprire la scheda **componenti di MarqueeControlTest** . La `DemoMarqueeControl` selezione sarà disponibile.

11. Trascinare un'istanza di `DemoMarqueeControl` nell'area di progettazione **Form1** .

12. Nei <xref:System.Windows.Forms.Control.Click> gestori eventi, richiamare i `Start` `Stop` metodi e su `DemoMarqueeControl` .

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

13. Impostare il `MarqueeControlTest` progetto come progetto di avvio ed eseguirlo. Viene visualizzato il modulo che Visualizza il `DemoMarqueeControl` . Selezionare il pulsante **Avvia** per avviare l'animazione. Si noterà che il testo lampeggia e le luci si spostano attorno al bordo.

## <a name="next-steps"></a>Passaggi successivi

`MarqueeControlLibrary`Viene illustrata una semplice implementazione di controlli personalizzati e finestre di progettazione associate. Questo esempio può essere reso più sofisticato in diversi modi:

- Modificare i valori delle proprietà di `DemoMarqueeControl` nella finestra di progettazione. Aggiungere altri `MarqueBorder` controlli e ancorarli all'interno delle istanze padre per creare un effetto annidato. Provare a usare impostazioni diverse per `UpdatePeriod` e le proprietà correlate alla luce.

- Creare implementazioni personalizzate di `IMarqueeWidget` . È possibile, ad esempio, creare un segno "neon" lampeggiante o un segno animato con più immagini.

- Personalizzare ulteriormente l'esperienza in fase di progettazione. È possibile provare ad ombreggiare più proprietà rispetto <xref:System.Windows.Forms.Control.Enabled%2A> a e <xref:System.Windows.Forms.Control.Visible%2A> e aggiungere nuove proprietà. Aggiungere nuovi verbi di progettazione per semplificare attività comuni come l'ancoraggio dei controlli figlio.

- Concedere in licenza il `MarqueeControl` .

- Controllare la modalità di serializzazione dei controlli e il modo in cui viene generato il codice. Per altre informazioni, vedere [generazione e compilazione di codice sorgente dinamico](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
