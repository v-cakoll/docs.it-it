---
title: 'Procedura dettagliata: Abilitare il trascinamento della selezione in un controllo utente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 9ffaab4115edec1fc0115b27b8904970854f79d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600674"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a>Procedura dettagliata: Abilitare il trascinamento della selezione in un controllo utente

Questa procedura dettagliata illustra come creare un controllo utente personalizzato che possa partecipare al trasferimento di dati tramite trascinamento in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].

In questa procedura dettagliata, si creerà un controllo personalizzato WPF <xref:System.Windows.Controls.UserControl> che rappresenta una forma circolare. Si implementeranno funzionalità nel controllo per consentire il trasferimento di dati tramite trascinamento. Ad esempio, se si trascina da un controllo Circle a un altro, i dati del colore di riempimento vengono copiati dal controllo Circle di origine a quello di destinazione. Se si trascina da un controllo Circle a un <xref:System.Windows.Controls.TextBox>, la rappresentazione di stringa del colore di riempimento viene copiata la <xref:System.Windows.Controls.TextBox>. Si creerà inoltre una piccola applicazione che contiene due controlli panel e un <xref:System.Windows.Controls.TextBox> per testare le funzionalità di trascinamento e rilascio. Si scriverà codice che consente ai pannelli di elaborare i dati Circle rilasciati per permettere di spostare o copiare cerchi dalla raccolta Children di un pannello all'altro.

Questa procedura dettagliata illustra le attività seguenti:

-   Creare un controllo utente personalizzato.

-   Consentire al controllo utente di essere un'origine di trascinamento.

-   Consentire al controllo utente di essere un obiettivo di rilascio.

-   Consentire a un pannello di ricevere dati rilasciati dal controllo utente.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-application-project"></a>Creare il progetto di applicazione
 In questa sezione si creerà l'infrastruttura dell'applicazione, che include una pagina principale con due pannelli e un <xref:System.Windows.Controls.TextBox>.

1.  Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato `DragDropExample`. Per altre informazioni, vedere [Procedura: Creare un nuovo progetto applicazione WPF](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).

2.  Aprire MainWindow.xaml.

3.  Aggiungere il markup seguente tra l'apertura e chiusura <xref:System.Windows.Controls.Grid> tag.

     Questo markup crea l'interfaccia utente per l'applicazione di prova.

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a>Aggiungere un nuovo controllo utente al progetto
 In questa sezione si aggiungerà un nuovo controllo utente al progetto.

1.  Scegliere **Aggiungi controllo utente** dal menu Progetto.

2.  Nel **Aggiungi nuovo elemento** finestra di dialogo, modificare il nome da `Circle.xaml`, fare clic su **Add**.

     Circle.xaml e il relativo code-behind vengono aggiunti al progetto.

3.  Aprire Circle.xaml.

     Questo file conterrà gli elementi dell'interfaccia utente del controllo utente.

4.  Aggiungere il markup seguente alla radice <xref:System.Windows.Controls.Grid> per creare un controllo utente semplice con un cerchio blu come interfaccia utente.

     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5.  Aprire Circle.xaml.cs o Circle.xaml.vb.

6.  In C# aggiungere il codice seguente dopo il costruttore predefinito per creare un costruttore di copia. In Visual Basic aggiungere il codice seguente per creare un costruttore predefinito e un costruttore di copia.

     Per consentire la copia del controllo utente, aggiungere un metodo di costruttore di copia nel file code-behind. Nel controllo utente Circle semplificato si copieranno solo il riempimento e le dimensioni del controllo utente.

     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a>Aggiungere il controllo utente alla finestra principale

1.  Aprire MainWindow.xaml.

2.  Aggiungere il seguente XAML per l'apertura <xref:System.Windows.Window> tag per creare un riferimento a spazio dei nomi XML per l'applicazione corrente.

    ```
    xmlns:local="clr-namespace:DragDropExample"
    ```

