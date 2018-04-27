---
title: 'Procedura dettagliata: hosting di controlli compositi di WPF in Windows Form'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
caps.latest.revision: 34
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f5a3cef6bc2614691584828ff61e0f8ea40b9f95
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Procedura dettagliata: hosting di controlli compositi di WPF in Windows Form
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si dispone di un investimento sostanziale in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] codice, può essere più efficace estendere esistente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] un'applicazione con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] anziché riscriverla, da zero. Uno scenario comune è quando si desidera incorporare uno o più controlli implementati con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all'interno dell'applicazione Windows Form. Per ulteriori informazioni sulla personalizzazione dei controlli WPF, vedere [controllo personalizzazione](../../../../docs/framework/wpf/controls/control-customization.md).  
  
 In questa procedura dettagliata è tramite un'applicazione che ospita un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito per eseguire l'immissione di dati in un'applicazione Windows Form. Il controllo composito è compresso in una DLL. Questa procedura generale può essere estesa ad applicazioni e controlli più complessi. Questa procedura dettagliata è progettata per essere pressoché identiche in aspetto e funzionalità a [procedura dettagliata: Hosting di controlli Windows Form composito in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md). La principale differenza è che lo scenario di hosting è invertito.  
  
 La procedura guidata è suddivisa in due sezioni. La prima sezione viene descritto brevemente l'implementazione del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito. La seconda sezione illustra in dettaglio come ospitare il controllo composito in un'applicazione Windows Forms, ricevere gli eventi dal controllo e accedere ad alcune delle proprietà del controllo.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Implementazione del controllo composito WPF.  
  
-   Implementazione dell'applicazione host Windows Forms.  
  
 Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere [ospita un controllo composito WPF in Windows Form](http://go.microsoft.com/fwlink/?LinkID=159996).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="implementing-the-wpf-composite-control"></a>Implementazione del controllo composito WPF  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito utilizzato in questo esempio è un form di immissione di dati semplici che accetta nome e l'indirizzo dell'utente. Quando l'utente fa clic su uno dei due pulsanti per indicare che l'attività è completata, il controllo genera un evento personalizzato per restituire tali informazioni all'host. La figura seguente mostra il controllo sottoposto a rendering.  
  
 ![Controllo WPF semplice](../../../../docs/framework/wpf/advanced/media/avaloncontrol.png "AvalonControl")  
Controllo composito WPF  
  
### <a name="creating-the-project"></a>Creazione del progetto  
 Per avviare il progetto:  
  
1.  Avviare [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]e aprire il **nuovo progetto** la finestra di dialogo.  
  
2.  In Visual c# e la categoria di Windows, selezionare il **libreria di controlli utente WPF** modello.  
  
3.  Assegnare il nome `MyControls` al nuovo progetto.  
  
4.  Per il percorso, specificare una cartella di primo livello denominata in modo appropriato, ad esempio `WindowsFormsHostingWpfControl`. Successivamente, si immetterà l'applicazione host in questa cartella.  
  
5.  Fare clic su **OK** per creare il progetto. Il progetto predefinito contiene un singolo controllo denominato `UserControl1`.  
  
6.  In Esplora soluzioni rinominare `UserControl1` a `MyControl1`.  
  
 Il progetto dovrebbe includere riferimenti alle DLL di sistema seguenti. Se alcune di queste DLL non sono incluse per impostazione predefinita, aggiungerle al progetto.  
  
-   PresentationCore  
  
-   PresentationFramework  
  
-   System  
  
-   WindowsBase  
  
### <a name="creating-the-user-interface"></a>Creazione dell'interfaccia utente  
 Il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] per il controllo composito è implementato con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Il controllo composito [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] è costituito da cinque <xref:System.Windows.Controls.TextBox> elementi. Ogni <xref:System.Windows.Controls.TextBox> è associato un elemento <xref:System.Windows.Controls.TextBlock> elemento che funge da un'etichetta. Esistono due <xref:System.Windows.Controls.Button> gli elementi nella parte inferiore, **OK** e **Annulla**. Quando l'utente fa clic su uno di questi pulsanti, il controllo genera un evento personalizzato per restituire le informazioni all'host.  
  
