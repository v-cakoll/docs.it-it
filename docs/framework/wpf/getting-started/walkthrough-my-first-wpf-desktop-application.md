---
title: Creare la prima app WPF in Visual Studio 2019-.NET Framework
titleSuffix: ''
description: Sviluppare un'applicazione desktop Windows Presentation Foundation (WPF) che includa elementi comuni alla maggior parte delle applicazioni WPF.
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
ms.openlocfilehash: c9af988bcf291325b11df4fd22827b47090c0b48
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853887"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a>Esercitazione: creare la prima applicazione WPF in Visual Studio 2019

Questo articolo illustra come sviluppare un'applicazione desktop Windows Presentation Foundation (WPF) che include gli elementi comuni alla maggior parte delle applicazioni WPF: markup Extensible Application Markup Language (XAML), code-behind, definizioni delle applicazioni, controlli, layout, data binding e stili. Per sviluppare l'applicazione, si userà Visual Studio.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare un progetto WPF.
> - Utilizzare XAML per progettare l'aspetto dell'interfaccia utente (UI) dell'applicazione.
> - Scrivere il codice per compilare il comportamento dell'applicazione.
> - Creare una definizione di applicazione per gestire l'applicazione.
> - Aggiungere i controlli e creare il layout per comporre l'interfaccia utente dell'applicazione.
> - Creare stili per un aspetto coerente nell'interfaccia utente dell'applicazione.
> - Associare l'interfaccia utente ai dati, sia per popolare l'interfaccia utente dai dati, sia per sincronizzare i dati e l'interfaccia utente.

Al termine dell'esercitazione, verrà creata un'applicazione Windows autonoma che consente agli utenti di visualizzare i report delle spese per le persone selezionate. L'applicazione è costituita da diverse pagine WPF ospitate in una finestra di tipo browser.

> [!TIP]
> Il codice di esempio usato in questa esercitazione è disponibile sia per Visual Basic che per C# nel [codice di esempio dell'app WPF dell'esercitazione](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).
>
> È possibile abilitare o disabilitare il linguaggio del codice di esempio tra C# e Visual Basic usando il selettore della lingua nella parte superiore di questa pagina.

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro sviluppo di applicazioni **desktop .NET** installato.

   Per ulteriori informazioni sull'installazione della versione più recente di Visual Studio, vedere [Install Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="create-the-application-project"></a>Creare il progetto dell'applicazione

Il primo passaggio consiste nel creare l'infrastruttura dell'applicazione, che include una definizione dell'applicazione, due pagine e un'immagine.

1. Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual C# denominato **`ExpenseIt`** :

   1. Aprire Visual Studio e selezionare **Crea un nuovo progetto** **nel menu inizia** .

      Verrà visualizzata la finestra **di dialogo Crea un nuovo progetto** .

   2. Nell'elenco a discesa **lingua** selezionare **C#** o **Visual Basic**.

   3. Selezionare il modello **applicazione WPF (.NET Framework)** e quindi fare clic su **Avanti**.

      ![Finestra di dialogo Crea nuovo progetto](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      Verrà visualizzata la finestra di dialogo **Configura nuovo progetto** .

   4. Immettere il nome del progetto **`ExpenseIt`** e quindi selezionare **Crea**.

      ![Finestra di dialogo Configura nuovo progetto](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      Visual Studio crea il progetto e apre la finestra di progettazione per la finestra dell'applicazione predefinita denominata **MainWindow. XAML**.

2. Aprire *Application. XAML* (Visual Basic) o *app. XAML* (C#).

    Questo file XAML definisce un'applicazione WPF e tutte le risorse dell'applicazione. Questo file viene usato anche per specificare l'interfaccia utente, in questo caso *MainWindow. XAML*, che mostra automaticamente all'avvio dell'applicazione.

    Il codice XAML dovrebbe essere simile al seguente in Visual Basic:

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    Analogamente a quanto riportato di seguito in C#:

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. Aprire *MainWindow. XAML*.

    Questo file XAML è la finestra principale dell'applicazione e visualizza il contenuto creato in pagine. La <xref:System.Windows.Window> classe definisce le proprietà di una finestra, ad esempio il titolo, le dimensioni o l'icona, e gestisce gli eventi, ad esempio la chiusura o il nascondiglio.

4. Modificare l' <xref:System.Windows.Window> elemento in un oggetto <xref:System.Windows.Navigation.NavigationWindow> , come illustrato nel codice XAML seguente:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   Questa app passa a un contenuto diverso a seconda dell'input dell'utente. Questo è il motivo per cui è <xref:System.Windows.Window> necessario modificare il principale in un <xref:System.Windows.Navigation.NavigationWindow> . <xref:System.Windows.Navigation.NavigationWindow>eredita tutte le proprietà di <xref:System.Windows.Window> . L' <xref:System.Windows.Navigation.NavigationWindow> elemento nel file XAML crea un'istanza della <xref:System.Windows.Navigation.NavigationWindow> classe. Per altre informazioni, vedere [Cenni preliminari sulla navigazione](../app-development/navigation-overview.md).

5. Rimuovere gli <xref:System.Windows.Controls.Grid> elementi tra i <xref:System.Windows.Navigation.NavigationWindow> tag.

6. Modificare le proprietà seguenti nel codice XAML per l' <xref:System.Windows.Navigation.NavigationWindow> elemento:

    - Impostare la <xref:System.Windows.Window.Title%2A> proprietà su " `ExpenseIt` ".

    - Impostare la <xref:System.Windows.FrameworkElement.Height%2A> proprietà su 350 pixel.

    - Impostare la <xref:System.Windows.FrameworkElement.Width%2A> proprietà su 500 pixel.

    Il codice XAML dovrebbe essere simile al seguente per Visual Basic:

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    E come il seguente per C#:

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. Aprire *MainWindow. XAML. vb* o *MainWindow.XAML.cs*.

    Questo file è un file code-behind che contiene il codice per gestire gli eventi dichiarati in *MainWindow. XAML*. Il file contiene una classe parziale per la finestra definita in XAML.

8. Se si usa C#, modificare la `MainWindow` classe in modo che derivi da <xref:System.Windows.Navigation.NavigationWindow> . (In Visual Basic, questa operazione viene eseguita automaticamente quando si modifica la finestra in XAML.) Il codice C# dovrebbe ora essere simile al seguente:

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a>Aggiunta di file all'applicazione

In questa sezione si aggiungeranno due pagine e un'immagine all'applicazione.

1. Aggiungere una nuova pagina al progetto e denominarla *`ExpenseItHome.xaml`* :

   1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul **`ExpenseIt`** nodo del progetto e scegliere **Aggiungi**  >  **pagina**.

   1. Nella finestra di dialogo **Aggiungi nuovo elemento** , il modello **pagina (WPF)** è già selezionato. Immettere il nome **`ExpenseItHome`** e quindi selezionare **Aggiungi**.

    Questa pagina è la prima pagina visualizzata all'avvio dell'applicazione. Verrà visualizzato un elenco di utenti da selezionare per visualizzare una nota spese per.

1. Aprire *`ExpenseItHome.xaml`* .

1. Impostare <xref:System.Windows.Controls.Page.Title%2A> su " `ExpenseIt - Home` ".

1. Impostare `DesignHeight` su 350 pixel e `DesignWidth` su 500 pixel.

    Il codice XAML ora viene visualizzato come segue per Visual Basic:

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    E come il seguente per C#:

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. Aprire *MainWindow. XAML*.

1. Aggiungere una <xref:System.Windows.Navigation.NavigationWindow.Source%2A> proprietà all' <xref:System.Windows.Navigation.NavigationWindow> elemento e impostarla su " `ExpenseItHome.xaml` ".

    Questa impostazione *`ExpenseItHome.xaml`* è la prima pagina aperta all'avvio dell'applicazione.

    XAML di esempio in Visual Basic:

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    E in C#:

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > È anche possibile impostare la proprietà **source** nella categoria **varie** della finestra **proprietà** .
   >
   > ![Proprietà di origine in Finestra Proprietà](./media/properties-source.png)

1. Aggiungere un'altra nuova pagina WPF al progetto e denominarla *ExpenseReportPage. XAML*::

   1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul **`ExpenseIt`** nodo del progetto e scegliere **Aggiungi**  >  **pagina**.

   1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello **pagina (WPF)** . Immettere il nome **ExpenseReportPage**e quindi selezionare **Aggiungi**.

    Questa pagina visualizzerà la nota spese per la persona selezionata nella **`ExpenseItHome`** pagina.

1. Aprire *ExpenseReportPage. XAML*.

1. Impostare <xref:System.Windows.Controls.Page.Title%2A> su " `ExpenseIt - View Expense` ".

1. Impostare `DesignHeight` su 350 pixel e `DesignWidth` su 500 pixel.

    *ExpenseReportPage. XAML* ha ora un aspetto simile al seguente in Visual Basic:

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    Analogamente a quanto riportato di seguito in C#:

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. Aprire *ExpenseItHome. XAML. vb* e *ExpenseReportPage. XAML. vb*o *ExpenseItHome.XAML.cs* e *ExpenseReportPage.XAML.cs*.

    Quando si crea un nuovo file di paging, Visual Studio crea automaticamente il file *code-behind* . Questi file code-behind gestiscono la logica per rispondere all'input dell'utente.

    Il codice dovrebbe essere simile al seguente per **`ExpenseItHome`** :

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    Come indicato di seguito per **ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. Aggiungere un'immagine denominata *watermark.png* al progetto. È possibile creare un'immagine personalizzata, copiare il file dal codice di esempio o ottenerlo dal repository GitHub [Microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) .

    1. Fare clic con il pulsante destro del mouse sul nodo del progetto e scegliere **Aggiungi**  >  **elemento esistente**oppure premere **MAIUSC** + **ALT** + **A**.

    2. Nella finestra di dialogo **Aggiungi elemento esistente** impostare filtro file su **tutti** i file o **file di immagine**, passare al file di immagine che si vuole usare e quindi selezionare **Aggiungi**.

## <a name="build-and-run-the-application"></a>Compilare ed eseguire l'applicazione

1. Per compilare ed eseguire l'applicazione, premere **F5** o scegliere **Avvia debug** dal menu **debug** .

    La figura seguente mostra l'applicazione con i <xref:System.Windows.Navigation.NavigationWindow> pulsanti:

    ![Applicazione dopo la compilazione e l'esecuzione.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. Chiudere l'applicazione per tornare a Visual Studio.

## <a name="create-the-layout"></a>Creare il layout

Il layout fornisce un modo ordinato per inserire gli elementi dell'interfaccia utente e gestisce anche le dimensioni e la posizione di tali elementi quando viene ridimensionata un'interfaccia utente. In genere si crea un layout tramite uno dei controlli di layout seguenti:

- <xref:System.Windows.Controls.Canvas>: Definisce un'area all'interno della quale è possibile posizionare in modo esplicito gli elementi figlio usando le coordinate relative all'area Canvas.
- <xref:System.Windows.Controls.DockPanel>: Definisce un'area in cui è possibile disporre gli elementi figlio in senso orizzontale o verticale, in relazione l'uno con l'altro.
- <xref:System.Windows.Controls.Grid>: Definisce un'area griglia flessibile costituita da righe e colonne.
- <xref:System.Windows.Controls.StackPanel>: Dispone gli elementi figlio in una sola riga che può essere orientata orizzontalmente o verticalmente.
- <xref:System.Windows.Controls.VirtualizingStackPanel>: Dispone e virtualizza il contenuto su una sola riga orientata orizzontalmente o verticalmente.
- <xref:System.Windows.Controls.WrapPanel>-Posiziona gli elementi figlio in sequenza da sinistra a destra, suddividendo il contenuto nella riga successiva al bordo della casella contenitore. L'ordinamento successivo avviene in sequenza dall'alto verso il basso o da destra a sinistra, a seconda del valore della proprietà Orientation.

Ognuno di questi controlli di layout supporta un particolare tipo di layout per i relativi elementi figlio. `ExpenseIt`le pagine possono essere ridimensionate e ogni pagina contiene elementi disposti orizzontalmente e verticalmente insieme ad altri elementi. In questo esempio, <xref:System.Windows.Controls.Grid> viene utilizzato come elemento layout per l'applicazione.

> [!TIP]
> Per altre informazioni sugli <xref:System.Windows.Controls.Panel> elementi, vedere [Cenni preliminari sui pannelli](../controls/panels-overview.md). Per ulteriori informazioni sul layout, vedere [layout](../advanced/layout.md).

In questa sezione viene creata una tabella a colonna singola con tre righe e un margine di 10 pixel aggiungendo definizioni di colonna e di riga a <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`* .

1. In *`ExpenseItHome.xaml`* impostare la <xref:System.Windows.FrameworkElement.Margin%2A> proprietà dell'elemento su <xref:System.Windows.Controls.Grid> "10, 0, 10, 10", che corrisponde ai margini sinistro, superiore, destro e inferiore:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > È inoltre possibile impostare i valori dei **margini** nella finestra **Proprietà** , sotto la categoria **layout** :
   >
   > ![Valori dei margini in Finestra Proprietà](./media/properties-margin.png)

2. Aggiungere il seguente codice XAML tra i <xref:System.Windows.Controls.Grid> tag per creare le definizioni di riga e di colonna:

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    Il <xref:System.Windows.Controls.RowDefinition.Height%2A> di due righe è impostato su <xref:System.Windows.GridLength.Auto%2A> , il che significa che le righe vengono ridimensionate in base al contenuto delle righe. Il valore predefinito <xref:System.Windows.Controls.RowDefinition.Height%2A> è il <xref:System.Windows.GridUnitType.Star> dimensionamento, che indica che l'altezza della riga è una proporzione ponderata dello spazio disponibile. Se, ad esempio, due righe hanno un valore <xref:System.Windows.Controls.RowDefinition.Height%2A> di "*", ognuna ha un'altezza pari alla metà dello spazio disponibile.

    Il <xref:System.Windows.Controls.Grid> dovrebbe ora contenere il seguente codice XAML:

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>Aggiungere controlli

In questa sezione verrà aggiornata l'interfaccia utente di home page per visualizzare un elenco di persone, in cui è possibile selezionare una persona per visualizzare la nota spese. I controlli sono oggetti dell'interfaccia utente che consentono agli utenti di interagire con l'applicazione. Per altre informazioni, vedere [Controlli](../controls/index.md).

Per creare questa interfaccia utente, aggiungere gli elementi seguenti a *`ExpenseItHome.xaml`* :

- <xref:System.Windows.Controls.ListBox>(Per l'elenco di persone).
- Oggetto <xref:System.Windows.Controls.Label> (per l'intestazione dell'elenco).
- <xref:System.Windows.Controls.Button>(Per fare clic per visualizzare la nota spese per la persona selezionata nell'elenco).

Ogni controllo è posizionato in una riga di impostando <xref:System.Windows.Controls.Grid> la <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> proprietà associata. Per ulteriori informazioni sulle proprietà associate, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).

1. In *`ExpenseItHome.xaml`* aggiungere il codice XAML seguente tra i <xref:System.Windows.Controls.Grid> Tag:

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > È anche possibile creare i controlli trascinandoli dalla finestra **casella degli strumenti** nella finestra di progettazione e quindi impostarne le proprietà nella finestra **Proprietà** .

2. Compilare ed eseguire l'applicazione.

    Nella figura seguente sono illustrati i controlli creati:

![Schermata di esempio ExpenseIt che visualizza un elenco di nomi](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a>Aggiungere un'immagine e un titolo

In questa sezione si aggiornerà l'interfaccia utente di home page con un'immagine e un titolo della pagina.

1. In *`ExpenseItHome.xaml`* aggiungere un'altra colonna a <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con un valore fisso <xref:System.Windows.Controls.ColumnDefinition.Width%2A> di 230 pixel:

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. Aggiungere un'altra riga a <xref:System.Windows.Controls.Grid.RowDefinitions%2A> , per un totale di quattro righe:

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. Spostare i controlli nella seconda colonna impostando la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> proprietà su 1 in ognuno dei tre controlli (bordo, casella di riepilogo e pulsante).

4. Spostare ogni controllo verso il basso di una riga incrementando il <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> valore di 1 per ognuno dei tre controlli (bordo, casella di riepilogo e pulsante) e per l'elemento Border.

   Il codice XAML per i tre controlli ha ora un aspetto simile al seguente:

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. Impostare la <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> proprietà sul file di immagine *watermark.png* , aggiungendo il codice XAML seguente in qualsiasi punto tra i `<Grid>` `</Grid>` tag e:

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. Prima dell' <xref:System.Windows.Controls.Border> elemento, aggiungere un oggetto <xref:System.Windows.Controls.Label> con il contenuto "View Expense Report". Questa etichetta è il titolo della pagina.

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. Compilare ed eseguire l'applicazione.

La figura seguente mostra i risultati di quanto appena aggiunto:

![Schermata di esempio di ExpenseIt che mostra la nuova immagine di sfondo e titolo della pagina](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a>Aggiungere codice per gestire gli eventi

1. In *`ExpenseItHome.xaml`* aggiungere un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi all' <xref:System.Windows.Controls.Button> elemento. Per altre informazioni, vedere [procedura: creare un gestore eventi semplice](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. Aprire *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`* .

3. Aggiungere il codice seguente alla `ExpenseItHome` classe per aggiungere un gestore dell'evento click del pulsante. Il gestore eventi apre la pagina **ExpenseReportPage** .

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>Creare l'interfaccia utente per ExpenseReportPage

*ExpenseReportPage. XAML* Visualizza la nota spese per la persona selezionata nella **`ExpenseItHome`** pagina. In questa sezione verrà creata l'interfaccia utente per **ExpenseReportPage**. Verranno inoltre aggiunti i colori di sfondo e riempimento ai vari elementi dell'interfaccia utente.

1. Aprire *ExpenseReportPage. XAML*.

2. Aggiungere il codice XAML seguente tra i <xref:System.Windows.Controls.Grid> Tag:

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    Questa interfaccia utente è simile a *`ExpenseItHome.xaml`* , ad eccezione del fatto che i dati del report vengono visualizzati in un oggetto <xref:System.Windows.Controls.DataGrid> .

3. Compilare ed eseguire l'applicazione.

4. Selezionare il pulsante **Visualizza** .

    Viene visualizzata la pagina della nota spese. Si noti anche che il pulsante di spostamento indietro è abilitato.

La figura seguente Mostra gli elementi dell'interfaccia utente aggiunti a *ExpenseReportPage. XAML*.

![Schermata di esempio ExpenseIt che mostra l'interfaccia utente appena creata per il ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a>Controlli di stile

L'aspetto dei vari elementi è spesso lo stesso per tutti gli elementi dello stesso tipo in un'interfaccia utente. L'interfaccia utente usa gli [stili](../../../desktop-wpf/fundamentals/styles-templates-overview.md) per rendere i riutilizzabili in più elementi. La riutilizzabilità degli stili consente di semplificare la creazione e la gestione di XAML. In questa sezione vengono sostituiti con gli stili gli attributi per elemento definiti nei passaggi precedenti.

1. Aprire *Application. XAML* o *app. XAML*.

2. Aggiungere il codice XAML seguente tra i <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Tag:

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    Questo codice XAML aggiunge gli stili seguenti:

    - `headerTextStyle`: per formattare il titolo della pagina <xref:System.Windows.Controls.Label>.

    - `labelStyle`: per formattare i controlli <xref:System.Windows.Controls.Label> .

    - `columnHeaderStyle`: per formattare <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.

    - `listHeaderStyle`: per formattare i controlli <xref:System.Windows.Controls.Border> dell'intestazione dell'elenco.

    - `listHeaderTextStyle`: Per formattare l'intestazione dell'elenco <xref:System.Windows.Controls.Label> .

    - `buttonStyle`: Per formattare l'oggetto <xref:System.Windows.Controls.Button> in `ExpenseItHome.xaml` .

    Si noti che gli stili sono risorse e elementi figlio dell' <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> elemento Property. In questa posizione, gli stili vengono applicati a tutti gli elementi di un'applicazione. Per un esempio dell'uso delle risorse in un'app .NET, vedere [usare le risorse dell'applicazione](../advanced/how-to-use-application-resources.md).

3. In *`ExpenseItHome.xaml`* sostituire tutti gli elementi tra gli <xref:System.Windows.Controls.Grid> elementi con il codice XAML seguente:

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    Le proprietà come <xref:System.Windows.VerticalAlignment> e <xref:System.Windows.Media.FontFamily> che definiscono l'aspetto di ciascun controllo vengono rimosse e sostituite mediante l'applicazione degli stili. Ad esempio, l'oggetto `headerTextStyle` viene applicato a "View Expense Report" <xref:System.Windows.Controls.Label> .

4. Aprire *ExpenseReportPage. XAML*.

5. Sostituire tutti gli <xref:System.Windows.Controls.Grid> elementi con il codice XAML seguente:

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    Questo codice XAML aggiunge stili agli <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Border> elementi e.

6. Compilare ed eseguire l'applicazione. L'aspetto della finestra è identico a quello precedente.

    ![Schermata di esempio ExpenseIt con lo stesso aspetto dell'ultima sezione.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. Chiudere l'applicazione per tornare a Visual Studio.

## <a name="bind-data-to-a-control"></a>Associare dati a un controllo

In questa sezione verranno creati i dati XML associati a vari controlli.

1. In *`ExpenseItHome.xaml`* , dopo l' <xref:System.Windows.Controls.Grid> elemento Opening, aggiungere il seguente codice XAML per creare un oggetto <xref:System.Windows.Data.XmlDataProvider> che contiene i dati per ogni persona:

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    I dati vengono creati come <xref:System.Windows.Controls.Grid> risorsa. Normalmente questi dati vengono caricati come file, ma per semplicità i dati vengono aggiunti inline.

2. Nell' `<Grid.Resources>` elemento aggiungere l' `<xref:System.Windows.DataTemplate>` elemento seguente, che definisce come visualizzare i dati in <xref:System.Windows.Controls.ListBox> , dopo l' `<XmlDataProvider>` elemento:

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    Per ulteriori informazioni sui modelli di dati, vedere [Cenni preliminari](../data/data-templating-overview.md)sui modelli di dati.

3. Sostituire il file esistente <xref:System.Windows.Controls.ListBox> con il codice XAML seguente:

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    Questo codice XAML associa la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà di <xref:System.Windows.Controls.ListBox> all'origine dati e applica il modello di dati come <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> .

## <a name="connect-data-to-controls"></a>Connettere i dati ai controlli

Successivamente, verrà aggiunto il codice per recuperare il nome selezionato nella **`ExpenseItHome`** pagina e passarlo al costruttore di **ExpenseReportPage**. **ExpenseReportPage** imposta il contesto dei dati con l'elemento passato, ovvero l'associazione tra i controlli definiti in *ExpenseReportPage. XAML* .

1. Aprire *ExpenseReportPage. XAML. vb* o *ExpenseReportPage.XAML.cs*.

2. Aggiungere un costruttore che accetti un oggetto, in modo da poter passare i dati della nota spese della persona selezionata.

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. Aprire *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`* .

4. Modificare il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi per chiamare il nuovo costruttore passando i dati della nota spese della persona selezionata.

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>Applicare uno stile ai dati con i modelli di dati

In questa sezione verrà aggiornata l'interfaccia utente per ogni elemento negli elenchi associati a dati utilizzando i modelli di dati.

1. Aprire *ExpenseReportPage. XAML*.

2. Associare il contenuto degli elementi "Name" e "Department" <xref:System.Windows.Controls.Label> alla proprietà dell'origine dati appropriata. Per ulteriori informazioni su data binding, vedere [Cenni preliminari sul data binding](../../../desktop-wpf/data/data-binding-overview.md).

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. Dopo l' <xref:System.Windows.Controls.Grid> elemento Opening, aggiungere i modelli di dati seguenti, che definiscono come visualizzare i dati della nota spese:

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. Sostituire gli <xref:System.Windows.Controls.DataGridTextColumn> elementi con <xref:System.Windows.Controls.DataGridTemplateColumn> sotto l' <xref:System.Windows.Controls.DataGrid> elemento e applicarvi i modelli.

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. Compilare ed eseguire l'applicazione.

6. Selezionare una persona e quindi fare clic sul pulsante **Visualizza** .

Nella figura seguente sono illustrate entrambe le pagine dell' `ExpenseIt` applicazione con i controlli, il layout, gli stili, data binding e i modelli di dati applicati:

![Entrambe le pagine dell'app che mostrano l'elenco dei nomi e una nota spese.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> Questo esempio illustra una funzionalità specifica di WPF e non segue tutte le procedure consigliate per elementi come sicurezza, localizzazione e accessibilità. Per una copertura completa delle procedure consigliate per lo sviluppo di applicazioni .NET e WPF, vedere gli argomenti seguenti:
>
> - [Accessibilità](../../ui-automation/accessibility-best-practices.md)
> - [Sicurezza](../security-wpf.md)
> - [Globalizzazione e localizzazione WPF](../advanced/wpf-globalization-and-localization-overview.md)
> - [Prestazioni di WPF](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>Passaggi successivi

In questa procedura dettagliata sono state illustrate alcune tecniche per la creazione di un'interfaccia utente con Windows Presentation Foundation (WPF). A questo punto si dovrebbe avere una conoscenza di base dei blocchi predefiniti di un'app .NET associata a dati. Per altre informazioni sull'architettura WPF e i modelli di programmazione, vedere gli argomenti seguenti:

- [Architettura WPF](../advanced/wpf-architecture.md)
- [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Panoramica delle proprietà di dipendenza](../advanced/dependency-properties-overview.md)
- [Layout](../advanced/layout.md)

Per altre informazioni sulla creazione di applicazioni, vedere gli argomenti seguenti:

- [Sviluppo di applicazioni](../app-development/index.md)
- [Controlli](../controls/index.md)
- [Panoramica del data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Elementi grafici e multimediali](../graphics-multimedia/index.md)
- [Documenti in WPF](../advanced/documents-in-wpf.md)

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui pannelli](../controls/panels-overview.md)
- [Panoramica sui modelli di dati](../data/data-templating-overview.md)
- [Creare un'applicazione WPF](../app-development/building-a-wpf-application-wpf.md)
- [Stili e modelli](../controls/styles-and-templates.md)
