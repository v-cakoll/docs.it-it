---
title: 'Procedura dettagliata: Disposizione di controlli Windows Form in WPF'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: fa0181e95a03324c4cfa9395ae57439c260d1c23
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972303"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Procedura dettagliata: Disposizione di controlli Windows Form in WPF

Questa procedura dettagliata illustra come usare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le funzionalità di layout per disporre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] i controlli in un'applicazione ibrida.

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

- Ridimensionamento.

- Rotazione.

- Impostazione della spaziatura interna e dei margini.

- Uso di contenitori di layout dinamici.

Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [disposizione di Windows Forms controlli in WPF di esempio](https://go.microsoft.com/fwlink/?LinkID=159971).

Al termine, si avrà una conoscenza delle funzionalità di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout nelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]applicazioni basate su.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="creating-the-project"></a>Creazione del progetto

### <a name="to-create-and-set-up-the-project"></a>Per creare e impostare il progetto

1. Creare un progetto di applicazione WPF `WpfLayoutHostingWf`denominato.

2. In Esplora soluzioni aggiungere riferimenti agli assembly seguenti.

    - WindowsFormsIntegration

    - System.Windows.Forms

    - System.Drawing

3. Fare doppio clic sul file MainWindow.xaml per aprirlo nella visualizzazione XAML.

4. Nell'elemento aggiungere il mapping dello spazio dei nomi seguente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. <xref:System.Windows.Window>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. Nell'elemento impostare la <xref:System.Windows.Controls.Grid.ShowGridLines%2A> proprietà su `true` e definire cinque righe e tre colonne. <xref:System.Windows.Controls.Grid>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a>Uso delle impostazioni di layout predefinite

Per impostazione predefinita, <xref:System.Windows.Forms.Integration.WindowsFormsHost> l'elemento gestisce il layout per il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo ospitato.

### <a name="to-use-default-layout-settings"></a>Per usare le impostazioni di layout predefinite

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. Premere F5 per compilare ed eseguire l'applicazione. <xref:System.Windows.Controls.Canvas>Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo<xref:System.Windows.Forms.Button?displayProperty=nameWithType> viene visualizzato in. Il controllo ospitato viene ridimensionato in base al relativo contenuto e <xref:System.Windows.Forms.Integration.WindowsFormsHost> l'elemento viene dimensionato per contenere il controllo ospitato.

## <a name="sizing-to-content"></a>Ridimensionamento in base al contenuto

L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento garantisce che il controllo ospitato venga ridimensionato per visualizzare correttamente il contenuto.

### <a name="to-size-to-content"></a>Per ridimensionare in base al contenuto

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. Premere F5 per compilare ed eseguire l'applicazione. I due nuovi controlli pulsante vengono ridimensionati in modo da visualizzare la stringa di testo più lunga e le dimensioni <xref:System.Windows.Forms.Integration.WindowsFormsHost> del carattere più grandi e gli elementi vengono ridimensionati per contenere i controlli ospitati.

## <a name="using-absolute-positioning"></a>Uso del posizionamento assoluto

È possibile usare il posizionamento assoluto per posizionare <xref:System.Windows.Forms.Integration.WindowsFormsHost> l'elemento in un punto qualsiasi dell'interfaccia utente.

### <a name="to-use-absolute-positioning"></a>Per usare il posizionamento assoluto

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. Premere F5 per compilare ed eseguire l'applicazione. L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene inserito a 20 pixel dal lato superiore della cella della griglia e a 20 pixel da sinistra.

## <a name="specifying-size-explicitly"></a>Specifica esplicita delle dimensioni

È possibile specificare le dimensioni dell' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento usando le <xref:System.Windows.FrameworkElement.Width%2A> proprietà e <xref:System.Windows.FrameworkElement.Height%2A> .

