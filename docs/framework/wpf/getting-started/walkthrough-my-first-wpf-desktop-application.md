---
title: Creare la prima app WPF in Visual Studio 2019 - .NET Framework
titleSuffix: ''
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: 9381873faa8cca1accf95d823f5183a218d28813
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646421"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a>Esercitazione: Creare la prima applicazione WPF in Visual Studio 2019Tutorial: Create your first WPF application in Visual Studio 2019

In questo articolo viene illustrato come sviluppare un'applicazione desktop Windows Presentation Foundation (WPF) che include gli elementi comuni alla maggior parte delle applicazioni WPFWPF: markup XAML (Extensible Application Markup Language), code-behind, definizioni di applicazioni, controlli, layout, associazione dati e stili. Per sviluppare l'applicazione, si userà Visual Studio.To develop the application, you'll use Visual Studio.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare un progetto WPF.
> - Usa XAML per progettare l'aspetto dell'interfaccia utente dell'applicazione.
> - Scrivere codice per compilare il comportamento dell'applicazione.
> - Creare una definizione di applicazione per gestire l'applicazione.
> - Aggiungere controlli e creare il layout per comporre l'interfaccia utente dell'applicazione.
> - Creare stili per un aspetto coerente in tutta l'interfaccia utente dell'applicazione.
> - Associare l'interfaccia utente ai dati, sia per popolare l'interfaccia utente dai dati che per mantenere sincronizzati i dati e l'interfaccia utente.

Alla fine dell'esercitazione, avrai creato un'applicazione Windows autonoma che consente agli utenti di visualizzare le note spese per persone selezionate. L'applicazione è composta da diverse pagine WPF ospitate in una finestra di tipo browser.

> [!TIP]
> Il codice di esempio utilizzato in questa esercitazione è disponibile sia per Visual Basic che per C, in [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).
>
> È possibile attivare o disattivare il linguaggio di codice del codice di esempio tra C ' e Visual Basic utilizzando il selettore del linguaggio nella parte superiore di questa pagina.

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro di **sviluppo desktop .NET** installato.

   Per ulteriori informazioni sull'installazione della versione più recente di Visual Studio, vedere [Installare Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="create-the-application-project"></a>Creare il progetto di applicazioneCreate the application project

Il primo passaggio consiste nel creare l'infrastruttura dell'applicazione, che include una definizione di applicazione, due pagine e un'immagine.

