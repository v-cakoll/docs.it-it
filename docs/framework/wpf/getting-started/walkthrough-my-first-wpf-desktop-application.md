---
title: Creare un'applicazione WPF in Visual Studio
ms.date: 04/12/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 876bf9bf952aa9591a9ccbe51baaca9c5c71388e
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314776"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>Procedura dettagliata: Prima applicazione desktop WPF

Questo articolo illustra come sviluppare un'applicazione Windows Presentation Foundation (WPF) semplice che include gli elementi che sono comuni alla maggior parte delle applicazioni WPF: markup Extensible Application Markup Language (XAML), codice-behind, definizioni delle applicazioni, i controlli, layout, associazione dati e stili.

Questa procedura dettagliata include i passaggi seguenti:

- Utilizzare XAML per progettare l'aspetto dell'interfaccia utente dell'applicazione (UI).

- Scrivere codice per compilare il comportamento dell'applicazione.

- Creare una definizione di applicazione per gestire l'applicazione.

- Aggiungere controlli e creare il layout per comporre l'interfaccia utente dell'applicazione.

- Creare gli stili per un aspetto uniforme per interfaccia utente dell'applicazione.

- Associare l'interfaccia utente ai dati sia popolare l'interfaccia utente da dati e mantenere i dati e dell'interfaccia utente sincronizzato.

Al termine della procedura dettagliata, verrà creata un'applicazione Windows che consente agli utenti di visualizzare i report di spesa per gli utenti selezionati autonoma. L'applicazione è composta da più pagine WPF ospitate in una finestra del browser stile.

> [!TIP]
> Il codice di esempio che consente di compilare in questa procedura dettagliata è disponibile per Visual Basic e c# al [Introduzione alla compilazione di applicazioni WPF](http://go.microsoft.com/fwlink/?LinkID=160008).

## <a name="prerequisites"></a>Prerequisiti

- Visual Studio 2012 o versione successiva

Per ulteriori informazioni sull'installazione della versione più recente di Visual Studio, vedere [installare Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="create-the-application-project"></a>Creare il progetto di applicazione

Il primo passaggio consiste nel creare l'infrastruttura dell'applicazione, che include una definizione di applicazione, due pagine e un'immagine.

1. Creare un nuovo progetto di applicazione WPF in Visual Basic o Visual c# denominato **ExpenseIt**:

   1. Aprire Visual Studio e selezionare **File** > **nuovo** > **progetto**.

      Il **nuovo progetto** verrà visualizzata la finestra di dialogo.

   2. Sotto il **installati** categoria, espandere il **Visual c#** o **Visual Basic** nodo e quindi selezionare **Windows Desktop classico**.

   3. Selezionare il **applicazione WPF (.NET Framework)** modello. Immettere il nome **ExpenseIt** e quindi selezionare **OK**.

      ![Finestra di dialogo Nuovo progetto con app WPF selezionata](media/new-project-dialog.png)

      Visual Studio crea il progetto e apre la finestra di progettazione per la finestra dell'applicazione predefinita denominata **MainWindow. XAML**.

   > [!NOTE]
   > Questa procedura dettagliata Usa il <xref:System.Windows.Controls.DataGrid> controllo che è disponibile in .NET Framework 4 e versioni successive. Essere certi che il progetto è destinato a .NET Framework 4 o versione successiva. Per altre informazioni, vedere [Procedura: Destinare una versione di .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).

