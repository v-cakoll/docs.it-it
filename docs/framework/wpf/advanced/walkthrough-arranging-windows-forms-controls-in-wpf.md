---
title: 'Procedura dettagliata: disposizione di controlli Windows Form in WPF'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: 98b108be518a9fef03ee299d43ed591cf736f68f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43786083"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Procedura dettagliata: disposizione di controlli Windows Form in WPF
Questa procedura dettagliata illustra come usare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funzionalità di layout per disporre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli in un'applicazione ibrida.  
  
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
  
 Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).  
  
 Al termine, si avrà una migliore comprensione del [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] le funzionalità di layout in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazioni basate su.  
  
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
  
4.  Nel <xref:System.Windows.Window> elemento, aggiungere il codice seguente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] mapping dello spazio dei nomi.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  Nel <xref:System.Windows.Controls.Grid> insieme di elementi di <xref:System.Windows.Controls.Grid.ShowGridLines%2A> proprietà `true` e definire cinque righe e tre colonne.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a>Uso delle impostazioni di layout predefinite  
 Per impostazione predefinita, il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento gestisce il layout del controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.  
  
#### <a name="to-use-default-layout-settings"></a>Per usare le impostazioni di layout predefinite  
  
1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> verrà visualizzato nel controllo di <xref:System.Windows.Controls.Canvas>. Il controllo ospitato viene ridimensionato in base al contenuto e <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene ridimensionato in base al controllo ospitato.  
  
## <a name="sizing-to-content"></a>Ridimensionamento in base al contenuto  
 Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento garantisce che il controllo ospitato venga ridimensionato per visualizzare correttamente il contenuto.  
  
#### <a name="to-size-to-content"></a>Per ridimensionare in base al contenuto  
  
1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. I due nuovi controlli pulsante vengono ridimensionati per visualizzare correttamente, la stringa di testo più lunga e dimensione del carattere e il <xref:System.Windows.Forms.Integration.WindowsFormsHost> gli elementi vengono ridimensionati in base ai controlli ospitati.  
  
## <a name="using-absolute-positioning"></a>Uso del posizionamento assoluto  
 È possibile usare il posizionamento assoluto per posizionare il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento in un punto qualsiasi nell'interfaccia utente (UI).  
  
#### <a name="to-use-absolute-positioning"></a>Per usare il posizionamento assoluto  
  
1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene inserito 20 pixel dal lato superiore della cella della griglia e 20 pixel da sinistra.  
  
## <a name="specifying-size-explicitly"></a>Specifica esplicita delle dimensioni  
 È possibile specificare le dimensioni dei <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento usando il <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà.  
  
#### <a name="to-specify-size-explicitly"></a>Per specificare le dimensioni in modo esplicito  
  
1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento è impostato su una dimensione di 50 pixel di larghezza per 70 pixel di altezza, ovvero inferiore a quelle del layout predefinito. Il contenuto di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene ridisposto di conseguenza.  
  
## <a name="setting-layout-properties"></a>Impostazione delle proprietà di layout  
 Sempre impostato le proprietà correlate al layout del controllo ospitato usando le proprietà del <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. L'impostazione diretta delle proprietà di layout nel controllo ospitato darà risultati imprevisti.  
  
 Impostazione delle proprietà correlate al layout del controllo ospitato in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non ha alcun effetto.  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a>Per visualizzare gli effetti dell'impostazione delle proprietà nel controllo  
  
1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  In Esplora soluzioni fare doppio clic su MainWindow.xaml. vb o MainWindow.xaml.cs per aprirlo nell'editor di codice.  
  
3.  Copiare il codice seguente nel `MainWindow` definizione di classe.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  Premere F5 per compilare ed eseguire l'applicazione.  
  
5.  Scegliere il **Click me** pulsante. Il `button1_Click` eventi gestore imposta la <xref:System.Windows.Forms.Control.Top%2A> e <xref:System.Windows.Forms.Control.Left%2A> proprietà nel controllo ospitato. In questo modo il controllo ospitato venga riposizionato all'interno di <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. L'host mantiene la stessa area dello schermo, ma il controllo ospitato viene ritagliato. Al contrario, il controllo ospitato dovrebbe sempre occupare il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.  
  
## <a name="understanding-z-order-limitations"></a>Informazioni sulle limitazioni di z order  
 Visibile <xref:System.Windows.Forms.Integration.WindowsFormsHost> gli elementi vengono sempre disegnati sopra altri elementi WPF e non sono interessate dal z order. Per visualizzare questo comportamento di z order, eseguire le operazioni seguenti:

1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
 
2.  Premere F5 per compilare ed eseguire l'applicazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene disegnato sopra l'elemento label.  


## <a name="docking"></a>Ancoraggio  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento supporta [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ancoraggio. Impostare il <xref:System.Windows.Controls.DockPanel.Dock%2A> proprietà associata per ancorare il controllo ospitato in un <xref:System.Windows.Controls.DockPanel> elemento.  
  
