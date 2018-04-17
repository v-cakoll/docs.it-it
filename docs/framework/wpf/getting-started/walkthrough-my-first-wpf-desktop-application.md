---
title: 'Procedura dettagliata: Prima applicazione desktop WPF'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: 71
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3725e96b514b0204f10f6b5c45ed2bbec1d892de
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>Procedura dettagliata: Prima applicazione desktop WPF
Questa procedura dettagliata viene fornita un'introduzione allo sviluppo di un [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] applicazione che include gli elementi che sono comuni alla maggior parte [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazioni: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup, codice, le definizioni di applicazioni, controlli, layout, Data binding e stili. 
  
In questa procedura dettagliata è illustrato lo sviluppo di un semplice [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione usando la procedura seguente. 
  
-   Definizione [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per progettare l'aspetto dell'applicazione [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. 
  
-   Scrittura di codice per compilare il comportamento dell'applicazione. 
  
-   Creazione di una definizione dell'applicazione per gestire l'applicazione stessa. 
  
-   Aggiunta di controlli e la creazione di layout per la composizione dell'applicazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. 
  
-   Creazione di stili per creare un aspetto coerente in tutta l'applicazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. 
  
-   Associazione di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ai dati sia popolare il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] da dati e di mantenere i dati e [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sincronizzato. 
  
Al termine della procedura dettagliata, verrà creata un'autonoma [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] applicazione che consente agli utenti di visualizzare i report di spesa per gli utenti selezionati. L'applicazione sarà costituita da più [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pagine in cui sono ospitate in una finestra del browser stile. 
  
Il codice di esempio che consente di compilare in questa procedura dettagliata è disponibile sia per [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] e [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] in [Introduzione alla compilazione di applicazioni WPF](http://go.microsoft.com/fwlink/?LinkID=160008). 

## <a name="prerequisites"></a>Prerequisiti  

- [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)] o versione successiva

Per ulteriori informazioni sull'installazione della versione più recente di Visual Studio, vedere [installare Visual Studio](/visualstudio/install/install-visual-studio).
  
## <a name="creating-the-application-project"></a>Creazione del progetto di applicazione  
In questa sezione si crea l'infrastruttura dell'applicazione che include una definizione dell'applicazione, due pagine e un'immagine. 
  
1. Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato `ExpenseIt`. Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82). 
  
    > [!NOTE]
    >  Questa procedura dettagliata Usa il <xref:System.Windows.Controls.DataGrid> controllo che è disponibile in .NET Framework 4. È possibile che il progetto è destinato a .NET Framework 4 o versione successiva. Per altre informazioni, vedere [Procedura: Destinare una versione di .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework). 
  
2. Aprire Application.xaml (Visual Basic) o App.xaml (C#). 
  
     Questo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file definisce un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applicazione e tutte le risorse dell'applicazione. Utilizzare questo file per specificare il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] visualizzata automaticamente all'avvio dell'applicazione; in questo caso, MainWindow. Xaml. 
  
     Il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dovrebbe essere simile al seguente in Visual Basic:  
  
    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     Oppure l'aspetto seguente in C#:  
  
    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3. Aprire MainWindow.xaml. 
  
     Questo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file la finestra principale dell'applicazione e visualizza il contenuto creato nelle pagine. La <xref:System.Windows.Window> classe definisce le proprietà di una finestra, ad esempio titolo, dimensioni o sull'icona e gestisce gli eventi, ad esempio la chiusura o disattivazione della visualizzazione. 
  
4. Modifica il <xref:System.Windows.Window> elemento da un <xref:System.Windows.Navigation.NavigationWindow>. 
  
     Questa applicazione passerà a contenuto diverso a seconda dell'interazione dell'utente. Pertanto, il principale <xref:System.Windows.Window> deve essere modificato in un <xref:System.Windows.Navigation.NavigationWindow>. <xref:System.Windows.Navigation.NavigationWindow> eredita tutte le proprietà di <xref:System.Windows.Window>. Il <xref:System.Windows.Navigation.NavigationWindow> elemento nel file XAML crea un'istanza di <xref:System.Windows.Navigation.NavigationWindow> classe. Per altre informazioni, vedere [Cenni preliminari sulla navigazione](../../../../docs/framework/wpf/app-development/navigation-overview.md). 
  
5. Modificare le proprietà seguenti nel <xref:System.Windows.Navigation.NavigationWindow> elemento:  
  
    -   Impostare il <xref:System.Windows.Window.Title%2A> proprietà su "ExpenseIt". 
  
    -   Impostare il <xref:System.Windows.FrameworkElement.Width%2A> proprietà su 500 pixel. 
  
    -   Impostare il <xref:System.Windows.FrameworkElement.Height%2A> proprietà 350 pixel. 
  
    -   Rimuovere il <xref:System.Windows.Controls.Grid> elementi tra il <xref:System.Windows.Navigation.NavigationWindow> tag. 
  
     Il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dovrebbe essere simile al seguente in Visual Basic:  
  
    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     Oppure l'aspetto seguente in C#:  
  
    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6. Aprire MainWindow.xaml.vb o MainWindow.xaml.cs. 
  
     Questo è un file code-behind che contiene il codice per gestire gli eventi dichiarati in MainWindow.xaml. Il file contiene una classe parziale per la finestra definita in XAML. 
  
7. Se si utilizza c#, modificare il `MainWindow` classe deriva da <xref:System.Windows.Navigation.NavigationWindow>. 
  
     In Visual Basic questo si verifica automaticamente quando si modifica la finestra in XAML. 
  
     Il codice dovrebbe risultare simile al seguente. 
  
    [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
    [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
## <a name="adding-files-to-the-application"></a>Aggiunta di file all'applicazione  
In questa sezione si aggiungono due pagine e un'immagine all'applicazione. 
  
1. Aggiungere una nuova pagina (WPF) al progetto denominato `ExpenseItHome.xaml`. Per ulteriori informazioni, vedere [procedura: aggiungere nuovi elementi a un progetto WPF](http://msdn.microsoft.com/library/17e6b238-fc32-4385-98ef-2f66ca09d9ad). 
  
     Questa è la prima pagina visualizzata quando viene avviata l'applicazione. Mostrerà un elenco di persone in cui l'utente può selezionare la persona desiderata per la visualizzazione della nota spese. 
  
2. Aprire ExpenseItHome.xaml. 
  
3. Impostare il <xref:System.Windows.Controls.Page.Title%2A> su "ExpenseIt - Home". 
  
     Il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dovrebbe essere simile al seguente in Visual Basic:  
  
    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     Oppure l'aspetto seguente in C#:  
  
    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4. Aprire MainWindow.xaml. 
  
5. Impostare il <xref:System.Windows.Navigation.NavigationWindow.Source%2A> proprietà il <xref:System.Windows.Navigation.NavigationWindow> a "ExpenseItHome. xaml". 
  
     Questo imposta ExpenseItHome.xaml come prima pagina aperta all'avvio dell'applicazione. Il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dovrebbe essere simile al seguente in Visual Basic:  
  
    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     Oppure l'aspetto seguente in C#:  
  
    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6. Aggiungere una nuova pagina (WPF) al progetto denominato `ExpenseReportPage.xaml`. 
  
     La pagina visualizzerà la nota spese relativa alla persona selezionata in ExpenseItHome.xaml. 
  
7. Aprire ExpenseReportPage.xaml. 
  
8. Impostare il <xref:System.Windows.Controls.Page.Title%2A> su "ExpenseIt - View Expense". 
  
     Il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dovrebbe essere simile al seguente in Visual Basic:  
  
    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     Oppure l'aspetto seguente in C#:  
  
    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. Aprire ExpenseItHome.xaml.vb e ExpenseReportPage.xaml.vb o ExpenseItHome.xaml.cs e ExpenseReportPage.xaml.cs. 
  
     Quando si crea un nuovo file di pagina, Visual Studio crea automaticamente un file code-behind. Questi file code-behind gestiscono la logica per rispondere all'input dell'utente. 
  
     Il codice dovrebbe risultare simile al seguente. 
  
    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. Aggiungere un'immagine denominata *watermark* al progetto. È possibile creare un'immagine personalizzata oppure copiare il file dal codice di esempio. Per altre informazioni, vedere [procedura: aggiungere elementi esistenti a un progetto](/previous-versions/visualstudio/visual-studio-2008/9f4t9t92(v=vs.90)). 

## <a name="building-and-running-the-application"></a>Compilazione e l'esecuzione dell'applicazione  
In questa sezione viene compilata ed eseguita l'applicazione. 
  
1. Compilare ed eseguire l'applicazione premendo F5 o selezionando **Avvia debug** dal **Debug** menu. 
  
     Nella figura seguente viene illustrata l'applicazione con il <xref:System.Windows.Navigation.NavigationWindow> pulsanti. 
  
     ![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")  
  
2. Chiudere l'applicazione per tornare alla [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]. 
  
## <a name="creating-the-layout"></a>Creazione del layout  
Il layout consente di posizionare in modo ordinato [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi e gestisce le dimensioni e posizione degli elementi quando un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] viene ridimensionato. In genere si crea un layout tramite uno dei controlli di layout seguenti:  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
Ognuno di questi controlli di layout supporta un tipo speciale di layout per i relativi elementi figlio. È possibile ridimensionare le pagine ExpenseIt e ogni pagina contiene elementi disposti in orizzontale e in verticale accanto ad altri elementi. Di conseguenza, il <xref:System.Windows.Controls.Grid> è l'elemento di layout ideale per l'applicazione. 
  
> [!NOTE]
>  Per ulteriori informazioni su <xref:System.Windows.Controls.Panel> elementi, vedere [Panoramica pannelli](../../../../docs/framework/wpf/controls/panels-overview.md). Per ulteriori informazioni sul layout, vedere [Layout](../../../../docs/framework/wpf/advanced/layout.md). 
  
Nella sezione crei una sola colonna di tabella con tre righe e un margine di 10 pixel mediante l'aggiunta di definizioni di colonna e riga di <xref:System.Windows.Controls.Grid> in ExpenseItHome. Xaml. 
  
1. Aprire ExpenseItHome.xaml. 
  
2. Impostare il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà il <xref:System.Windows.Controls.Grid> elemento "10,0,10,10", che corrispondono ai margini sinistro, superiore, destro e inferiore. 
  
3. Aggiungere il seguente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tra il <xref:System.Windows.Controls.Grid> tag per creare le definizioni di riga e colonna. 
  
    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     Il <xref:System.Windows.Controls.RowDefinition.Height%2A> di due righe è impostato su <xref:System.Windows.GridLength.Auto%2A> di base che significa che le righe verranno ridimensionato in base al contenuto delle righe. Il valore predefinito <xref:System.Windows.Controls.RowDefinition.Height%2A> è <xref:System.Windows.GridUnitType.Star> dimensioni, il che significa che la riga sarà una proporzione ponderata dello spazio disponibile. Se ad esempio due righe hanno un'altezza pari a "*", ognuna avrà un'altezza pari alla metà dello spazio disponibile.  
  
     Il <xref:System.Windows.Controls.Grid> dovrebbe essere simile al codice XAML seguente:  
  
    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
## <a name="adding-controls"></a>Aggiunta di controlli  
In questa sezione, la home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] viene aggiornato per visualizzare un elenco di persone che gli utenti possono selezionare per mostrare la nota spese per una persona selezionata. I controlli sono oggetti dell'interfaccia utente che consentono agli utenti di interagire con l'applicazione. Per altre informazioni, vedere [Controlli](../../../../docs/framework/wpf/controls/index.md). 
  
Per creare questa [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], gli elementi seguenti sono aggiunti a ExpenseItHome. XAML:  
  
-   <xref:System.Windows.Controls.ListBox> (per un elenco di persone). 
  
-   <xref:System.Windows.Controls.Label> (per l'intestazione dell'elenco). 
  
-   <xref:System.Windows.Controls.Button> (possibile fare clic per visualizzare la nota spese per la persona che sia selezionata nell'elenco). 
  
Ogni controllo viene posizionato in una riga del <xref:System.Windows.Controls.Grid> impostando il <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> proprietà associata. Per ulteriori informazioni sulle proprietà associate, vedere [collegato Cenni preliminari sulle proprietà](../../../../docs/framework/wpf/advanced/attached-properties-overview.md). 
  
1. Aprire ExpenseItHome.xaml. 
  
2. Aggiungere il seguente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tra il <xref:System.Windows.Controls.Grid> tag. 
  
    [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3. Compilare ed eseguire l'applicazione. 
  
La figura seguente mostra i controlli creati da XAML in questa sezione. 
  
![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")  
  
## <a name="adding-an-image-and-a-title"></a>Aggiunta di un'immagine e un titolo  
In questa sezione, la home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] viene aggiornato con un'immagine e un titolo della pagina. 
  
1. Aprire ExpenseItHome.xaml. 
  
2. Aggiungere un'altra colonna per il <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con fisse <xref:System.Windows.Controls.ColumnDefinition.Width%2A> di 230 pixel. 
  
    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3. Aggiungere un'altra riga per il <xref:System.Windows.Controls.Grid.RowDefinitions%2A>. 
  
    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4. Spostare i controlli nella seconda colonna impostando <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> su 1. Spostare ogni controllo in basso di una riga, aumentando la <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> di 1. 
  
    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5. Impostare il <xref:System.Windows.Controls.Panel.Background%2A> del <xref:System.Windows.Controls.Grid> come file di immagine watermark. 
  
    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6. Prima di <xref:System.Windows.Controls.Border>, aggiungere un <xref:System.Windows.Controls.Label> con il contenuto "View Expense Report" per il titolo della pagina. 
  
    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7. Compilare ed eseguire l'applicazione. 
  
La figura seguente mostra i risultati di questa sezione. 
  
![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")  
  
## <a name="adding-code-to-handle-events"></a>Aggiungere il codice per gestire gli eventi  
  
1. Aprire ExpenseItHome.xaml. 
  
2. Aggiungere un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi per il <xref:System.Windows.Controls.Button> elemento. Per ulteriori informazioni, vedere [procedura: creare un semplice gestore](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480). 
  
    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3. Aprire ExpenseItHome.xaml.vb o ExpenseItHome.xaml.cs. 
  
4. Aggiungere il codice seguente per il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi, che fa sì che la finestra passare al file ExpenseReportPage. Xaml. 
  
    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
## <a name="creating-the-ui-for-expensereportpage"></a>Creazione dell'interfaccia utente per ExpenseReportPage  
ExpenseReportPage.xaml visualizza la nota spese per la persona selezionata nel file ExpenseItHome.xaml. In questa sezione verranno aggiunti i controlli e crea il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per ExpenseReportPage. Xaml. In questa sezione vengono inoltre aggiunti i colori di sfondo e del riempimento ai diversi [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi. 
  
1. Aprire ExpenseReportPage.xaml. 
  
2. Aggiungere il seguente codice XAML tra i tag <xref:System.Windows.Controls.Grid>. 
  
     Questa interfaccia è simile all'interfaccia utente creato in ExpenseItHome. XAML, tranne i dati del report viene visualizzati un <xref:System.Windows.Controls.DataGrid>. 
  
    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3. Compilare ed eseguire l'applicazione. 
  
    > [!NOTE]
    >  Se si verifica un errore di <xref:System.Windows.Controls.DataGrid> non è stato trovato o non esiste, verificare che il progetto è destinato a .NET Framework 4 o versione successivo. Per altre informazioni, vedere [Procedura: Destinare una versione di .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework). 
  
4. Fare clic su di **vista** pulsante. 
  
     Viene visualizzata la pagina della nota spese. 
  
La figura seguente mostra il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi aggiunti alla ExpenseReportPage. Xaml. Notare che il pulsante di navigazione all'indietro è abilitato. 
  
![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")  
  
## <a name="styling-controls"></a>Stile di controlli  
L'aspetto dei diversi elementi spesso può essere uguale per tutti gli elementi dello stesso tipo in un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] usa gli stili per rendere l'aspetto riutilizzabile tra più elementi. La possibilità di riutilizzo consente di semplificare [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] creazione e la gestione. Per ulteriori informazioni sugli stili, vedere [stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md). In questa sezione vengono sostituiti con gli stili gli attributi per elemento definiti nei passaggi precedenti. 
  
1. Aprire Application.xaml o App.xaml. 
  
2. Aggiungere il codice XAML seguente tra i <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tag:  
  
    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     Questo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] aggiunge gli stili seguenti:  
  
    -  `headerTextStyle`: per formattare il titolo della pagina <xref:System.Windows.Controls.Label>. 
  
    -  `labelStyle`: per formattare i controlli <xref:System.Windows.Controls.Label> . 
  
    -  `columnHeaderStyle`: per formattare <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>. 
  
    -  `listHeaderStyle`: per formattare i controlli <xref:System.Windows.Controls.Border> dell'intestazione dell'elenco. 
  
    -  `listHeaderTextStyle`: Per formattare l'intestazione dell'elenco <xref:System.Windows.Controls.Label>. 
  
    -  `buttonStyle`: Per formattare il <xref:System.Windows.Controls.Button> in ExpenseItHome. Xaml. 
  
     Si noti che gli stili sono risorse e i relativi elementi figlio di <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> elemento proprietà. In questa posizione, gli stili vengono applicati a tutti gli elementi di un'applicazione. Per un esempio di utilizzo delle risorse in un [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] applicazione, vedere [le risorse dell'applicazione di utilizzare](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md). 
  
3. Aprire ExpenseItHome.xaml. 
  
4. Sostituire tutto il contenuto tra il <xref:System.Windows.Controls.Grid> gli elementi con il seguente codice XAML. 
  
    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     Le proprietà come <xref:System.Windows.VerticalAlignment> e <xref:System.Windows.Media.FontFamily> che definiscono l'aspetto di ciascun controllo vengono rimosse e sostituite mediante l'applicazione degli stili. Ad esempio, il `headerTextStyle` viene applicato a "View Expense Report" <xref:System.Windows.Controls.Label>. 
  
5. Aprire ExpenseReportPage.xaml. 
  
6. Sostituire tutto il contenuto tra il <xref:System.Windows.Controls.Grid> gli elementi con il seguente codice XAML. 
  
    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     Vengono aggiunti gli stili agli elementi <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.Border> . 
  
7. Compilare ed eseguire l'applicazione. 
  
     Dopo aver aggiunto il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in questa sezione, l'applicazione abbia lo stesso aspetto era prima che venga aggiornato con gli stili. 
  
## <a name="binding-data-to-a-control"></a>Associazione dati a un controllo  
In questa sezione si crea il [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] dati associati ai vari controlli. 
  
1. Aprire ExpenseItHome.xaml. 
  
2. Dopo l'apertura <xref:System.Windows.Controls.Grid> elemento, aggiungere il codice XAML seguente per creare un <xref:System.Windows.Data.XmlDataProvider> che contiene i dati per ogni persona. 
  
     I dati vengono creati come un <xref:System.Windows.Controls.Grid> risorse. In genere questi dati vengono caricati sotto forma di file, ma in questo caso, per semplicità, verranno aggiunti inline. 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3. Nel <xref:System.Windows.Controls.Grid> risorsa, aggiungere le seguenti <xref:System.Windows.DataTemplate>, che definisce come visualizzare i dati di <xref:System.Windows.Controls.ListBox>. Per altre informazioni sui modelli di dati, vedere [Cenni preliminari sui modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md). 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4. Sostituire <xref:System.Windows.Controls.ListBox> con il seguente codice XAML. 
  
    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     Questo codice XAML associa il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.ListBox> all'origine dati e applica il modello di dati come il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>. 
  
## <a name="connecting-data-to-controls"></a>Connessione dati a controlli  
In questa sezione, scritto il codice per recuperare l'elemento corrente che sia selezionata nell'elenco di utenti nella pagina ExpenseItHome. XAML e passa il relativo riferimento al costruttore di `ExpenseReportPage` durante la creazione di istanze. `ExpenseReportPage` imposta il contesto dei dati con l'elemento passato, a cui verranno associati i controlli definiti in ExpenseReportPage.xaml. 
  
1. Aprire ExpenseReportPage.xaml.vb o ExpenseReportPage.xaml.cs. 
  
2. Aggiungere un costruttore che accetti un oggetto, in modo da poter passare i dati della nota spese della persona selezionata. 
  
    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3. Aprire ExpenseItHome.xaml.vb o ExpenseItHome.xaml.cs. 
  
4. Modifica il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi per chiamare il nuovo costruttore passando i dati della nota spese della persona selezionata. 
  
    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
## <a name="styling-data-with-data-templates"></a>Lo stile dati con i modelli di dati  
In questa sezione, si aggiorna il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per ciascun elemento nei dati associati gli elenchi con i modelli di dati. 
  
1. Aprire ExpenseReportPage.xaml. 
  
2. Associare il contenuto di "Nome" e "Department" <xref:System.Windows.Controls.Label> proprietà source elementi per i dati appropriati. Per altre informazioni sul data binding, vedere [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md). 
  
    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3. Dopo l'apertura <xref:System.Windows.Controls.Grid> elemento, aggiungere i seguenti modelli di dati, che definiscono la modalità di visualizzazione dei dati della nota spese.  
    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4. Applicare i modelli per il <xref:System.Windows.Controls.DataGrid> colonne che visualizzano i costi per i dati del report. 
  
    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5. Compilare ed eseguire l'applicazione. 
  
6. Selezionare una persona e fare clic su di **vista** pulsante. 
  
 La figura seguente mostra le due pagine dell'applicazione ExpenseIt con i controlli, il layout, gli stili, il data binding e i modelli di dati applicati. 
  
 ![Schermate dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")  
  
## <a name="best-practices"></a>Procedure consigliate  
Questo esempio illustra una funzionalità specifica di WPF e, di conseguenza, non segue le procedure consigliate per lo sviluppo di applicazioni. Per una descrizione completa di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] applicazione consigliate per lo sviluppo, vedere gli argomenti seguenti come appropriato:  
  
-   Accessibilità: [Procedure consigliate per l'accesso facilitato](../../../../docs/framework/ui-automation/accessibility-best-practices.md)  
  
-   Sicurezza - [sicurezza](../../../../docs/framework/wpf/security-wpf.md)  
  
-   Localizzazione: [Panoramica della globalizzazione e localizzazione WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)  
  
-   Prestazioni: [Ottimizzazione delle prestazioni di applicazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
  
## <a name="whats-next"></a>Argomenti successivi  
È ora una serie di tecniche a disposizione per la creazione di un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] utilizzando [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. È stata acquisita una conoscenza approfondita dei blocchi di compilazione di base di un controllo con associazione a dati [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] dell'applicazione. Questo argomento non è esaustivo, ma intende fornire all'utente le informazioni e gli strumenti per approfondire autonomamente le numerose opzioni di cui dispone, che vanno oltre le tecniche descritte nell'argomento. 
  
 Per altre informazioni sull'architettura WPF e i modelli di programmazione, vedere gli argomenti seguenti:  
  
-   [Architettura WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [Layout](../../../../docs/framework/wpf/advanced/layout.md)  
  
 Per altre informazioni sulla creazione di applicazioni, vedere gli argomenti seguenti:  
  
-   [Sviluppo di applicazioni](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [Controlli](../../../../docs/framework/wpf/controls/index.md)  
  
-   [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [Grafica e funzionalità multimediali](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Panoramica sui modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Compilazione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Stili e modelli](../../../../docs/framework/wpf/controls/styles-and-templates.md)
