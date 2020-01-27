---
title: Ospitare un controllo Windows Forms composito in WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: 16c09b4bb393fa830412385b4b405dd1fae9878b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745002"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>Procedura dettagliata: hosting di controlli Windows Form compositi in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si ha un investimento sostanziale nel codice [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], può essere più efficace riutilizzare almeno parte del codice nell'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] anziché riscriverla da zero. Lo scenario più comune è quello in cui si dispone di controlli di Windows Forms esistenti. In alcuni casi, è possibile che non si abbia accesso al codice sorgente di questi controlli. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce una procedura semplice per l'hosting di tali controlli in un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Ad esempio, è possibile usare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per la maggior parte della programmazione durante l'hosting dei controlli <xref:System.Windows.Forms.DataGridView> specializzati.  
  
 Questa procedura dettagliata illustra un'applicazione che ospita un controllo Windows Forms composito per eseguire l'immissione di dati in un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Il controllo composito è compresso in una DLL. Questa procedura generale può essere estesa ad applicazioni e controlli più complessi. Questa procedura dettagliata è progettata per essere pressoché identica per quanto riguarda aspetto e funzionalità per [la procedura dettagliata: hosting di un controllo composito WPF in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md). La principale differenza è che lo scenario di hosting è invertito.  
  
 La procedura guidata è suddivisa in due sezioni. Nella prima sezione viene brevemente descritta l'implementazione del controllo Windows Forms composito. La seconda sezione illustra in dettaglio come ospitare il controllo composito in un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ricevere eventi dal controllo e accedere ad alcune delle proprietà del controllo.  
  
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
  
1. Avviare Visual Studio e aprire la finestra di dialogo **nuovo progetto** .  
  
2. Nella categoria finestra selezionare il modello **libreria di controlli Windows Forms** .  
  
3. Assegnare il nome `MyControls` al nuovo progetto.  
  
4. Per il percorso specificare una cartella di primo livello con un nome appropriato, ad esempio `WpfHostingWindowsFormsControl`. Successivamente, si immetterà l'applicazione host in questa cartella.  
  
5. Fare clic su **OK** per creare il progetto. Il progetto predefinito contiene un singolo controllo denominato `UserControl1`.  
  
6. In Esplora soluzioni rinominare `UserControl1` `MyControl1`.  
  
 Il progetto dovrebbe includere riferimenti alle DLL di sistema seguenti. Se alcune di queste DLL non sono incluse per impostazione predefinita, aggiungerle al progetto.  
  
- System  
  
- System.Data  
  
- System.Drawing  
  
- System.Windows.Forms  
  
- System.Xml  
  
### <a name="adding-controls-to-the-form"></a>Aggiunta di controlli al form  
 Per aggiungere controlli al form:  
  
- Aprire `MyControl1` nella finestra di progettazione.  
  
 Aggiungere cinque controlli <xref:System.Windows.Forms.Label> e i controlli <xref:System.Windows.Forms.TextBox> corrispondenti, ridimensionati e disposti come sono nell'illustrazione precedente, nel form. Nell'esempio, i controlli <xref:System.Windows.Forms.TextBox> sono denominati:  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 Aggiungere due controlli <xref:System.Windows.Forms.Button> con etichetta **OK** e **Annulla**. Nell'esempio i nomi dei pulsanti sono `btnOK` e `btnCancel`rispettivamente.  
  
### <a name="implementing-the-supporting-code"></a>Implementazione del codice di supporto  
 Aprire il form nella visualizzazione codice. Il controllo restituisce i dati raccolti al relativo host generando l'evento `OnButtonClick` personalizzato. I dati sono contenuti nell'oggetto argomento dell'evento. Il codice seguente mostra la dichiarazione di evento e delegato.  
  
 Aggiungere il codice seguente alla classe `MyControl1` .  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 La classe `MyControlEventArgs` contiene le informazioni da restituire all'host.

 Aggiungere la classe seguente al form.

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 Quando l'utente fa clic sul pulsante **OK** o **Annulla** , i gestori eventi <xref:System.Windows.Forms.Control.Click> creano un oggetto `MyControlEventArgs` che contiene i dati e genera l'evento di `OnButtonClick`. L'unica differenza tra i due gestori è la proprietà `IsOK` dell'argomento dell'evento. Questa proprietà consente all'host di determinare su quale pulsante è stato fatto clic. È impostato su `true` per il pulsante **OK** e `false` per il pulsante **Annulla** . Il codice seguente illustra i gestori dei due pulsanti.

 Aggiungere il codice seguente alla classe `MyControl1` .

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>Assegnazione di un nome sicuro all'assembly e compilazione dell'assembly
 Per fare in modo che a questo assembly venga fatto riferimento da un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è necessario che disponga di un nome sicuro. Per creare un nome sicuro, creare un file di chiave con sn. exe e aggiungerlo al progetto.

