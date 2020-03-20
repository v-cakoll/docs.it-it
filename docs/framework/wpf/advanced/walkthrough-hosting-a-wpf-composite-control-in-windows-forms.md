---
title: Ospitare un controllo composito WPF in Windows FormHost a WPF composite control in Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: e3326f654e05ef7d487a76f076f8ad0da3637096
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187238"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Procedura dettagliata: hosting di controlli compositi di WPF in Windows Form
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si dispone di un investimento sostanziale nel codice Windows Form, può essere più efficace estendere l'applicazione Windows Form esistente con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] anziché riscriverla da zero. Uno scenario comune è quando si desidera incorporare uno o più controlli implementati con all'interno dell'applicazione Windows Form.A common scenario is when you want to embed one or more controls implemented with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] within your Windows Forms application. Per ulteriori informazioni sulla personalizzazione dei controlli WPFWPF, vedere [Personalizzazione dei controlli](../controls/control-customization.md).  
  
 In questa procedura dettagliata viene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] illustrato un'applicazione che ospita un controllo composito per eseguire l'immissione di dati in un'applicazione Windows Form.This walkthrough steps you through an application that hosts a composite control to perform data-entry in a Windows Forms application. Il controllo composito è compresso in una DLL. Questa procedura generale può essere estesa ad applicazioni e controlli più complessi. Questa procedura dettagliata è progettata per essere quasi identica nell'aspetto e nella funzionalità di Walkthrough: Hosting di [un controllo composito Windows Form in WPF.](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md) La principale differenza è che lo scenario di hosting è invertito.  
  
 La procedura guidata è suddivisa in due sezioni. La prima sezione descrive brevemente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l'implementazione del controllo composito. Nella seconda sezione viene illustrato in dettaglio come ospitare il controllo composito in un'applicazione Windows Form, ricevere eventi dal controllo e accedere ad alcune delle proprietà del controllo.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
- Implementazione del controllo composito WPF.  
  
- Implementazione dell'applicazione host Windows Forms.  
  
 Per un elenco di codice completo delle attività illustrate in questa procedura dettagliata, vedere Hosting di [un controllo composito WPF in Esempio di Windows Form](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl).  
  
## <a name="prerequisites"></a>Prerequisites  

Per completare la procedura dettagliata, è necessario Visual Studio.  
  
## <a name="implementing-the-wpf-composite-control"></a>Implementazione del controllo composito WPF  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito utilizzato in questo esempio è un semplice modulo di immissione dati che accetta il nome e l'indirizzo dell'utente. Quando l'utente fa clic su uno dei due pulsanti per indicare che l'attività è completata, il controllo genera un evento personalizzato per restituire tali informazioni all'host. La figura seguente mostra il controllo sottoposto a rendering.

 L'immagine seguente mostra un controllo composito WPF:The following image shows a WPFWPF composite control:

 ![Screenshot che mostra un controllo WPF semplice.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-presentation-foundation-composite-control.png)  
  
### <a name="creating-the-project"></a>Creazione del progetto  
 Per avviare il progetto:  
  
1. Avviare Visual Studio e aprire la finestra di dialogo **Nuovo progetto.**  
  
2. In Visual C, e la categoria Windows, selezionare il modello Di libreria di controlli **utente WPF.**  
  
3. Assegnare il nome `MyControls` al nuovo progetto.  
  
4. Per la posizione, specificare una cartella di `WindowsFormsHostingWpfControl`primo livello denominata in modo pratico, ad esempio . Successivamente, si immetterà l'applicazione host in questa cartella.  
  
5. Fare clic su **OK** per creare il progetto. Il progetto predefinito contiene `UserControl1`un singolo controllo denominato .  
  
6. In Esplora soluzioni rinominare `UserControl1` `MyControl1`in .  
  
 Il progetto dovrebbe includere riferimenti alle DLL di sistema seguenti. Se alcune di queste DLL non sono incluse per impostazione predefinita, aggiungerle al progetto.  
  
- PresentationCore  
  
- PresentationFramework  
  
- Sistema  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>Creazione dell'interfaccia utente  
 L'oggetto [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] per il [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]controllo composito viene implementato con . Il controllo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] composito è costituito da cinque <xref:System.Windows.Controls.TextBox> elementi. A <xref:System.Windows.Controls.TextBox> ogni elemento <xref:System.Windows.Controls.TextBlock> è associato un elemento che funge da etichetta. Ci sono <xref:System.Windows.Controls.Button> due elementi in basso, **OK** e **Annulla**. Quando l'utente fa clic su uno di questi pulsanti, il controllo genera un evento personalizzato per restituire le informazioni all'host.  
  