### <a name="to-specify-size-explicitly"></a>Per specificare le dimensioni in modo esplicito

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. Premere F5 per compilare ed eseguire l'applicazione. L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento è impostato su una dimensione di 50 pixel in larghezza per 70 pixel di altezza, minore rispetto alle impostazioni predefinite del layout. Il contenuto del [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene ridisposto di conseguenza.

## <a name="setting-layout-properties"></a>Impostazione delle proprietà di layout

Impostare sempre le proprietà correlate al layout nel controllo ospitato usando le proprietà dell' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. L'impostazione diretta delle proprietà di layout nel controllo ospitato darà risultati imprevisti.

 L'impostazione delle proprietà correlate al layout nel controllo ospitato [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in non ha alcun effetto.

### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a>Per visualizzare gli effetti dell'impostazione delle proprietà nel controllo

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. In Esplora soluzioni fare doppio clic su MainWindow.xaml. vb o MainWindow.xaml.cs per aprirlo nell'editor di codice.

3. Copiare il codice seguente nella definizione `MainWindow` della classe.

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. Premere F5 per compilare ed eseguire l'applicazione.

5. Fare clic sul pulsante **fare clic su me** . Il `button1_Click` gestore eventi imposta le <xref:System.Windows.Forms.Control.Top%2A> proprietà <xref:System.Windows.Forms.Control.Left%2A> e sul controllo ospitato. In questo modo il controllo ospitato viene riposizionato all'interno dell' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. L'host mantiene la stessa area dello schermo, ma il controllo ospitato viene ritagliato. Al contrario, il controllo ospitato deve sempre riempire <xref:System.Windows.Forms.Integration.WindowsFormsHost> l'elemento.

## <a name="understanding-z-order-limitations"></a>Informazioni sulle limitazioni di z order

Gli <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementi visibili vengono sempre disegnati sopra gli altri elementi WPF e non sono interessati dall'ordine z. Per visualizzare questo comportamento dell'ordine z, eseguire le operazioni seguenti:

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. Premere F5 per compilare ed eseguire l'applicazione. L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene disegnato sull'elemento label.

## <a name="docking"></a>Ancoraggio

<xref:System.Windows.Forms.Integration.WindowsFormsHost>l'elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta l'ancoraggio. Impostare la <xref:System.Windows.Controls.DockPanel.Dock%2A> proprietà associata per ancorare il controllo ospitato in <xref:System.Windows.Controls.DockPanel> un elemento.

### <a name="to-dock-a-hosted-control"></a>Per ancorare un controllo ospitato

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. Premere F5 per compilare ed eseguire l'applicazione. L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento è ancorato al lato destro <xref:System.Windows.Controls.DockPanel> dell'elemento.

## <a name="setting-visibility"></a>Impostazione della visibilità

È possibile rendere il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo invisibile o comprimerlo impostando <xref:System.Windows.UIElement.Visibility%2A> la proprietà sull' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. Quando un controllo non è visibile, non viene visualizzato, ma occupa spazio del layout. Quando un controllo è compresso, non viene visualizzato né occupa spazio del layout.

### <a name="to-set-the-visibility-of-a-hosted-control"></a>Per impostare la visibilità di un controllo ospitato

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. In MainWindow.xaml.vb o MainWindow.xaml.cs copiare il codice seguente nella definizione della classe.

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. Premere F5 per compilare ed eseguire l'applicazione.

4. Fare clic sul pulsante **fare clic per rendere invisibile** per <xref:System.Windows.Forms.Integration.WindowsFormsHost> rendere invisibile l'elemento.

5. Fare clic sul pulsante **fare clic per** comprimere per nascondere completamente l' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento del layout. Quando il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene compresso, gli elementi circostanti vengono ridisposti per occuparne lo spazio.

## <a name="hosting-a-control-that-does-not-stretch"></a>Hosting di un controllo che non si adatta

Alcuni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli hanno dimensioni fisse e non si adattano per riempire lo spazio disponibile nel layout. Ad esempio, il <xref:System.Windows.Forms.MonthCalendar> controllo Visualizza un mese in uno spazio fisso.

