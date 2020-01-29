---
title: Disporre i controlli Windows Forms in WPF
titleSuffix: ''
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: 5e7544dfdbee234bb968c9a7f39814e8749ece15
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735295"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Procedura dettagliata: disposizione di controlli Windows Form in WPF

Questa procedura dettagliata illustra come usare le funzionalità di layout [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per disporre i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] in un'applicazione ibrida.

Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione del progetto.
- Uso delle impostazioni di layout predefinite.
- Ridimensionamento in base al contenuto.
- Uso del posizionamento assoluto.
- Specifica esplicita delle dimensioni.
- Impostazione delle proprietà di layout.
- Informazioni sulle limitazioni di z order.
- Ancoraggio.
- Impostazione della visibilità.
- Hosting di un controllo che non si adatta.
- Scalabilità.
- Rotazione.
- Impostazione della spaziatura interna e dei margini.
- Uso di contenitori di layout dinamici.

Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [disposizione di Windows Forms controlli in WPF di esempio](https://go.microsoft.com/fwlink/?LinkID=159971).

Al termine, sarà possibile comprendere [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] funzionalità di layout nelle applicazioni basate su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="creating-the-project"></a>Creazione del progetto

Per creare e configurare il progetto, attenersi alla procedura seguente:

1. Creare un progetto di applicazione WPF denominato `WpfLayoutHostingWf`.

2. In Esplora soluzioni aggiungere riferimenti agli assembly seguenti:

    - WindowsFormsIntegration
    - System.Windows.Forms
    - System.Drawing

3. Fare doppio clic su *MainWindow. XAML* per aprirlo nella visualizzazione XAML.

4. Nell'elemento <xref:System.Windows.Window> aggiungere il seguente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] mapping dello spazio dei nomi.

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. Nell'elemento <xref:System.Windows.Controls.Grid> impostare la proprietà <xref:System.Windows.Controls.Grid.ShowGridLines%2A> su `true` e definire cinque righe e tre colonne.

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a>Uso delle impostazioni di layout predefinite

Per impostazione predefinita, l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> gestisce il layout per il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato.

Per usare le impostazioni di layout predefinite, seguire questa procedura:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione. Il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> viene visualizzato nella <xref:System.Windows.Controls.Canvas>. Il controllo ospitato viene ridimensionato in base al relativo contenuto e l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> viene dimensionato per contenere il controllo ospitato.

## <a name="sizing-to-content"></a>Ridimensionamento in base al contenuto

L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> garantisce che il controllo ospitato venga ridimensionato per visualizzare correttamente il contenuto.

Per ridimensionare il contenuto, attenersi alla seguente procedura:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione. I due nuovi controlli pulsante vengono ridimensionati in modo da visualizzare la stringa di testo più lunga e le dimensioni del carattere più grandi e gli elementi <xref:System.Windows.Forms.Integration.WindowsFormsHost> vengono ridimensionati per contenere i controlli ospitati.

## <a name="using-absolute-positioning"></a>Uso del posizionamento assoluto

È possibile usare il posizionamento assoluto per inserire l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> in un punto qualsiasi dell'interfaccia utente.

Per usare il posizionamento assoluto, attenersi alla procedura seguente:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> viene inserito a 20 pixel dal lato superiore della cella della griglia e a 20 pixel da sinistra.

## <a name="specifying-size-explicitly"></a>Specifica esplicita delle dimensioni

È possibile specificare le dimensioni dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> usando le proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A>.

Per specificare le dimensioni in modo esplicito, attenersi alla procedura seguente:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> è impostato su una dimensione di 50 pixel in larghezza per 70 pixel di altezza, minore rispetto alle impostazioni predefinite del layout. Il contenuto del controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] viene ridisposto di conseguenza.

## <a name="setting-layout-properties"></a>Impostazione delle proprietà di layout

Impostare sempre le proprietà correlate al layout nel controllo ospitato usando le proprietà dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>. L'impostazione diretta delle proprietà di layout nel controllo ospitato darà risultati imprevisti.

 L'impostazione delle proprietà correlate al layout nel controllo ospitato in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non ha alcun effetto.

Per visualizzare gli effetti dell'impostazione delle proprietà nel controllo ospitato, attenersi alla seguente procedura:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. In **Esplora soluzioni**fare doppio clic su *MainWindow. XAML. vb* o *MainWindow.XAML.cs* per aprirlo nell'editor di codice.

3. Copiare il codice seguente nella definizione della classe `MainWindow`:

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.

5. Fare clic sul pulsante **fare clic su me** . Il gestore dell'evento `button1_Click` imposta le proprietà <xref:System.Windows.Forms.Control.Top%2A> e <xref:System.Windows.Forms.Control.Left%2A> sul controllo ospitato. In questo modo il controllo ospitato viene riposizionato all'interno dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>. L'host mantiene la stessa area dello schermo, ma il controllo ospitato viene ritagliato. Al contrario, il controllo ospitato deve riempire sempre l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

## <a name="understanding-z-order-limitations"></a>Informazioni sulle limitazioni di z order