#### <a name="basic-layout"></a>Layout di base  
 I [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] vari elementi sono <xref:System.Windows.Controls.Grid> contenuti in un elemento. È possibile <xref:System.Windows.Controls.Grid> utilizzare per disporre il contenuto del controllo composito in modo molto simile all'utilizzo di un `Table` elemento in HTML. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ha anche <xref:System.Windows.Documents.Table> un <xref:System.Windows.Controls.Grid> elemento, ma è più leggero e più adatto per semplici attività di layout.  
  
 Il codice XAML seguente illustra il layout di base. Questo codice XAML definisce la struttura complessiva del controllo specificando <xref:System.Windows.Controls.Grid> il numero di colonne e righe nell'elemento.  
  
 In MyControl1.xaml sostituire il codice XAML esistente con il seguente.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>Aggiunta di elementi TextBlock e TextBox alla griglia  
 Per posizionare un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento nella griglia, <xref:System.Windows.Controls.Grid.RowProperty> <xref:System.Windows.Controls.Grid.ColumnProperty> impostare gli attributi e dell'elemento sul numero di riga e di colonna appropriato. Ricordare che la numerazione di righe e colonne e in base zero. È possibile fare in modo che <xref:System.Windows.Controls.Grid.ColumnSpanProperty> un elemento si estenda su più colonne impostandone l'attributo. Per ulteriori <xref:System.Windows.Controls.Grid> informazioni sugli elementi, consultate [Creare un elemento Grid.](../controls/how-to-create-a-grid-element.md)  
  
 Il codice XAML seguente mostra <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBlock> gli elementi <xref:System.Windows.Controls.Grid.RowProperty> <xref:System.Windows.Controls.Grid.ColumnProperty> e del controllo composito con i relativi attributi e , che sono impostati per posizionare correttamente gli elementi nella griglia.  
  
 In MyControl1.xaml aggiungi il codice <xref:System.Windows.Controls.Grid> XAML seguente all'interno dell'elemento.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Applicazione di stili agli elementi dell'interfaccia utente  
 Molti degli elementi nel form di immissione dati hanno un aspetto simile, che significa che hanno impostazioni identiche per alcune delle loro proprietà. Anziché impostare gli attributi di ogni <xref:System.Windows.Style> elemento separatamente, il codice XAML precedente usa gli elementi per definire le impostazioni delle proprietà standard per le classi di elementi. Questo approccio riduce la complessità del controllo e consente di modificare l'aspetto di più elementi tramite un unico attributo di stile.  
  
 Gli <xref:System.Windows.Style> elementi sono <xref:System.Windows.Controls.Grid> contenuti nella <xref:System.Windows.FrameworkElement.Resources%2A> proprietà dell'elemento, in modo che possano essere utilizzati da tutti gli elementi nel controllo. Se uno stile è denominato, è possibile <xref:System.Windows.Style> applicarlo a un elemento aggiungendo un set di elementi al nome dello stile. Gli stili che non sono denominati diventano lo stile predefinito per l'elemento. Per ulteriori [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] informazioni sugli stili, consultate [Applicazione di stili e modelli.](../../../desktop-wpf/fundamentals/styles-templates-overview.md)  
  
 Il codice XAML <xref:System.Windows.Style> seguente mostra gli elementi per il controllo composito. Per visualizzare come gli stili vengono applicati agli elementi, vedere il codice XAML precedente. Ad esempio, <xref:System.Windows.Controls.TextBlock> l'ultimo `inlineText` elemento ha <xref:System.Windows.Controls.TextBox> lo stile e l'ultimo elemento utilizza lo stile predefinito.  
  
 In MyControl1.xaml aggiungere il codice <xref:System.Windows.Controls.Grid> XAML seguente subito dopo l'elemento iniziale.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Aggiunta dei pulsanti OK e Cancel  
 Gli elementi finali nel controllo composito sono gli elementi **OK** e **Cancel,** <xref:System.Windows.Controls.Button> che occupano le prime due colonne dell'ultima riga dell'oggetto <xref:System.Windows.Controls.Grid>. Questi elementi utilizzano un `ButtonClicked`gestore <xref:System.Windows.Controls.Button> eventi comune, , e lo stile predefinito definito nel codice XAML precedente.  
  
 In MyControl1.xaml aggiungere il codice <xref:System.Windows.Controls.TextBox> XAML seguente dopo l'ultimo elemento. La [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] parte del controllo composito è ora completa.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Implementazione del file code-behind  
 Il file code-behind, MyControl1.xaml.cs, implementa tre attività essenziali:The code-behind file, MyControl1.xaml.cs, implements three essential tasks:
  
