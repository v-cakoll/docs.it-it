---
title: 'Procedura dettagliata: hosting di controlli Windows Form compositi in WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f332461bd5abb5e3fca705a8a5fd363c3d33296
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>Procedura dettagliata: hosting di controlli Windows Form compositi in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si dispone di un investimento sostanziale in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] codice, può essere più efficiente riutilizzare almeno alcuni che il codice del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione anziché riscriverla, da zero. Lo scenario più comune è quando si dispone [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] controlli. In alcuni casi, è possibile che non si abbia accesso al codice sorgente di questi controlli. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce una procedura molto semplice per l'hosting di tali controlli in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione. Ad esempio, è possibile utilizzare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per la maggior parte della programmazione pur ospitando specializzate <xref:System.Windows.Forms.DataGridView> controlli.  
  
 Questa procedura dettagliata viene descritta un'applicazione che ospita un [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] controllo composito per eseguire l'immissione di dati in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione. Il controllo composito è compresso in una DLL. Questa procedura generale può essere estesa ad applicazioni e controlli più complessi. Questa procedura dettagliata è progettata per essere pressoché identiche in aspetto e funzionalità a [procedura dettagliata: Hosting di un controllo composito WPF in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md). La principale differenza è che lo scenario di hosting è invertito.  
  
 La procedura guidata è suddivisa in due sezioni. La prima sezione viene descritto brevemente l'implementazione del [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] controllo composito. La seconda sezione illustra in dettaglio come ospitare il controllo composito in una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ricevere gli eventi dal controllo, applicazione e accedere ad alcune delle proprietà del controllo.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Implementazione del controllo Windows Forms composito.  
  
-   Implementazione dell'applicazione host WPF.  
  
 Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [ospita un controllo Windows Form composito in WPF esempio](http://go.microsoft.com/fwlink/?LinkID=159999).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="implementing-the-windows-forms-composite-control"></a>Implementazione del controllo Windows Forms composito  
 Il [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] controllo composito utilizzato in questo esempio è un form di immissione di dati semplice. Questo form accetta nome e indirizzo dell'utente e quindi usa un evento personalizzato per restituire le informazioni all'host. La figura seguente mostra il controllo sottoposto a rendering.  
  
 ![Controllo Windows Form semplice](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")  
Controllo Windows Forms composito  
  
### <a name="creating-the-project"></a>Creazione del progetto  
 Per avviare il progetto:  
  
1.  Avviare [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]e aprire il **nuovo progetto** la finestra di dialogo.  
  
2.  Nella categoria di finestra, selezionare il **libreria di controlli Windows Form** modello.  
  
3.  Denominare il nuovo progetto `MyControls`.  
  
4.  Per il percorso, specificare una cartella di primo livello denominata in modo appropriato, ad esempio `WpfHostingWindowsFormsControl`. Successivamente, si immetterà l'applicazione host in questa cartella.  
  
5.  Fare clic su **OK** per creare il progetto. Il progetto predefinito contiene un singolo controllo denominato `UserControl1`.  
  
6.  In Esplora soluzioni rinominare `UserControl1` a `MyControl1`.  
  
 Il progetto dovrebbe includere riferimenti alle DLL di sistema seguenti. Se alcune di queste DLL non sono incluse per impostazione predefinita, aggiungerle al progetto.  
  
-   System  
  
-   System.Data  
  
-   System.Drawing  
  
-   System.Windows.Forms  
  
-   System.Xml  
  
### <a name="adding-controls-to-the-form"></a>Aggiunta di controlli al form  
 Per aggiungere controlli al form:  
  
-   Aprire `MyControl1` nella finestra di progettazione.  
  
 Aggiungere cinque <xref:System.Windows.Forms.Label> controlli e le relative <xref:System.Windows.Forms.TextBox> controlli, ridimensionati e disposti come nell'illustrazione precedente, nel form. Nell'esempio di <xref:System.Windows.Forms.TextBox> sono denominati controlli:  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 Aggiungere due <xref:System.Windows.Forms.Button> controlli etichettati **OK** e **Annulla**. Nell'esempio, i nomi sono `btnOK` e `btnCancel`, rispettivamente.  
  
### <a name="implementing-the-supporting-code"></a>Implementazione del codice di supporto  
 Aprire il form nella visualizzazione codice. Il controllo restituisce i dati raccolti per il relativo host tramite la generazione personalizzata `OnButtonClick` evento. I dati sono contenuti nell'oggetto argomento dell'evento. Il codice seguente mostra la dichiarazione di evento e delegato.  
  
 Aggiungere il codice seguente alla classe `MyControl1`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]  
  
 La `MyControlEventArgs` classe contiene le informazioni da restituire all'host.  
  
 Aggiungere la classe seguente al form.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]  
  
 Quando l'utente fa clic il **OK** o **Annulla** pulsante, il <xref:System.Windows.Forms.Control.Click> creare gestori eventi un `MyControlEventArgs` oggetto che contiene i dati e genera il `OnButtonClick` evento. L'unica differenza tra i due gestori è l'argomento di evento `IsOK` proprietà. Questa proprietà consente all'host di determinare su quale pulsante è stato fatto clic. È impostato su `true` per il **OK** pulsante e `false` per il **Annulla** pulsante. Il codice seguente illustra i gestori dei due pulsanti.  
  
 Aggiungere il codice seguente alla classe `MyControl1`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]  
  
### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>Assegnazione di un nome sicuro all'assembly e compilazione dell'assembly  
 Per questo assembly venga fatto riferimento in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un'applicazione, è necessario avere un nome sicuro. Per creare un nome sicuro, creare un file di chiave con Sn.exe e aggiungerlo al progetto.  
  
1.  Aprire il prompt dei comandi di [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]. A tale scopo, fare clic su di **avviare** menu e quindi selezionare **tutti i programmi/Microsoft Visual Studio 2010 e Visual Studio Tools e Visual Studio prompt dei comandi**. Verrà avviata una finestra della console con variabili di ambiente personalizzate.  
  
2.  Al prompt dei comandi, utilizzare il `cd` comando per passare alla cartella del progetto.  
  
3.  Generare un file di chiave denominato MyControls.snk eseguendo il comando seguente.  
  
    ```  
    Sn.exe -k MyControls.snk  
    ```  
  
4.  Per includere il file di chiave nel progetto, fare doppio clic sul nome del progetto in Esplora soluzioni e quindi fare clic su **proprietà**. In Progettazione progetti, fare clic su di **firma** , selezionare il **firmare l'assembly** casella di controllo e quindi individuare il file di chiave.  
  
5.  Compilare la soluzione. La compilazione genererà una DLL denominata MyControls.dll.  
  