### <a name="to-host-a-control-that-does-not-stretch"></a>Per ospitare un controllo che non si adatta

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. Premere F5 per compilare ed eseguire l'applicazione. L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento è centrato nella riga della griglia, ma non viene allungato per riempire lo spazio disponibile. Se la finestra è sufficientemente grande, è possibile che vengano visualizzati due o più mesi dal controllo <xref:System.Windows.Forms.MonthCalendar> ospitato, che però sono centrati nella riga. Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motore di layout centra gli elementi che non possono essere ridimensionati per riempire lo spazio disponibile.

## <a name="scaling"></a>Ridimensionamento

Diversamente dagli elementi WPF, la maggior parte dei controlli Windows Forms non è continuamente scalabile. Per fornire scalabilità personalizzata, eseguire l' <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> override del metodo.

### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a>Per ridimensionare un controllo ospitato usando il comportamento predefinito

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. Premere F5 per compilare ed eseguire l'applicazione. Il controllo ospitato e gli elementi che lo circondano vengono ridimensionati in base a un fattore di 0,5. Tuttavia il tipo di carattere del controllo ospitato non viene ridimensionato.

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>Rotazione

Diversamente dagli elementi WPF, i controlli Windows Forms non supportano la rotazione. L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento non viene ruotato con altri elementi WPF quando viene applicata una trasformazione di rotazione. Qualsiasi valore di rotazione diverso da 180 gradi genera <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> l'evento.

### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a>Per visualizzare l'effetto di rotazione in un'applicazione ibrida

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. Premere F5 per compilare ed eseguire l'applicazione. Il controllo ospitato non viene ruotato, ma i relativi elementi circostanti vengono ruotati di 180 gradi. Potrebbe essere necessario ridimensionare la finestra per vedere gli elementi.

## <a name="setting-padding-and-margins"></a>Impostazione della spaziatura interna e dei margini

La spaziatura interna e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] i margini nel layout sono simili a spaziatura interna e margini in. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] È sufficiente impostare <xref:System.Windows.Controls.Control.Padding%2A> le <xref:System.Windows.FrameworkElement.Margin%2A> proprietà e sull' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.

### <a name="to-set-padding-and-margins-for-a-hosted-control"></a>Per impostare spaziatura interna e margini per un controllo ospitato

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. Premere F5 per compilare ed eseguire l'applicazione. Le impostazioni di spaziatura interna e margini vengono [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] applicate ai controlli ospitati nello stesso modo in cui [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]verrebbero applicate.

## <a name="using-dynamic-layout-containers"></a>Uso di contenitori di layout dinamici

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]fornisce due contenitori di layout dinamici <xref:System.Windows.Forms.FlowLayoutPanel> , <xref:System.Windows.Forms.TableLayoutPanel>e. È anche possibile usare questi contenitori nei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout.

### <a name="to-use-a-dynamic-layout-container"></a>Per usare un contenitore di layout dinamico

1. Copiare il codice XAML seguente nell' <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. In MainWindow.xaml.vb o MainWindow.xaml.cs copiare il codice seguente nella definizione della classe.

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. Aggiungere una chiamata al metodo `InitializeFlowLayoutPanel` nel costruttore.

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. Premere F5 per compilare ed eseguire l'applicazione. L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento riempie l' <xref:System.Windows.Controls.DockPanel>oggetto e <xref:System.Windows.Forms.FlowLayoutPanel> dispone i relativi controlli figlio nel valore predefinito <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Considerazioni sul layout per l'elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md)
- [Disposizione di controlli Windows Forms nell'esempio WPF](https://go.microsoft.com/fwlink/?LinkID=159971)
- [Procedura dettagliata: Hosting di un controllo Windows Forms composito in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettagliata: Hosting di un controllo composito WPF in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