#### <a name="basic-layout"></a>Layout di base  
 I vari [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] gli elementi sono contenuti un <xref:System.Windows.Controls.Grid> elemento. È possibile utilizzare <xref:System.Windows.Controls.Grid> per disporre il contenuto del composita controllo praticamente la stessa modalità si utilizzerebbe un `Table` elemento in formato HTML. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dispone anche di un <xref:System.Windows.Documents.Table> elemento, ma <xref:System.Windows.Controls.Grid> è più semplice e più appropriata per le attività di layout semplice.  
  
 Il codice XAML seguente illustra il layout di base. Questo codice XAML definisce la struttura generale del controllo specificando il numero di colonne e righe di <xref:System.Windows.Controls.Grid> elemento.  
  
 In MyControl1.xaml sostituire il codice XAML esistente con il seguente.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>Aggiunta di elementi TextBlock e TextBox alla griglia  
 Inserire un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento nella griglia impostando l'elemento <xref:System.Windows.Controls.Grid.RowProperty> e <xref:System.Windows.Controls.Grid.ColumnProperty> gli attributi per il numero di riga e colonna appropriato. Ricordare che la numerazione di righe e colonne e in base zero. È possibile disporre di un elemento occupa più colonne impostando il relativo <xref:System.Windows.Controls.Grid.ColumnSpanProperty> attributo. Per ulteriori informazioni su <xref:System.Windows.Controls.Grid> elementi, vedere [creare un elemento griglia](../../../../docs/framework/wpf/controls/how-to-create-a-grid-element.md).  
  
 Il codice XAML seguente viene illustrato il controllo composito <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.TextBlock> gli elementi con i relativi <xref:System.Windows.Controls.Grid.RowProperty> e <xref:System.Windows.Controls.Grid.ColumnProperty> gli attributi, che possono essere impostati per inserire correttamente gli elementi nella griglia.  
  
 In Mycontrol1, aggiungere il codice XAML seguente all'interno di <xref:System.Windows.Controls.Grid> elemento.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Applicazione di stili agli elementi dell'interfaccia utente  
 Molti degli elementi nel form di immissione dati hanno un aspetto simile, che significa che hanno impostazioni identiche per alcune delle loro proprietà. Anziché impostare separatamente i relativi attributi, Usa il codice XAML precedente <xref:System.Windows.Style> elementi per definire le impostazioni delle proprietà standard per le classi di elementi. Questo approccio riduce la complessità del controllo e consente di modificare l'aspetto di più elementi tramite un unico attributo di stile.  
  
 Il <xref:System.Windows.Style> gli elementi sono contenuti nel <xref:System.Windows.Controls.Grid> dell'elemento <xref:System.Windows.FrameworkElement.Resources%2A> proprietà, possono essere utilizzati da tutti gli elementi nel controllo. Se è denominato uno stile, applicarlo a un elemento tramite l'aggiunta di un <xref:System.Windows.Style> impostato su nome dello stile. Gli stili che non sono denominati diventano lo stile predefinito per l'elemento. Per ulteriori informazioni su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stili, vedere [stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Il codice XAML seguente viene illustrata la <xref:System.Windows.Style> elementi per il controllo composito. Per visualizzare come gli stili vengono applicati agli elementi, vedere il codice XAML precedente. Ad esempio, l'ultima <xref:System.Windows.Controls.TextBlock> elemento ha il `inlineText` stile e l'ultimo <xref:System.Windows.Controls.TextBox> elemento utilizza lo stile predefinito.  
  
 In Mycontrol1, aggiungere il codice XAML seguente subito dopo il <xref:System.Windows.Controls.Grid> elemento iniziale.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Aggiunta dei pulsanti OK e Cancel  
 Gli elementi finali sul controllo composito sono il **OK** e **Annulla** <xref:System.Windows.Controls.Button> elementi che occupano le prime due colonne dell'ultima riga del <xref:System.Windows.Controls.Grid>. Questi elementi utilizzano un gestore eventi comune, `ButtonClicked`e il valore predefinito <xref:System.Windows.Controls.Button> stile definito nel codice XAML precedente.  
  
 In Mycontrol1, aggiungere il seguente codice XAML dopo l'ultimo <xref:System.Windows.Controls.TextBox> elemento. Il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] parte del controllo composito è stata completata.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Implementazione del file code-behind  
 Il file code-behind, MyControl1.xaml.cs, implementate tre attività essenziali:
  
1.  Gestisce l'evento che si verifica quando l'utente fa clic su uno dei pulsanti.  
  
2.  Recupera i dati di <xref:System.Windows.Controls.TextBox> elementi e il pacchetto in un oggetto argomento dell'evento personalizzato.  
  
