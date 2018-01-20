---
title: 'Procedura dettagliata: abilitare il trascinamento della selezione in un controllo utente'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d87872d3009b46878b7b614c1aef728d5b1d511d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a>Procedura dettagliata: abilitare il trascinamento della selezione in un controllo utente
Questa procedura dettagliata illustra come creare un controllo utente personalizzato che possa partecipare al trasferimento di dati tramite trascinamento in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 In questa procedura dettagliata, si creerà un controllo personalizzato WPF <xref:System.Windows.Controls.UserControl> che rappresenta una forma di cerchio. Si implementeranno funzionalità nel controllo per consentire il trasferimento di dati tramite trascinamento. Ad esempio, se si trascina da un controllo Circle a un altro, i dati del colore di riempimento vengono copiati dal controllo Circle di origine a quello di destinazione. Se si trascina da un controllo cerchio per un <xref:System.Windows.Controls.TextBox>, la rappresentazione di stringa del colore di riempimento viene copiata il <xref:System.Windows.Controls.TextBox>. Si creerà inoltre una piccola applicazione che contiene due controlli pannello e <xref:System.Windows.Controls.TextBox> per testare le funzionalità di trascinamento e rilascio. Si scriverà codice che consente ai pannelli di elaborare i dati Circle rilasciati per permettere di spostare o copiare cerchi dalla raccolta Children di un pannello all'altro.  
  
 Questa procedura dettagliata illustra le attività seguenti:  
  
-   Creare un controllo utente personalizzato.  
  
-   Consentire al controllo utente di essere un'origine di trascinamento.  
  
-   Consentire al controllo utente di essere un obiettivo di rilascio.  
  
-   Consentire a un pannello di ricevere dati rilasciati dal controllo utente.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   Visual Studio 2010  
  
## <a name="creating-the-application-project"></a>Creazione del progetto di applicazione  
 In questa sezione si creerà l'infrastruttura dell'applicazione, che include una pagina principale con due pannelli e un <xref:System.Windows.Controls.TextBox>.  
  
### <a name="to-create-the-project"></a>Per creare il progetto  
  
1.  Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato `DragDropExample`. Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Aprire MainWindow.xaml.  
  
3.  Aggiungere il markup seguente tra i tag <xref:System.Windows.Controls.Grid> tag.  
  
     Questo markup crea l'interfaccia utente per l'applicazione di prova.  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## <a name="adding-a-new-user-control-to-the-project"></a>Aggiunta di un nuovo controllo utente al progetto  
 In questa sezione si aggiungerà un nuovo controllo utente al progetto.  
  
### <a name="to-add-a-new-user-control"></a>Per aggiungere un nuovo controllo utente  
  
1.  Scegliere **Aggiungi controllo utente** dal menu Progetto.  
  
2.  Nella finestra di dialogo Aggiungi nuovo elemento modificare il nome in `Circle.xaml` e fare clic su **Aggiungi**.  
  
     Circle.xaml e il relativo code-behind vengono aggiunti al progetto.  
  
3.  Aprire Circle.xaml.  
  
     Questo file conterrà gli elementi dell'interfaccia utente del controllo utente.  
  
4.  Aggiungere il markup seguente alla radice <xref:System.Windows.Controls.Grid> per creare un controllo utente semplice che dispone di un cerchio blu come relativa interfaccia utente.  
  
     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  Aprire Circle.xaml.cs o Circle.xaml.vb.  
  
6.  In C# aggiungere il codice seguente dopo il costruttore predefinito per creare un costruttore di copia. In Visual Basic aggiungere il codice seguente per creare un costruttore predefinito e un costruttore di copia.  
  
     Per consentire la copia del controllo utente, aggiungere un metodo di costruttore di copia nel file code-behind. Nel controllo utente Circle semplificato si copieranno solo il riempimento e le dimensioni del controllo utente.  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### <a name="to-add-the-user-control-to-the-main-window"></a>Per aggiungere il controllo utente alla finestra principale  
  
1.  Aprire MainWindow.xaml.  
  