1. Aprire il prompt dei comandi di Visual Studio. A tale scopo, fare clic sul menu **Start** , quindi selezionare **tutti i programmi/Microsoft Visual Studio 2010/strumenti di Visual Studio/prompt dei comandi di Visual Studio**. Verrà avviata una finestra della console con variabili di ambiente personalizzate.

2. Al prompt dei comandi usare il comando `cd` per passare alla cartella del progetto.

3. Generare un file di chiave denominato MyControls.snk eseguendo il comando seguente.

    ```console
    Sn.exe -k MyControls.snk
    ```

4. Per includere il file di chiave nel progetto, fare clic con il pulsante destro del mouse sul nome del progetto in Esplora soluzioni e quindi scegliere **Proprietà**. In Creazione progetti fare clic sulla scheda **firma** , selezionare la casella di controllo **Firma assembly** e quindi passare al file di chiave.

5. Compila la soluzione. La compilazione genererà una DLL denominata MyControls.dll.

## <a name="implementing-the-wpf-host-application"></a>Implementazione dell'applicazione host WPF
 L'applicazione host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa il controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> per ospitare `MyControl1`. L'applicazione gestisce l'evento `OnButtonClick` per ricevere i dati dal controllo. Dispone inoltre di una raccolta di pulsanti di opzione che consentono di modificare alcune delle proprietà del controllo dall'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La figura seguente illustra l'applicazione finita.

