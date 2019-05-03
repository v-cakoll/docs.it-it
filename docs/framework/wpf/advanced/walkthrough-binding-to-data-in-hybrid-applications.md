---
title: 'Procedura dettagliata: Data binding in applicazioni ibride'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: f6fd1f2f5d0a729ee5610b81d4bfdca052a6e01e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61981812"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>Procedura dettagliata: Data binding in applicazioni ibride
Associazione di un'origine dati a un controllo è essenziale per fornire agli utenti l'accesso ai dati sottostanti, se si usa [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Questa procedura dettagliata illustra come usare l'associazione dati in applicazioni ibride che includono entrambe [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
- Creazione del progetto.  
  
- Definizione del modello dati.  
  
- Specifica del layout del form.  
  
- Specifica delle associazioni dati.  
  
- Visualizzazione dei dati usando l'interoperabilità.  
  
- Aggiunta dell'origine dati al progetto.  
  
- Associazione all'origine dati.  
  
 Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Data Binding nell'esempio di applicazioni ibride](https://go.microsoft.com/fwlink/?LinkID=159983).  
  
 Al termine, si conosceranno le funzionalità di associazione dati nelle applicazioni ibride.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
- Visual Studio.  
  
- Accesso al database Northwind di esempio in esecuzione su Microsoft SQL Server.  
  
## <a name="creating-the-project"></a>Creazione del progetto  
  
#### <a name="to-create-and-set-up-the-project"></a>Per creare e impostare il progetto  
  
1. Creare un progetto di applicazione WPF denominato `WPFWithWFAndDatabinding`.  
  
2. In Esplora soluzioni aggiungere riferimenti agli assembly seguenti.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. Aprire MainWindow. XAML nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4. Nel <xref:System.Windows.Window> elemento, aggiungere il codice seguente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] mapping degli spazi dei nomi.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. Denominare il valore predefinito <xref:System.Windows.Controls.Grid> elemento `mainGrid` assegnando il <xref:System.Windows.FrameworkElement.Name%2A> proprietà.  
  
     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## <a name="defining-the-data-template"></a>Definizione del modello dati  
 Viene visualizzato l'elenco master dei clienti un <xref:System.Windows.Controls.ListBox> controllo. L'esempio di codice seguente definisce una <xref:System.Windows.DataTemplate> oggetto denominato `ListItemsTemplate` che controlla la struttura ad albero visuale del <xref:System.Windows.Controls.ListBox> controllo. Ciò <xref:System.Windows.DataTemplate> viene assegnato per il <xref:System.Windows.Controls.ListBox> del controllo <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà.  
  
#### <a name="to-define-the-data-template"></a>Per definire il modello di dati  
  
- Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> dichiarazione dell'elemento.  
  
     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## <a name="specifying-the-form-layout"></a>Specifica del layout del form  
 Il layout del form è definito da una griglia con tre righe e tre colonne. <xref:System.Windows.Controls.Label> sono disponibili controlli per identificare ogni colonna nella tabella Customers.  
  
#### <a name="to-set-up-the-grid-layout"></a>Per impostare il layout Grid  
  
- Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> dichiarazione dell'elemento.  
  
     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### <a name="to-set-up-the-label-controls"></a>Per impostare i controlli Label  
  
- Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> dichiarazione dell'elemento.  
  
     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## <a name="specifying-data-bindings"></a>Specifica delle associazioni dati  
 Viene visualizzato l'elenco master dei clienti un <xref:System.Windows.Controls.ListBox> controllo. L'oggetto associato `ListItemsTemplate` associa un <xref:System.Windows.Controls.TextBlock> controllo di `ContactName` campo dal database.  
  
 I dettagli di ogni record del cliente vengono visualizzati in diverse <xref:System.Windows.Controls.TextBox> controlli.  
  
#### <a name="to-specify-data-bindings"></a>Per specificare le associazioni dati  
  
- Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> dichiarazione dell'elemento.  
  
     Il <xref:System.Windows.Data.Binding> classe associa il <xref:System.Windows.Controls.TextBox> controlli ai campi appropriati nel database.  
  
     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## <a name="displaying-data-by-using-interoperation"></a>Visualizzazione dei dati utilizzando l'interoperabilità  
 Gli ordini corrispondenti al cliente selezionato sono visualizzati una <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> controllo denominato `dataGridView1`. Il `dataGridView1` è associato all'origine dati nel file code-behind. Oggetto <xref:System.Windows.Forms.Integration.WindowsFormsHost> è il padre di questo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.  
  
#### <a name="to-display-data-in-the-datagridview-control"></a>Per visualizzare i dati nel controllo DataGridView  
  
- Copiare il seguente XAML nel <xref:System.Windows.Controls.Grid> dichiarazione dell'elemento.  
  
     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## <a name="adding-the-data-source-to-the-project"></a>Aggiunta dell'origine dati al progetto  
 Con Visual Studio, è possibile aggiungere facilmente un'origine dati al progetto. Con questa procedura vengono aggiunti dati fortemente tipizzati al progetto. Vengono anche aggiunte altre classi di supporto, ad esempio adattatori di tabelle.  
  
#### <a name="to-add-the-data-source"></a>Per aggiungere l'origine dati  
  
1. Dal **Data** dal menu **Aggiungi nuova origine dati**.  
  
2. Nel **configurazione guidata origine dati**, creare una connessione al database Northwind usando un set di dati. Per altre informazioni, vedere [Procedura: Connettersi ai dati in un Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).  
  
3. Quando viene richiesto per il **configurazione guidata origine dati**, salvare la stringa di connessione come `NorthwindConnectionString`.  
  
4. Quando viene chiesto di scegliere gli oggetti di database, selezionare la `Customers` e `Orders` tabelle e il nome di set di dati generato `NorthwindDataSet`.  
  
## <a name="binding-to-the-data-source"></a>Associazione all'origine dati  
 Il <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> componente fornisce un'interfaccia uniforme per l'origine dati dell'applicazione. L'associazione all'origine dati è implementata nel file code-behind.  
  
#### <a name="to-bind-to-the-data-source"></a>Per associare l'origine dati  
  
1. Aprire il file code-behind, denominato MainWindow.xaml.vb o MainWindow.xaml.cs.  
  
2. Copiare il codice seguente nel `MainWindow` definizione di classe.  
  
     Questo codice dichiara il <xref:System.Windows.Forms.BindingSource> componente e le classi helper associate che si connettono al database.  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. Copiare il seguente codice nel costruttore.

     Questo codice crea e inizializza il <xref:System.Windows.Forms.BindingSource> componente.

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. Aprire MainWindow.xaml.

5. Nella visualizzazione progettazione o XAML, selezionare il <xref:System.Windows.Window> elemento.

6. Nella finestra Proprietà scegliere il **eventi** scheda.

7. Fare doppio clic il <xref:System.Windows.FrameworkElement.Loaded> evento.

8. Copiare il codice seguente nel <xref:System.Windows.FrameworkElement.Loaded> gestore dell'evento.

     Questo codice assegna il <xref:System.Windows.Forms.BindingSource> componente come contesto dei dati e popola la `Customers` e `Orders` oggetti adattatore.

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. Copiare il codice seguente nel `MainWindow` definizione di classe.

     Questo metodo gestisce la <xref:System.Windows.Data.CollectionView.CurrentChanged> eventi e aggiorna l'elemento corrente dell'associazione dati.

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. Premere F5 per compilare ed eseguire l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Data Binding nell'esempio di applicazioni ibride](https://go.microsoft.com/fwlink/?LinkID=159983)
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
