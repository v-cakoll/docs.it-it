---
title: 'Procedura dettagliata: associazione ai dati in applicazioni ibride'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: 1bb38436049e338ab6033ae3b6370732a457d520
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794218"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>Procedura dettagliata: associazione ai dati in applicazioni ibride

Il binding di un'origine dati a un controllo è essenziale per consentire agli utenti di accedere ai dati sottostanti, indipendentemente dal fatto che si utilizzino Windows Forms o [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Questa procedura dettagliata illustra come è possibile usare data binding in applicazioni ibride che includono controlli sia Windows Forms che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione del progetto.

- Definizione del modello dati.

- Specifica del layout del form.

- Specifica delle associazioni dati.

- Visualizzazione dei dati usando l'interoperabilità.

- Aggiunta dell'origine dati al progetto.

- Associazione all'origine dati.

Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [esempio di associazione dati in applicazioni ibride](https://go.microsoft.com/fwlink/?LinkID=159983).

Al termine, si conosceranno le funzionalità di associazione dati nelle applicazioni ibride.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

- Visual Studio.

- Accesso al database di esempio Northwind in esecuzione in Microsoft SQL Server.

## <a name="creating-the-project"></a>Creazione del progetto

### <a name="to-create-and-set-up-the-project"></a>Per creare e impostare il progetto

1. Creare un progetto di applicazione WPF denominato `WPFWithWFAndDatabinding`.

2. In Esplora soluzioni aggiungere riferimenti agli assembly seguenti.

    - WindowsFormsIntegration

    - System.Windows.Forms

3. Aprire MainWindow. XAML in WPF Designer.

4. Nell'elemento <xref:System.Windows.Window> aggiungere il mapping degli spazi dei nomi Windows Forms seguente.

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. Denominare l'elemento predefinito <xref:System.Windows.Controls.Grid> `mainGrid` assegnando la proprietà <xref:System.Windows.FrameworkElement.Name%2A>.

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a>Definizione del modello dati

L'elenco principale dei clienti viene visualizzato in un controllo <xref:System.Windows.Controls.ListBox>. Nell'esempio di codice seguente viene definito un oggetto <xref:System.Windows.DataTemplate> denominato `ListItemsTemplate` che controlla la struttura ad albero visuale del controllo <xref:System.Windows.Controls.ListBox>. Questo <xref:System.Windows.DataTemplate> viene assegnato alla proprietà <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> del controllo <xref:System.Windows.Controls.ListBox>.

### <a name="to-define-the-data-template"></a>Per definire il modello di dati

- Copiare il codice XAML seguente nella dichiarazione dell'elemento <xref:System.Windows.Controls.Grid>.

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a>Specifica del layout del form

Il layout del form è definito da una griglia con tre righe e tre colonne. per identificare ogni colonna della tabella Customers sono disponibili controlli <xref:System.Windows.Controls.Label>.

### <a name="to-set-up-the-grid-layout"></a>Per impostare il layout Grid

- Copiare il codice XAML seguente nella dichiarazione dell'elemento <xref:System.Windows.Controls.Grid>.

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a>Per impostare i controlli Label

- Copiare il codice XAML seguente nella dichiarazione dell'elemento <xref:System.Windows.Controls.Grid>.

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a>Specifica delle associazioni dati

L'elenco principale dei clienti viene visualizzato in un controllo <xref:System.Windows.Controls.ListBox>. Il `ListItemsTemplate` collegato associa un controllo <xref:System.Windows.Controls.TextBlock> al campo `ContactName` dal database.

I dettagli di ogni record cliente vengono visualizzati in diversi controlli <xref:System.Windows.Controls.TextBox>.

### <a name="to-specify-data-bindings"></a>Per specificare le associazioni dati

- Copiare il codice XAML seguente nella dichiarazione dell'elemento <xref:System.Windows.Controls.Grid>.

     La classe <xref:System.Windows.Data.Binding> associa i controlli <xref:System.Windows.Controls.TextBox> ai campi appropriati nel database.

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a>Visualizzazione dei dati utilizzando l'interoperabilità

Gli ordini corrispondenti al cliente selezionato vengono visualizzati in un controllo <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> denominato `dataGridView1`. Il controllo `dataGridView1` viene associato all'origine dati nel file code-behind. Un controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> è l'elemento padre di questo controllo Windows Forms.

### <a name="to-display-data-in-the-datagridview-control"></a>Per visualizzare i dati nel controllo DataGridView

- Copiare il codice XAML seguente nella dichiarazione dell'elemento <xref:System.Windows.Controls.Grid>.

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a>Aggiunta dell'origine dati al progetto

Con Visual Studio è possibile aggiungere facilmente un'origine dati al progetto. Con questa procedura vengono aggiunti dati fortemente tipizzati al progetto. Vengono anche aggiunte altre classi di supporto, ad esempio adattatori di tabelle.

### <a name="to-add-the-data-source"></a>Per aggiungere l'origine dati

1. Scegliere **Aggiungi nuova origine dati**dal menu **dati** .

2. Nella **Configurazione guidata origine dati**creare una connessione al database Northwind utilizzando un set di dati. Per altre informazioni, vedere [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).

3. Quando viene richiesta la **Configurazione guidata origine dati**, salvare la stringa di connessione come `NorthwindConnectionString`.

4. Quando viene richiesto di scegliere gli oggetti di database, selezionare le tabelle `Customers` e `Orders` e denominare il set di dati generato `NorthwindDataSet`.

## <a name="binding-to-the-data-source"></a>Associazione all'origine dati

Il componente <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> fornisce un'interfaccia uniforme per l'origine dati dell'applicazione. L'associazione all'origine dati è implementata nel file code-behind.

### <a name="to-bind-to-the-data-source"></a>Per associare l'origine dati

1. Aprire il file code-behind, denominato MainWindow.xaml.vb o MainWindow.xaml.cs.

2. Copiare il codice seguente nella definizione della classe `MainWindow`.

     Questo codice dichiara il componente <xref:System.Windows.Forms.BindingSource> e le classi helper associate che si connettono al database.

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. Copiare il seguente codice nel costruttore.

     Questo codice crea e inizializza il componente <xref:System.Windows.Forms.BindingSource>.

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. Aprire MainWindow.xaml.

5. Nella visualizzazione progettazione o nella visualizzazione XAML Selezionare l'elemento <xref:System.Windows.Window>.

6. Nella Finestra Proprietà fare clic sulla scheda **eventi** .

7. Fare doppio clic sull'evento <xref:System.Windows.FrameworkElement.Loaded>.

8. Copiare il codice seguente nel gestore eventi <xref:System.Windows.FrameworkElement.Loaded>.

     Questo codice assegna il componente <xref:System.Windows.Forms.BindingSource> come contesto dati e popola gli oggetti `Customers` e `Orders` adapter.

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. Copiare il codice seguente nella definizione della classe `MainWindow`.

     Questo metodo gestisce l'evento <xref:System.Windows.Data.CollectionView.CurrentChanged> e aggiorna l'elemento corrente del data binding.

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. Premere F5 per compilare ed eseguire l'applicazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Esempio di associazione dati in applicazioni ibride](https://go.microsoft.com/fwlink/?LinkID=159983)
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
