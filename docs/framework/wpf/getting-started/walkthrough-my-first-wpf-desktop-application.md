---
title: Creare un'applicazione WPF in Visual Studio
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.custom: vs-dotnet
ms.openlocfilehash: c3440ddf6cdae6b24bcf1059ab2c76d8fb957263
ms.sourcegitcommit: 11deacc8ec9f229ab8ee3cd537515d4c2826515f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2019
ms.locfileid: "66003861"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>Procedura dettagliata: Compilare una prima applicazione desktop WPF

Questo articolo illustra come sviluppare un'applicazione desktop di Windows Presentation Foundation (WPF) che include gli elementi che sono comuni alla maggior parte delle applicazioni WPF: Extensible Application Markup Language (XAML) markup, code-behind, definizioni delle applicazioni, controlli, layout, associazione dati e stili. Per sviluppare l'applicazione, si userà Visual Studio. 

Questa procedura dettagliata include i passaggi seguenti:

- Usare XAML per progettare l'aspetto dell'interfaccia utente dell'applicazione (UI).

- Scrivere codice per compilare un comportamento dell'applicazione.

- Creare una definizione di applicazione per gestire l'applicazione.

- Aggiungere controlli e creare il layout per comporre l'interfaccia utente dell'applicazione.

- Creare stili per coerenza dell'aspetto dell'interfaccia utente dell'applicazione.

- Associare l'interfaccia utente ai dati per popolare l'interfaccia utente dai dati e mantenere i dati e dell'interfaccia utente sincronizzato.

Al termine della procedura dettagliata, verrà creata un'applicazione Windows che consente agli utenti di visualizzare rapporti spese per gli utenti selezionati autonoma. L'applicazione è costituita da diverse pagine WPF ospitate in una finestra di tipo browser.

> [!TIP]
> Il codice di esempio che viene usato per compilare questa procedura dettagliata è disponibile per entrambi Visual Basic e C# alla [codice di esempio di App WPF Walkthrough](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).
>
> È possibile attivare o disattivare il linguaggio del codice del codice di esempio tra C# e Visual Basic usando il **\< />** elenco a discesa in alto a destra di questo articolo.

## <a name="prerequisites"></a>Prerequisiti

- Visual Studio 2017 o versione successiva (in questo articolo Usa Visual Studio 2019)

   Per altre informazioni sull'installazione della versione più recente di Visual Studio, vedere [installazione di Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="create-the-application-project"></a>Creare il progetto di applicazione

Il primo passaggio consiste nel creare l'infrastruttura dell'applicazione, che include una definizione di applicazione, due pagine e un'immagine.

1. Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual c# denominato **`ExpenseIt`**:

   1. Aprire Visual Studio e selezionare **creare un nuovo progetto** sotto il **iniziare** menu.

      Il **creare un nuovo progetto** verrà visualizzata la finestra di dialogo.

   2. Nel **Language** elenco a discesa, selezionare **C#** oppure **Visual Basic**.
      
   3. Selezionare il **App WPF (.NET Framework)** modello e quindi selezionare **successivo**. 
     
      ![Creare una finestra di dialogo Nuovo progetto](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      Il **configurare il nuovo progetto** verrà visualizzata la finestra di dialogo.

   4. Immettere il nome del progetto **`ExpenseIt`** e quindi selezionare **Create**.

      ![Configurare una finestra di dialogo Nuovo progetto](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      Visual Studio crea il progetto e apre la finestra di progettazione per la finestra dell'applicazione predefinita denominata **MainWindow. XAML**.

2. Aprire *Application. XAML* (Visual Basic) o *app* (c#).

    Questo file XAML definisce un'applicazione WPF e tutte le risorse dell'applicazione. È anche usare questo file per specificare l'interfaccia utente, in questo caso *MainWindow. XAML*, visualizzato automaticamente all'avvio dell'applicazione.

    il XAML dovrebbe essere simile al seguente in Visual Basic:

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    E come il seguente in C#:

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. Aprire *MainWindow. XAML*.

    Questo file XAML è la finestra principale dell'applicazione e visualizza il contenuto creato nelle pagine. Il <xref:System.Windows.Window> classe definisce le proprietà di una finestra, ad esempio titolo, dimensione o icona e gestisce gli eventi, ad esempio la chiusura o nascondere.

4. Modifica il <xref:System.Windows.Window> elemento da un <xref:System.Windows.Navigation.NavigationWindow>, come illustrato in XAML i seguenti:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   Questa app consente di passare a contenuto diverso a seconda di input dell'utente. Questo è il motivo principale <xref:System.Windows.Window> deve essere modificato in un <xref:System.Windows.Navigation.NavigationWindow>. <xref:System.Windows.Navigation.NavigationWindow> eredita tutte le proprietà di <xref:System.Windows.Window>. Il <xref:System.Windows.Navigation.NavigationWindow> elemento nel file XAML crea un'istanza di <xref:System.Windows.Navigation.NavigationWindow> classe. Per altre informazioni, vedere [Cenni preliminari sulla navigazione](../app-development/navigation-overview.md).

5. Rimuovere il <xref:System.Windows.Controls.Grid> degli elementi da tra il <xref:System.Windows.Navigation.NavigationWindow> tag.

6. Modificare le proprietà seguenti nel codice XAML per il <xref:System.Windows.Navigation.NavigationWindow> elemento:

    - Impostare il <xref:System.Windows.Window.Title%2A> proprietà su "`ExpenseIt`".

    - Impostare il <xref:System.Windows.FrameworkElement.Height%2A> proprietà su 350 pixel.

    - Impostare il <xref:System.Windows.FrameworkElement.Width%2A> proprietà su 500 pixel.

    il XAML dovrebbe essere simile al seguente per Visual Basic:

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    E simili al seguente per C#:

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. Aprire *XAML. vb* oppure *MainWindow.xaml.cs*.

    Questo file è un file code-behind che contiene il codice per gestire gli eventi dichiarati nelle *MainWindow. XAML*. Il file contiene una classe parziale per la finestra definita in XAML.

8. Se si usa C#, modificare il `MainWindow` classe derivandola da <xref:System.Windows.Navigation.NavigationWindow>. (In Visual Basic, ciò avviene automaticamente quando si modifica la finestra in XAML.) Il C# codice dovrebbe ora essere simile al seguente:

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a>Aggiungere i file all'applicazione

In questa sezione si aggiungeranno due pagine e un'immagine all'applicazione.

1. Aggiungere una nuova pagina al progetto e denominarlo *`ExpenseItHome.xaml`*:

   1. Nelle **Esplora soluzioni**, fare clic sul **`ExpenseIt`** nodo del progetto e scegliere **Add** > **pagina**.

   1. Nel **Aggiungi nuovo elemento** finestra di dialogo, il **pagina (WPF)** modello è già selezionato. Immettere il nome **`ExpenseItHome`**, quindi selezionare **Add**.

    Questa pagina è la prima pagina visualizzata quando viene avviata l'applicazione. Mostrerà un elenco di utenti di selezionare, per visualizzare una nota spese per.

1. Aprire *`ExpenseItHome.xaml`*.

1. Impostare il <xref:System.Windows.Controls.Page.Title%2A> a "`ExpenseIt - Home`".

1. Impostare il `DesignHeight` e `DesignWidth` valori degli elementi di 300 pixel.

    il XAML ora viene visualizzata come indicato di seguito per Visual Basic:

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    E simili al seguente per C#:

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. Aprire *MainWindow. XAML*.

1. Aggiungere un <xref:System.Windows.Navigation.NavigationWindow.Source%2A> proprietà per il <xref:System.Windows.Navigation.NavigationWindow> elemento e impostarla su "`ExpenseItHome.xaml`".

    Questo imposta *`ExpenseItHome.xaml`* prima pagina aperta all'avvio dell'applicazione. 

    Esempio di XAML in Visual Basic:

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    E nel linguaggio C#:

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > È anche possibile impostare il **origine** proprietà nel **varie** categoria del **proprietà** finestra.
   >
   > ![Proprietà di origine nella finestra proprietà](./media/properties-source.png)

1. Aggiungere un'altra nuova pagina WPF al progetto e denominarlo *ExpenseReportPage. XAML*::

   1. Nelle **Esplora soluzioni**, fare clic sul **`ExpenseIt`** nodo del progetto e scegliere **Add** > **pagina**.

   1. Nel **Aggiungi nuovo elemento** finestra di dialogo, seleziona la **pagina (WPF)** modello. Immettere il nome **ExpenseReportPage**, quindi selezionare **Add**.

    Questa pagina visualizzerà la nota spese della persona selezionata nella **`ExpenseItHome`** pagina.

1. Aprire *ExpenseReportPage.xaml*.

1. Impostare il <xref:System.Windows.Controls.Page.Title%2A> a "`ExpenseIt - View Expense`".

1. Impostare il `DesignHeight` e `DesignWidth` valori degli elementi di 300 pixel.

    *ExpenseReportPage. XAML* ora ha un aspetto analogo al seguente in Visual Basic:

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    E come il seguente in C#:

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. Aprire *ExpenseItHome* e *ExpenseReportPage*, o *ExpenseItHome.xaml.cs* e *ExpenseReportPage.xaml.cs*.

    Quando si crea un nuovo file di paging, Visual Studio crea automaticamente relativi *code-behind* file. Questi file code-behind gestiscono la logica per rispondere all'input dell'utente.

    Il codice dovrebbe essere simile al seguente per **`ExpenseItHome`**:

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    E simili al seguente per **ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. Aggiungere un'immagine denominata *watermark. PNG* al progetto. È possibile creare un'immagine, copiare il file dal codice di esempio o ottenerlo [qui](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).

    1. Fare doppio clic sul nodo del progetto e selezionare **Add** > **elemento esistente**, oppure premere **MAIUSC**+**Alt** + **Oggetto**.

    2. Nel **Aggiungi elemento esistente** finestra di dialogo impostare il filtro del file a uno **tutti i file** o **i file di immagine**, selezionare il file di immagine si vuole usare e quindi selezionare **Add** .

## <a name="build-and-run-the-application"></a>Compilazione ed esecuzione dell'applicazione

1. Per compilare ed eseguire l'applicazione, premere **F5** oppure selezionare **Avvia debug** dal **Debug** menu.

    La figura seguente mostra l'applicazione con il <xref:System.Windows.Navigation.NavigationWindow> pulsanti:

    ![Applicazione dopo aver compilato e di eseguirlo.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. Chiudere l'applicazione per tornare a Visual Studio.

## <a name="create-the-layout"></a>Creare il layout

Layout consente di posizionare gli elementi dell'interfaccia utente in modo ordinato e di gestione le dimensioni e posizione degli elementi durante il ridimensionamento di un'interfaccia utente. In genere si crea un layout tramite uno dei controlli di layout seguenti:

- <xref:System.Windows.Controls.Canvas> -Definisce un'area all'interno del quale è possibile posizionare in modo esplicito elementi figlio tramite coordinate relative rispetto all'area di disegno.
- <xref:System.Windows.Controls.DockPanel> -Definisce un'area in cui è possibile disporre elementi figlio orizzontalmente o verticalmente, uno rispetto a altro.
- <xref:System.Windows.Controls.Grid> -Definisce un'area griglia flessibile costituita da righe e colonne.
- <xref:System.Windows.Controls.StackPanel> -Dispone gli elementi figlio in una singola riga che può essere orientata orizzontalmente o verticalmente.
- <xref:System.Windows.Controls.VirtualizingStackPanel> -Dispone e virtualizza il contenuto in una sola riga che può essere orientata orizzontalmente o verticalmente.
- <xref:System.Windows.Controls.WrapPanel> -Posiziona gli elementi figlio in sequenza da sinistra a destra, contenuto di rilievo alla riga successiva sul bordo della casella contenitore. Ordinamento successivo procede in sequenza dall'alto verso il basso o da destra a sinistra, a seconda del valore della proprietà Orientation.

Ognuno di questi controlli di layout supporta un determinato tipo di layout per i relativi elementi figlio. `ExpenseIt` è possono ridimensionare le pagine e ogni pagina contiene elementi disposti orizzontalmente e verticalmente insieme ad altri elementi. In questo esempio, il <xref:System.Windows.Controls.Grid> viene usato come elemento di layout per l'applicazione.

> [!TIP]
> Per altre informazioni sulle <xref:System.Windows.Controls.Panel> elementi, vedere [Cenni preliminari su pannelli](../controls/panels-overview.md). Per altre informazioni sul layout, vedere [Layout](../advanced/layout.md).

In questa sezione è creare una tabella a colonna singola con tre righe e un margine di 10 pixel tramite l'aggiunta di definizioni di colonna e riga per il <xref:System.Windows.Controls.Grid> nelle *`ExpenseItHome.xaml`*.

1. Nel *`ExpenseItHome.xaml`*, impostare il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà di <xref:System.Windows.Controls.Grid> elemento "10,0,10,10", che corrispondono ai margini sinistro, superiore, destro e inferiore:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > È anche possibile impostare il **margine** i valori del **proprietà** finestra, sotto il **Layout** categoria:
   >
   > ![Valori dei margini nella finestra proprietà](./media/properties-margin.png)

2. Aggiungere il seguente XAML tra i <xref:System.Windows.Controls.Grid> tag per creare le definizioni di riga e colonna:

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    Il <xref:System.Windows.Controls.RowDefinition.Height%2A> di due righe è impostata su <xref:System.Windows.GridLength.Auto%2A>, il che significa che le righe vengono ridimensionate in base al contenuto delle righe. Il valore predefinito <xref:System.Windows.Controls.RowDefinition.Height%2A> è <xref:System.Windows.GridUnitType.Star> determinazione della dimensione, ciò significa che l'altezza della riga è una proporzione ponderata dello spazio disponibile. Se, ad esempio due righe hanno un <xref:System.Windows.Controls.RowDefinition.Height%2A> di "*", ognuno ha un'altezza pari alla metà dello spazio disponibile.

    Il <xref:System.Windows.Controls.Grid> dovrebbe ora contenere il seguente XAML:

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>Aggiungere controlli

In questa sezione, si aggiornerà la home page dell'interfaccia utente per visualizzare un elenco di persone, in cui si seleziona una persona per visualizzare la nota spese. I controlli sono oggetti dell'interfaccia utente che consentono agli utenti di interagire con l'applicazione. Per altre informazioni, vedere [Controlli](../controls/index.md).

Per creare questa interfaccia utente, è necessario aggiungere gli elementi seguenti alla *`ExpenseItHome.xaml`*:

- Oggetto <xref:System.Windows.Controls.ListBox> (per l'elenco di persone).
- Oggetto <xref:System.Windows.Controls.Label> (per l'intestazione dell'elenco).
- Oggetto <xref:System.Windows.Controls.Button> (deve fare clic per visualizzare la nota spese della persona selezionata nell'elenco).

Ogni controllo viene inserito in una riga della <xref:System.Windows.Controls.Grid> impostando la <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> proprietà associata. Per altre informazioni sulle proprietà associate, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).

1. Nelle *`ExpenseItHome.xaml`*, aggiungere il seguente XAML in una posizione tra le <xref:System.Windows.Controls.Grid> tag:

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > È anche possibile creare i controlli trascinandoli dal **casella degli strumenti** alla finestra di progettazione e quindi impostando le proprietà nella finestra di **proprietà** finestra.

2. Compilare ed eseguire l'applicazione.

    La figura seguente mostra i controlli che è stato creato:

![Screenshot di esempio ExpenseIt Mostra un elenco di nomi](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a>Aggiungere un'immagine e un titolo

In questa sezione, si verrà aggiornata la home page dell'interfaccia utente con un'immagine e un titolo della pagina.

1. Nelle *`ExpenseItHome.xaml`*, aggiungere un'altra colonna per il <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con fisse <xref:System.Windows.Controls.ColumnDefinition.Width%2A> di 230 pixel:

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. Aggiungere un'altra riga per il <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, per un totale di quattro righe:

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. Spostare i controlli nella seconda colonna impostando il <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> proprietà su 1 in ognuno dei tre controlli (bordo, ListBox e pulsante).

4. Spostare ogni controllo verso il basso una riga incrementando il relativo <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> valore di 1 per ognuno dei tre controlli (bordo, ListBox e pulsante) e per l'elemento Border.

   il XAML per i tre controlli ora simile al seguente:

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. Impostare il <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> proprietà per il *watermark. PNG* file di immagine, aggiungendo il seguente XAML in un punto qualsiasi tra il `<Grid>` e `</Grid>` tag:

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. Prima di <xref:System.Windows.Controls.Border> elemento, aggiungere un <xref:System.Windows.Controls.Label> con il contenuto "View Expense Report". Questa etichetta è il titolo della pagina.

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. Compilare ed eseguire l'applicazione.

La figura seguente mostra i risultati di ciò che appena aggiunto:

![Screenshot di esempio ExpenseIt che mostra il nuovo titolo della pagina e in background immagine](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a>Aggiungere il codice per gestire gli eventi

1. Nelle *`ExpenseItHome.xaml`*, aggiungere un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore dell'evento per il <xref:System.Windows.Controls.Button> elemento. Per altre informazioni, vedere [Procedura: Creare un gestore eventi semplice](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. Aprire *`ExpenseItHome.xaml.vb`* oppure *`ExpenseItHome.xaml.cs`*.

3. Aggiungere il codice seguente per il `ExpenseItHome` classe per aggiungere un pulsante gestore dell'evento click. Il gestore eventi apre la **ExpenseReportPage** pagina.

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>Creare l'interfaccia utente per ExpenseReportPage

*ExpenseReportPage. XAML* consente di visualizzare la nota spese della persona selezionata nella **`ExpenseItHome`** pagina. In questa sezione si creerà l'interfaccia utente per **ExpenseReportPage**. Verrà inoltre aggiunto sfondo e colori di riempimento ai vari elementi dell'interfaccia utente.

1. Aprire *ExpenseReportPage.xaml*.

2. Aggiungere il seguente XAML tra i <xref:System.Windows.Controls.Grid> tag:

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    Questa interfaccia utente è simile a *`ExpenseItHome.xaml`*, tranne i dati del report viene visualizzati un <xref:System.Windows.Controls.DataGrid>.

3. Compilare ed eseguire l'applicazione.

4. Selezionare il **vista** pulsante.

    Viene visualizzata la pagina della nota spese. Si noti inoltre che il pulsante di navigazione indietro è abilitato.

La figura seguente mostra gli elementi dell'interfaccia utente aggiunti alla *ExpenseReportPage. XAML*.

![Screenshot di esempio ExpenseIt che mostra l'interfaccia utente appena creato per il ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a>Controlli in stile

L'aspetto dei diversi elementi spesso è lo stesso per tutti gli elementi dello stesso tipo in un'interfaccia utente. Interfaccia utente usa [stili](../controls/styling-and-templating.md) per rendere l'aspetto riutilizzabile tra più elementi. La possibilità di riutilizzo consente di semplificare la gestione e la creazione di XAML. In questa sezione vengono sostituiti con gli stili gli attributi per elemento definiti nei passaggi precedenti.

1. Aprire *Application. XAML* oppure *app*.

2. Aggiungere il seguente XAML tra i <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tag:

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    Questo codice XAML aggiunge gli stili seguenti:

    - `headerTextStyle`: Per formattare il titolo della pagina <xref:System.Windows.Controls.Label>.

    - `labelStyle`: Per formattare il <xref:System.Windows.Controls.Label> controlli.

    - `columnHeaderStyle`: Per formattare il <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.

    - `listHeaderStyle`: Per formattare l'intestazione dell'elenco <xref:System.Windows.Controls.Border> controlli.

    - `listHeaderTextStyle`: Per formattare l'intestazione dell'elenco <xref:System.Windows.Controls.Label>.

    - `buttonStyle`: Per formattare il <xref:System.Windows.Controls.Button> su `ExpenseItHome.xaml`.

    Si noti che gli stili sono risorse ed elementi figlio del <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property (elemento). In questa posizione, gli stili vengono applicati a tutti gli elementi di un'applicazione. Per un esempio di utilizzo delle risorse in un'app .NET, vedere [le risorse dell'applicazione usare](../advanced/how-to-use-application-resources.md).

3. Nelle *`ExpenseItHome.xaml`*, sostituire tutto il contenuto tra il <xref:System.Windows.Controls.Grid> gli elementi con il XAML seguente:

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    Le proprietà come <xref:System.Windows.VerticalAlignment> e <xref:System.Windows.Media.FontFamily> che definiscono l'aspetto di ciascun controllo vengono rimosse e sostituite mediante l'applicazione degli stili. Ad esempio, il `headerTextStyle` viene applicato a "View Expense Report" <xref:System.Windows.Controls.Label>.

4. Aprire *ExpenseReportPage.xaml*.

5. Sostituire tutto il contenuto tra il <xref:System.Windows.Controls.Grid> gli elementi con il XAML seguente:

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    Questo XAML aggiunge gli stili per il <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.Border> elementi.

6. Compilare ed eseguire l'applicazione. L'aspetto delle finestre è uguale come in precedenza.

    ![Screenshot di esempio ExpenseIt con lo stesso aspetto come nell'ultima sezione.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. Chiudere l'applicazione per tornare a Visual Studio.

## <a name="bind-data-to-a-control"></a>Associare dati a un controllo

In questa sezione si creerà i dati XML che sono associati a vari controlli.

1. Nelle *`ExpenseItHome.xaml`*, dopo l'apertura <xref:System.Windows.Controls.Grid> elemento, aggiungere il seguente XAML per creare un <xref:System.Windows.Data.XmlDataProvider> che contiene i dati per ogni persona:

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    I dati vengono creati come una <xref:System.Windows.Controls.Grid> risorsa. In genere questi dati verranno caricati come file, ma per semplicità i dati verranno aggiunti inline.

2. All'interno di `<Grid.Resources>` elemento, aggiungere quanto segue `<xref:System.Windows.DataTemplate>` elemento che definisce come visualizzare i dati nel <xref:System.Windows.Controls.ListBox>, dopo il `<XmlDataProvider>` elemento:

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    Per altre informazioni sui modelli di dati, vedere [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md).

3. Sostituire il <xref:System.Windows.Controls.ListBox> con il XAML seguente:

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    Questo XAML associa il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.ListBox> all'origine dati e applica il modello di dati come il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.

## <a name="connect-data-to-controls"></a>Connetti i dati a controlli

Successivamente, si aggiungerà codice per recuperare il nome selezionato sul **`ExpenseItHome`** pagina e passarlo al costruttore della **ExpenseReportPage**. **ExpenseReportPage** imposta il contesto dei dati con l'elemento passato, ovvero i controlli definiti in *ExpenseReportPage. XAML* associarsi.

1. Aprire *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.

2. Aggiungere un costruttore che accetti un oggetto, in modo da poter passare i dati della nota spese della persona selezionata.

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. Aprire *`ExpenseItHome.xaml.vb`* oppure *`ExpenseItHome.xaml.cs`*.

4. Modifica il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi per chiamare il nuovo costruttore che passa i dati della nota spese della persona selezionata.

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>Dati di tipo con i modelli di dati

In questa sezione, si aggiornerà l'interfaccia utente per ogni elemento negli elenchi associati a dati con i modelli di dati.

1. Aprire *ExpenseReportPage.xaml*.

2. Associare il contenuto del "Name" e "Department" <xref:System.Windows.Controls.Label> proprietà dell'origine elementi per i dati appropriati. Per altre informazioni sul data binding, vedere [Panoramica sul Data binding](../data/data-binding-overview.md).

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. Dopo l'apertura <xref:System.Windows.Controls.Grid> elemento, aggiungere i seguenti modelli di dati, che definiscono la modalità visualizzare i dati della nota spese:

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. Sostituire il <xref:System.Windows.Controls.DataGridTextColumn> elementi con <xref:System.Windows.Controls.DataGridTemplateColumn> sotto il <xref:System.Windows.Controls.DataGrid> elemento e applica i modelli a essi.

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. Compilare ed eseguire l'applicazione.

6. Selezionare una persona e quindi selezionare il **vista** pulsante.

Nella figura seguente mostra le due pagine del `ExpenseIt` applicazione controlli, layout, stili, associazione dati e modelli di dati applicati:

![Entrambe le pagine dell'app che mostra l'elenco di nomi e una nota spese.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> Questo esempio illustra una funzionalità specifica di WPF e non segue tutte le procedure consigliate per aspetti quali sicurezza, localizzazione e accessibilità. Per una descrizione completa di WPF e le procedure guidate di sviluppo .NET di app, vedere gli argomenti seguenti:
>
> - [Accessibilità](../../ui-automation/accessibility-best-practices.md)
>
> - [Sicurezza](../security-wpf.md)
>
> - [Globalizzazione e localizzazione WPF](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [Prestazioni WPF](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>Passaggi successivi

In questa procedura dettagliata si è appreso diverse tecniche per la creazione di un'interfaccia utente mediante Windows Presentation Foundation (WPF). È stata acquisita una conoscenza di base dei blocchi predefiniti di un'app .NET con associazione a dati. Per altre informazioni sull'architettura WPF e i modelli di programmazione, vedere gli argomenti seguenti:

- [Architettura WPF](../advanced/wpf-architecture.md)
- [Panoramica di XAML (WPF)](../advanced/xaml-overview-wpf.md)
- [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md)
- [Layout](../advanced/layout.md)

Per altre informazioni sulla creazione di applicazioni, vedere gli argomenti seguenti:

- [Sviluppo di applicazioni](../app-development/index.md)
- [Controlli](../controls/index.md)
- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Grafica e funzionalità multimediali](../graphics-multimedia/index.md)
- [Documenti in WPF](../advanced/documents-in-wpf.md)

## <a name="see-also"></a>Vedere anche

- [Panoramica di pannelli](../controls/panels-overview.md)
- [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md)
- [Compilare un'applicazione WPF](../app-development/building-a-wpf-application-wpf.md)
- [Stili e modelli](../controls/styles-and-templates.md)
