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
ms.openlocfilehash: 90d0e2f3c6ebab070809a4813c87da3539fd14f1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337851"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>Procedura dettagliata: Hosting di un controllo composito Windows Form in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando è presente un investimento sostanziale [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] codice, può essere più efficace riutilizzare almeno parte di tale codice nella [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione anziché riscriverla da zero. Lo scenario più comune è quando si dispone di controlli Windows Form esistenti. In alcuni casi, è possibile che non si abbia accesso al codice sorgente di questi controlli. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre una procedura semplice per l'hosting di tali controlli in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione. Ad esempio, è possibile usare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per la maggior parte della programmazione e che ospita lo specializzato <xref:System.Windows.Forms.DataGridView> controlli.  
  
 Questa procedura dettagliata descritta un'applicazione che ospita un controllo composito Windows Forms per eseguire l'immissione di dati in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione. Il controllo composito è compresso in una DLL. Questa procedura generale può essere estesa ad applicazioni e controlli più complessi. Questa procedura dettagliata è progettata per essere pressoché identiche aspetto e funzionalità a [procedura dettagliata: Hosting di un controllo composito WPF in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md). La principale differenza è che lo scenario di hosting è invertito.  
  
 La procedura guidata è suddivisa in due sezioni. La prima sezione descrive brevemente l'implementazione del controllo composito Windows Forms. La seconda sezione illustra in dettaglio come ospitare il controllo composito in una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione, ricevere eventi dal controllo e accedere ad alcune delle proprietà del controllo.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Implementazione del controllo Windows Forms composito.  
  
-   Implementazione dell'applicazione host WPF.  
  
 Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [che ospita un controllo Windows Forms composito in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159999).  
  
## <a name="prerequisites"></a>Prerequisiti  

Per completare la procedura dettagliata, è necessario Visual Studio.
  