1. Creare un nuovo progetto di applicazione WPF **`ExpenseIt`** in Visual Basic o Visual C, denominato :

   1. Aprire Visual Studio e selezionare **Crea un nuovo progetto** nel menu Inizia.Open Visual Studio and select Create a new project under the Get **started** menu.

      Viene visualizzata la finestra di dialogo **Crea un nuovo progetto.**

   2. Nell'elenco a discesa **Linguaggio,** selezionare **C '** o **Visual Basic**.

   3. Selezionare il modello **App WPF (.NET Framework)** e quindi **scegliere Avanti**.

      ![Finestra di dialogo Crea un nuovo progetto](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      Viene visualizzata la finestra di dialogo **Configura il nuovo progetto.**

   4. Immettere il **`ExpenseIt`** nome del progetto e quindi selezionare **Crea**.

      ![Finestra di dialogo Configura un nuovo progetto](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      Visual Studio crea il progetto e apre la finestra di progettazione per la finestra dell'applicazione predefinita **denominata MainWindow.xaml**.

2. Aprire *Application.xaml* (Visual Basic) o *App.xaml* (C' ).

    Questo file XAML definisce un'applicazione WPF e tutte le risorse dell'applicazione. Questo file viene utilizzato anche per specificare l'interfaccia utente, in questo caso *MainWindow.xaml*, che viene visualizzata automaticamente all'avvio dell'applicazione.

    Il codice XAML dovrebbe essere simile al seguente in Visual Basic:Your XAML should look like the following in Visual Basic:

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    E come il seguente in C :

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. Aprire *MainWindow.xaml*.

    Questo file XAML è la finestra principale dell'applicazione e visualizza il contenuto creato nelle pagine. La <xref:System.Windows.Window> classe definisce le proprietà di una finestra, ad esempio il titolo, le dimensioni o l'icona, e gestisce gli eventi, ad esempio la chiusura o l'occultamento.

4. Modificare <xref:System.Windows.Window> l'elemento <xref:System.Windows.Navigation.NavigationWindow>in un oggetto , come illustrato nel codice XAML seguente:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   Questa app passa a contenuti diversi a seconda dell'input dell'utente. Questo è il <xref:System.Windows.Window> motivo per <xref:System.Windows.Navigation.NavigationWindow>cui il principale deve essere cambiato in un . <xref:System.Windows.Navigation.NavigationWindow>eredita tutte le <xref:System.Windows.Window>proprietà di . L'elemento <xref:System.Windows.Navigation.NavigationWindow> nel file XAML crea <xref:System.Windows.Navigation.NavigationWindow> un'istanza della classe. Per ulteriori informazioni, consultate [Panoramica della navigazione.](../app-development/navigation-overview.md)

5. Rimuovere <xref:System.Windows.Controls.Grid> gli elementi <xref:System.Windows.Navigation.NavigationWindow> tra i tag.

6. Modificare le proprietà seguenti nel <xref:System.Windows.Navigation.NavigationWindow> codice XAML per l'elemento:

    - Impostare <xref:System.Windows.Window.Title%2A> la`ExpenseIt`proprietà su " ".

    - Impostare <xref:System.Windows.FrameworkElement.Height%2A> la proprietà su 350 pixel.

    - Impostare <xref:System.Windows.FrameworkElement.Width%2A> la proprietà su 500 pixel.

    Il codice XAML dovrebbe essere simile al seguente per Visual Basic:Your XAML should look like the following for Visual Basic:

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    E come il seguente per il linguaggio C:

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. Aprire *MainWindow.xaml.vb* o *MainWindow.xaml.cs*.

    Questo file è un file code-behind che contiene il codice per gestire gli eventi dichiarati in *MainWindow.xaml*. Il file contiene una classe parziale per la finestra definita in XAML.

8. Se si utilizza C, modificare `MainWindow` la classe <xref:System.Windows.Navigation.NavigationWindow>in modo che derivi da . (In Visual Basic, questo accade automaticamente quando si modifica la finestra in XAML.) Il codice di C'è ora simile al seguente:Your C's code should now look like this:

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a>Aggiungere file all'applicazione

In questa sezione si aggiungeranno due pagine e un'immagine all'applicazione.

1. Aggiungere una nuova pagina al progetto *`ExpenseItHome.xaml`* e denominarla:

   1. In **Esplora soluzioni**fare **`ExpenseIt`** clic con il pulsante destro del mouse sul nodo del progetto e **scegliere Aggiungi** > **pagina**.

   1. Nella finestra di dialogo **Aggiungi nuovo elemento,** il modello **Pagina (WPF)** è già selezionato. Immettere **`ExpenseItHome`** il nome , quindi selezionare **Aggiungi**.

    Questa pagina è la prima pagina visualizzata all'avvio dell'applicazione. Verrà visualizzato un elenco di persone tra cui scegliere, per cui visualizzare una nota spese.

1. Aperto *`ExpenseItHome.xaml`*.

1. Impostare <xref:System.Windows.Controls.Page.Title%2A> il`ExpenseIt - Home`su " ".

1. Impostare `DesignHeight` il valore di `DesignWidth` 350 pixel e 500 pixel.

    Il codice XAML viene ora visualizzato come segue per Visual Basic:The XAML now appears as follows for Visual Basic:

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    E come il seguente per il linguaggio C:

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. Aprire *MainWindow.xaml*.

1. Aggiungere <xref:System.Windows.Navigation.NavigationWindow.Source%2A> una proprietà <xref:System.Windows.Navigation.NavigationWindow> all'elemento e`ExpenseItHome.xaml`impostarla su " ".

    Questo *`ExpenseItHome.xaml`* imposta per essere la prima pagina aperta all'avvio dell'applicazione.

    XAML di esempio in Visual Basic:Example XAML in Visual Basic:

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    E in C:

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > È inoltre possibile impostare la proprietà **Source** nella categoria **Varie** della finestra **Proprietà.**
   >
   > ![Proprietà Source nella finestra Proprietà](./media/properties-source.png)

1. Aggiungere un'altra nuova pagina WPF al progetto e denominarla *ExpenseReportPage.xaml*::

   1. In **Esplora soluzioni**fare **`ExpenseIt`** clic con il pulsante destro del mouse sul nodo del progetto e **scegliere Aggiungi** > **pagina**.

   1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello Pagina **(WPF).** Immettere il nome **ExpenseReportPage**, quindi selezionare **Aggiungi**.

    In questa pagina verrà visualizzata la nota **`ExpenseItHome`** spese per la persona selezionata nella pagina.

1. Aprire *ExpenseReportPage.xaml*.

1. Impostare <xref:System.Windows.Controls.Page.Title%2A> il`ExpenseIt - View Expense`su " ".

1. Impostare `DesignHeight` il valore di `DesignWidth` 350 pixel e 500 pixel.

    *ExpenseReportPage.xaml* è ora simile al seguente in Visual Basic:

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    E come il seguente in C :

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. Aprire *ExpenseItHome.xaml.vb* e *ExpenseReportPage.xaml.vb*oppure *ExpenseItHome.xaml.cs* e *ExpenseReportPage.xaml.cs*.

    Quando si crea un nuovo file di paging, Visual Studio crea automaticamente il relativo file *code-behind.* Questi file code-behind gestiscono la logica per rispondere all'input dell'utente.

    Il codice dovrebbe essere **`ExpenseItHome`** simile al seguente per :

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    E come il seguente per **ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. Aggiungere un'immagine denominata *watermark.png* al progetto. È possibile creare un'immagine personalizzata, copiare il file dal codice di esempio o ottenerlo dal repository GitHub [di microsoft/WPF-Samples.You](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) can create your own image, copy the file from the sample code, or get it from the microsoft/WPF-Samples GitHub repository.

    1. Fare clic con il pulsante destro del mouse sul nodo del progetto e selezionare **Aggiungi** > **elemento esistente**oppure premere**ALT**+**A** **.**+

    2. Nella finestra di dialogo **Aggiungi elemento esistente** impostare il filtro di file su Tutti i **file** o **File di immagine**, individuare il file di immagine che si desidera utilizzare e quindi scegliere **Aggiungi**.

## <a name="build-and-run-the-application"></a>Compilare ed eseguire l'applicazione

1. Per compilare ed eseguire l'applicazione, premere **F5** o scegliere **Avvia debug** dal menu **Debug** .

    La figura seguente mostra <xref:System.Windows.Navigation.NavigationWindow> l'applicazione con i pulsanti:

    ![L'applicazione dopo averla compilata ed eseguita.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. Chiudere l'applicazione per tornare a Visual Studio.

## <a name="create-the-layout"></a>Creare il layout

Layout fornisce un modo ordinato per posizionare gli elementi dell'interfaccia utente e gestisce anche le dimensioni e la posizione di tali elementi quando un'interfaccia utente viene ridimensionata. In genere si crea un layout tramite uno dei controlli di layout seguenti:

- <xref:System.Windows.Controls.Canvas>- Definisce un'area all'interno della quale è possibile posizionare in modo esplicito gli elementi figlio utilizzando coordinate relative all'area di disegno.
- <xref:System.Windows.Controls.DockPanel>- Definisce un'area in cui è possibile disporre gli elementi figlio orizzontalmente o verticalmente, uno rispetto all'altro.
- <xref:System.Windows.Controls.Grid>- Definisce un'area della griglia flessibile costituita da colonne e righe.
- <xref:System.Windows.Controls.StackPanel>- Dispone gli elementi figlio in un'unica riga che può essere orientata orizzontalmente o verticalmente.
- <xref:System.Windows.Controls.VirtualizingStackPanel>- Dispone e virtualizza il contenuto su una singola riga orientata orizzontalmente o verticalmente.
- <xref:System.Windows.Controls.WrapPanel>- Posiziona gli elementi figlio in posizione sequenziale da sinistra a destra, suddividendo il contenuto alla riga successiva sul bordo della casella contenitore. L'ordinamento successivo viene eseguito in sequenza dall'alto verso il basso o da destra a sinistra, a seconda del valore della proprietà Orientation.

Ognuno di questi controlli di layout supporta un particolare tipo di layout per i relativi elementi figlio. `ExpenseIt`le pagine possono essere ridimensionate e ogni pagina contiene elementi disposti orizzontalmente e verticalmente insieme ad altri elementi. In questo esempio, l'oggetto <xref:System.Windows.Controls.Grid> viene utilizzato come elemento di layout per l'applicazione.

> [!TIP]
> Per ulteriori <xref:System.Windows.Controls.Panel> informazioni sugli elementi, consultate [Panoramica dei pannelli.](../controls/panels-overview.md) Per ulteriori informazioni sul layout, consultate [Layout.](../advanced/layout.md)

In questa sezione viene creata una tabella a colonna singola con tre righe e un <xref:System.Windows.Controls.Grid> *`ExpenseItHome.xaml`* margine di 10 pixel aggiungendo definizioni di colonna e riga alla .

1. In *`ExpenseItHome.xaml`*, <xref:System.Windows.FrameworkElement.Margin%2A> impostare <xref:System.Windows.Controls.Grid> la proprietà dell'elemento su "10,0,10,10", che corrisponde ai margini sinistro, superiore, destro e inferiore:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > È inoltre possibile impostare i valori **Margine** nella finestra **Proprietà,** nella categoria **Layout:**
   >
   > ![Valori di margine nella finestra Proprietà](./media/properties-margin.png)

2. Aggiungere il codice <xref:System.Windows.Controls.Grid> XAML seguente tra i tag per creare le definizioni di riga e colonna:

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    L'oggetto <xref:System.Windows.Controls.RowDefinition.Height%2A> di due <xref:System.Windows.GridLength.Auto%2A>righe è impostato su , il che significa che le righe vengono ridimensionate in base al contenuto delle righe. L'impostazione predefinita <xref:System.Windows.Controls.RowDefinition.Height%2A> è <xref:System.Windows.GridUnitType.Star> il ridimensionamento, il che significa che l'altezza della riga è una proporzione ponderata dello spazio disponibile. Ad esempio, se due <xref:System.Windows.Controls.RowDefinition.Height%2A> righe hanno ciascuna un dici, ognuna di esse ha un'altezza pari alla metà dello spazio disponibile.

    Il <xref:System.Windows.Controls.Grid> codice XAML dovrebbe ora contenere il codice XAML seguente:Your should now contain the following XAML:

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>Aggiungere controlli

In questa sezione si aggiornerà l'interfaccia utente della home page per visualizzare un elenco di persone, in cui è possibile selezionare una persona per visualizzare la nota spese. I controlli sono oggetti dell'interfaccia utente che consentono agli utenti di interagire con l'applicazione. Per altre informazioni, vedere [Controlli](../controls/index.md).

Per creare questa interfaccia utente, si *`ExpenseItHome.xaml`* aggiungeranno i seguenti elementi a:

- A <xref:System.Windows.Controls.ListBox> (per l'elenco delle persone).
- A <xref:System.Windows.Controls.Label> (per l'intestazione dell'elenco).
- A <xref:System.Windows.Controls.Button> (per visualizzare la nota spese per la persona selezionata nell'elenco).

Ogni controllo viene inserito <xref:System.Windows.Controls.Grid> in una <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> riga dell'oggetto impostando la proprietà associata. Per ulteriori informazioni sulle proprietà associate, vedere [Cenni preliminari](../advanced/attached-properties-overview.md)sulle proprietà associate .

1. In *`ExpenseItHome.xaml`*, aggiungi il codice <xref:System.Windows.Controls.Grid> XAML seguente tra i tag:

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > È inoltre possibile creare i controlli trascinandoli dalla finestra **Casella degli strumenti** nella finestra di progettazione e impostandone le proprietà nella finestra **Proprietà.**

2. Compilare ed eseguire l'applicazione.

    Nella figura seguente vengono illustrati i controlli creati:

![Schermata di esempio ExpenseIt che visualizza un elenco di nomi](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a>Aggiungere un'immagine e un titolo

In questa sezione aggiornerai l'interfaccia utente della home page con un'immagine e un titolo di pagina.

1. In *`ExpenseItHome.xaml`*, aggiungere un'altra colonna al <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con un fisso <xref:System.Windows.Controls.ColumnDefinition.Width%2A> di 230 pixel:

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. Aggiungere un'altra <xref:System.Windows.Controls.Grid.RowDefinitions%2A>riga a , per un totale di quattro righe:

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. Spostare i controlli nella seconda <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> colonna impostando la proprietà su 1 in ognuno dei tre controlli (Border, ListBox e Button).

4. Spostare ogni controllo verso il <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> basso di una riga incrementandone il valore di 1 per ognuno dei tre controlli (Border, ListBox e Button) e per l'elemento Border.

   Il codice XAML per i tre controlli è ora simile al seguente:The XAML for the three controls now looks like the following:

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. Impostare <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> la proprietà sul file di immagine *watermark.png,* aggiungendo il codice XAML seguente in qualsiasi punto tra i `<Grid>` tag e `</Grid>` :

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. Prima <xref:System.Windows.Controls.Border> dell'elemento, <xref:System.Windows.Controls.Label> aggiungere a con il contenuto "Visualizza nota spese". Questa etichetta è il titolo della pagina.

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. Compilare ed eseguire l'applicazione.

La figura seguente mostra i risultati di ciò che è stato appena aggiunto:

![Schermata di esempio ExpenseIt che mostra lo sfondo della nuova immagine e il titolo della pagina](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a>Aggiungere codice per gestire gli eventiAdd code to handle events

1. In *`ExpenseItHome.xaml`*, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> aggiungere un <xref:System.Windows.Controls.Button> gestore eventi all'elemento. Per ulteriori informazioni, vedere [Procedura: creare un gestore eventi semplice.](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. Aperto *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* o .

3. Aggiungere il codice `ExpenseItHome` seguente alla classe per aggiungere un gestore dell'evento Click del pulsante. Il gestore eventi apre la pagina **ExpenseReportPage.**

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>Creare l'interfaccia utente per ExpenseReportPageCreate the UI for ExpenseReportPage

*ExpenseReportPage.xaml* visualizza la nota spese per la **`ExpenseItHome`** persona selezionata nella pagina. In questa sezione verrà creata l'interfaccia utente per **ExpenseReportPage**. Potrai anche aggiungere colori di sfondo e riempimento ai vari elementi dell'interfaccia utente.

1. Aprire *ExpenseReportPage.xaml*.

2. Aggiungere il codice <xref:System.Windows.Controls.Grid> XAML seguente tra i tag:

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    Questa interfaccia utente *`ExpenseItHome.xaml`* è simile a , ad <xref:System.Windows.Controls.DataGrid>eccezione del fatto che i dati del report vengono visualizzati in un oggetto .

3. Compilare ed eseguire l'applicazione.

4. Selezionare il pulsante **Visualizza.**

    Viene visualizzata la pagina della nota spese. Si noti inoltre che il pulsante di spostamento indietro è abilitato.

Nella figura seguente vengono illustrati gli elementi dell'interfaccia utente aggiunti a *ExpenseReportPage.xaml*.

![ExpenseIt sample screenshot showing the UI just created for the ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a>Controlli di stile

L'aspetto di vari elementi è spesso lo stesso per tutti gli elementi dello stesso tipo in un'interfaccia utente. L'interfaccia utente usa [gli stili](../../../desktop-wpf/fundamentals/styles-templates-overview.md) per rendere gli aspetti riutilizzabili su più elementi. La riusabilità degli stili consente di semplificare la creazione e la gestione di XAML. In questa sezione vengono sostituiti con gli stili gli attributi per elemento definiti nei passaggi precedenti.

1. Aprire *Application.xaml* o *App.xaml*.

2. Aggiungere il codice <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> XAML seguente tra i tag:

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    Questo codice XAML aggiunge gli stili seguenti:

    - `headerTextStyle`: per formattare il titolo della pagina <xref:System.Windows.Controls.Label>.

    - `labelStyle`: per formattare i controlli <xref:System.Windows.Controls.Label> .

    - `columnHeaderStyle`: per formattare <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.

    - `listHeaderStyle`: per formattare i controlli <xref:System.Windows.Controls.Border> dell'intestazione dell'elenco.

    - `listHeaderTextStyle`: per formattare <xref:System.Windows.Controls.Label>l'intestazione dell'elenco.

    - `buttonStyle`: per <xref:System.Windows.Controls.Button> formattare `ExpenseItHome.xaml`l'oggetto .

    Si noti che gli stili <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> sono risorse e elementi figlio dell'elemento proprietà. In questa posizione, gli stili vengono applicati a tutti gli elementi di un'applicazione. Per un esempio di utilizzo delle risorse in un'app .NET, vedere [Usare le risorse dell'applicazione.](../advanced/how-to-use-application-resources.md)

3. In *`ExpenseItHome.xaml`*, sostituisci <xref:System.Windows.Controls.Grid> tutti gli elementi tra gli elementi con il codice XAML seguente:

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    Le proprietà come <xref:System.Windows.VerticalAlignment> e <xref:System.Windows.Media.FontFamily> che definiscono l'aspetto di ciascun controllo vengono rimosse e sostituite mediante l'applicazione degli stili. Ad esempio, `headerTextStyle` l'oggetto viene applicato <xref:System.Windows.Controls.Label>alla cartella "Visualizza nota spese".

4. Aprire *ExpenseReportPage.xaml*.

5. Sostituisci tutti <xref:System.Windows.Controls.Grid> gli elementi tra gli elementi con il codice XAML seguente:

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    Questo codice XAML <xref:System.Windows.Controls.Label> aggiunge <xref:System.Windows.Controls.Border> stili agli elementi e .

6. Compilare ed eseguire l'applicazione. L'aspetto della finestra è lo stesso di prima.

    ![Schermata di esempio ExpenseIt con lo stesso aspetto dell'ultima sezione.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. Chiudere l'applicazione per tornare a Visual Studio.

## <a name="bind-data-to-a-control"></a>Associare dati a un controlloBind data to a control

In questa sezione verranno creati i dati XML associati a vari controlli.

1. In *`ExpenseItHome.xaml`*, dopo <xref:System.Windows.Controls.Grid> l'elemento di apertura, <xref:System.Windows.Data.XmlDataProvider> aggiungere il codice XAML seguente per creare un oggetto che contiene i dati per ogni persona:

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    I dati vengono <xref:System.Windows.Controls.Grid> creati come risorsa. Normalmente questi dati verrebbero caricati come file, ma per semplicità i dati vengono aggiunti inline.

2. All'interno `<Grid.Resources>` dell'elemento, aggiungere il `<xref:System.Windows.DataTemplate>` seguente elemento, che <xref:System.Windows.Controls.ListBox>definisce `<XmlDataProvider>` come visualizzare i dati in , dopo l'elemento:

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    Per ulteriori informazioni sui modelli di dati, vedere [Panoramica](../data/data-templating-overview.md)dei modelli di dati .

3. Sostituire l'esistente <xref:System.Windows.Controls.ListBox> con il codice XAML seguente:

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    Questo codice XAML <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> associa <xref:System.Windows.Controls.ListBox> la proprietà dell'oggetto all'origine <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>dati e applica il modello di dati come metodo .

## <a name="connect-data-to-controls"></a>Connettere i dati ai controlli

Successivamente, si aggiungerà il codice per recuperare il **`ExpenseItHome`** nome selezionato nella pagina e passarlo al costruttore di **ExpenseReportPage**. **ExpenseReportPage** imposta il contesto dati con l'elemento passato, ovvero a cosa si associano i controlli definiti in *ExpenseReportPage.xaml.*

1. Aprire *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.

2. Aggiungere un costruttore che accetti un oggetto, in modo da poter passare i dati della nota spese della persona selezionata.

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. Aperto *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* o .

4. Modificare <xref:System.Windows.Controls.Primitives.ButtonBase.Click> il gestore eventi per chiamare il nuovo costruttore passando i dati della nota spese della persona selezionata.

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>Applicare stili ai dati con i modelli di dati

In questa sezione si aggiornerà l'interfaccia utente per ogni elemento negli elenchi con associazione a dati usando i modelli di dati.

1. Aprire *ExpenseReportPage.xaml*.

2. Associare il contenuto degli elementi "Name" e "Department" <xref:System.Windows.Controls.Label> alla proprietà dell'origine dati appropriata. Per ulteriori informazioni sull'associazione dati, vedere [Panoramica dell'associazione dati](../../../desktop-wpf/data/data-binding-overview.md).

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. Dopo l'elemento di apertura, <xref:System.Windows.Controls.Grid> aggiungere i modelli di dati seguenti, che definiscono come visualizzare i dati della nota spese:

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. Sostituire <xref:System.Windows.Controls.DataGridTextColumn> gli <xref:System.Windows.Controls.DataGridTemplateColumn> elementi <xref:System.Windows.Controls.DataGrid> con sotto l'elemento e applicarvi i modelli.

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. Compilare ed eseguire l'applicazione.

6. Selezionare una persona, quindi fare clic sul pulsante **Visualizza.**

Nella figura seguente vengono `ExpenseIt` illustrate entrambe le pagine dell'applicazione con controlli, layout, stili, associazione dati e modelli di dati applicati:

![Entrambe le pagine dell'app che mostrano l'elenco dei nomi e una nota spese.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> In questo esempio viene illustrata una funzionalità specifica di WPFWPF e non vengono illustrate tutte le procedure consigliate per elementi quali sicurezza, localizzazione e accessibilità. Per una copertura completa delle procedure consigliate per lo sviluppo di app .NET e WPF e .NET, vedere gli argomenti seguenti:For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:
>
> - [Accessibilità](../../ui-automation/accessibility-best-practices.md)
> - [Sicurezza](../security-wpf.md)
> - [Globalizzazione e localizzazione WPF](../advanced/wpf-globalization-and-localization-overview.md)
> - [Prestazioni WPFWPF performance](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>Passaggi successivi

In questa procedura dettagliata sono state illustrate diverse tecniche per la creazione di un'interfaccia utente tramite Windows Presentation Foundation (WPF). A questo punto dovresti avere una conoscenza di base dei blocchi predefiniti di un'app .NET con associazione a dati. Per altre informazioni sull'architettura WPF e i modelli di programmazione, vedere gli argomenti seguenti:

- [Architettura WPFWPF architecture](../advanced/wpf-architecture.md)
- [Panoramica di XAML (WPF)XAML overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Panoramica delle proprietà di dipendenzaDependency properties overview](../advanced/dependency-properties-overview.md)
- [Layout](../advanced/layout.md)

Per altre informazioni sulla creazione di applicazioni, vedere gli argomenti seguenti:

- [Sviluppo di applicazioni](../app-development/index.md)
- [Controlli](../controls/index.md)
- [Panoramica del data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Grafica e multimedia](../graphics-multimedia/index.md)
- [Documenti in WPF](../advanced/documents-in-wpf.md)

## <a name="see-also"></a>Vedere anche

- [Panoramica dei pannelli](../controls/panels-overview.md)
- [Panoramica dei modelli di datiData templating overview](../data/data-templating-overview.md)
- [Compilare un'applicazione WPFBuild a WPF application](../app-development/building-a-wpf-application-wpf.md)
- [Stili e modelli](../controls/styles-and-templates.md)