3.  Nel primo <xref:System.Windows.Controls.StackPanel>, aggiungere il seguente XAML per creare due istanze del controllo utente Circle nel primo pannello.

     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     Il codice XAML completo per il pannello è analogo al seguente.

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a>Implementare eventi di origine di trascinamento nel controllo utente
 In questa sezione si eseguirà l'override di <xref:System.Windows.UIElement.OnMouseMove%2A> (metodo) e avviare l'operazione di trascinamento e rilascio.

 Se viene avviato un trascinamento viene premuto un pulsante del mouse e il mouse viene spostato, verranno inseriti i dati per il trasferimento in un <xref:System.Windows.DataObject>. In questo caso, il controllo Circle assemblerà tre elementi di dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.

### <a name="to-initiate-a-drag-and-drop-operation"></a>Per avviare un'operazione di riempimento

1.  Aprire Circle.xaml.cs o Circle.xaml.vb.

2.  Aggiungere il codice seguente <xref:System.Windows.UIElement.OnMouseMove%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.MouseMove> evento.

     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     Ciò <xref:System.Windows.UIElement.OnMouseMove%2A> override esegue le attività seguenti:

    -   Controlla se il pulsante sinistro del mouse viene premuto mentre il mouse è in movimento.

    -   Assembla i dati Circle in una <xref:System.Windows.DataObject>. In questo caso, il controllo Circle assembla tre elementi dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.

    -   Chiama il metodo statico <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> metodo per avviare l'operazione di trascinamento e rilascio. Passare i tre parametri seguenti per il <xref:System.Windows.DragDrop.DoDragDrop%2A> metodo:

        -   `dragSource` - Un riferimento a questo controllo.

        -   `data` : Le <xref:System.Windows.DataObject> creato nel codice precedente.

        -   `allowedEffects` -Le operazioni di trascinamento e rilascio consentite, che sono <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.

3.  Premere **F5** per compilare ed eseguire l'applicazione.

4.  Fare clic su uno dei controlli Circle e trascinarlo sui pannelli, su altro controllo Circle e <xref:System.Windows.Controls.TextBox>. Quando viene trascinato sul <xref:System.Windows.Controls.TextBox>, il cursore cambia per indicare un'operazione di spostamento.

5.  Durante il trascinamento di un cerchio tramite il <xref:System.Windows.Controls.TextBox>, premere la **Ctrl** chiave. Notare come il cursore cambia aspetto per indicare una copia.

