---
title: 'Procedura dettagliata: disposizione di controlli Windows Form in WPF'
ms.custom: ''
ms.date: 04/03/2018
ms.prod: .net-framework
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4f3129b4128444530b1277299f3f95ce49232421
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Procedura dettagliata: disposizione di controlli Windows Form in WPF
Questa procedura dettagliata viene illustrato come utilizzare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le funzionalità di layout per disporre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli in un'applicazione ibrida.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione del progetto.  
  
-   Uso delle impostazioni di layout predefinite.  
  
-   Ridimensionamento in base al contenuto.  
  
-   Uso del posizionamento assoluto.  
  
-   Specifica esplicita delle dimensioni.  
  
-   Impostazione delle proprietà di layout.  
  
-   Informazioni sulle limitazioni di z order.  
  
-   Ancoraggio.  
  
-   Impostazione della visibilità.  
  
-   Hosting di un controllo che non si adatta.  
  
-   Ridimensionamento.  
  
-   Rotazione.  
  
-   Impostazione della spaziatura interna e dei margini.  
  
-   Uso di contenitori di layout dinamici.  
  
 Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [disposizione di controlli Windows Form in WPF](http://go.microsoft.com/fwlink/?LinkID=159971).  
  
 Al termine, si avrà una migliore comprensione di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] le caratteristiche di layout in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazioni basate su.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="creating-the-project"></a>Creazione del progetto  
  
#### <a name="to-create-and-set-up-the-project"></a>Per creare e impostare il progetto  
  
1.  Creare un progetto di applicazione WPF denominato `WpfLayoutHostingWf`.  
  
2.  In Esplora soluzioni aggiungere riferimenti agli assembly seguenti.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
    -   System.Drawing  
  
3.  Fare doppio clic sul file MainWindow.xaml per aprirlo nella visualizzazione XAML.  
  
4.  Nel <xref:System.Windows.Window> elemento, aggiungere il seguente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] mapping dello spazio dei nomi.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  Nel <xref:System.Windows.Controls.Grid> insieme di elementi di <xref:System.Windows.Controls.Grid.ShowGridLines%2A> proprietà `true` e definire cinque righe e tre colonne.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a>Uso delle impostazioni di layout predefinite  
 Per impostazione predefinita, il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento gestisce il layout del controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.  
  
#### <a name="to-use-default-layout-settings"></a>Per usare le impostazioni di layout predefinite  
  
1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> verrà visualizzato un controllo di <xref:System.Windows.Controls.Canvas>. Il controllo viene ridimensionato in base al contenuto e <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene ridimensionato in base al controllo ospitato.  
  
## <a name="sizing-to-content"></a>Ridimensionamento in base al contenuto  
 Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento garantisce che il controllo viene ridimensionato per visualizzare correttamente il contenuto.  
  
#### <a name="to-size-to-content"></a>Per ridimensionare in base al contenuto  
  
1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. I due nuovi controlli pulsante vengono ridimensionati per visualizzare correttamente, la stringa di testo più lungo e dimensione del carattere e il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementi vengono ridimensionati in base ai controlli ospitati.  
  
## <a name="using-absolute-positioning"></a>Uso del posizionamento assoluto  
 È possibile utilizzare il posizionamento assoluto per inserire il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento in un punto qualsiasi nell'interfaccia utente (UI).  
  
#### <a name="to-use-absolute-positioning"></a>Per usare il posizionamento assoluto  
  
1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene inserito 20 pixel dal lato superiore della cella della griglia e 20 pixel dal bordo sinistro.  
  
## <a name="specifying-size-explicitly"></a>Specifica esplicita delle dimensioni  
 È possibile specificare le dimensioni del <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento utilizzando il <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà.  
  
#### <a name="to-specify-size-explicitly"></a>Per specificare le dimensioni in modo esplicito  
  