2. Aprire *Application. XAML* (Visual Basic) o *app* (c#).

    Questo file XAML definisce un'applicazione WPF e tutte le risorse dell'applicazione. Utilizzare questo file per specificare l'interfaccia utente che visualizza automaticamente quando l'avvio dell'applicazione; In questo caso *MainWindow. XAML*.

    In Visual Basic, il codice XAML dovrebbe essere simile al seguente:

    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    Oppure l'aspetto seguente in C#:

    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. Aprire *MainWindow. XAML*.

    Questo file XAML è la finestra principale dell'applicazione e visualizza il contenuto creato nelle pagine. Il <xref:System.Windows.Window> classe definisce le proprietà di una finestra, ad esempio il relativo titolo, dimensioni o sull'icona e gestisce gli eventi, ad esempio la chiusura o disattivazione della visualizzazione.

4. Modifica il <xref:System.Windows.Window> elemento da un <xref:System.Windows.Navigation.NavigationWindow>, come illustrato nel codice XAML seguente:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   Questa app passa a un contenuto diverso a seconda di input dell'utente. Questo è il motivo principale <xref:System.Windows.Window> deve essere modificato in un <xref:System.Windows.Navigation.NavigationWindow>. <xref:System.Windows.Navigation.NavigationWindow> eredita tutte le proprietà di <xref:System.Windows.Window>. Il <xref:System.Windows.Navigation.NavigationWindow> elemento nel file XAML crea un'istanza di <xref:System.Windows.Navigation.NavigationWindow> classe. Per altre informazioni, vedere [Panoramica di navigazione](../../../../docs/framework/wpf/app-development/navigation-overview.md).

5. Modificare le proprietà seguenti nel <xref:System.Windows.Navigation.NavigationWindow> elemento:

    - Impostare il <xref:System.Windows.Window.Title%2A> proprietà su "ExpenseIt".

    - Impostare il <xref:System.Windows.FrameworkElement.Width%2A> proprietà su 500 pixel.

    - Impostare il <xref:System.Windows.FrameworkElement.Height%2A> proprietà 350 pixel.

    - Rimuovere il <xref:System.Windows.Controls.Grid> degli elementi tra il <xref:System.Windows.Navigation.NavigationWindow> tag.

    In Visual Basic, il codice XAML dovrebbe essere simile al seguente:

    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    Oppure l'aspetto seguente in C#:

    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

6. Aprire *. Xaml. vb* oppure *MainWindow.xaml.cs*.

    Questo file è un file code-behind che contiene il codice per gestire gli eventi dichiarati nelle *MainWindow. XAML*. Il file contiene una classe parziale per la finestra definita in XAML.

7. Se si usa c#, modificare il `MainWindow` classe deriva da <xref:System.Windows.Navigation.NavigationWindow>. (In Visual Basic, ciò avviene automaticamente quando si modifica la finestra in XAML)

   Il codice dovrebbe essere simile al seguente:

   [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
   [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]

   > [!TIP]
   > È possibile attivare o disattivare il linguaggio del codice del codice di esempio tra linguaggi c# e Visual Basic nel **Language** elenco a discesa in alto a destra di questo articolo.

## <a name="add-files-to-the-application"></a>Aggiungere i file all'applicazione

In questa sezione si aggiungeranno due pagine e un'immagine all'applicazione.

1. Aggiungere una nuova pagina WPF al progetto e denominarlo *ExpenseItHome. XAML*:

   1. In **Esplora soluzioni**, fare clic sui **ExpenseIt** nodo del progetto e scegliere **Aggiungi** > **pagina**.

   1. Nel **Aggiungi nuovo elemento** finestra di dialogo, la **pagina (WPF)** il modello è già selezionato. Immettere il nome **ExpenseItHome**, quindi selezionare **Add**.

    Questa pagina è la prima pagina che viene visualizzata quando viene avviata l'applicazione. Verrà visualizzato un elenco di utenti di selezionare questa opzione, per visualizzare una nota spese per.

2. Aprire *ExpenseItHome.xaml*.

3. Impostare il <xref:System.Windows.Controls.Page.Title%2A> su "ExpenseIt - Home".

    In Visual Basic, il codice XAML dovrebbe essere simile al seguente:

    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    Oppure l'aspetto seguente in C#:

    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

4. Aprire *MainWindow. XAML*.

5. Impostare il <xref:System.Windows.Navigation.NavigationWindow.Source%2A> proprietà di <xref:System.Windows.Navigation.NavigationWindow> a "ExpenseItHome. xaml".

    *ExpenseItHome.xaml* viene impostata come la prima pagina aperta all'avvio dell'applicazione. In Visual Basic, il codice XAML dovrebbe essere simile al seguente:

    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    Oppure l'aspetto seguente in C#:

    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > È inoltre possibile impostare il **origine** proprietà il **varie** categoria del **proprietà** finestra.
   >
   > ![Proprietà di origine nella finestra proprietà](media/properties-source.png)

6. Aggiungere una nuova pagina WPF al progetto e denominarlo *ExpenseReportPage*::

   1. In **Esplora soluzioni**, fare clic sui **ExpenseIt** nodo del progetto e scegliere **Aggiungi** > **pagina**.

   1. Nel **Aggiungi nuovo elemento** finestra di dialogo, la **pagina (WPF)** il modello è già selezionato. Immettere il nome **ExpenseReportPage**, quindi selezionare **Add**.

    Questa pagina visualizzerà la nota spese per la persona a cui viene selezionata per il **ExpenseItHome** pagina.

7. Aprire *ExpenseReportPage.xaml*.

8. Impostare il <xref:System.Windows.Controls.Page.Title%2A> su "ExpenseIt - View Expense".

    In Visual Basic, il codice XAML dovrebbe essere simile al seguente:

    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    Oppure l'aspetto seguente in C#:

    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

9. Aprire *ExpenseItHome.xaml.vb* e *ExpenseReportPage.xaml.vb*, o *ExpenseItHome.xaml.cs* e *ExpenseReportPage.xaml.cs*.

    Quando si crea un nuovo file di paging, Visual Studio crea automaticamente un *codice* file. Questi file code-behind gestiscono la logica per rispondere all'input dell'utente.

    Il codice dovrebbe essere simile alla seguente per **ExpenseItHome**:

    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    Oppure per **ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

10. Aggiungere un'immagine denominata *watermark* al progetto. È possibile creare un'immagine personalizzata, copiare il file il codice di esempio o ottenerlo [qui](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png).

   1. Fare clic sul nodo del progetto e selezionare **Add** > **elemento esistente**, oppure premere **MAIUSC**+**Alt** + **A**.

   2. Nel **Aggiungi elemento esistente** finestra di dialogo, selezionare il file di immagine si desidera utilizzare e quindi selezionare **Add**.

## <a name="build-and-run-the-application"></a>Compilazione ed esecuzione dell'applicazione

1. Per compilare ed eseguire l'applicazione, premere **F5** oppure selezionare **Avvia debug** dal **Debug** menu.

    Nella figura seguente viene illustrata l'applicazione con il <xref:System.Windows.Navigation.NavigationWindow> pulsanti:

    ![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png)

2. Chiudere l'applicazione per tornare a Visual Studio.

## <a name="create-the-layout"></a>Creare il layout

Layout fornisce un modo ordinato per posizionare elementi dell'interfaccia utente e di gestione le dimensioni e la posizione di tali elementi durante il ridimensionamento di un'interfaccia utente. In genere si crea un layout tramite uno dei controlli di layout seguenti:

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.VirtualizingStackPanel>
- <xref:System.Windows.Controls.WrapPanel>

Ognuno di questi controlli di layout supporta un tipo speciale di layout per i relativi elementi figlio. È possibile ridimensionare le pagine ExpenseIt e ogni pagina contiene elementi disposti in orizzontale e in verticale accanto ad altri elementi. Di conseguenza, il <xref:System.Windows.Controls.Grid> è l'elemento di layout ideale per l'applicazione.

> [!TIP]
> Per ulteriori informazioni <xref:System.Windows.Controls.Panel> elementi, vedere [Panoramica pannelli](../../../../docs/framework/wpf/controls/panels-overview.md). Per ulteriori informazioni sul layout, vedere [Layout](../../../../docs/framework/wpf/advanced/layout.md).

Nella sezione crei una tabella a colonna singola con tre righe e un margine di 10 pixel mediante l'aggiunta di definizioni di colonna e riga per il <xref:System.Windows.Controls.Grid> in *ExpenseItHome. XAML*.

1. Aprire *ExpenseItHome.xaml*.

2. Impostare il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà il <xref:System.Windows.Controls.Grid> elemento "10,0,10,10", che corrispondono ai margini sinistro, superiore, destro e inferiore:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > È inoltre possibile impostare il **margine** valori il **proprietà** finestra, sotto il **Layout** categoria:
   >
   > ![Valori dei margini nella finestra proprietà](media/properties-margin.png)

3. Aggiungere il codice XAML seguente tra i <xref:System.Windows.Controls.Grid> tag per creare le definizioni di riga e colonna:

    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    Il <xref:System.Windows.Controls.RowDefinition.Height%2A> di due righe è impostato su <xref:System.Windows.GridLength.Auto%2A>, vale a dire che le righe vengono ridimensionate i basare il contenuto nelle righe. Il valore predefinito <xref:System.Windows.Controls.RowDefinition.Height%2A> è <xref:System.Windows.GridUnitType.Star> ridimensionamento, che significa che l'altezza della riga è una proporzione ponderata dello spazio disponibile. Se, ad esempio due righe hanno un <xref:System.Windows.Controls.RowDefinition.Height%2A> di "*", ognuna di esse presenta un'altezza pari alla metà dello spazio disponibile.

    Il <xref:System.Windows.Controls.Grid> dovrebbe essere simile al seguente XAML:

    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>Aggiunta di controlli

In questa sezione si aggiornerà la home page dell'interfaccia utente per visualizzare un elenco di persone che un utente può selezionare per mostrare la nota spese per. I controlli sono oggetti dell'interfaccia utente che consentono agli utenti di interagire con l'applicazione. Per altre informazioni, vedere [Controlli](../../../../docs/framework/wpf/controls/index.md).

Per creare questa interfaccia utente, aggiungerai gli elementi seguenti per *ExpenseItHome. XAML*:

- <xref:System.Windows.Controls.ListBox> (per un elenco di persone).
- <xref:System.Windows.Controls.Label> (per l'intestazione dell'elenco).
- <xref:System.Windows.Controls.Button> (possibile fare clic per visualizzare la nota spese per la persona che sia selezionata nell'elenco).

Ogni controllo viene inserito in una riga della <xref:System.Windows.Controls.Grid> impostando la <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> proprietà associata. Per ulteriori informazioni sulle proprietà associate, vedere [collegato Cenni preliminari sulle proprietà](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).

1. Aprire *ExpenseItHome.xaml*.

2. Aggiungere il seguente codice XAML in un punto compreso tra il <xref:System.Windows.Controls.Grid> tag:

   [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > È anche possibile creare i controlli trascinandole dal **casella degli strumenti** nella finestra di progettazione e quindi impostando le proprietà nella finestra di **proprietà** finestra.

3. Compilare ed eseguire l'applicazione.

La figura seguente mostra i controlli che appena creato:

![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png)

## <a name="add-an-image-and-a-title"></a>Aggiungere un'immagine e un titolo

In questa sezione, si verrà aggiornata l'interfaccia utente della home page con un'immagine e un titolo della pagina.

1. Aprire *ExpenseItHome.xaml*.

2. Aggiungere un'altra colonna per il <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con fissa <xref:System.Windows.Controls.ColumnDefinition.Width%2A> di 230 pixel:

    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]

3. Aggiungere un'altra riga per il <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, per un totale di quattro righe:

    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]

4. Spostare i controlli nella seconda colonna impostando il <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> proprietà su 1 in ognuno dei tre controlli (bordo, casella di riepilogo e pulsante).

5. Spostare ogni controllo verso il basso una riga, incrementando il relativo <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> valore di 1.

   Il codice XAML per i tre controlli avrà ora un aspetto simile al seguente:

    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

6. Impostare il <xref:System.Windows.Controls.Panel.Background%2A> del <xref:System.Windows.Controls.Grid> sia il *watermark* file di immagine, aggiungendo il seguente codice XAML in un punto compreso tra il `<Grid>` e `</Grid>` tag:

    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

7. Prima di <xref:System.Windows.Controls.Border> elemento, aggiungere un <xref:System.Windows.Controls.Label> con il contenuto "View Expense Report". Questo è il titolo della pagina.

    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

8. Compilare ed eseguire l'applicazione.

La figura seguente mostra i risultati di ciò che appena aggiunto:

![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a>Aggiungere il codice per gestire gli eventi

1. Aprire *ExpenseItHome.xaml*.

2. Aggiungere un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore dell'evento per il <xref:System.Windows.Controls.Button> elemento. Per altre informazioni, vedere [procedura: creare un gestore di evento semplice](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).

    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

3. Aprire *ExpenseItHome.xaml.vb* o *ExpenseItHome.xaml.cs*.

4. Aggiungere il codice seguente per il `ExpenseItHome` classe per aggiungere un pulsante gestore dell'evento click. Il gestore eventi apre il **ExpenseReportPage** pagina.

    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>Creare l'interfaccia utente per ExpenseReportPage

*ExpenseReportPage* Visualizza la nota spese per la persona che viene selezionata per il **ExpenseItHome** pagina. In questa sezione, che consentono controlli di creare l'interfaccia utente per **ExpenseReportPage**. Aggiungerai anche in background e colori di riempimento ai vari elementi dell'interfaccia utente.

1. Aprire *ExpenseReportPage.xaml*.

2. Aggiungere il codice XAML seguente tra i <xref:System.Windows.Controls.Grid> tag:

    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    Questa interfaccia è simile a *ExpenseItHome. XAML*, ma i dati del report viene visualizzati un <xref:System.Windows.Controls.DataGrid>.

3. Compilare ed eseguire l'applicazione.

    > [!NOTE]
    > Se si verifica un errore di <xref:System.Windows.Controls.DataGrid> non è stato trovato o non esiste, verificare che il progetto è destinato a .NET Framework 4 o versione successivo. Per altre informazioni, vedere [Procedura: Destinare una versione di .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).

4. Selezionare il **vista** pulsante.

    Viene visualizzata la pagina della nota spese. Si noti inoltre che il pulsante di navigazione all'indietro è abilitato.

La figura seguente mostra gli elementi dell'interfaccia utente aggiunti alla *ExpenseReportPage*.

![Schermata dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png)

## <a name="style-controls"></a>Controlli in stile

L'aspetto dei diversi elementi è spesso lo stesso per tutti gli elementi dello stesso tipo in un'interfaccia utente. Interfaccia utente vengono usati [stili](../../../../docs/framework/wpf/controls/styling-and-templating.md) per rendere riutilizzabile l'aspetto degli elementi. La possibilità di riutilizzo consente di semplificare la gestione e la creazione di XAML. In questa sezione vengono sostituiti con gli stili gli attributi per elemento definiti nei passaggi precedenti.

1. Aprire *Application. XAML* oppure *app*.

2. Aggiungere il codice XAML seguente tra i <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tag:

    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    Questo codice XAML aggiunge gli stili seguenti:

    - `headerTextStyle`: per formattare il titolo della pagina <xref:System.Windows.Controls.Label>.

    - `labelStyle`: per formattare i controlli <xref:System.Windows.Controls.Label> .

    - `columnHeaderStyle`: per formattare <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.

    - `listHeaderStyle`: per formattare i controlli <xref:System.Windows.Controls.Border> dell'intestazione dell'elenco.

    - `listHeaderTextStyle`: Per formattare l'intestazione dell'elenco <xref:System.Windows.Controls.Label>.

    - `buttonStyle`: Per formattare il <xref:System.Windows.Controls.Button> in ExpenseItHome. Xaml.

    Si noti che gli stili sono le risorse e i relativi elementi figlio di <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> elemento property. In questa posizione, gli stili vengono applicati a tutti gli elementi di un'applicazione. Per un esempio di utilizzo delle risorse in un'applicazione .NET Framework, vedere [le risorse dell'applicazione di utilizzare](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).

3. Aprire *ExpenseItHome.xaml*.

4. Sostituire tutto il contenuto tra il <xref:System.Windows.Controls.Grid> gli elementi con il codice XAML seguente:

    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    Le proprietà come <xref:System.Windows.VerticalAlignment> e <xref:System.Windows.Media.FontFamily> che definiscono l'aspetto di ciascun controllo vengono rimosse e sostituite mediante l'applicazione degli stili. Ad esempio, il `headerTextStyle` si riferisce alle "View Expense Report" <xref:System.Windows.Controls.Label>.

5. Aprire *ExpenseReportPage.xaml*.

6. Sostituire tutto il contenuto tra il <xref:System.Windows.Controls.Grid> gli elementi con il codice XAML seguente:

    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    Vengono aggiunti gli stili agli elementi <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.Border> .

## <a name="bind-data-to-a-control"></a>Associare dati a un controllo

In questa sezione, si creeranno i dati XML sono associati a vari controlli.

1. Aprire *ExpenseItHome.xaml*.

2. Dopo l'apertura <xref:System.Windows.Controls.Grid> elemento, aggiungere il codice XAML seguente per creare un <xref:System.Windows.Data.XmlDataProvider> che contiene i dati per ogni persona:

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    I dati vengono creati come una <xref:System.Windows.Controls.Grid> risorse. In genere questi dati vengono caricati sotto forma di file, ma in questo caso, per semplicità, verranno aggiunti inline.

3. All'interno di `<Grid.Resources>` elemento, aggiungere quanto segue <xref:System.Windows.DataTemplate>, che definisce come visualizzare i dati nel <xref:System.Windows.Controls.ListBox>:

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    Per ulteriori informazioni sui modelli di dati, vedere [panoramica dei modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md).

4. Sostituire <xref:System.Windows.Controls.ListBox> con il codice XAML seguente:

    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    Questo codice XAML associa il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.ListBox> all'origine dati e viene applicato il modello di dati come il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.

## <a name="connect-data-to-controls"></a>Connettere i dati ai controlli

Successivamente, verrà aggiunto il codice per recuperare il nome che viene selezionato per il **ExpenseItHome** pagina e passarlo al costruttore della **ExpenseReportPage**. **ExpenseReportPage** imposta il contesto dati con l'elemento passato, ovvero i controlli definiti in *ExpenseReportPage* associare.

1. Aprire *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.

2. Aggiungere un costruttore che accetti un oggetto, in modo da poter passare i dati della nota spese della persona selezionata.

    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. Aprire *ExpenseItHome.xaml.vb* o *ExpenseItHome.xaml.cs*.

4. Modifica il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi per chiamare il nuovo costruttore passando i dati della nota spese della persona selezionata.

    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>Dati di tipo con i modelli di dati

In questa sezione si aggiornerà l'interfaccia utente per ogni articolo negli elenchi di associazione a dati mediante i modelli di dati.

1. Aprire *ExpenseReportPage.xaml*.

2. Associare il contenuto di "Nome" e "Department" <xref:System.Windows.Controls.Label> proprietà source elementi per i dati appropriati. Per ulteriori informazioni sull'associazione dati, vedere [Panoramica sul Data binding](../../../../docs/framework/wpf/data/data-binding-overview.md).

    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. Dopo l'apertura <xref:System.Windows.Controls.Grid> elemento, aggiungere i seguenti modelli di dati, che consentono di definire come visualizzare i dati della nota spese:

    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. Applicare i modelli per il <xref:System.Windows.Controls.DataGrid> le colonne che visualizzano i costi per i dati del report.

    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. Compilare ed eseguire l'applicazione.

6. Selezionare una persona, quindi selezionare il **vista** pulsante.

La figura seguente mostra le due pagine dell'applicazione ExpenseIt con i controlli, layout, stili, associazione dati e modelli di dati applicati:

![Schermate dell'esempio ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png)

> [!NOTE]
> Questo esempio viene illustrata una funzionalità specifica di WPF e non è conforme a tutte le procedure consigliate per elementi quali sicurezza, localizzazione e accessibilità. Per informazioni complete di WPF e .NET Framework applicazione sviluppo consigliate, vedere gli argomenti seguenti:
>
> - [Accessibilità](../../../../docs/framework/ui-automation/accessibility-best-practices.md)
>
> - [Sicurezza](../../../../docs/framework/wpf/security-wpf.md)
>
> - [Globalizzazione e localizzazione WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)
>
> - [Delle prestazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>Passaggi successivi

In questa procedura dettagliata è stato diverse tecniche per la creazione di un'interfaccia utente mediante Windows Presentation Foundation (WPF). È stata acquisita una conoscenza di base dei componenti fondamentali di un'applicazione .NET Framework associato a dati. Per altre informazioni sull'architettura WPF e i modelli di programmazione, vedere gli argomenti seguenti:

- [Architettura WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
- [Panoramica di XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Cenni preliminari sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [Layout](../../../../docs/framework/wpf/advanced/layout.md)

Per altre informazioni sulla creazione di applicazioni, vedere gli argomenti seguenti:

- [Sviluppo di applicazioni](../../../../docs/framework/wpf/app-development/index.md)
- [Controlli](../../../../docs/framework/wpf/controls/index.md)
- [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Grafica e multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)
- [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)

## <a name="see-also"></a>Vedere anche

- [Panoramica di pannelli](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Panoramica del modello di dati](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [Compilare un'applicazione WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [Stili e modelli](../../../../docs/framework/wpf/controls/styles-and-templates.md)