1. Gestisce l'evento che si verifica quando l'utente fa clic su uno dei pulsanti.  
  
2. Recupera i dati <xref:System.Windows.Controls.TextBox> dagli elementi e li comprime in un oggetto argomento dell'evento personalizzato.  
  
3. Genera l'evento personalizzato, `OnButtonClick` che notifica all'host che l'utente è terminato e passa i dati all'host.  
  
 Il controllo espone inoltre un numero di proprietà di colore e tipo di carattere che consentono di modificare l'aspetto. A <xref:System.Windows.Forms.Integration.WindowsFormsHost> differenza della classe , utilizzata per ospitare <xref:System.Windows.Forms.Integration.ElementHost> un controllo Windows <xref:System.Windows.Controls.Panel.Background%2A> Form, la classe espone solo la proprietà del controllo. Per mantenere la somiglianza tra questo esempio di codice e l'esempio illustrato in Procedura dettagliata: hosting di [un controllo composito Windows Form in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md), il controllo espone direttamente le proprietà rimanenti.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>Struttura di base del file code-behind  
 Il file code-behind è costituito da un singolo spazio dei nomi, `MyControls`, che conterrà due classi e `MyControl1` `MyControlEventArgs`.  
  
```csharp  
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
  
 La prima `MyControl1`classe, , è una classe parziale [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] contenente il codice che implementa la funzionalità del definito in MyControl1.xaml. Quando MyControl1.xaml viene analizzato, l'oggetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene convertito nella stessa classe parziale e le due classi parziali vengono unite per formare il controllo compilato. Per questo motivo, il nome della classe nel file code-behind deve corrispondere al nome della classe assegnato a MyControl1.xaml e deve ereditare dall'elemento radice del controllo. La seconda `MyControlEventArgs`classe, , è una classe di argomenti dell'evento utilizzata per inviare i dati all'host.  
  
 Aprire MyControl1.xaml.cs. Modificare la dichiarazione di classe esistente in modo <xref:System.Windows.Controls.Grid>che abbia il nome seguente ed erediti da .  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Inizializzazione del controllo  
 Il codice seguente implementa alcune attività di base:  
  
- Dichiara un evento `OnButtonClick`privato, , e `MyControlEventHandler`il delegato associato, .  
  
- Crea diverse variabili globali private che archiviano i dati dell'utente. Questi dati vengono esposti tramite le proprietà corrispondenti.  
  
- Implementa un `Init`gestore, , <xref:System.Windows.FrameworkElement.Loaded> per l'evento del controllo. Questo gestore inizializza le variabili globali assegnando loro i valori definiti in MyControl1.xaml. A tale scopo, <xref:System.Windows.FrameworkElement.Name%2A> viene utilizzato <xref:System.Windows.Controls.TextBlock> l'oggetto assegnato a un elemento tipico, `nameLabel`, per accedere alle impostazioni delle proprietà dell'elemento.  
  
 Eliminare il costruttore esistente e `MyControl1` aggiungere il codice seguente alla classe.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Gestione degli eventi clic dei pulsanti  
 L'utente indica che l'attività di immissione dati è terminata facendo clic sul pulsante **OK** o **Annulla.** Entrambi i pulsanti utilizzano lo stesso <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi, `ButtonClicked`. Entrambi i pulsanti `btnOK` `btnCancel`hanno un nome, o , che consente al gestore di determinare su quale pulsante è stato fatto clic esaminando il valore dell'argomento `sender` . Il gestore esegue le operazioni seguenti:  
  
- Crea `MyControlEventArgs` un oggetto che contiene <xref:System.Windows.Controls.TextBox> i dati degli elementi.  
  
- Se l'utente ha fatto clic `MyControlEventArgs` sul `IsOK` pulsante `false` **Annulla,** imposta la proprietà dell'oggetto su .  
  
- Genera `OnButtonClick` l'evento per indicare all'host che l'utente è terminato e restituisce i dati raccolti.  
  
 Aggiungere il codice `MyControl1` seguente alla `Init` classe, dopo il metodo.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Creazione di proprietà  
 Il resto della classe espone semplicemente proprietà che corrispondono alle variabili globali precedentemente illustrate. Quando una proprietà viene modificata, la funzione di accesso impostata modifica l'aspetto del controllo cambiando le proprietà degli elementi corrispondenti e aggiornando le variabili globali sottostanti.  
  
 Aggiungere il codice `MyControl1` seguente alla classe.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Invio di dati di nuovo all'host  
 Il componente finale nel `MyControlEventArgs` file è la classe , che viene utilizzata per inviare i dati raccolti all'host.  
  
 Aggiungere il codice `MyControls` seguente allo spazio dei nomi. L'implementazione è semplice e non verrà ulteriormente illustrata.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Compilare la soluzione. La compilazione genererà una DLL denominata MyControls.dll.  
  
<a name="winforms_host_section"></a>
## <a name="implementing-the-windows-forms-host-application"></a>Implementazione dell'applicazione host Windows Forms  
 L'applicazione host Windows <xref:System.Windows.Forms.Integration.ElementHost> Form utilizza [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un oggetto per ospitare il controllo composito. L'applicazione `OnButtonClick` gestisce l'evento per ricevere i dati dal controllo composito. L'applicazione presenta anche un insieme di pulsanti di opzione che è possibile utilizzare per modificare l'aspetto del controllo. La figura seguente mostra l'applicazione.  

L'immagine seguente mostra un controllo composito WPF ospitato in un'applicazione Windows Form"The following image shows a WPF composite control hosted in a Windows Forms application"  

 ![Scteenshot che mostra un controllo Avalon di Windows Form Hosting.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>Creazione del progetto  
 Per avviare il progetto:  
  
1. Avviare Visual Studio e aprire la finestra di dialogo **Nuovo progetto.**  
  
2. In Visual Ce e la categoria Windows, selezionare il modello **applicazione Windows Form.**  
  
3. Assegnare il nome `WFHost` al nuovo progetto.  
  
4. Come percorso, specificare la stessa cartella di livello superiore che contiene il progetto MyControls.  
  
5. Fare clic su **OK** per creare il progetto.  
  
 È inoltre necessario aggiungere riferimenti alla `MyControl1` DLL che contiene e altri assembly.  
  
1. Fare clic con il pulsante destro del mouse sul nome del progetto in Esplora soluzioni e scegliere **Aggiungi riferimento**.  
  
2. Fare clic sulla scheda **Sfoglia** e individuare la cartella contenente MyControls.dll. In questa procedura dettagliata la cartella è MyControls\bin\Debug.  
  
3. Selezionare MyControls.dll, quindi fare clic su **OK**.  
  
4. Aggiungere riferimenti agli assembly indicati di seguito.  
  
    - PresentationCore  
  
    - PresentationFramework  
  
    - System.Xaml  
  
    - WindowsBase  
  
    - WindowsFormsIntegration  
  
### <a name="implementing-the-user-interface-for-the-application"></a>Implementazione dell'interfaccia utente per l'applicazione  
 L'interfaccia utente per l'applicazione Windows Form contiene vari controlli per interagire con il controllo composito WPF.  
  
1. Aprire Form1 in Progettazione Windows Form.  
  
2. Ingrandire il form per cui inserire i controlli.  
  
3. Nell'angolo superiore destro del form <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> aggiungere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo per contenere il controllo composito.  
  
4. Aggiungere i <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> controlli seguenti al form.  
  
    |Nome|Text|  
    |----------|----------|  
    |groupBox1|Colore di sfondo|  
    |groupBox2|Colore primo piano|  
    |groupBox3|Dimensione carattere|  
    |groupBox4|Famiglia di caratteri|  
    |groupBox5|Stile|  
    |groupBox6|Spessore carattere|  
    |groupBox7|Dati dal controllo|  
  
5. Aggiungere i <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> seguenti <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> controlli ai controlli.  
  
    |GroupBox|Nome|Text|  
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
  
6. Aggiungere i <xref:System.Windows.Forms.Label?displayProperty=nameWithType> seguenti controlli <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>all'ultimo file . Questi controlli visualizzano i [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dati restituiti dal controllo composito.  
  
    |GroupBox|Nome|Text|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Nome:|  
    |groupBox7|lblAddress|Indirizzo:|  
    |groupBox7|lblCity|Città:|  
    |groupBox7|lblState|Stato:|  
    |groupBox7|lblZip|CAP:|  
  
### <a name="initializing-the-form"></a>Inizializzazione del form  
 In genere si implementa il codice <xref:System.Windows.Forms.Form.Load> di hosting nel gestore eventi del form. Il codice seguente <xref:System.Windows.Forms.Form.Load> mostra il gestore [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventi, <xref:System.Windows.FrameworkElement.Loaded> un gestore per l'evento del controllo composito e le dichiarazioni per diverse variabili globali utilizzate in un secondo momento.  
  
 In Progettazione Windows Form fare doppio clic <xref:System.Windows.Forms.Form.Load> sul form per creare un gestore eventi. Nella parte superiore di Form1.cs `using` aggiungere le istruzioni seguenti.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Sostituire il contenuto `Form1` della classe esistente con il codice seguente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 Il `Form1_Load` metodo nel codice precedente mostra la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] procedura generale per ospitare un controllo:The method in the preceding code shows the general procedure for hosting a control:  
  
1. Creare un nuovo oggetto <xref:System.Windows.Forms.Integration.ElementHost>.  
  
2. Impostare la <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>del controllo su .  
  
3. Aggiungere <xref:System.Windows.Forms.Integration.ElementHost> il controllo <xref:System.Windows.Forms.Panel> alla <xref:System.Windows.Forms.Control.Controls%2A> raccolta del controllo.  
  
4. Creare un'istanza [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del controllo.  
  
5. Ospitare il controllo composito nel form <xref:System.Windows.Forms.Integration.ElementHost> assegnando <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> il controllo alla proprietà del controllo.  
  
 Le due righe `Form1_Load` rimanenti nel metodo collegano i gestori a due eventi di controllo:The remaining two lines in the method attach handlers to two control events:  
  
- `OnButtonClick`è un evento personalizzato generato dal controllo composito quando l'utente fa clic sul pulsante **OK** o **Annulla.** Si gestisce l'evento per ottenere la risposta dell'utente e per raccogliere i dati specificati dall'utente.  
  
- <xref:System.Windows.FrameworkElement.Loaded>è un evento standard generato [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] da un controllo quando è completamente caricato. L'evento è usato qui poiché nell'esempio è necessario inizializzare diverse variabili globali usando le proprietà del controllo. Al momento dell'evento <xref:System.Windows.Forms.Form.Load> del form, il controllo non è completamente `null`caricato e tali valori sono ancora impostati su . È necessario attendere che si <xref:System.Windows.FrameworkElement.Loaded> verifichi l'evento del controllo prima di poter accedere a tali proprietà.  
  
 Il <xref:System.Windows.FrameworkElement.Loaded> gestore eventi viene visualizzato nel codice precedente. Il `OnButtonClick` gestore viene illustrato nella sezione successiva.  
  
### <a name="handling-onbuttonclick"></a>Gestione dell'evento OnButtonClick  
 L'evento `OnButtonClick` si verifica quando l'utente fa clic sul pulsante **OK** o **Annulla.**  
  
 Il gestore eventi controlla `IsOK` il campo dell'argomento dell'evento per determinare su quale pulsante è stato fatto clic. Le `lbl`variabili *di* <xref:System.Windows.Forms.Label> dati corrispondono ai controlli descritti in precedenza. Se l'utente fa clic sul pulsante **OK,** i dati dei controlli del <xref:System.Windows.Controls.TextBox> controllo vengono assegnati al controllo corrispondente. <xref:System.Windows.Forms.Label> Se l'utente **Cancel**fa <xref:System.Windows.Forms.Label.Text%2A> clic su Annulla , i valori vengono impostati sulle stringhe predefinite.  
  
 Aggiungere il codice del gestore `Form1` eventi Click del pulsante seguente alla classe.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Compilare ed eseguire l'applicazione. Aggiungere del testo nel controllo composito WPFWPF e quindi fare clic su **OK**. Il testo viene visualizzato nelle etichette. A questo punto, il codice non è stato aggiunto ai pulsanti di opzione.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Modifica dell'aspetto del controllo  
 I <xref:System.Windows.Forms.RadioButton> controlli nel form consentiranno all'utente di modificare i [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] colori di primo piano e di sfondo del controllo composito, nonché diverse proprietà del carattere. Il colore di sfondo <xref:System.Windows.Forms.Integration.ElementHost> viene esposto dall'oggetto. Le proprietà restanti sono esposte come proprietà personalizzate del controllo.  
  
 Fare doppio <xref:System.Windows.Forms.RadioButton> clic su ogni <xref:System.Windows.Forms.RadioButton.CheckedChanged> controllo del form per creare gestori eventi. Sostituire <xref:System.Windows.Forms.RadioButton.CheckedChanged> i gestori eventi con il codice seguente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Compilare ed eseguire l'applicazione. Fare clic sui vari pulsanti di opzione per vedere l'effetto sul controllo composito WPF.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettagliata: hosting di controlli compositi 3D di WPF in Windows Form](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