3.  Genera l'oggetto personalizzato `OnButtonClick` evento, che notifica all'host che l'utente ha terminato e passa i dati all'host.  
  
 Il controllo espone inoltre un numero di proprietà di colore e tipo di carattere che consentono di modificare l'aspetto. A differenza di <xref:System.Windows.Forms.Integration.WindowsFormsHost> classe, che consente di ospitare un controllo Windows Form, il <xref:System.Windows.Forms.Integration.ElementHost> classe espone il controllo <xref:System.Windows.Controls.Panel.Background%2A> solo per la proprietà. Per mantenere le similitudini tra questo esempio di codice e l'esempio illustrato in [procedura dettagliata: Hosting di controlli Windows Form composito in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md), il controllo espone le proprietà rimanenti direttamente.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>Struttura di base del file code-behind  
 Il file code-behind è costituito da un singolo spazio dei nomi, `MyControls`, che conterrà due classi, `MyControl1` e `MyControlEventArgs`.  
  
```  
namespace MyControls  
{  
  public partial class MyControl1 : Grid  
  {  
    //...  
  }  
  public class MyControlEventArgs : EventArgs  
  {  
    //...  
  }  
}  
```  
  
 La prima classe `MyControl1`, è una classe parziale contenente il codice che implementa la funzionalità del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] definiti in MyControl1. Xaml. Quando viene analizzato Mycontrol1, il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene convertito nella stessa classe parziale, e vengono unite le due classi parziali per formare il controllo compilato. Per questo motivo, il nome della classe nel file code-behind deve corrispondere al nome della classe assegnato a MyControl1.xaml e deve ereditare dall'elemento radice del controllo. La seconda classe, `MyControlEventArgs`, è una classe di argomenti di evento che viene utilizzata per inviare i dati all'host.  
  
 Aprire MyControl1.xaml.cs. Modificare la dichiarazione di classe esistente in modo che abbia il seguente nome eredita da <xref:System.Windows.Controls.Grid>.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Inizializzazione del controllo  
 Il codice seguente implementa alcune attività di base:  
  
-   Dichiara un evento privato, `OnButtonClick`e del delegato associato, `MyControlEventHandler`.  
  
-   Crea diverse variabili globali private che archiviano i dati dell'utente. Questi dati vengono esposti tramite le proprietà corrispondenti.  
  
-   Implementa un gestore, `Init`, per il controllo <xref:System.Windows.FrameworkElement.Loaded> evento. Questo gestore inizializza le variabili globali assegnando loro i valori definiti in MyControl1.xaml. A tale scopo, viene utilizzato il <xref:System.Windows.FrameworkElement.Name%2A> assegnato a un tipico <xref:System.Windows.Controls.TextBlock> elemento `nameLabel`, per accedere alle impostazioni di proprietà dell'elemento.  
  
 Eliminare il costruttore esistente e aggiungere il codice seguente per la `MyControl1` classe.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Gestione degli eventi clic dei pulsanti  
 L'utente indica che l'attività di immissione dati è stata completata, fare clic su uno di **OK** pulsante o **Annulla** pulsante. Entrambi i pulsanti utilizzano lo stesso <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi, `ButtonClicked`. Entrambi i pulsanti hanno un nome, `btnOK` o `btnCancel`, che consente al gestore di determinare quale pulsante è stato scelto dall'analisi del valore di `sender` argomento. Il gestore esegue le operazioni seguenti:  
  
-   Crea un `MyControlEventArgs` oggetto che contiene i dati di <xref:System.Windows.Controls.TextBox> elementi.  
  
-   Se l'utente ha fatto clic il **Annulla** pulsante, imposta il `MyControlEventArgs` dell'oggetto `IsOK` proprietà `false`.  
  
-   Genera il `OnButtonClick` evento per indicare all'host che l'utente termina e il passaggio dei dati raccolti.  
  
 Aggiungere il codice seguente per il `MyControl1` classe, dopo il `Init` metodo.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Creazione di proprietà  
 Il resto della classe espone semplicemente proprietà che corrispondono alle variabili globali precedentemente illustrate. Quando una proprietà viene modificata, la funzione di accesso impostata modifica l'aspetto del controllo cambiando le proprietà degli elementi corrispondenti e aggiornando le variabili globali sottostanti.  
  
 Aggiungere il codice seguente per la `MyControl1` classe.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Invio di dati di nuovo all'host  
 Il componente finale nel file è la `MyControlEventArgs` classe, che viene utilizzato per inviare i dati raccolti all'host.  
  
 Aggiungere il codice seguente per il `MyControls` dello spazio dei nomi. L'implementazione è semplice e non verrà ulteriormente illustrata.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Compilare la soluzione. La compilazione genererà una DLL denominata MyControls.dll.  
  