2.  Aggiungere il codice XAML seguente all'apertura <xref:System.Windows.Window> tag per creare un riferimento dello spazio dei nomi XML all'applicazione corrente.  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  Nel primo <xref:System.Windows.Controls.StackPanel>, aggiungere il codice XAML seguente per creare due istanze del controllo utente Circle nel primo pannello.  
  
     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     Il codice XAML completo per il pannello è analogo al seguente.  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## <a name="implementing-drag-source-events-in-the-user-control"></a>Implementazione di eventi di origine di trascinamento nel controllo utente  
 In questa sezione, si eseguirà l'override di <xref:System.Windows.UIElement.OnMouseMove%2A> (metodo) e avviare l'operazione di trascinamento e rilascio.  
  
 Se viene avviato un trascinamento viene premuto un pulsante del mouse e il mouse viene spostato, si creerà un pacchetto di dati da trasferire in un <xref:System.Windows.DataObject>. In questo caso, il controllo Circle assemblerà tre elementi di dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.  
  
### <a name="to-initiate-a-drag-and-drop-operation"></a>Per avviare un'operazione di riempimento  
  
1.  Aprire Circle.xaml.cs o Circle.xaml.vb.  
  
2.  Aggiungere il seguente <xref:System.Windows.UIElement.OnMouseMove%2A> override di gestione delle classi per fornire il <xref:System.Windows.UIElement.MouseMove> evento.  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     Questo <xref:System.Windows.UIElement.OnMouseMove%2A> override esegue le attività seguenti:  
  
    -   Controlla se il pulsante sinistro del mouse viene premuto mentre il mouse è in movimento.  
  
    -   Pacchetti di dati di Circle in un <xref:System.Windows.DataObject>. In questo caso, il controllo Circle assembla tre elementi dati: una rappresentazione di stringa del colore di riempimento, una rappresentazione doppia dell'altezza e una copia di se stesso.  
  
    -   Chiama il metodo statico <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> per avviare l'operazione di trascinamento e rilascio. Passare i seguenti tre parametri per il <xref:System.Windows.DragDrop.DoDragDrop%2A> metodo:  
  
        -   `dragSource` - Un riferimento a questo controllo.  
  
        -   `data`– La <xref:System.Windows.DataObject> creato nel codice precedente.  
  
        -   `allowedEffects`: Le operazioni di trascinamento e rilascio consentite, che sono <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.  
  
3.  Premere F5 per compilare ed eseguire l'applicazione.  
  
4.  Fare clic su uno dei controlli Circle e trascinarlo sui pannelli, cerchio e <xref:System.Windows.Controls.TextBox>. Quando viene trascinato sul <xref:System.Windows.Controls.TextBox>, il cursore cambia per indicare uno spostamento.  
  
5.  Durante il trascinamento di un cerchio sul <xref:System.Windows.Controls.TextBox>, premere il tasto CTRL. Notare come il cursore cambia aspetto per indicare una copia.  
  