6.  Trascinare e rilasciare un controllo Circle sul <xref:System.Windows.Controls.TextBox>. Rappresentazione di stringa del colore di riempimento del cerchio viene aggiunto il <xref:System.Windows.Controls.TextBox>.

     ![Rappresentazione di stringa del colore di riempimento del controllo Circle](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")

Per impostazione predefinita, il cursore cambierà aspetto durante un'operazione di trascinamento per indicare l'effetto che avrà il rilascio dei dati. È possibile personalizzare il feedback fornito all'utente gestendo il <xref:System.Windows.UIElement.GiveFeedback> evento e l'impostazione di un cursore diverso.

## <a name="give-feedback-to-the-user"></a>Fornire commenti e suggerimenti all'utente

1.  Aprire Circle.xaml.cs o Circle.xaml.vb.

2.  Aggiungere il codice seguente <xref:System.Windows.UIElement.OnGiveFeedback%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.GiveFeedback> evento.

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     Ciò <xref:System.Windows.UIElement.OnGiveFeedback%2A> override esegue le attività seguenti:

    -   Controlla il <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> i valori impostati nell'obiettivo di rilascio <xref:System.Windows.UIElement.DragOver> gestore dell'evento.

    -   Impostare un cursore personalizzato in base il <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valore. Il cursore ha lo scopo di fornire un feedback visivo all'utente sull'effetto che avrà il rilascio dei dati.

3.  Premere **F5** per compilare ed eseguire l'applicazione.

4.  Trascinare uno del cerchio controlli sui pannelli, su altro controllo Circle e <xref:System.Windows.Controls.TextBox>. Si noti che i cursori sono ora i cursori personalizzati specificati nella <xref:System.Windows.UIElement.OnGiveFeedback%2A> eseguire l'override.

     ![Trascinamento con cursori personalizzati](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")

5.  Selezionare il testo `green` dal <xref:System.Windows.Controls.TextBox>.

6.  Trascinare il testo `green` su un controllo Circle. Notare che vengono visualizzati i cursori predefiniti per indicare gli effetti dell'operazione di trascinamento. Il cursore di feedback viene sempre impostato dall'origine di trascinamento.

## <a name="implement-drop-target-events-in-the-user-control"></a>Implementare gli eventi di destinazione di rilascio nel controllo utente
 In questa sezione si specificherà che il controllo utente è un obiettivo di rilascio, si eseguirà l'override dei metodi che consentono al controllo utente di essere un obiettivo di rilascio e si elaboreranno i dati rilasciati sul controllo.

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a>Per consentire al controllo utente di essere un obiettivo di rilascio

1.  Aprire Circle.xaml.

2.  Nell'apertura <xref:System.Windows.Controls.UserControl> tag, aggiungere i <xref:System.Windows.UIElement.AllowDrop%2A> proprietà e impostarla su `true`.

     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

Il <xref:System.Windows.UIElement.OnDrop%2A> metodo viene chiamato quando il <xref:System.Windows.UIElement.AllowDrop%2A> è impostata su `true` e dati dall'origine di trascinamento vengono rilasciati sul controllo utente Circle. In questo metodo si elaboreranno i dati rilasciati e li si applicheranno al controllo Circle.

### <a name="to-process-the-dropped-data"></a>Per elaborare i dati rilasciati

1.  Aprire Circle.xaml.cs o Circle.xaml.vb.

2.  Aggiungere il codice seguente <xref:System.Windows.UIElement.OnDrop%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.Drop> evento.

     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     Ciò <xref:System.Windows.UIElement.OnDrop%2A> override esegue le attività seguenti:

    -   Usa il <xref:System.Windows.DataObject.GetDataPresent%2A> metodo per verificare se i dati trascinati contengono un oggetto stringa.

    -   Usa il <xref:System.Windows.DataObject.GetData%2A> metodo per estrarre i dati stringa, se presente.

    -   Usa un' <xref:System.Windows.Media.BrushConverter> per provare a convertire la stringa in un <xref:System.Windows.Media.Brush>.

    -   Se la conversione ha esito positivo, si applica il pennello per il <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo Circle.

    -   Segni di <xref:System.Windows.UIElement.Drop> evento come gestito. È necessario contrassegnare l'evento di trascinamento come gestito per segnalare agli altri elementi che ricevono l'evento che questo è stato gestito dal controllo utente Circle.

3.  Premere **F5** per compilare ed eseguire l'applicazione.

4.  Selezionare il testo `green` nella <xref:System.Windows.Controls.TextBox>.

5.  Trascinare il testo su un controllo Circle e rilasciarlo. Il controllo Circle passa da blu a verde.

     ![Convertire una stringa in pennello](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")

6.  Digitare il testo `green` nella <xref:System.Windows.Controls.TextBox>.

7.  Selezionare il testo `gre` nella <xref:System.Windows.Controls.TextBox>.

8.  Trascinarlo su un controllo Circle e rilasciarlo. Notare che il cursore cambia aspetto per indicare che è consentito il trascinamento ma il colore del controllo Circle non cambia poiché `gre` non è un colore valido.

9. Trascinare dal controllo Circle verde e rilasciare sul controllo Circle blu. Il controllo Circle passa da blu a verde. Si noti che il cursore visualizzato dipende dal fatto che il <xref:System.Windows.Controls.TextBox> o cerchio è l'origine di trascinamento.

Impostando il <xref:System.Windows.UIElement.AllowDrop%2A> proprietà `true` ed elabora i dati rilasciati è tutto ciò che è necessaria per consentire un elemento per ottenere un obiettivo di rilascio. Per fornire un'esperienza utente migliore, tuttavia, è necessario gestire anche il <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, e <xref:System.Windows.UIElement.DragOver> eventi. In questi eventi, è possibile eseguire controlli e offrire feedback all'utente prima che i dati vengono rilasciati.

Quando i dati vengono rilasciati sul controllo utente Circle, il controllo deve notificare all'origine di trascinamento se può elaborare i dati trascinati. Se il controllo non è in grado di elaborare i dati, deve rifiutare il rilascio. A tale scopo, è necessario gestire il <xref:System.Windows.UIElement.DragOver> evento e impostare il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà.

### <a name="to-verify-that-the-data-drop-is-allowed"></a>Per verificare se il rilascio dei dati è consentito

1.  Aprire Circle.xaml.cs o Circle.xaml.vb.

2.  Aggiungere il codice seguente <xref:System.Windows.UIElement.OnDragOver%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.DragOver> evento.

     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     Ciò <xref:System.Windows.UIElement.OnDragOver%2A> override esegue le attività seguenti:

    -   Imposta la proprietà <xref:System.Windows.DragEventArgs.Effects%2A> su <xref:System.Windows.DragDropEffects.None>.

    -   Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se il controllo utente Circle può elaborare i dati trascinati.

    -   Se il controllo utente può elaborare i dati, imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.

3.  Premere **F5** per compilare ed eseguire l'applicazione.

4.  Selezionare il testo `gre` nella <xref:System.Windows.Controls.TextBox>.

5.  Trascinare il testo su un controllo Circle. Notare che ora il cursore cambia aspetto per indicare che il trascinamento non è consentito poiché `gre` non è un colore valido.

 È possibile migliorare ulteriormente l'esperienza utente applicando un'anteprima dell'operazione di trascinamento. Per il controllo utente Circle, si eseguirà l'override di <xref:System.Windows.UIElement.OnDragEnter%2A> e <xref:System.Windows.UIElement.OnDragLeave%2A> metodi. Quando i dati vengono trascinati sul controllo, lo sfondo corrente <xref:System.Windows.Shapes.Shape.Fill%2A> viene salvato in una variabile segnaposto. La stringa viene quindi convertita in un pennello e applicata al <xref:System.Windows.Shapes.Ellipse> che fornisce il cerchio dell'interfaccia utente. Se i dati vengono trascinati all'esterno del cerchio senza essere rilasciati, originale <xref:System.Windows.Shapes.Shape.Fill%2A> valore viene nuovamente applicato al controllo Circle.

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a>Per visualizzare in anteprima gli effetti dell'operazione di trascinamento

1.  Aprire Circle.xaml.cs o Circle.xaml.vb.

2.  Nella classe Circle dichiarare una privata <xref:System.Windows.Media.Brush> variabile denominata `_previousFill` e inizializzarla su `null`.

     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3.  Aggiungere il codice seguente <xref:System.Windows.UIElement.OnDragEnter%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.DragEnter> evento.

     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     Ciò <xref:System.Windows.UIElement.OnDragEnter%2A> override esegue le attività seguenti:

    -   Salva il <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà del <xref:System.Windows.Shapes.Ellipse> nel `_previousFill` variabile.

    -   Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se i dati possono essere convertiti in un <xref:System.Windows.Media.Brush>.

    -   Se i dati vengono convertiti in un oggetto valido <xref:System.Windows.Media.Brush>, viene applicata al <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse>.

4.  Aggiungere il codice seguente <xref:System.Windows.UIElement.OnDragLeave%2A> sottoposto a override per fornire la gestione delle classi di <xref:System.Windows.UIElement.DragLeave> evento.

     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     Ciò <xref:System.Windows.UIElement.OnDragLeave%2A> override esegue le attività seguenti:

    -   Si applica il <xref:System.Windows.Media.Brush> salvato nel `_previousFill` variabili per il <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo utente Circle.

5.  Premere **F5** per compilare ed eseguire l'applicazione.

6.  Selezionare il testo `green` nella <xref:System.Windows.Controls.TextBox>.

7.  Trascinare il testo su un controllo Circle senza rilasciarlo. Il controllo Circle passa da blu a verde.

     ![Visualizzare in anteprima gli effetti di un'operazione di trascinamento](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")

8.  Trascinare il testo dal controllo Circle. Il controllo Circle passa da verde a blu.

## <a name="enable-a-panel-to-receive-dropped-data"></a>Abilitare un pannello di ricevere dati rilasciati

In questa sezione si abilita i pannelli di ospitano controlli utente Circle per fungere da destinazioni di rilascio per i dati Circle trascinati. Si implementerà codice che consente di spostare un controllo Circle da un pannello a altro o per creare una copia di un controllo Circle tenendo premuto il **Ctrl** chiave durante il trascinamento della selezione di un cerchio.

1.  Aprire MainWindow.xaml.

2.  Come illustrato nella finestra di XAML seguente, in ognuna delle <xref:System.Windows.Controls.StackPanel> (controlli), aggiungere i gestori per il <xref:System.Windows.UIElement.DragOver> e <xref:System.Windows.UIElement.Drop> eventi. Nome di <xref:System.Windows.UIElement.DragOver> gestore eventi `panel_DragOver`e assegnare un nome il <xref:System.Windows.UIElement.Drop> gestore eventi, `panel_Drop`.

     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3.  Aprire MainWindows.xaml.cs o MainWindow.xaml.vb.

4.  Aggiungere il codice seguente per il <xref:System.Windows.UIElement.DragOver> gestore dell'evento.

     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     Ciò <xref:System.Windows.UIElement.DragOver> gestore eventi esegue le attività seguenti:

    -   Verifica che i dati trascinati contengano i dati "Object" che è stati inseriti nel <xref:System.Windows.DataObject> dal controllo utente Circle e passati nella chiamata a <xref:System.Windows.DragDrop.DoDragDrop%2A>.

    -   Se i dati "Object" sono presenti, controlla se il **Ctrl** viene premuto.

    -   Se il **Ctrl** viene premuto, imposta la <xref:System.Windows.DragEventArgs.Effects%2A> proprietà <xref:System.Windows.DragDropEffects.Copy>. In caso contrario, impostare il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà <xref:System.Windows.DragDropEffects.Move>.

5.  Aggiungere il codice seguente per il <xref:System.Windows.UIElement.Drop> gestore dell'evento.

     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     Ciò <xref:System.Windows.UIElement.Drop> gestore eventi esegue le attività seguenti:

    -   Controlla se il <xref:System.Windows.UIElement.Drop> evento è già stato gestito. Ad esempio, se viene eliminato un cerchio in un'altra Circle che gestisce il <xref:System.Windows.UIElement.Drop> evento, non si desidera il pannello che contiene il controllo Circle anche gestirla.

    -   Se il <xref:System.Windows.UIElement.Drop> evento non è gestito, controlla se il **Ctrl** viene premuto.

    -   Se il **Ctrl** premuto quando il <xref:System.Windows.UIElement.Drop> avviene, viene creata una copia del cerchio di controllo e aggiungerlo al <xref:System.Windows.Controls.Panel.Children%2A> raccolta del <xref:System.Windows.Controls.StackPanel>.

    -   Se il **Ctrl** non viene premuto, sposta il controllo Circle dal <xref:System.Windows.Controls.Panel.Children%2A> del pannello padre alla raccolta di <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello che è stato rilasciato.

    -   Set il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà per notificare il <xref:System.Windows.DragDrop.DoDragDrop%2A> metodo indica se è stata eseguita un'operazione di copia o spostamento.

6.  Premere **F5** per compilare ed eseguire l'applicazione.

7.  Selezionare il testo `green` dal <xref:System.Windows.Controls.TextBox>.

8.  Trascinare il testo su un controllo Circle e rilasciarlo.

9. Trascinare un controllo Circle dal pannello di sinistra al pannello di destra e rilasciarlo. Il controllo Circle viene rimosso dal <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello a sinistra e aggiunto alla raccolta Children del Pannello di destra.

10. Trascinare un controllo Circle dal Pannello di cui si trova a altro pannello e rilasciarlo mentre si tiene premuto il **Ctrl** chiave. Il controllo Circle viene copiato e la copia viene aggiunto al <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello del ricevente.

     ![Trascinamento di un controllo Circle mentre si preme CTRL](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sul trascinamento della selezione](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)