<a name="winforms_host_section"></a>   
## <a name="implementing-the-windows-forms-host-application"></a>Implementazione dell'applicazione host Windows Forms  
 Windows Form ospitare l'applicazione utilizza un <xref:System.Windows.Forms.Integration.ElementHost> oggetto per ospitare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito. Gli handle di applicazioni di `OnButtonClick` eventi per ricevere i dati dal controllo composito. L'applicazione presenta anche un insieme di pulsanti di opzione che è possibile utilizzare per modificare l'aspetto del controllo. La figura seguente mostra l'applicazione.  
  
 ![Windows Form che ospita un controllo Avalon](../../../../docs/framework/wpf/advanced/media/wfhost.png "WFHost")  
Controllo composito WPF ospitato in un'applicazione Windows Forms  
  
### <a name="creating-the-project"></a>Creazione del progetto  
 Per avviare il progetto:  
  
1.  Avviare [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]e aprire il **nuovo progetto** la finestra di dialogo.  
  
2.  In Visual c# e la categoria di Windows, selezionare il **Windows Forms Application** modello.  
  
3.  Assegnare il nome `WFHost` al nuovo progetto.  
  
4.  Come percorso, specificare la stessa cartella di livello superiore che contiene il progetto MyControls.  
  
5.  Fare clic su **OK** per creare il progetto.  
  
 È inoltre necessario aggiungere i riferimenti alla DLL contenente `MyControl1` e altri assembly.  
  
1.  Il nome del progetto in Esplora soluzioni e scegliere **Aggiungi riferimento**.  
  
2.  Fare clic su di **Sfoglia** scheda e passare alla cartella che contiene MyControls. In questa procedura dettagliata la cartella è MyControls\bin\Debug.  
  
3.  Selezionare MyControls e quindi fare clic su **OK**.  
  
4.  Aggiungere riferimenti agli assembly indicati di seguito.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   System.Xaml  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
### <a name="implementing-the-user-interface-for-the-application"></a>Implementazione dell'interfaccia utente per l'applicazione  
 L'interfaccia utente per l'applicazione Windows Form contiene vari controlli per interagire con il controllo composito WPF.  
  
1.  Aprire Form1 in Progettazione Windows Form.  
  
2.  Ingrandire il form per cui inserire i controlli.  
  
3.  Nell'angolo superiore destro del form, aggiungere un <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> controllo per contenere il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito.  
  
4.  Aggiungere il seguente <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> controlli al form.  
  
    |nome|Testo|  
    |----------|----------|  
    |groupBox1|Colore di sfondo|  
    |groupBox2|Colore primo piano|  
    |groupBox3|Dimensione carattere|  
    |groupBox4|Famiglia di caratteri|  
    |groupBox5|Stile|  
    |groupBox6|Spessore carattere|  
    |groupBox7|Dati dal controllo|  
  
5.  Aggiungere il seguente <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> controlli per il <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> controlli.  
  
    |GroupBox|nome|Testo|  
    |--------------|----------|----------|  
    |groupBox1|radioBackgroundOriginal|Originale|  
    |groupBox1|radioBackgroundLightGreen|LightGreen|  
    |groupBox1|radioBackgroundLightSalmon|LightSalmon|  
    |groupBox2|radioForegroundOriginal|Originale|  
    |groupBox2|radioForegroundRed|Rosso|  
    |groupBox2|radioForegroundYellow|Giallo|  
    |groupBox3|radioSizeOriginal|Originale|  
    |groupBox3|radioSizeTen|10|  
    |groupBox3|radioSizeTwelve|12|  
    |groupBox4|radioFamilyOriginal|Originale|  
    |groupBox4|radioFamilyTimes|Times New Roman|  
    |groupBox4|radioFamilyWingDings|WingDings|  
    |groupBox5|radioStyleOriginal|Normale|  
    |groupBox5|radioStyleItalic|Corsivo|  
    |groupBox6|radioWeightOriginal|Originale|  
    |groupBox6|radioWeightBold|Grassetto|  
  
6.  Aggiungere il seguente <xref:System.Windows.Forms.Label?displayProperty=nameWithType> controlla all'ultimo <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>. Questi controlli visualizzano i dati restituiti dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito.  
  
    |GroupBox|nome|Testo|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Nome:|  
    |groupBox7|lblAddress|Indirizzo:|  
    |groupBox7|lblCity|Città:|  
    |groupBox7|lblState|Stato:|  
    |groupBox7|lblZip|CAP:|  
  
