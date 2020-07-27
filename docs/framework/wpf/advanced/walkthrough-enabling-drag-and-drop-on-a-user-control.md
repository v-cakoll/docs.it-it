---
title: 'Procedura dettagliata: Abilitare il trascinamento della selezione in un controllo utente'
description: Informazioni su come creare un controllo utente personalizzato che possa partecipare al trasferimento dei dati con trascinamento della selezione in Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 12ad47035a09995094014841b083062743fc2574
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168281"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a>Procedura dettagliata: Abilitare il trascinamento della selezione in un controllo utente

Questa procedura dettagliata illustra come creare un controllo utente personalizzato che possa partecipare al trasferimento di dati tramite trascinamento in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].

In questa procedura dettagliata verrà creato un oggetto WPF personalizzato <xref:System.Windows.Controls.UserControl> che rappresenta una forma circolare. Si implementeranno funzionalità nel controllo per consentire il trasferimento di dati tramite trascinamento. Ad esempio, se si trascina da un controllo Circle a un altro, i dati del colore di riempimento vengono copiati dal controllo Circle di origine a quello di destinazione. Se si trascina da un controllo Circle a un oggetto <xref:System.Windows.Controls.TextBox> , la rappresentazione di stringa del colore di riempimento viene copiata in <xref:System.Windows.Controls.TextBox> . Si creerà anche una piccola applicazione che contiene due controlli Panel e un oggetto <xref:System.Windows.Controls.TextBox> per testare la funzionalità di trascinamento della selezione. Si scriverà codice che consente ai pannelli di elaborare i dati Circle rilasciati per permettere di spostare o copiare cerchi dalla raccolta Children di un pannello all'altro.

Vengono illustrate le attività seguenti:

- Creare un controllo utente personalizzato.

- Consentire al controllo utente di essere un'origine di trascinamento.

- Consentire al controllo utente di essere un obiettivo di rilascio.

- Consentire a un pannello di ricevere dati rilasciati dal controllo utente.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-application-project"></a>Creare il progetto dell'applicazione
 In questa sezione verrà creata l'infrastruttura dell'applicazione, che include una pagina principale con due pannelli e un oggetto <xref:System.Windows.Controls.TextBox> .

1. Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato `DragDropExample`. Per altre informazioni, vedere [Procedura dettagliata: La prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

2. Aprire MainWindow.xaml.

3. Aggiungere il markup seguente tra i tag di apertura e di chiusura <xref:System.Windows.Controls.Grid> .

     Questo markup crea l'interfaccia utente per l'applicazione di prova.

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a>Aggiungere un nuovo controllo utente al progetto
 In questa sezione si aggiungerà un nuovo controllo utente al progetto.

1. Scegliere **Aggiungi controllo utente** dal menu Progetto.

2. Nella finestra di dialogo **Aggiungi nuovo elemento** modificare il nome in `Circle.xaml` , quindi fare clic su **Aggiungi**.

     Circle.xaml e il relativo code-behind vengono aggiunti al progetto.

3. Aprire Circle.xaml.

     Questo file conterrà gli elementi dell'interfaccia utente del controllo utente.

4. Aggiungere il markup seguente alla radice <xref:System.Windows.Controls.Grid> per creare un controllo utente semplice con un cerchio blu come interfaccia utente.

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. Aprire Circle.xaml.cs o Circle.xaml.vb.

6. In C# aggiungere il codice seguente dopo il costruttore senza parametri per creare un costruttore di copia. In Visual Basic aggiungere il codice seguente per creare un costruttore senza parametri e un costruttore di copia.

     Per consentire la copia del controllo utente, aggiungere un metodo di costruttore di copia nel file code-behind. Nel controllo utente Circle semplificato si copieranno solo il riempimento e le dimensioni del controllo utente.

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a>Aggiungere il controllo utente alla finestra principale

1. Aprire MainWindow.xaml.

2. Aggiungere il codice XAML seguente al <xref:System.Windows.Window> tag di apertura per creare un riferimento allo spazio dei nomi XML all'applicazione corrente.

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. Nel primo <xref:System.Windows.Controls.StackPanel> , aggiungere il codice XAML seguente per creare due istanze del controllo utente Circle nel primo pannello.

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     Il codice XAML completo per il pannello è analogo al seguente.

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a>Implementare gli eventi di origine del trascinamento nel controllo utente
 In questa sezione verrà eseguito l'override del <xref:System.Windows.UIElement.OnMouseMove%2A> metodo e verrà avviata l'operazione di trascinamento della selezione.

 Se viene avviato un trascinamento (viene premuto un pulsante del mouse e il mouse viene spostato), i dati verranno inseriti in un pacchetto da trasferire in un oggetto <xref:System.Windows.DataObject> . In questo caso, il controllo Circle assemblerà tre elementi di dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.

### <a name="to-initiate-a-drag-and-drop-operation"></a>Per avviare un'operazione di riempimento

1. Aprire Circle.xaml.cs o Circle.xaml.vb.

2. Aggiungere la seguente <xref:System.Windows.UIElement.OnMouseMove%2A> sostituzione per fornire la gestione delle classi per l' <xref:System.Windows.UIElement.MouseMove> evento.

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     Questo <xref:System.Windows.UIElement.OnMouseMove%2A> override esegue le attività seguenti:

    - Controlla se il pulsante sinistro del mouse viene premuto mentre il mouse è in movimento.

    - Inserisce i dati Circle in un oggetto <xref:System.Windows.DataObject> . In questo caso, il controllo Circle assembla tre elementi dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.

    - Chiama il <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> metodo statico per avviare l'operazione di trascinamento della selezione. Passare i tre parametri seguenti al <xref:System.Windows.DragDrop.DoDragDrop%2A> Metodo:

        - `dragSource` - Un riferimento a questo controllo.

        - `data`: Oggetto <xref:System.Windows.DataObject> creato nel codice precedente.

        - `allowedEffects`: Le operazioni di trascinamento della selezione consentite, ovvero <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move> .

3. Premere **F5** per compilare ed eseguire l'applicazione.

4. Fare clic su uno dei controlli Circle e trascinarlo sui pannelli, sull'altro cerchio e su <xref:System.Windows.Controls.TextBox> . Quando si trascina su <xref:System.Windows.Controls.TextBox> , il cursore cambia per indicare uno spostamento.

5. Quando si trascina un cerchio sul controllo <xref:System.Windows.Controls.TextBox> , premere il tasto **CTRL** . Notare come il cursore cambia aspetto per indicare una copia.

6. Trascinare e rilasciare un cerchio nell'oggetto <xref:System.Windows.Controls.TextBox> . La rappresentazione di stringa del colore di riempimento del cerchio viene aggiunta all'oggetto <xref:System.Windows.Controls.TextBox> .

     ![Rappresentazione del colore di riempimento del cerchio](./media/dragdrop-colorstring.png "DragDrop_ColorString")

Per impostazione predefinita, il cursore cambierà aspetto durante un'operazione di trascinamento per indicare l'effetto che avrà il rilascio dei dati. È possibile personalizzare il feedback fornito all'utente gestendo l' <xref:System.Windows.UIElement.GiveFeedback> evento e impostando un cursore diverso.

## <a name="give-feedback-to-the-user"></a>Inviare commenti e suggerimenti all'utente

1. Aprire Circle.xaml.cs o Circle.xaml.vb.

2. Aggiungere la seguente <xref:System.Windows.UIElement.OnGiveFeedback%2A> sostituzione per fornire la gestione delle classi per l' <xref:System.Windows.UIElement.GiveFeedback> evento.

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     Questo <xref:System.Windows.UIElement.OnGiveFeedback%2A> override esegue le attività seguenti:

    - Verifica i <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valori impostati nel gestore eventi dell'obiettivo di rilascio <xref:System.Windows.UIElement.DragOver> .

    - Imposta un cursore personalizzato in base al <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valore. Il cursore ha lo scopo di fornire un feedback visivo all'utente sull'effetto che avrà il rilascio dei dati.

3. Premere **F5** per compilare ed eseguire l'applicazione.

4. Trascinare uno dei controlli Circle sui pannelli, sull'altro cerchio e sull'oggetto <xref:System.Windows.Controls.TextBox> . Si noti che i cursori sono ora i cursori personalizzati specificati nella <xref:System.Windows.UIElement.OnGiveFeedback%2A> sostituzione.

     ![Trascina selezione con cursori personalizzati](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")

5. Selezionare il testo `green` da <xref:System.Windows.Controls.TextBox> .

6. Trascinare il testo `green` su un controllo Circle. Notare che vengono visualizzati i cursori predefiniti per indicare gli effetti dell'operazione di trascinamento. Il cursore di feedback viene sempre impostato dall'origine di trascinamento.

## <a name="implement-drop-target-events-in-the-user-control"></a>Implementare eventi di destinazione di rilascio nel controllo utente
 In questa sezione si specificherà che il controllo utente è un obiettivo di rilascio, si eseguirà l'override dei metodi che consentono al controllo utente di essere un obiettivo di rilascio e si elaboreranno i dati rilasciati sul controllo.

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a>Per consentire al controllo utente di essere un obiettivo di rilascio

1. Aprire Circle.xaml.

2. Nel tag di apertura <xref:System.Windows.Controls.UserControl> aggiungere la <xref:System.Windows.UIElement.AllowDrop%2A> proprietà e impostarla su `true` .

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

Il <xref:System.Windows.UIElement.OnDrop%2A> metodo viene chiamato quando la <xref:System.Windows.UIElement.AllowDrop%2A> proprietà è impostata su `true` e i dati dell'origine di trascinamento vengono rilasciati sul controllo utente Circle. In questo metodo si elaboreranno i dati rilasciati e li si applicheranno al controllo Circle.

### <a name="to-process-the-dropped-data"></a>Per elaborare i dati rilasciati

1. Aprire Circle.xaml.cs o Circle.xaml.vb.

2. Aggiungere la seguente <xref:System.Windows.UIElement.OnDrop%2A> sostituzione per fornire la gestione delle classi per l' <xref:System.Windows.UIElement.Drop> evento.

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     Questo <xref:System.Windows.UIElement.OnDrop%2A> override esegue le attività seguenti:

    - Usa il <xref:System.Windows.DataObject.GetDataPresent%2A> metodo per verificare se i dati trascinati contengono un oggetto String.

    - Usa il <xref:System.Windows.DataObject.GetData%2A> metodo per estrarre i dati di stringa, se presenti.

    - Usa un oggetto <xref:System.Windows.Media.BrushConverter> per tentare di convertire la stringa in un oggetto <xref:System.Windows.Media.Brush> .

    - Se la conversione ha esito positivo, applica il pennello all'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> dell'oggetto <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo Circle.

    - Contrassegna l' <xref:System.Windows.UIElement.Drop> evento come gestito. È necessario contrassegnare l'evento di trascinamento come gestito per segnalare agli altri elementi che ricevono l'evento che questo è stato gestito dal controllo utente Circle.

3. Premere **F5** per compilare ed eseguire l'applicazione.

4. Selezionare il testo `green` in <xref:System.Windows.Controls.TextBox> .

5. Trascinare il testo su un controllo Circle e rilasciarlo. Il controllo Circle passa da blu a verde.

     ![Converti stringa in pennello](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")

6. Digitare il testo `green` in <xref:System.Windows.Controls.TextBox> .

7. Selezionare il testo `gre` in <xref:System.Windows.Controls.TextBox> .

8. Trascinarlo su un controllo Circle e rilasciarlo. Notare che il cursore cambia aspetto per indicare che è consentito il trascinamento ma il colore del controllo Circle non cambia poiché `gre` non è un colore valido.

9. Trascinare dal controllo Circle verde e rilasciare sul controllo Circle blu. Il controllo Circle passa da blu a verde. Si noti che il cursore viene visualizzato a seconda che il <xref:System.Windows.Controls.TextBox> o il cerchio sia l'origine del trascinamento.

L'impostazione della <xref:System.Windows.UIElement.AllowDrop%2A> proprietà su `true` e l'elaborazione dei dati eliminati è tutto ciò che è necessario per consentire a un elemento di essere un obiettivo di rilascio. Tuttavia, per offrire un'esperienza utente migliore, è necessario gestire anche gli <xref:System.Windows.UIElement.DragEnter> <xref:System.Windows.UIElement.DragLeave> eventi, e <xref:System.Windows.UIElement.DragOver> . In questi eventi, è possibile eseguire controlli e offrire feedback all'utente prima che i dati vengono rilasciati.

Quando i dati vengono rilasciati sul controllo utente Circle, il controllo deve notificare all'origine di trascinamento se può elaborare i dati trascinati. Se il controllo non è in grado di elaborare i dati, deve rifiutare il rilascio. A tale scopo, si gestirà l' <xref:System.Windows.UIElement.DragOver> evento e si imposterà la <xref:System.Windows.DragEventArgs.Effects%2A> Proprietà.

### <a name="to-verify-that-the-data-drop-is-allowed"></a>Per verificare se il rilascio dei dati è consentito

1. Aprire Circle.xaml.cs o Circle.xaml.vb.

2. Aggiungere la seguente <xref:System.Windows.UIElement.OnDragOver%2A> sostituzione per fornire la gestione delle classi per l' <xref:System.Windows.UIElement.DragOver> evento.

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     Questo <xref:System.Windows.UIElement.OnDragOver%2A> override esegue le attività seguenti:

    - Imposta la proprietà <xref:System.Windows.DragEventArgs.Effects%2A> su <xref:System.Windows.DragDropEffects.None>.

    - Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se il controllo utente Circle può elaborare i dati trascinati.

    - Se il controllo utente può elaborare i dati, imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà su <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move> .

3. Premere **F5** per compilare ed eseguire l'applicazione.

4. Selezionare il testo `gre` in <xref:System.Windows.Controls.TextBox> .

5. Trascinare il testo su un controllo Circle. Notare che ora il cursore cambia aspetto per indicare che il trascinamento non è consentito poiché `gre` non è un colore valido.

 È possibile migliorare ulteriormente l'esperienza utente applicando un'anteprima dell'operazione di trascinamento. Per il controllo utente Circle, si eseguirà l'override dei <xref:System.Windows.UIElement.OnDragEnter%2A> <xref:System.Windows.UIElement.OnDragLeave%2A> metodi e. Quando i dati vengono trascinati sul controllo, lo sfondo corrente <xref:System.Windows.Shapes.Shape.Fill%2A> viene salvato in una variabile segnaposto. La stringa viene quindi convertita in un pennello e applicata all'oggetto <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del cerchio. Se i dati vengono trascinati fuori dal cerchio senza essere eliminati, il <xref:System.Windows.Shapes.Shape.Fill%2A> valore originale viene nuovamente applicato al cerchio.

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a>Per visualizzare in anteprima gli effetti dell'operazione di trascinamento

1. Aprire Circle.xaml.cs o Circle.xaml.vb.

2. Nella classe Circle dichiarare una <xref:System.Windows.Media.Brush> variabile privata denominata `_previousFill` e inizializzarla su `null` .

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. Aggiungere la seguente <xref:System.Windows.UIElement.OnDragEnter%2A> sostituzione per fornire la gestione delle classi per l' <xref:System.Windows.UIElement.DragEnter> evento.

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     Questo <xref:System.Windows.UIElement.OnDragEnter%2A> override esegue le attività seguenti:

    - Salva la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà dell'oggetto <xref:System.Windows.Shapes.Ellipse> nella `_previousFill` variabile.

    - Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se i dati possono essere convertiti in un oggetto <xref:System.Windows.Media.Brush> .

    - Se i dati vengono convertiti in un oggetto valido <xref:System.Windows.Media.Brush> , lo applica a <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> .

4. Aggiungere la seguente <xref:System.Windows.UIElement.OnDragLeave%2A> sostituzione per fornire la gestione delle classi per l' <xref:System.Windows.UIElement.DragLeave> evento.

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     Questo <xref:System.Windows.UIElement.OnDragLeave%2A> override esegue le attività seguenti:

    - Applica l'oggetto <xref:System.Windows.Media.Brush> salvato nella `_previousFill` variabile all'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> dell'oggetto <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo utente Circle.

5. Premere **F5** per compilare ed eseguire l'applicazione.

6. Selezionare il testo `green` in <xref:System.Windows.Controls.TextBox> .

7. Trascinare il testo su un controllo Circle senza rilasciarlo. Il controllo Circle passa da blu a verde.

     ![Visualizzare in anteprima gli effetti di un'operazione di trascinamento&#45;e&#45;drop](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")

8. Trascinare il testo dal controllo Circle. Il controllo Circle passa da verde a blu.

## <a name="enable-a-panel-to-receive-dropped-data"></a>Abilitare un pannello per la ricezione dei dati eliminati

In questa sezione si abilitano i pannelli che ospitano i controlli utente Circle in modo che fungano da destinazioni di rilascio per i dati del cerchio trascinato. Si implementerà il codice che consente di spostare un cerchio da un pannello a un altro o di creare una copia di un controllo Circle tenendo premuto il tasto **CTRL** mentre si trascina e si elimina un cerchio.

1. Aprire MainWindow.xaml.

2. Come illustrato nel codice XAML seguente, in ognuno dei <xref:System.Windows.Controls.StackPanel> controlli aggiungere i gestori per gli <xref:System.Windows.UIElement.DragOver> <xref:System.Windows.UIElement.Drop> eventi e. Assegnare un nome al <xref:System.Windows.UIElement.DragOver> gestore eventi, `panel_DragOver` , e denominare il <xref:System.Windows.UIElement.Drop> gestore dell'evento, `panel_Drop` .

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. Aprire MainWindows.xaml.cs o MainWindow.xaml.vb.

4. Aggiungere il codice seguente per il <xref:System.Windows.UIElement.DragOver> gestore eventi.

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     Questo <xref:System.Windows.UIElement.DragOver> gestore eventi esegue le attività seguenti:

    - Verifica che i dati trascinati contengano i dati "Object" inclusi nel pacchetto <xref:System.Windows.DataObject> dal controllo utente Circle e passati nella chiamata a <xref:System.Windows.DragDrop.DoDragDrop%2A> .

    - Se i dati dell'oggetto sono presenti, controlla se il tasto **CTRL** è premuto.

    - Se viene premuto il tasto **CTRL** , imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà su <xref:System.Windows.DragDropEffects.Copy> . In caso contrario, impostare la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà su <xref:System.Windows.DragDropEffects.Move> .

5. Aggiungere il codice seguente per il <xref:System.Windows.UIElement.Drop> gestore eventi.

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     Questo <xref:System.Windows.UIElement.Drop> gestore eventi esegue le attività seguenti:

    - Verifica se l' <xref:System.Windows.UIElement.Drop> evento è già stato gestito. Ad esempio, se un cerchio viene rilasciato in un altro cerchio che gestisce l' <xref:System.Windows.UIElement.Drop> evento, non si vuole che il pannello che contiene il cerchio lo gestisca anche.

    - Se l' <xref:System.Windows.UIElement.Drop> evento non viene gestito, controlla se il tasto **CTRL** è premuto.

    - Se si preme il tasto **CTRL** quando si <xref:System.Windows.UIElement.Drop> verifica l'evento, crea una copia del controllo Circle e la aggiunge alla <xref:System.Windows.Controls.Panel.Children%2A> raccolta di <xref:System.Windows.Controls.StackPanel> .

    - Se il tasto **CTRL** non è premuto, sposta il cerchio dalla <xref:System.Windows.Controls.Panel.Children%2A> raccolta del relativo pannello padre alla <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello su cui è stata rilasciata.

    - Imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà per notificare al <xref:System.Windows.DragDrop.DoDragDrop%2A> metodo se è stata eseguita un'operazione di spostamento o copia.

6. Premere **F5** per compilare ed eseguire l'applicazione.

7. Selezionare il testo `green` da <xref:System.Windows.Controls.TextBox> .

8. Trascinare il testo su un controllo Circle e rilasciarlo.

9. Trascinare un controllo Circle dal pannello di sinistra al pannello di destra e rilasciarlo. Il cerchio viene rimosso dalla <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello sinistro e aggiunto alla raccolta Children del pannello di destra.

10. Trascinare un controllo Circle dal pannello in cui si trova nell'altro pannello e rilasciarlo mentre si preme il tasto **CTRL** . Il cerchio viene copiato e la copia viene aggiunta alla <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello di destinazione.

     ![Trascinamento di un cerchio premendo CTRL](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sul trascinamento della selezione](drag-and-drop-overview.md)