1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento è impostato su una dimensione pari a 50 pixel in larghezza per 70 pixel di altezza, che è minore di impostazioni di layout predefinito. Il contenuto del [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene riordinato di conseguenza.  
  
## <a name="setting-layout-properties"></a>Impostazione delle proprietà di layout  
 Impostare sempre le proprietà relative al layout del controllo ospitato utilizzando le proprietà del <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. L'impostazione diretta delle proprietà di layout nel controllo ospitato darà risultati imprevisti.  
  
 Impostazione delle proprietà relative al layout del controllo ospitato in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non ha alcun effetto.  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a>Per visualizzare gli effetti dell'impostazione delle proprietà nel controllo  
  
1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  In Esplora soluzioni fare doppio clic su MainWindow.xaml. vb o MainWindow.xaml.cs per aprirlo nell'editor di codice.  
  
3.  Copiare il codice seguente nel `MainWindow` definizione di classe.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  Premere F5 per compilare ed eseguire l'applicazione.  
  
5.  Fare clic su di **Click me** pulsante. Il `button1_Click` gestore eventi imposta il <xref:System.Windows.Forms.Control.Top%2A> e <xref:System.Windows.Forms.Control.Left%2A> le proprietà del controllo ospitato. In questo modo il controllo ospitato venga riposizionato all'interno di <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. L'host mantiene la stessa area dello schermo, ma il controllo ospitato viene ritagliato. Al contrario, il controllo ospitato dovrebbe sempre occupare il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.  
  
## <a name="understanding-z-order-limitations"></a>Informazioni sulle limitazioni di z order  
 Visibile <xref:System.Windows.Forms.Integration.WindowsFormsHost> gli elementi vengono sempre disegnati sopra gli altri elementi WPF e non vengono influenzati dall'ordine z. Per visualizzare questo comportamento nell'ordine z, eseguire le operazioni seguenti:

1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
 
2.  Premere F5 per compilare ed eseguire l'applicazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> viene disegnato un elemento tramite l'elemento label.  


## <a name="docking"></a>Ancoraggio  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento supporta [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ancoraggio. Impostare il <xref:System.Windows.Controls.DockPanel.Dock%2A> proprietà associata per ancorare il controllo ospitato in un <xref:System.Windows.Controls.DockPanel> elemento.  
  
#### <a name="to-dock-a-hosted-control"></a>Per ancorare un controllo ospitato  
  
1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene ancorato al lato destro del <xref:System.Windows.Controls.DockPanel> elemento.  
  
## <a name="setting-visibility"></a>Impostazione della visibilità  
 È possibile rendere il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo invisibile o comprimerlo impostando il <xref:System.Windows.UIElement.Visibility%2A> proprietà il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. Quando un controllo non è visibile, non viene visualizzato, ma occupa spazio del layout. Quando un controllo è compresso, non viene visualizzato né occupa spazio del layout.  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a>Per impostare la visibilità di un controllo ospitato  
  
1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  In MainWindow.xaml.vb o MainWindow.xaml.cs copiare il codice seguente nella definizione della classe.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  Premere F5 per compilare ed eseguire l'applicazione.  
  
4.  Fare clic su di **fare clic per rendere invisibili** pulsante per rendere il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento invisibile.  
  
5.  Fare clic su di **fare clic per comprimere** pulsante per nascondere il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento dal layout completamente. Quando il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene compresso, gli elementi circostanti vengono riorganizzati in modo da occupare lo spazio.  
  
## <a name="hosting-a-control-that-does-not-stretch"></a>Hosting di un controllo che non si adatta  
 Alcuni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli hanno dimensioni fisse e non si adattano per riempire lo spazio disponibile nel layout. Ad esempio, il <xref:System.Windows.Forms.MonthCalendar> controllo consente di visualizzare un mese in uno spazio fisso.  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a>Per ospitare un controllo che non si adatta  
  
1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene centrato nella riga della griglia, ma non è estesa per riempire lo spazio disponibile. Se la finestra è sufficientemente grande, è possibile riscontrare due o più mesi tramite l'hosting <xref:System.Windows.Forms.MonthCalendar> controllo, ma questi sono centrati nella riga. Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motore di layout Centra gli elementi che non possono essere ridimensionati per riempire lo spazio disponibile.  
  
## <a name="scaling"></a>Ridimensionamento  
 A differenza degli elementi WPF, la maggior parte dei controlli Windows Form non sono scalabili in modo continuo. Consenta un ridimensionamento personalizzato, si esegue l'override di <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> metodo. 
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a>Per ridimensionare un controllo ospitato usando il comportamento predefinito  
  
1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il controllo ospitato e gli elementi che lo circondano vengono ridimensionati in base a un fattore di 0,5. Tuttavia il tipo di carattere del controllo ospitato non viene ridimensionato.

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>Rotazione  
 A differenza degli elementi WPF, controlli Windows Form non supportano la rotazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento non ruota con altri elementi di WPF quando viene applicata una trasformazione di rotazione. Qualsiasi valore di rotazione diverso da 180 gradi genera il <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> evento.
 
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a>Per visualizzare l'effetto di rotazione in un'applicazione ibrida  
  
1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il controllo ospitato non viene ruotato, ma i relativi elementi circostanti vengono ruotati di 180 gradi. Potrebbe essere necessario ridimensionare la finestra per vedere gli elementi.  
 

## <a name="setting-padding-and-margins"></a>Impostazione della spaziatura interna e dei margini  
 Spaziatura e margini in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout sono simili alla spaziatura interna e margini [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Impostare semplicemente il <xref:System.Windows.Controls.Control.Padding%2A> e <xref:System.Windows.FrameworkElement.Margin%2A> proprietà il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a>Per impostare spaziatura interna e margini per un controllo ospitato  
  
1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Le impostazioni di spaziatura e margini vengono applicate in essa contenuto [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli nello stesso modo in cui verrebbero applicate in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
## <a name="using-dynamic-layout-containers"></a>Uso di contenitori di layout dinamici  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] fornisce due contenitori di layout dinamico, <xref:System.Windows.Forms.FlowLayoutPanel> e <xref:System.Windows.Forms.TableLayoutPanel>. È inoltre possibile utilizzare questi contenitori in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout.  
  
#### <a name="to-use-a-dynamic-layout-container"></a>Per usare un contenitore di layout dinamico  
  
1.  Copiare il seguente codice XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  In MainWindow.xaml.vb o MainWindow.xaml.cs copiare il codice seguente nella definizione della classe.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  Aggiungere una chiamata al `InitializeFlowLayoutPanel` metodo nel costruttore.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  Premere F5 per compilare ed eseguire l'applicazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento riempie il <xref:System.Windows.Controls.DockPanel>, e <xref:System.Windows.Forms.FlowLayoutPanel> dispone i controlli figlio nel valore predefinito <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Considerazioni sul layout per l'elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [Disposizione dei Windows Form controlli nell'esempio di WPF](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