### <a name="initializing-the-form"></a>Inizializzazione del form  
 Il codice di hosting viene in genere implementato il formato <xref:System.Windows.Forms.Form.Load> gestore dell'evento. Il codice seguente illustra il <xref:System.Windows.Forms.Form.Load> gestore dell'evento, un gestore per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito <xref:System.Windows.FrameworkElement.Loaded> evento e le dichiarazioni di diverse variabili globali utilizzate in un secondo momento.  
  
 In Progettazione Windows Form, fare doppio clic sul form per creare un <xref:System.Windows.Forms.Form.Load> gestore dell'evento. All'inizio di Form1. cs, aggiungere le seguenti `using` istruzioni.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Sostituire il contenuto dell'oggetto esistente `Form1` classe con il codice seguente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 Il `Form1_Load` metodo nel codice precedente viene illustrata la procedura generale per l'hosting di un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo:  
  
1.  Creare un nuovo <xref:System.Windows.Forms.Integration.ElementHost> oggetto.  
  
2.  Impostare il controllo <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>.  
  
3.  Aggiungere il <xref:System.Windows.Forms.Integration.ElementHost> controllo il <xref:System.Windows.Forms.Panel> del controllo <xref:System.Windows.Forms.Control.Controls%2A> insieme.  
  
4.  Creare un'istanza di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo.  
  
5.  Ospitare il controllo composito nel form assegnando il controllo per il <xref:System.Windows.Forms.Integration.ElementHost> del controllo <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> proprietà.  
  
 Le due righe rimanenti nel `Form1_Load` metodo associano i gestori per due eventi di controllo:  
  
-   `OnButtonClick` è un evento personalizzato che viene generato dal controllo composito quando l'utente sceglie il **OK** oppure **Annulla** pulsante. Si gestisce l'evento per ottenere la risposta dell'utente e per raccogliere i dati specificati dall'utente.  
  
-   <xref:System.Windows.FrameworkElement.Loaded> è un evento standard che viene generato da un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllare quando è stato caricato completamente. L'evento è usato qui poiché nell'esempio è necessario inizializzare diverse variabili globali usando le proprietà del controllo. Al momento nel formato <xref:System.Windows.Forms.Form.Load> evento, il controllo non è stato caricato completamente e tali valori sono ancora impostati su `null`. È necessario attendere fino a quando il controllo <xref:System.Windows.FrameworkElement.Loaded> evento si verifica prima di poter accedere a tali proprietà.  
  
 Il <xref:System.Windows.FrameworkElement.Loaded> gestore dell'evento è illustrato nel codice precedente. Il `OnButtonClick` gestore è descritto nella sezione successiva.  
  
### <a name="handling-onbuttonclick"></a>Gestione dell'evento OnButtonClick  
 Il `OnButtonClick` evento si verifica quando l'utente sceglie il **OK** o **Annulla** pulsante.  
  
 Il gestore eventi controlla dell'argomento dell'evento `IsOK` campo per determinare quale pulsante è stato fatto clic. Il `lbl` *dati* variabili corrispondano per il <xref:System.Windows.Forms.Label> controlli descritti in precedenza. Se l'utente sceglie il **OK** pulsante, i dati del controllo <xref:System.Windows.Controls.TextBox> controlli viene assegnato alla corrispondente <xref:System.Windows.Forms.Label> controllo. Se l'utente fa clic **Annulla**, <xref:System.Windows.Forms.Label.Text%2A> valori vengono impostati per le stringhe predefinite.  
  
 Aggiungere il seguente pulsante fare clic su codice del gestore eventi per il `Form1` classe.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Compilare ed eseguire l'applicazione. Aggiungere del testo nel controllo composito WPF e quindi fare clic su **OK**. Il testo viene visualizzato nelle etichette. A questo punto, il codice non è stato aggiunto ai pulsanti di opzione.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Modifica dell'aspetto del controllo  
 Il <xref:System.Windows.Forms.RadioButton> controlli nel form consentirà all'utente di modificare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , nonché molte proprietà dei caratteri di colori di sfondo e primo piano di controllo composito. Il colore di sfondo è esposto dal <xref:System.Windows.Forms.Integration.ElementHost> oggetto. Le proprietà restanti sono esposte come proprietà personalizzate del controllo.  
  
 Fare doppio clic su ogni <xref:System.Windows.Forms.RadioButton> controllo sul form per creare <xref:System.Windows.Forms.RadioButton.CheckedChanged> gestori eventi. Sostituire il <xref:System.Windows.Forms.RadioButton.CheckedChanged> gestori di eventi con il codice seguente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Compilare ed eseguire l'applicazione. Fare clic sui vari pulsanti di opzione per vedere l'effetto sul controllo composito WPF.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Procedura dettagliata: hosting di controlli compositi 3D di WPF in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