Gli elementi <xref:System.Windows.Forms.Integration.WindowsFormsHost> visibili vengono sempre disegnati sopra gli altri elementi WPF e non sono interessati dall'ordine z. Per visualizzare questo comportamento dell'ordine z, eseguire le operazioni seguenti:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> viene disegnato sull'elemento label.

## <a name="docking"></a>Docking

<xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento supporta l'ancoraggio [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Impostare la proprietà associata <xref:System.Windows.Controls.DockPanel.Dock%2A> per ancorare il controllo ospitato in un elemento <xref:System.Windows.Controls.DockPanel>.

Per ancorare un controllo ospitato, attenersi alla procedura seguente:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> è ancorato al lato destro dell'elemento <xref:System.Windows.Controls.DockPanel>.

## <a name="setting-visibility"></a>Impostazione della visibilità

È possibile rendere invisibile il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o comprimerlo impostando la proprietà <xref:System.Windows.UIElement.Visibility%2A> sull'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Quando un controllo non è visibile, non viene visualizzato, ma occupa spazio del layout. Quando un controllo è compresso, non viene visualizzato né occupa spazio del layout.

Per impostare la visibilità di un controllo ospitato, attenersi alla procedura seguente:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. In *MainWindow. XAML. vb* o *MainWindow.XAML.cs*copiare il codice seguente nella definizione della classe:

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione.

4. Fare clic sul pulsante **fare clic per rendere invisibile** per rendere invisibile l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

5. Fare clic sul pulsante **fare clic per comprimere** per nascondere completamente l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> dal layout. Quando il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] viene compresso, gli elementi circostanti vengono ridisposti per occuparne lo spazio.

## <a name="hosting-a-control-that-does-not-stretch"></a>Hosting di un controllo che non si adatta

Alcuni controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hanno una dimensione fissa e non si adattano per riempire lo spazio disponibile nel layout. Ad esempio, il controllo <xref:System.Windows.Forms.MonthCalendar> Visualizza un mese in uno spazio fisso.

Per ospitare un controllo che non si estende, attenersi alla procedura seguente:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> viene centrato nella riga della griglia, ma non viene allungato per riempire lo spazio disponibile. Se la finestra è sufficientemente grande, è possibile che vengano visualizzati due o più mesi dal controllo <xref:System.Windows.Forms.MonthCalendar> host, che però sono centrati nella riga. Il motore di layout di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] centra gli elementi che non possono essere ridimensionati per riempire lo spazio disponibile.

## <a name="scaling"></a>Ridimensionamento

Diversamente dagli elementi WPF, la maggior parte dei controlli Windows Forms non è continuamente scalabile. Per fornire scalabilità personalizzata, è necessario eseguire l'override del metodo <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>.

Per ridimensionare un controllo ospitato usando il comportamento predefinito, attenersi alla procedura seguente:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione. Il controllo ospitato e gli elementi che lo circondano vengono ridimensionati in base a un fattore di 0,5. Tuttavia il tipo di carattere del controllo ospitato non viene ridimensionato.

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>Rotazione

Diversamente dagli elementi WPF, i controlli Windows Forms non supportano la rotazione. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> non viene ruotato con altri elementi WPF quando viene applicata una trasformazione di rotazione. Qualsiasi valore di rotazione diverso da 180 gradi genera l'evento <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>.

Per visualizzare l'effetto della rotazione in un'applicazione ibrida, attenersi alla procedura seguente:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione. Il controllo ospitato non viene ruotato, ma i relativi elementi circostanti vengono ruotati di 180 gradi. Potrebbe essere necessario ridimensionare la finestra per vedere gli elementi.

## <a name="setting-padding-and-margins"></a>Impostazione della spaziatura interna e dei margini

La spaziatura interna e i margini nel layout [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono simili a spaziatura interna e margini in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. È sufficiente impostare le proprietà <xref:System.Windows.Controls.Control.Padding%2A> e <xref:System.Windows.FrameworkElement.Margin%2A> sull'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

Per impostare spaziatura interna e margini per un controllo ospitato, attenersi alla seguente procedura:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione. Le impostazioni di spaziatura interna e margini vengono applicate ai controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitati nello stesso modo in cui vengono applicati in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].

## <a name="using-dynamic-layout-containers"></a>Uso di contenitori di layout dinamici

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] fornisce due contenitori di layout dinamici, <xref:System.Windows.Forms.FlowLayoutPanel> e <xref:System.Windows.Forms.TableLayoutPanel>. È anche possibile usare questi contenitori in layout [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Per usare un contenitore di layout dinamico, attenersi alla procedura seguente:

1. Copiare il codice XAML seguente nell'elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. In *MainWindow. XAML. vb* o *MainWindow.XAML.cs*copiare il codice seguente nella definizione della classe:

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. Aggiungere una chiamata al metodo `InitializeFlowLayoutPanel` nel costruttore:

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. Premere <kbd>F5</kbd> per compilare ed eseguire l'applicazione. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> riempie l'<xref:System.Windows.Controls.DockPanel>e <xref:System.Windows.Forms.FlowLayoutPanel> dispone i relativi controlli figlio nel <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>predefinito.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Considerazioni sul layout per l'elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md)
- [Disposizione di controlli Windows Forms nell'esempio WPF](https://go.microsoft.com/fwlink/?LinkID=159971)
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