6.  Trascinare e rilasciare un cerchio sul <xref:System.Windows.Controls.TextBox>. Rappresentazione di stringa del colore di riempimento del cerchio viene aggiunto per il <xref:System.Windows.Controls.TextBox>.  
  
     ![Rappresentazione di stringa del colore di riempimento del controllo Circle](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")  
  
 Per impostazione predefinita, il cursore cambierà aspetto durante un'operazione di trascinamento per indicare l'effetto che avrà il rilascio dei dati. È possibile personalizzare il feedback fornito all'utente gestendo il <xref:System.Windows.UIElement.GiveFeedback> evento e l'impostazione di un cursore diverso.  
  
### <a name="to-give-feedback-to-the-user"></a>Per fornire un feedback all'utente  
  
1.  Aprire Circle.xaml.cs o Circle.xaml.vb.  
  
2.  Aggiungere il seguente <xref:System.Windows.UIElement.OnGiveFeedback%2A> override di gestione delle classi per fornire il <xref:System.Windows.UIElement.GiveFeedback> evento.  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     Questo <xref:System.Windows.UIElement.OnGiveFeedback%2A> override esegue le attività seguenti:  
  
    -   Controlla il <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valori impostati nella destinazione di trascinamento <xref:System.Windows.UIElement.DragOver> gestore dell'evento.  
  
    -   Imposta un cursore personalizzato in base il <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valore. Il cursore ha lo scopo di fornire un feedback visivo all'utente sull'effetto che avrà il rilascio dei dati.  
  
3.  Premere F5 per compilare ed eseguire l'applicazione.  
  
4.  Trascinare uno del cerchio controlli sui pannelli, cerchio, e <xref:System.Windows.Controls.TextBox>. Si noti che i cursori sono ora i cursori personalizzati specificati nel <xref:System.Windows.UIElement.OnGiveFeedback%2A> eseguire l'override.  
  
     ![Trascinamento con cursori personalizzati](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")  
  
5.  Selezionare il testo `green` dal <xref:System.Windows.Controls.TextBox>.  
  
6.  Trascinare il testo `green` su un controllo Circle. Notare che vengono visualizzati i cursori predefiniti per indicare gli effetti dell'operazione di trascinamento. Il cursore di feedback viene sempre impostato dall'origine di trascinamento.  
  
## <a name="implementing-drop-target-events-in-the-user-control"></a>Implementazione di eventi di obiettivo di rilascio nel controllo utente  
 In questa sezione si specificherà che il controllo utente è un obiettivo di rilascio, si eseguirà l'override dei metodi che consentono al controllo utente di essere un obiettivo di rilascio e si elaboreranno i dati rilasciati sul controllo.  
  
### <a name="to-enable-the-user-control-to-be-a-drop-target"></a>Per consentire al controllo utente di essere un obiettivo di rilascio  
  
1.  Aprire Circle.xaml.  
  
2.  Nell'apertura <xref:System.Windows.Controls.UserControl> tag, aggiungere il <xref:System.Windows.UIElement.AllowDrop%2A> proprietà e impostarla su `true`.  
  
     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 Il <xref:System.Windows.UIElement.OnDrop%2A> metodo viene chiamato quando il <xref:System.Windows.UIElement.AllowDrop%2A> è impostata su `true` e dati dall'origine di trascinamento viene eliminati il controllo utente Circle. In questo metodo si elaboreranno i dati rilasciati e li si applicheranno al controllo Circle.  
  
### <a name="to-process-the-dropped-data"></a>Per elaborare i dati rilasciati  
  
1.  Aprire Circle.xaml.cs o Circle.xaml.vb.  
  
2.  Aggiungere il seguente <xref:System.Windows.UIElement.OnDrop%2A> override di gestione delle classi per fornire il <xref:System.Windows.UIElement.Drop> evento.  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     Questo <xref:System.Windows.UIElement.OnDrop%2A> override esegue le attività seguenti:  
  
    -   Usa il <xref:System.Windows.DataObject.GetDataPresent%2A> metodo per verificare se i dati trascinati contengano un oggetto stringa.  
  
    -   Usa il <xref:System.Windows.DataObject.GetData%2A> metodo per estrarre i dati stringa, se presente.  
  
    -   Usa un <xref:System.Windows.Media.BrushConverter> per tentare di convertire la stringa in un <xref:System.Windows.Media.Brush>.  
  
    -   Se la conversione ha esito positivo, viene applicato il pennello per il <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo Circle.  
  
    -   I segni di <xref:System.Windows.UIElement.Drop> evento come gestito. È necessario contrassegnare l'evento di trascinamento come gestito per segnalare agli altri elementi che ricevono l'evento che questo è stato gestito dal controllo utente Circle.  
  
3.  Premere F5 per compilare ed eseguire l'applicazione.  
  
4.  Selezionare il testo `green` nel <xref:System.Windows.Controls.TextBox>.  
  
5.  Trascinare il testo su un controllo Circle e rilasciarlo. Il controllo Circle passa da blu a verde.  
  
     ![Convertire una stringa in pennello](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")  
  
6.  Digitare il testo `green` nel <xref:System.Windows.Controls.TextBox>.  
  
7.  Selezionare il testo `gre` nel <xref:System.Windows.Controls.TextBox>.  
  
8.  Trascinarlo su un controllo Circle e rilasciarlo. Notare che il cursore cambia aspetto per indicare che è consentito il trascinamento ma il colore del controllo Circle non cambia poiché `gre` non è un colore valido.  
  
9. Trascinare dal controllo Circle verde e rilasciare sul controllo Circle blu. Il controllo Circle passa da blu a verde. Si noti che il cursore visualizzato dipende dal fatto che il <xref:System.Windows.Controls.TextBox> o il cerchio è l'origine di trascinamento.  
  
 L'impostazione di <xref:System.Windows.UIElement.AllowDrop%2A> proprietà `true` e l'elaborazione dei dati eliminati è tutto ciò che è necessaria per consentire a un elemento di un obiettivo di rilascio. Per fornire una migliore esperienza utente, tuttavia, è necessario gestire anche il <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, e <xref:System.Windows.UIElement.DragOver> eventi. In questi eventi, è possibile eseguire controlli e offrire feedback all'utente prima che i dati vengono rilasciati.  
  
 Quando i dati vengono rilasciati sul controllo utente Circle, il controllo deve notificare all'origine di trascinamento se può elaborare i dati trascinati. Se il controllo non è in grado di elaborare i dati, deve rifiutare il rilascio. A tale scopo, è necessario gestire il <xref:System.Windows.UIElement.DragOver> evento e impostare il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà.  
  
### <a name="to-verify-that-the-data-drop-is-allowed"></a>Per verificare se il rilascio dei dati è consentito  
  
1.  Aprire Circle.xaml.cs o Circle.xaml.vb.  
  
2.  Aggiungere il seguente <xref:System.Windows.UIElement.OnDragOver%2A> override di gestione delle classi per fornire il <xref:System.Windows.UIElement.DragOver> evento.  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     Questo <xref:System.Windows.UIElement.OnDragOver%2A> override esegue le attività seguenti:  
  
    -   Imposta la proprietà <xref:System.Windows.DragEventArgs.Effects%2A> su <xref:System.Windows.DragDropEffects.None>.  
  
    -   Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se il controllo utente Circle può elaborare i dati trascinati.  
  
    -   Se il controllo utente può elaborare i dati, imposta il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move>.  
  
3.  Premere F5 per compilare ed eseguire l'applicazione.  
  
4.  Selezionare il testo `gre` nel <xref:System.Windows.Controls.TextBox>.  
  
5.  Trascinare il testo su un controllo Circle. Notare che ora il cursore cambia aspetto per indicare che il trascinamento non è consentito poiché `gre` non è un colore valido.  
  
 È possibile migliorare ulteriormente l'esperienza utente applicando un'anteprima dell'operazione di trascinamento. Per il controllo utente di cerchio, si eseguirà l'override di <xref:System.Windows.UIElement.OnDragEnter%2A> e <xref:System.Windows.UIElement.OnDragLeave%2A> metodi. Quando i dati viene trascinati sul controllo, lo sfondo corrente <xref:System.Windows.Shapes.Shape.Fill%2A> viene salvato in una variabile di segnaposto. La stringa viene quindi convertita in un pennello e applicare il <xref:System.Windows.Shapes.Ellipse> che fornisce il cerchio dell'interfaccia utente. Se i dati viene trascinati fuori il cerchio senza essere rilasciato originale <xref:System.Windows.Shapes.Shape.Fill%2A> valore viene applicato di nuovo al cerchio.  
  
### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a>Per visualizzare in anteprima gli effetti dell'operazione di trascinamento  
  
1.  Aprire Circle.xaml.cs o Circle.xaml.vb.  
  
2.  Nella classe Circle, dichiarare una privata <xref:System.Windows.Media.Brush> variabile denominata `_previousFill` e inizializzarla su `null`.  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  Aggiungere il seguente <xref:System.Windows.UIElement.OnDragEnter%2A> override di gestione delle classi per fornire il <xref:System.Windows.UIElement.DragEnter> evento.  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     Questo <xref:System.Windows.UIElement.OnDragEnter%2A> override esegue le attività seguenti:  
  
    -   Salva il <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà del <xref:System.Windows.Shapes.Ellipse> nel `_previousFill` variabile.  
  
    -   Esegue gli stessi controlli che vengono eseguiti nel <xref:System.Windows.UIElement.OnDrop%2A> metodo per determinare se i dati possono essere convertiti in un <xref:System.Windows.Media.Brush>.  
  
    -   Se i dati vengono convertiti in un oggetto valido <xref:System.Windows.Media.Brush>, viene applicato per la <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse>.  
  
4.  Aggiungere il seguente <xref:System.Windows.UIElement.OnDragLeave%2A> override di gestione delle classi per fornire il <xref:System.Windows.UIElement.DragLeave> evento.  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     Questo <xref:System.Windows.UIElement.OnDragLeave%2A> override esegue le attività seguenti:  
  
    -   Si applica il <xref:System.Windows.Media.Brush> salvato nel `_previousFill` variabile il <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> che fornisce l'interfaccia utente del controllo utente cerchio.  
  
5.  Premere F5 per compilare ed eseguire l'applicazione.  
  
6.  Selezionare il testo `green` nel <xref:System.Windows.Controls.TextBox>.  
  
7.  Trascinare il testo su un controllo Circle senza rilasciarlo. Il controllo Circle passa da blu a verde.  
  
     ![Visualizzare in anteprima gli effetti di un'operazione di trascinamento](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")  
  
8.  Trascinare il testo dal controllo Circle. Il controllo Circle passa da verde a blu.  
  
## <a name="enabling-a-panel-to-receive-dropped-data"></a>Consentire a un pannello di ricevere i dati rilasciati  
 In questa sezione si consentirà ai pannelli di ospitare controlli utente Circle che fungono da obiettivi di rilascio per i dati Circle trascinati. Si implementerà codice che consente di spostare un controllo Circle da un pannello a un altro o di eseguire una copia di un controllo Circle tenendo premuto CTRL mentre lo si trascina.  
  
### <a name="to-enable-the-panel-to-be-a-drop-target"></a>Per consentire al pannello di essere un obiettivo di rilascio  
  
1.  Aprire MainWindow.xaml.  
  
2.  Come illustrato nel codice XAML seguente, in ogni il <xref:System.Windows.Controls.StackPanel> controlli, aggiungere i gestori per il <xref:System.Windows.UIElement.DragOver> e <xref:System.Windows.UIElement.Drop> eventi. Nome di <xref:System.Windows.UIElement.DragOver> gestore eventi, `panel_DragOver`e il nome di <xref:System.Windows.UIElement.Drop> gestore eventi, `panel_Drop`.  
  
     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  Aprire MainWindows.xaml.cs o MainWindow.xaml.vb.  
  
4.  Aggiungere il codice seguente per il <xref:System.Windows.UIElement.DragOver> gestore dell'evento.  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     Questo <xref:System.Windows.UIElement.DragOver> gestore esegue le attività seguenti:  
  
    -   Controlla che i dati trascinati contengano i dati "Oggetto" in cui è stati distribuiti il <xref:System.Windows.DataObject> dal controllo utente cerchio e passato nella chiamata a <xref:System.Windows.DragDrop.DoDragDrop%2A>.  
  
    -   Se i dati "Object" non sono presenti, controlla se viene premuto CTRL.  
  
    -   Se viene premuto il tasto CTRL, imposta il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà <xref:System.Windows.DragDropEffects.Copy>. In caso contrario, impostare il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà <xref:System.Windows.DragDropEffects.Move>.  
  
5.  Aggiungere il codice seguente per il <xref:System.Windows.UIElement.Drop> gestore dell'evento.  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     Questo <xref:System.Windows.UIElement.Drop> gestore esegue le attività seguenti:  
  
    -   Controlla se il <xref:System.Windows.UIElement.Drop> evento è già stato gestito. Ad esempio, se viene eliminato un cerchio in un'altra Circle che gestisce il <xref:System.Windows.UIElement.Drop> evento, il pannello che contiene il cerchio per gestire anche non si desidera.  
  
    -   Se il <xref:System.Windows.UIElement.Drop> evento non viene gestita, verifica se viene premuto il tasto CTRL.  
  
    -   Se viene premuto il tasto CTRL quando il <xref:System.Windows.UIElement.Drop> si verifica, viene creata una copia del cerchio e aggiungerlo al <xref:System.Windows.Controls.Panel.Children%2A> insieme del <xref:System.Windows.Controls.StackPanel>.  
  
    -   Se non viene premuto il tasto CTRL, sposta il cerchio dal <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello padre per il <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello che è stato eliminato.  
  
    -   Imposta il <xref:System.Windows.DragEventArgs.Effects%2A> proprietà per notificare il <xref:System.Windows.DragDrop.DoDragDrop%2A> metodo se viene eseguita un'operazione di copia o spostamento.  
  
6.  Premere F5 per compilare ed eseguire l'applicazione.  
  
7.  Selezionare il testo `green` dal <xref:System.Windows.Controls.TextBox>.  
  
8.  Trascinare il testo su un controllo Circle e rilasciarlo.  
  
9. Trascinare un controllo Circle dal pannello di sinistra al pannello di destra e rilasciarlo. Il cerchio viene rimosso dal <xref:System.Windows.Controls.Panel.Children%2A> raccolta del riquadro sinistro e aggiunto alla raccolta di elementi figlio del Pannello di destra.  
  
10. Trascinare un controllo Circle dal pannello in cui si trova all'altro pannello premendo CTRL. Il cerchio viene copiato e la copia viene aggiunta la <xref:System.Windows.Controls.Panel.Children%2A> raccolta del pannello ricevente.  
  
     ![Trascinamento di un controllo Circle mentre si preme CTRL](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sul trascinamento della selezione](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