## <a name="implementing-the-wpf-host-application"></a>Implementazione dell'applicazione host WPF  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitare l'applicazione utilizza il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo host `MyControl1`. Gli handle di applicazioni di `OnButtonClick` eventi per ricevere i dati dal controllo. Include inoltre una raccolta di pulsanti di opzione che consente di modificare alcune delle proprietà del controllo dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione. La figura seguente illustra l'applicazione finita.  
  
 ![Un controllo incorporato in una pagina WPF](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost")  
Applicazione completa che mostra il controllo incorporato nell'applicazione WPF  
  
### <a name="creating-the-project"></a>Creazione del progetto  
 Per avviare il progetto:  
  
1.  Aprire [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]e selezionare **nuovo progetto**.  
  
2.  Nella categoria di finestra, selezionare il **applicazione WPF** modello.
  
3.  Denominare il nuovo progetto `WpfHost`.  
  
4.  Come percorso, specificare la stessa cartella di livello superiore che contiene il progetto MyControls.  
  
5.  Fare clic su **OK** per creare il progetto.  
  
 È inoltre necessario aggiungere i riferimenti alla DLL contenente `MyControl1` e altri assembly.  
  
1.  Il nome del progetto in Esplora soluzioni e scegliere **Aggiungi riferimento**.  
  
2.  Fare clic su di **Sfoglia** scheda e passare alla cartella che contiene MyControls. In questa procedura dettagliata la cartella è MyControls\bin\Debug.  
  
3.  Selezionare MyControls e quindi fare clic su **OK**.  
  
4.  Aggiungere un riferimento all'assembly WindowsFormsIntegration, denominato WindowsFormsIntegration.  
  
### <a name="implementing-the-basic-layout"></a>Implementazione del layout di base  
 Il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dell'host applicazione viene implementata in MainWindow. Xaml. Questo file contiene [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup che definisce il layout e ospita il [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] controllo. L'applicazione è suddivisa in tre aree:  
  
-   Il **le proprietà del controllo** pannello che contiene una raccolta di pulsanti di opzione che consente di modificare diverse proprietà del controllo ospitato.  
  
-   Il **dati dal controllo** pannello che contiene numerosi <xref:System.Windows.Controls.TextBlock> gli elementi che consentono di visualizzare i dati restituiti dal controllo ospitato.  
  
-   Il controllo ospitato stesso.  
  
 Il layout di base è illustrato nel codice XAML seguente. Il codice necessario per ospitare `MyControl1` viene omesso da questo esempio, ma verrà descritta più avanti.  
  
 Sostituire il codice XAML in MainWindow.xaml con il seguente. Se si utilizza Visual Basic, modificare la classe a `x:Class="MainWindow"`.  
  
 [!code-xaml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]  
  
 Il primo <xref:System.Windows.Controls.StackPanel> elemento contiene diversi set di <xref:System.Windows.Controls.RadioButton> i controlli che consentono di modificare diverse proprietà predefinite del controllo ospitato. Che è seguito da un <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento, che ospita `MyControl1`. Finale <xref:System.Windows.Controls.StackPanel> elemento contiene numerosi <xref:System.Windows.Controls.TextBlock> gli elementi che consentono di visualizzare i dati restituiti dal controllo ospitato. L'ordinamento degli elementi e <xref:System.Windows.Controls.DockPanel.Dock%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le impostazioni di attributi incorporare il controllo ospitato nella finestra senza spazi o una distorsione.  
  
#### <a name="hosting-the-control"></a>Hosting del controllo  
 La seguente versione modificata del codice XAML precedente è incentrato sugli elementi necessari per ospitare `MyControl1`.  
  
 [!code-xaml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]  
[!code-xaml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]  
  
 Il `xmlns` attributo di mapping dello spazio dei nomi creato un riferimento di `MyControls` dello spazio dei nomi che contiene il controllo ospitato. Questo mapping consente di rappresentare `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] come `<mcl:MyControl1>`.  
  
 Due elementi nel codice XAML gestiscono l'hosting:  
  
-   `WindowsFormsHost`rappresenta il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento che consente di ospitare un [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] controllo un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione.  
  
-   `mcl:MyControl1`, che rappresenta `MyControl1`, viene aggiunto per il <xref:System.Windows.Forms.Integration.WindowsFormsHost> insieme figlio dell'elemento. Di conseguenza, questo [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] come parte del rendering del controllo di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finestra ed è possibile comunicare con il controllo dall'applicazione.  
  
### <a name="implementing-the-code-behind-file"></a>Implementazione del file code-behind  
 Il file code-behind, vb o MainWindow.xaml.cs, contiene il codice procedurale che implementa la funzionalità del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] descritto nella sezione precedente. Le attività principali sono:  
  
-   Associare un gestore eventi per `MyControl1`del `OnButtonClick` evento.  
  
-   Modificare diverse proprietà di `MyControl1`, in base al modo in cui viene impostato l'insieme di pulsanti di opzione.  
  
-   Visualizzare i dati raccolti dal controllo.  
  
#### <a name="initializing-the-application"></a>Inizializzazione dell'applicazione  
 Il codice di inizializzazione è contenuto in un gestore eventi per la finestra <xref:System.Windows.FrameworkElement.Loaded> evento e associa un gestore eventi per il controllo `OnButtonClick` evento.  
  
 In MainWindow.Xaml.cs o MainWindow, aggiungere il codice seguente per la `MainWindow` classe.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]  
  
 Perché il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] descritti precedentemente aggiunti `MyControl1` per il <xref:System.Windows.Forms.Integration.WindowsFormsHost> raccolta di elementi figlio dell'elemento, è possibile eseguire il cast di <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> per ottenere il riferimento a `MyControl1`. Quindi, è possibile utilizzare tale riferimento per collegare un gestore eventi per `OnButtonClick`.  
  
 Oltre a fornire un riferimento al controllo stesso, <xref:System.Windows.Forms.Integration.WindowsFormsHost> espone un numero di proprietà del controllo, che è possibile modificare dall'applicazione. Il codice di inizializzazione assegna tali valori a variabili globali private per l'uso successivo nell'applicazione.  
  
 In modo che è possibile accedere facilmente i tipi di `MyControls` DLL, aggiungere il seguente `Imports` o `using` all'inizio del file.  
  
```vb  
Imports MyControls  
```  
  
```csharp  
using MyControls;  
```  
  
#### <a name="handling-the-onbuttonclick-event"></a>Gestione dell'evento OnButtonClick  
 `MyControl1`Genera il `OnButtonClick` evento quando l'utente fa clic su uno dei pulsanti del controllo.  
  
 Aggiungere il codice seguente alla classe `MainWindow`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]  
  
 I dati nelle caselle di testo vengono compressi nel `MyControlEventArgs` oggetto. Se l'utente sceglie il **OK** pulsante, il gestore dell'evento estrae i dati e di visualizzarlo nel pannello inferiore `MyControl1`.  
  
#### <a name="modifying-the-controls-properties"></a>Modifica delle proprietà del controllo  
 Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento espone numerose proprietà predefinite del controllo ospitato. Di conseguenza, è possibile modificare l'aspetto del controllo in modo che corrisponda maggiormente allo stile dell'applicazione. Gli insiemi di pulsanti di opzione nel pannello di sinistra consentono all'utente di modificare varie proprietà di colore e tipo di carattere. Ogni serie di pulsanti dispone di un gestore per il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento, che rileva le selezioni dell'utente opzione pulsante e modifica la proprietà corrispondente nel controllo.  
  
 Aggiungere il codice seguente alla classe `MainWindow`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Compilare ed eseguire l'applicazione. Aggiungere del testo nel controllo Windows Form composito e quindi fare clic su **OK**. Il testo viene visualizzato nelle etichette. Fare clic sui vari pulsanti di opzione per vedere l'effetto sul controllo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Procedura dettagliata: hosting di controlli Windows Form in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