## <a name="implementing-the-windows-forms-composite-control"></a>Implementazione del controllo Windows Forms composito  
 Del controllo di Windows Forms composito usato in questo esempio è una forma semplice immissione di dati. Questo form accetta nome e indirizzo dell'utente e quindi usa un evento personalizzato per restituire le informazioni all'host. La figura seguente mostra il controllo sottoposto a rendering.  

 L'immagine seguente mostra un controllo Windows Forms composito:  

 ![Screenshot che mostra un controllo Windows Form semplice.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a>Creazione del progetto  
 Per avviare il progetto:  
  
1. Avvio veloce [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]e aprire la **nuovo progetto** nella finestra di dialogo.  
  
2. Nella categoria finestra selezionare il **libreria di controlli Windows Form** modello.  
  
3. Assegnare il nome `MyControls` al nuovo progetto.  
  
4. Per il percorso, specificare una cartella di livello superiore denominata in modo appropriato, ad esempio `WpfHostingWindowsFormsControl`. Successivamente, si immetterà l'applicazione host in questa cartella.  
  
5. Fare clic su **OK** per creare il progetto. Il progetto predefinito contiene un unico controllo denominato `UserControl1`.  
  
6. In Esplora soluzioni rinominare `UserControl1` a `MyControl1`.  
  
 Il progetto dovrebbe includere riferimenti alle DLL di sistema seguenti. Se alcune di queste DLL non sono incluse per impostazione predefinita, aggiungerle al progetto.  
  
-   System  
  
-   System.Data  
  
-   System.Drawing  
  
-   System.Windows.Forms  
  
-   System.Xml  
  
### <a name="adding-controls-to-the-form"></a>Aggiunta di controlli al form  
 Per aggiungere controlli al form:  
  
-   Apri `MyControl1` nella finestra di progettazione.  
  
 Aggiungere cinque <xref:System.Windows.Forms.Label> controlli e i relativi <xref:System.Windows.Forms.TextBox> controlli, dimensioni e la disposizione che presentano nella figura precedente, nel form. Nell'esempio di <xref:System.Windows.Forms.TextBox> sono denominati controlli:  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 Aggiungere due <xref:System.Windows.Forms.Button> controlli con etichettati **OK** e **Annulla**. Nell'esempio sono i nomi dei pulsanti `btnOK` e `btnCancel`, rispettivamente.  
  
### <a name="implementing-the-supporting-code"></a>Implementazione del codice di supporto  
 Aprire il form nella visualizzazione codice. Il controllo restituisce i dati raccolti al relativo host generando l'oggetto personalizzato `OnButtonClick` evento. I dati sono contenuti nell'oggetto argomento dell'evento. Il codice seguente mostra la dichiarazione di evento e delegato.  
  
 Aggiungere il codice seguente alla classe `MyControl1` .  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 Il `MyControlEventArgs` classe contiene le informazioni da restituire all'host.

 Aggiungere la classe seguente al form.

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 Quando l'utente fa clic il **OK** o **Annulla** pulsante, il <xref:System.Windows.Forms.Control.Click> creare gestori eventi un `MyControlEventArgs` oggetto che contiene i dati e genera il `OnButtonClick` evento. L'unica differenza tra i due gestori è l'argomento dell'evento `IsOK` proprietà. Questa proprietà consente all'host di determinare su quale pulsante è stato fatto clic. È impostato su `true` per il **OK** pulsante, e `false` per il **Annulla** pulsante. Il codice seguente illustra i gestori dei due pulsanti.

 Aggiungere il codice seguente alla classe `MyControl1` .

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>Assegnazione di un nome sicuro all'assembly e compilazione dell'assembly
 Per questo assembly a cui fa riferimento un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un'applicazione, deve avere un nome sicuro. Per creare un nome sicuro, creare un file di chiave con Sn.exe e aggiungerlo al progetto.

1. Aprire il prompt dei comandi di [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]. A tale scopo, fare clic sui **avviare** dal menu e quindi selezionare **tutti i programmi/Microsoft Visual Studio 2010 e Visual Studio Tools e Visual Studio Command Prompt**. Verrà avviata una finestra della console con variabili di ambiente personalizzate.

2. Al prompt dei comandi, usare il `cd` comando per passare alla cartella del progetto.

3. Generare un file di chiave denominato MyControls.snk eseguendo il comando seguente.

    ```
    Sn.exe -k MyControls.snk
    ```

4. Per includere il file di chiave nel progetto, fare clic sul nome del progetto in Esplora soluzioni e quindi fare clic su **proprietà**. In Creazione progetti, fare clic sui **Signing** scheda, seleziona la **firmare l'assembly** casella di controllo e quindi passare al file della chiave.

5. Compilare la soluzione. La compilazione genererà una DLL denominata MyControls.dll.

## <a name="implementing-the-wpf-host-application"></a>Implementazione dell'applicazione host WPF
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitare l'applicazione utilizza le <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo host `MyControl1`. L'applicazione gestisce il `OnButtonClick` eventi per ricevere i dati dal controllo. Include anche una raccolta di pulsanti di opzione che consentono di modificare alcune delle proprietà del controllo dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione. La figura seguente illustra l'applicazione finita.

L'immagine seguente mostra l'applicazione completa, tra cui il controllo incorporato nell'applicazione WPF:

 ![Screenshot che mostra un controllo incorporato in una pagina WPF.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a>Creazione del progetto
 Per avviare il progetto:

1. Aprire [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]e selezionare **nuovo progetto**.

2. Nella categoria finestra selezionare il **WPF Application** modello.

3. Assegnare il nome `WpfHost` al nuovo progetto.

4. Come percorso, specificare la stessa cartella di livello superiore che contiene il progetto MyControls.

5. Fare clic su **OK** per creare il progetto.

 È inoltre necessario aggiungere i riferimenti alla DLL contenente `MyControl1` e ad altri assembly.

1. Il nome del progetto in Esplora soluzioni e scegliere **Aggiungi riferimento**.

2. Scegliere il **esplorare** scheda e passare alla cartella che contiene MyControls. In questa procedura dettagliata la cartella è MyControls\bin\Debug.

3. Selezionare MyControls e quindi fare clic su **OK**.

4. Aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration. dll.

### <a name="implementing-the-basic-layout"></a>Implementazione del layout di base
 Il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dell'host applicazione viene implementata in MainWindow. Xaml. Questo file contiene [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup che definisce il layout e ospita il controllo Windows Form. L'applicazione è suddivisa in tre aree:

-   Il **le proprietà del controllo** pannello che contiene una raccolta di pulsanti di opzione che è possibile usare per modificare varie proprietà del controllo ospitato.

-   Il **i dati di controllo** pannello che contiene numerosi <xref:System.Windows.Controls.TextBlock> gli elementi che consentono di visualizzare i dati restituiti dal controllo ospitato.

-   Il controllo ospitato stesso.

 Il layout di base è illustrato nel codice XAML seguente. Il markup necessario per ospitare `MyControl1` viene omesso da questo esempio, ma verrà discusso più avanti.

 Sostituire il codice XAML in MainWindow.xaml con il seguente. Se si usa Visual Basic, modificare la classe in `x:Class="MainWindow"`.

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 Il primo <xref:System.Windows.Controls.StackPanel> elemento contiene diversi insiemi di <xref:System.Windows.Controls.RadioButton> controlli che consentono di modificare varie proprietà predefinite del controllo ospitato. Che è seguita da un <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento, che ospita `MyControl1`. L'elemento finale <xref:System.Windows.Controls.StackPanel> elemento contiene numerosi <xref:System.Windows.Controls.TextBlock> gli elementi che consentono di visualizzare i dati restituiti dal controllo ospitato. L'ordinamento degli elementi e il <xref:System.Windows.Controls.DockPanel.Dock%2A> e <xref:System.Windows.FrameworkElement.Height%2A> impostazioni degli attributi di incorporare il controllo ospitato nella finestra senza spazi o distorsioni.

#### <a name="hosting-the-control"></a>Hosting del controllo
 La versione modificata seguente del XAML precedente è incentrato sugli elementi necessari all'host `MyControl1`.

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 Il `xmlns` attributo di mapping dello spazio dei nomi viene creato un riferimento al `MyControls` dello spazio dei nomi che contiene il controllo ospitato. Questo mapping consente di rappresentare `MyControl1` nelle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] come `<mcl:MyControl1>`.

 Due elementi nel codice XAML gestiscono l'hosting:

-   `WindowsFormsHost` rappresenta il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento che consente di ospitare un controllo Windows Form in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione.

-   `mcl:MyControl1`, che rappresenta `MyControl1`, viene aggiunto al <xref:System.Windows.Forms.Integration.WindowsFormsHost> raccolta figlio dell'elemento. Di conseguenza, questo controllo Windows Forms viene eseguito il rendering come parte di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finestra ed è possibile comunicare con il controllo dall'applicazione.

### <a name="implementing-the-code-behind-file"></a>Implementazione del file code-behind
 Il file code-behind,. Xaml. vb o MainWindow.xaml.cs, contiene il codice procedurale che implementa la funzionalità del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] illustrati nella sezione precedente. Le attività principali sono:

-   Collegare un gestore eventi per `MyControl1`del `OnButtonClick` evento.

-   Modificare varie proprietà di `MyControl1`, in base al modo in cui viene impostato l'insieme di pulsanti di opzione.

-   Visualizzare i dati raccolti dal controllo.

#### <a name="initializing-the-application"></a>Inizializzazione dell'applicazione
 Il codice di inizializzazione è contenuto in un gestore eventi per la finestra <xref:System.Windows.FrameworkElement.Loaded> eventi e associa un gestore eventi per il controllo `OnButtonClick` evento.

 In MainWindow.xaml.cs o MainWindow. Xaml. vb, aggiungere il codice seguente per il `MainWindow` classe.

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 Poiché il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedentemente illustrato ha aggiunto `MyControl1` per il <xref:System.Windows.Forms.Integration.WindowsFormsHost> raccolta di elementi figlio dell'elemento, è possibile eseguire il cast il <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> per ottenere il riferimento a `MyControl1`. È quindi possibile usare che fanno riferimento a collegare un gestore eventi al `OnButtonClick`.

 Oltre a fornire un riferimento al controllo stesso, <xref:System.Windows.Forms.Integration.WindowsFormsHost> espone un numero di proprietà del controllo, che è possibile modificare dall'applicazione. Il codice di inizializzazione assegna tali valori a variabili globali private per l'uso successivo nell'applicazione.

 In modo che i tipi facilmente accessibile la `MyControls` DLL, aggiungere quanto segue `Imports` o `using` istruzione all'inizio del file.

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a>Gestione dell'evento OnButtonClick
 `MyControl1` Genera il `OnButtonClick` evento quando l'utente fa clic su uno dei pulsanti del controllo.

 Aggiungere il codice seguente alla classe `MainWindow` .

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 I dati nelle caselle di testo vengono compressi nel `MyControlEventArgs` oggetto. Se l'utente sceglie il **OK** pulsante, il gestore eventi estrae i dati e lo visualizza nel pannello inferiore `MyControl1`.

#### <a name="modifying-the-controls-properties"></a>Modifica delle proprietà del controllo
 Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento espone varie delle proprietà predefinite del controllo ospitato. Di conseguenza, è possibile modificare l'aspetto del controllo in modo che corrisponda maggiormente allo stile dell'applicazione. Gli insiemi di pulsanti di opzione nel pannello di sinistra consentono all'utente di modificare varie proprietà di colore e tipo di carattere. Ogni set di pulsanti presenta un gestore per il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento, che rileva selezioni del pulsante di opzione dell'utente e la proprietà corrispondente sul controllo di modifica.

 Aggiungere il codice seguente alla classe `MainWindow` .

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Compilare ed eseguire l'applicazione. Aggiungere il testo nel controllo composito Windows Forms e quindi fare clic su **OK**. Il testo viene visualizzato nelle etichette. Fare clic sui vari pulsanti di opzione per vedere l'effetto sul controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Procedura dettagliata: Hosting di un controllo Windows Form in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