#### <a name="to-dock-a-hosted-control"></a>Per ancorare un controllo ospitato  
  
1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> l'elemento è ancorato al lato destro del <xref:System.Windows.Controls.DockPanel> elemento.  
  
## <a name="setting-visibility"></a>Impostazione della visibilità  
 È possibile rendere il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo invisibile o comprimerlo impostando la <xref:System.Windows.UIElement.Visibility%2A> proprietà il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. Quando un controllo non è visibile, non viene visualizzato, ma occupa spazio del layout. Quando un controllo è compresso, non viene visualizzato né occupa spazio del layout.  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a>Per impostare la visibilità di un controllo ospitato  
  
1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  In MainWindow.xaml.vb o MainWindow.xaml.cs copiare il codice seguente nella definizione della classe.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  Premere F5 per compilare ed eseguire l'applicazione.  
  
4.  Fare clic sui **fare clic per rendere invisibile** pulsante per rendere il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento invisibile.  
  
5.  Fare clic sui **fare clic per comprimere** pulsante per nascondere il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento dal layout interamente. Quando il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo è compresso, gli elementi circostanti vengono ridisposti per occuparne lo spazio.  
  
## <a name="hosting-a-control-that-does-not-stretch"></a>Hosting di un controllo che non si adatta  
 Alcuni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli hanno una dimensione fissa e non si adattano per riempire lo spazio disponibile nel layout. Ad esempio, il <xref:System.Windows.Forms.MonthCalendar> controllo Visualizza un mese in uno spazio fisso.  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a>Per ospitare un controllo che non si adatta  
  
1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento è centrato nella riga della griglia, ma non viene adattata per riempire lo spazio disponibile. Se la finestra è sufficientemente grande, si possono vedere due o più mesi tramite ospitato <xref:System.Windows.Forms.MonthCalendar> controllo, ma questi sono centrati nella riga. Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motore di layout Centra gli elementi che non possono essere ridimensionati per riempire lo spazio disponibile.  
  
## <a name="scaling"></a>Ridimensionamento  
 A differenza degli elementi WPF, la maggior parte dei controlli Windows Form non sono scalabili in modo continuo. Per fornire scalabilità personalizzato, si esegue l'override di <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> (metodo). 
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a>Per ridimensionare un controllo ospitato usando il comportamento predefinito  
  
1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il controllo ospitato e gli elementi che lo circondano vengono ridimensionati in base a un fattore di 0,5. Tuttavia il tipo di carattere del controllo ospitato non viene ridimensionato.

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>Rotazione  
 A differenza degli elementi WPF, controlli Windows Form non supportano la rotazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento non ruota con gli altri elementi WPF quando viene applicata una trasformazione di rotazione. Qualsiasi valore di rotazione diverso da 180 gradi genera il <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> evento.
 
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a>Per visualizzare l'effetto di rotazione in un'applicazione ibrida  
  
1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Il controllo ospitato non viene ruotato, ma i relativi elementi circostanti vengono ruotati di 180 gradi. Potrebbe essere necessario ridimensionare la finestra per vedere gli elementi.  
 

## <a name="setting-padding-and-margins"></a>Impostazione della spaziatura interna e dei margini  
 Spaziatura interna e margini [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono simili alla spaziatura interna e margini nel layout [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. È sufficiente impostare il <xref:System.Windows.Controls.Control.Padding%2A> e <xref:System.Windows.FrameworkElement.Margin%2A> proprietà di <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a>Per impostare spaziatura interna e margini per un controllo ospitato  
  
1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  Premere F5 per compilare ed eseguire l'applicazione. Le impostazioni di spaziatura e margini vengono applicate a ospitato [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli nello stesso modo cui verrebbero applicate in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
## <a name="using-dynamic-layout-containers"></a>Uso di contenitori di layout dinamici  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] fornisce due contenitori di layout dinamici, <xref:System.Windows.Forms.FlowLayoutPanel> e <xref:System.Windows.Forms.TableLayoutPanel>. È anche possibile usare questi contenitori in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout.  
  
#### <a name="to-use-a-dynamic-layout-container"></a>Per usare un contenitore di layout dinamico  
  
1.  Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  In MainWindow.xaml.vb o MainWindow.xaml.cs copiare il codice seguente nella definizione della classe.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  Aggiungere una chiamata al `InitializeFlowLayoutPanel` metodo nel costruttore.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  Premere F5 per compilare ed eseguire l'applicazione. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento riempie il <xref:System.Windows.Controls.DockPanel>, e <xref:System.Windows.Forms.FlowLayoutPanel> dispone i relativi controlli figlio nel predefinito <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)  
 [Considerazioni sul layout per l'elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [I controlli di disposizione Windows Form in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971)  
 [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
