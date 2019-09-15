---
title: 'Procedura dettagliata: Hosting di un controllo composito Windows Form in WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: e4c1de17b131ee68c6e6fce0035b703eb5b489a0
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991877"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>Procedura dettagliata: Hosting di un controllo composito Windows Form in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si ha un investimento sostanziale [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] nel codice, può essere più efficace riutilizzare almeno parte del codice [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nell'applicazione anziché riscriverla da zero. Lo scenario più comune è quello in cui si dispone di controlli di Windows Forms esistenti. In alcuni casi, è possibile che non si abbia accesso al codice sorgente di questi controlli. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce una procedura semplice per l'hosting di tali controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in un'applicazione. Ad esempio, è possibile usare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per la maggior parte della programmazione mentre si ospitano i controlli specializzati. <xref:System.Windows.Forms.DataGridView>  
  
 Questa procedura dettagliata illustra un'applicazione che ospita un controllo Windows Forms composito per eseguire l'immissione di dati [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in un'applicazione. Il controllo composito è compresso in una DLL. Questa procedura generale può essere estesa ad applicazioni e controlli più complessi. Questa procedura dettagliata è progettata per essere pressoché identica per quanto riguarda aspetto [e funzionalità per la procedura dettagliata: Hosting di un controllo composito WPF](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)in Windows Forms. La principale differenza è che lo scenario di hosting è invertito.  
  
 La procedura guidata è suddivisa in due sezioni. Nella prima sezione viene brevemente descritta l'implementazione del controllo Windows Forms composito. La seconda sezione illustra in dettaglio come ospitare il controllo composito in un' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione, ricevere eventi dal controllo e accedere ad alcune delle proprietà del controllo.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
- Implementazione del controllo Windows Forms composito.  
  
- Implementazione dell'applicazione host WPF.  
  
 Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere la pagina relativa all' [hosting di un controllo Windows Forms composito in WPF di esempio](https://go.microsoft.com/fwlink/?LinkID=159999).  
  
## <a name="prerequisites"></a>Prerequisiti  

Per completare la procedura dettagliata, è necessario Visual Studio.
  
## <a name="implementing-the-windows-forms-composite-control"></a>Implementazione del controllo Windows Forms composito  
 Il Windows Forms controllo composito usato in questo esempio è un semplice form di immissione dati. Questo form accetta nome e indirizzo dell'utente e quindi usa un evento personalizzato per restituire le informazioni all'host. La figura seguente mostra il controllo sottoposto a rendering.  

 Nell'immagine seguente viene illustrato un controllo Windows Forms composito:  

 ![Screenshot che mostra un semplice controllo Windows Forms.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a>Creazione del progetto  
 Per avviare il progetto:  
  
1. Avviare [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]e aprire la finestra di dialogo **nuovo progetto** .  
  
2. Nella categoria finestra selezionare il modello **libreria di controlli Windows Forms** .  
  
3. Assegnare il nome `MyControls` al nuovo progetto.  
  
4. Per il percorso specificare una cartella di primo livello con un nome appropriato, ad esempio `WpfHostingWindowsFormsControl`. Successivamente, si immetterà l'applicazione host in questa cartella.  
  
5. Fare clic su **OK** per creare il progetto. Il progetto predefinito contiene un solo controllo denominato `UserControl1`.  
  
6. In Esplora soluzioni rinominare `UserControl1` `MyControl1`in.  
  
 Il progetto dovrebbe includere riferimenti alle DLL di sistema seguenti. Se alcune di queste DLL non sono incluse per impostazione predefinita, aggiungerle al progetto.  
  
- System  
  
- System.Data  
  
- System.Drawing  
  
- System.Windows.Forms  
  
- System.Xml  
  
### <a name="adding-controls-to-the-form"></a>Aggiunta di controlli al form  
 Per aggiungere controlli al form:  
  
- Apri `MyControl1` nella finestra di progettazione.  
  
 Aggiungere cinque <xref:System.Windows.Forms.Label> controlli e i controlli <xref:System.Windows.Forms.TextBox> corrispondenti, ridimensionati e disposti come sono nell'illustrazione precedente, nel form. Nell'esempio, i <xref:System.Windows.Forms.TextBox> controlli sono denominati:  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 Aggiungere due <xref:System.Windows.Forms.Button> controlli con etichetta **OK** e **Annulla**. Nell'esempio, i nomi dei pulsanti sono `btnOK` rispettivamente `btnCancel`e.  
  
### <a name="implementing-the-supporting-code"></a>Implementazione del codice di supporto  
 Aprire il form nella visualizzazione codice. Il controllo restituisce i dati raccolti al relativo host generando l'evento `OnButtonClick` personalizzato. I dati sono contenuti nell'oggetto argomento dell'evento. Il codice seguente mostra la dichiarazione di evento e delegato.  
  
 Aggiungere il codice seguente alla classe `MyControl1` .  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 La `MyControlEventArgs` classe contiene le informazioni da restituire all'host.

 Aggiungere la classe seguente al form.

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 Quando l'utente fa clic sul pulsante **OK** o **Annulla** , <xref:System.Windows.Forms.Control.Click> i gestori eventi creano un `MyControlEventArgs` oggetto che contiene i dati e genera l' `OnButtonClick` evento. L'unica differenza tra i due gestori è la `IsOK` proprietà dell'argomento dell'evento. Questa proprietà consente all'host di determinare su quale pulsante è stato fatto clic. Viene impostato su `true` per il pulsante **OK** e `false` per il pulsante **Annulla** . Il codice seguente illustra i gestori dei due pulsanti.

 Aggiungere il codice seguente alla classe `MyControl1` .

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>Assegnazione di un nome sicuro all'assembly e compilazione dell'assembly
 Per fare in modo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che l'applicazione faccia riferimento a questo assembly, deve avere un nome sicuro. Per creare un nome sicuro, creare un file di chiave con sn. exe e aggiungerlo al progetto.

1. Aprire il prompt dei comandi di [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]. A tale scopo, fare clic sul menu **Start** , quindi selezionare **tutti i programmi/Microsoft Visual Studio 2010/strumenti di Visual Studio/prompt dei comandi di Visual Studio**. Verrà avviata una finestra della console con variabili di ambiente personalizzate.

2. Al prompt dei comandi usare il `cd` comando per passare alla cartella del progetto.

3. Generare un file di chiave denominato MyControls.snk eseguendo il comando seguente.

    ```console
    Sn.exe -k MyControls.snk
    ```

4. Per includere il file di chiave nel progetto, fare clic con il pulsante destro del mouse sul nome del progetto in Esplora soluzioni e quindi scegliere **Proprietà**. In Creazione progetti fare clic sulla scheda **firma** , selezionare la casella di controllo **Firma assembly** e quindi passare al file di chiave.

5. Compilare la soluzione. La compilazione genererà una DLL denominata MyControls.dll.

## <a name="implementing-the-wpf-host-application"></a>Implementazione dell'applicazione host WPF
 L' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione host usa il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo per ospitare `MyControl1`. L'applicazione gestisce l' `OnButtonClick` evento per ricevere i dati dal controllo. Dispone inoltre di una raccolta di pulsanti di opzione che consentono di modificare alcune delle proprietà del controllo dall' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione. La figura seguente illustra l'applicazione finita.

Nell'immagine seguente viene illustrata l'applicazione completa, incluso il controllo incorporato nell'applicazione WPF:

 ![Screenshot che mostra un controllo incorporato in una pagina WPF.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a>Creazione del progetto
 Per avviare il progetto:

1. Aprire [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]e selezionare **nuovo progetto**.

2. Nella categoria finestra selezionare il modello **applicazione WPF** .

3. Assegnare il nome `WpfHost` al nuovo progetto.

4. Come percorso, specificare la stessa cartella di livello superiore che contiene il progetto MyControls.

5. Fare clic su **OK** per creare il progetto.

 È anche necessario aggiungere riferimenti alla dll che contiene `MyControl1` e ad altri assembly.

1. Fare clic con il pulsante destro del mouse sul nome del progetto in Esplora soluzioni e scegliere **Aggiungi riferimento**.

2. Fare clic sulla scheda **Sfoglia** e selezionare la cartella che contiene i controlli. dll. In questa procedura dettagliata la cartella è MyControls\bin\Debug.

3. Selezionare controllo. dll e quindi fare clic su **OK**.

4. Aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration. dll.

### <a name="implementing-the-basic-layout"></a>Implementazione del layout di base
 L' [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] oggetto dell'applicazione host viene implementato nel file MainWindow. XAML. Questo file contiene [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] il markup che definisce il layout e ospita il controllo Windows Forms. L'applicazione è suddivisa in tre aree:

- Il pannello **Proprietà controllo** , che contiene una raccolta di pulsanti di opzione che è possibile utilizzare per modificare varie proprietà del controllo ospitato.

- **Dati dal pannello di controllo** , che contiene diversi <xref:System.Windows.Controls.TextBlock> elementi che visualizzano i dati restituiti dal controllo ospitato.

- Il controllo ospitato stesso.

 Il layout di base è illustrato nel codice XAML seguente. Il markup necessario per ospitare `MyControl1` viene omesso da questo esempio, ma verrà discusso più avanti.

 Sostituire il codice XAML in MainWindow.xaml con il seguente. Se si utilizza Visual Basic, modificare la classe in `x:Class="MainWindow"`.

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 Il primo <xref:System.Windows.Controls.StackPanel> elemento contiene diversi set di <xref:System.Windows.Controls.RadioButton> controlli che consentono di modificare diverse proprietà predefinite del controllo ospitato. Seguito da un <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento che ospita `MyControl1`. L'elemento <xref:System.Windows.Controls.StackPanel> finale contiene diversi <xref:System.Windows.Controls.TextBlock> elementi che visualizzano i dati restituiti dal controllo ospitato. L'ordinamento degli elementi e <xref:System.Windows.Controls.DockPanel.Dock%2A> delle impostazioni degli attributi e <xref:System.Windows.FrameworkElement.Height%2A> incorpora il controllo ospitato nella finestra senza gap o distorsione.

#### <a name="hosting-the-control"></a>Hosting del controllo
 La versione modificata seguente del codice XAML precedente è incentrata sugli elementi necessari per ospitare `MyControl1`.

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 L' `xmlns` attributo mapping dello spazio dei nomi crea un `MyControls` riferimento allo spazio dei nomi che contiene il controllo ospitato. Questo mapping consente di rappresentare `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] come `<mcl:MyControl1>`.

 Due elementi nel codice XAML gestiscono l'hosting:

- `WindowsFormsHost`rappresenta l' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento che consente di ospitare un controllo Windows Forms in un' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione.

- `mcl:MyControl1`, che rappresenta `MyControl1`, viene aggiunto alla raccolta <xref:System.Windows.Forms.Integration.WindowsFormsHost> figlio dell'elemento. Di conseguenza, viene eseguito il rendering di questo controllo Windows Forms come parte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] della finestra ed è possibile comunicare con il controllo dall'applicazione.

### <a name="implementing-the-code-behind-file"></a>Implementazione del file code-behind
 Il file code-behind, MainWindow. XAML. vb o MainWindow.XAML.cs, contiene il codice procedurale che implementa la funzionalità di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] descritta nella sezione precedente. Le attività principali sono:

- Associazione di un gestore eventi all' `MyControl1` `OnButtonClick` evento.

- Modifica di diverse proprietà `MyControl1`di, in base alla modalità di impostazione della raccolta di pulsanti di opzione.

- Visualizzare i dati raccolti dal controllo.

#### <a name="initializing-the-application"></a>Inizializzazione dell'applicazione
 Il codice di inizializzazione è contenuto in un gestore eventi per l' <xref:System.Windows.FrameworkElement.Loaded> evento della finestra e connette un gestore eventi all' `OnButtonClick` evento del controllo.

 In MainWindow. XAML. vb o MainWindow.XAML.cs aggiungere il codice seguente alla `MainWindow` classe.

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 Poiché l' [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] oggetto illustrato in `MyControl1` precedenza è <xref:System.Windows.Forms.Integration.WindowsFormsHost> stato aggiunto alla <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> raccolta di elementi figlio dell'elemento, <xref:System.Windows.Forms.Integration.WindowsFormsHost> è possibile eseguire il cast dell'elemento `MyControl1`per ottenere il riferimento a. È quindi possibile usare tale riferimento per alleghi un gestore eventi `OnButtonClick`a.

 Oltre a fornire un riferimento al controllo stesso, <xref:System.Windows.Forms.Integration.WindowsFormsHost> espone un numero di proprietà del controllo, che è possibile modificare dall'applicazione. Il codice di inizializzazione assegna tali valori a variabili globali private per l'uso successivo nell'applicazione.

 Per poter accedere facilmente ai tipi nella `MyControls` dll, aggiungere la seguente `Imports` istruzione o `using` all'inizio del file.

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a>Gestione dell'evento OnButtonClick
 `MyControl1`genera l' `OnButtonClick` evento quando l'utente fa clic su uno dei pulsanti del controllo.

 Aggiungere il codice seguente alla classe `MainWindow` .

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 I dati nelle caselle di testo vengono compressi nell' `MyControlEventArgs` oggetto. Se l'utente fa clic sul pulsante **OK** , il gestore dell'evento estrae i dati e li Visualizza nel pannello `MyControl1`seguente.

#### <a name="modifying-the-controls-properties"></a>Modifica delle proprietà del controllo
 L' <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento espone diverse proprietà predefinite del controllo ospitato. Di conseguenza, è possibile modificare l'aspetto del controllo in modo che corrisponda maggiormente allo stile dell'applicazione. Gli insiemi di pulsanti di opzione nel pannello di sinistra consentono all'utente di modificare varie proprietà di colore e tipo di carattere. Ogni set di pulsanti dispone di un gestore per <xref:System.Windows.Controls.Primitives.ButtonBase.Click> l'evento, che rileva le selezioni dei pulsanti di opzione dell'utente e modifica la proprietà corrispondente nel controllo.

 Aggiungere il codice seguente alla classe `MainWindow` .

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Compilare ed eseguire l'applicazione. Aggiungere testo nel controllo Windows Forms composito, quindi fare clic su **OK**. Il testo viene visualizzato nelle etichette. Fare clic sui vari pulsanti di opzione per vedere l'effetto sul controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Procedura dettagliata: Hosting di un controllo Windows Forms in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Procedura dettagliata: Hosting di un controllo composito WPF in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