Nell'immagine seguente viene illustrata l'applicazione completa, incluso il controllo incorporato nell'applicazione WPF:

 ![Screenshot che mostra un controllo incorporato in una pagina WPF.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a>Creazione del progetto
 Per avviare il progetto:

1. Aprire Visual Studio e selezionare **nuovo progetto**.

2. Nella categoria finestra selezionare il modello **applicazione WPF** .

3. Assegnare il nome `WpfHost` al nuovo progetto.

4. Come percorso, specificare la stessa cartella di livello superiore che contiene il progetto MyControls.

5. Fare clic su **OK** per creare il progetto.

 È anche necessario aggiungere riferimenti alla DLL che contiene `MyControl1` e altri assembly.

1. Fare clic con il pulsante destro del mouse sul nome del progetto in Esplora soluzioni e scegliere **Aggiungi riferimento**.

2. Fare clic sulla scheda **Sfoglia** e selezionare la cartella che contiene i controlli. dll. In questa procedura dettagliata la cartella è MyControls\bin\Debug.

3. Selezionare controllo. dll e quindi fare clic su **OK**.

4. Aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration. dll.

### <a name="implementing-the-basic-layout"></a>Implementazione del layout di base
 Il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dell'applicazione host viene implementato nel file MainWindow. XAML. Questo file contiene [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup che definisce il layout e ospita il controllo Windows Forms. L'applicazione è suddivisa in tre aree:

- Il pannello **Proprietà controllo** , che contiene una raccolta di pulsanti di opzione che è possibile utilizzare per modificare varie proprietà del controllo ospitato.

- **Dati dal pannello di controllo** , che contiene diversi elementi <xref:System.Windows.Controls.TextBlock> che visualizzano i dati restituiti dal controllo ospitato.

- Il controllo ospitato stesso.

 Il layout di base è illustrato nel codice XAML seguente. Il markup necessario per ospitare `MyControl1` viene omesso da questo esempio, ma verrà discusso più avanti.

 Sostituire il codice XAML in MainWindow.xaml con il seguente. Se si utilizza Visual Basic, impostare la classe su `x:Class="MainWindow"`.

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 Il primo elemento <xref:System.Windows.Controls.StackPanel> contiene diversi set di controlli <xref:System.Windows.Controls.RadioButton> che consentono di modificare diverse proprietà predefinite del controllo ospitato. Seguito da un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> che ospita `MyControl1`. L'elemento <xref:System.Windows.Controls.StackPanel> finale contiene diversi elementi <xref:System.Windows.Controls.TextBlock> che visualizzano i dati restituiti dal controllo ospitato. L'ordinamento degli elementi e le impostazioni degli attributi <xref:System.Windows.Controls.DockPanel.Dock%2A> e <xref:System.Windows.FrameworkElement.Height%2A> incorporano il controllo ospitato nella finestra senza gap o distorsione.

#### <a name="hosting-the-control"></a>Hosting del controllo
 La versione modificata seguente del codice XAML precedente è incentrata sugli elementi necessari per ospitare `MyControl1`.

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 L'attributo di mapping dello spazio dei nomi `xmlns` crea un riferimento allo spazio dei nomi `MyControls` che contiene il controllo ospitato. Questo mapping consente di rappresentare `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] `<mcl:MyControl1>`.

 Due elementi nel codice XAML gestiscono l'hosting:

- `WindowsFormsHost` rappresenta l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> che consente di ospitare un controllo Windows Forms in un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

- `mcl:MyControl1`, che rappresenta `MyControl1`, viene aggiunto alla raccolta figlio dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Di conseguenza, viene eseguito il rendering di questo controllo Windows Forms come parte della finestra di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ed è possibile comunicare con il controllo dall'applicazione.

### <a name="implementing-the-code-behind-file"></a>Implementazione del file code-behind
 Il file code-behind, MainWindow. XAML. vb o MainWindow.xaml.cs, contiene il codice procedurale che implementa la funzionalità della [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] descritta nella sezione precedente. Le attività principali sono:

- Associazione di un gestore eventi all'evento `OnButtonClick` di `MyControl1`.

- Modifica di diverse proprietà di `MyControl1`, in base alla modalità di impostazione della raccolta di pulsanti di opzione.

- Visualizzare i dati raccolti dal controllo.

#### <a name="initializing-the-application"></a>Inizializzazione dell'applicazione
 Il codice di inizializzazione è contenuto in un gestore eventi per l'evento <xref:System.Windows.FrameworkElement.Loaded> della finestra e connette un gestore eventi all'evento `OnButtonClick` del controllo.

 In MainWindow. XAML. vb o MainWindow.xaml.cs aggiungere il codice seguente alla classe `MainWindow`.

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 Poiché la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] descritta in precedenza ha aggiunto `MyControl1` alla raccolta di elementi figlio dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, è possibile eseguire il cast del <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> per ottenere il riferimento a `MyControl1`. È quindi possibile utilizzare tale riferimento per alleghi un gestore eventi a `OnButtonClick`.

 Oltre a fornire un riferimento al controllo stesso, <xref:System.Windows.Forms.Integration.WindowsFormsHost> espone alcune proprietà del controllo, che è possibile modificare dall'applicazione. Il codice di inizializzazione assegna tali valori a variabili globali private per l'uso successivo nell'applicazione.

 Per poter accedere facilmente ai tipi nella DLL `MyControls`, aggiungere la `Imports` o l'istruzione `using` seguente all'inizio del file.

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a>Gestione dell'evento OnButtonClick
 `MyControl1` genera l'evento `OnButtonClick` quando l'utente fa clic su uno dei pulsanti del controllo.

 Aggiungere il codice seguente alla classe `MainWindow` .

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 I dati nelle caselle di testo vengono compressi nell'oggetto `MyControlEventArgs`. Se l'utente fa clic sul pulsante **OK** , il gestore dell'evento estrae i dati e li Visualizza nel pannello riportato di seguito `MyControl1`.

#### <a name="modifying-the-controls-properties"></a>Modifica delle proprietà del controllo
 L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> espone diverse proprietà predefinite del controllo ospitato. Di conseguenza, è possibile modificare l'aspetto del controllo in modo che corrisponda maggiormente allo stile dell'applicazione. Gli insiemi di pulsanti di opzione nel pannello di sinistra consentono all'utente di modificare varie proprietà di colore e tipo di carattere. Ogni set di pulsanti dispone di un gestore per l'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, che rileva le selezioni dei pulsanti di opzione dell'utente e modifica la proprietà corrispondente nel controllo.

 Aggiungere il codice seguente alla classe `MainWindow` .

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Compilare ed eseguire l'applicazione. Aggiungere testo nel controllo Windows Forms composito, quindi fare clic su **OK**. Il testo viene visualizzato nelle etichette. Fare clic sui vari pulsanti di opzione per vedere l'effetto sul controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Procedura dettagliata: hosting di controlli Windows Form in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
