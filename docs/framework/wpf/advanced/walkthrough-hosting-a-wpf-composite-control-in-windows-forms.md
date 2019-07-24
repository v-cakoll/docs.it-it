---
title: 'Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: bff89f1d81b16c8c66d73901ef951626f6d2cb9e
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400618"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si ha un investimento sostanziale [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] nel codice, può essere più efficace estendere l'applicazione esistente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] anziché riscriverla da zero. Uno scenario comune è quando si desidera incorporare uno o più controlli implementati [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con all'interno del Windows Forms Application. Per ulteriori informazioni sulla personalizzazione dei controlli WPF, vedere [personalizzazione del controllo](../controls/control-customization.md).  
  
 Questa procedura dettagliata illustra un'applicazione che ospita un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito per eseguire l'immissione di dati in un Windows Forms Application. Il controllo composito è compresso in una DLL. Questa procedura generale può essere estesa ad applicazioni e controlli più complessi. Questa procedura dettagliata è progettata per essere pressoché identica per quanto riguarda aspetto [e funzionalità per la procedura dettagliata: Hosting di un controllo Windows Forms composito](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)in WPF. La principale differenza è che lo scenario di hosting è invertito.  
  
 La procedura guidata è suddivisa in due sezioni. Nella prima sezione viene brevemente descritta l'implementazione del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito. La seconda sezione illustra in dettaglio come ospitare il controllo composito in una Windows Forms Application, ricevere eventi dal controllo e accedere ad alcune delle proprietà del controllo.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
- Implementazione del controllo composito WPF.  
  
- Implementazione dell'applicazione host Windows Forms.  
  
 Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [hosting di un controllo composito WPF nell'esempio Windows Forms](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl).  
  
## <a name="prerequisites"></a>Prerequisiti  

Per completare la procedura dettagliata, è necessario Visual Studio.  
  
## <a name="implementing-the-wpf-composite-control"></a>Implementazione del controllo composito WPF  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito usato in questo esempio è un semplice form di immissione dati che accetta il nome e l'indirizzo dell'utente. Quando l'utente fa clic su uno dei due pulsanti per indicare che l'attività è completata, il controllo genera un evento personalizzato per restituire tali informazioni all'host. La figura seguente mostra il controllo sottoposto a rendering. 

 Nell'immagine seguente viene illustrato un controllo composito WPF: 

 ![Screenshot che mostra un semplice controllo WPF.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-presentation-foundation-composite-control.png)  
  
### <a name="creating-the-project"></a>Creazione del progetto  
 Per avviare il progetto:  
  
1. Avviare [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]e aprire la finestra di dialogo **nuovo progetto** .  
  
2. In Visual C# e nella Categoria Windows selezionare il modello **libreria di controlli utente WPF** .  
  
3. Assegnare il nome `MyControls` al nuovo progetto.  
  
4. Per il percorso specificare una cartella di primo livello con un nome appropriato, ad esempio `WindowsFormsHostingWpfControl`. Successivamente, si immetterà l'applicazione host in questa cartella.  
  
5. Fare clic su **OK** per creare il progetto. Il progetto predefinito contiene un solo controllo denominato `UserControl1`.  
  
6. In Esplora soluzioni rinominare `UserControl1` `MyControl1`in.  
  
 Il progetto dovrebbe includere riferimenti alle DLL di sistema seguenti. Se alcune di queste DLL non sono incluse per impostazione predefinita, aggiungerle al progetto.  
  
- PresentationCore  
  
- PresentationFramework  
  
- System  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>Creazione dell'interfaccia utente  
 Per il controllo composito viene implementato con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Il controllo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] composito è costituito da cinque <xref:System.Windows.Controls.TextBox> elementi. A <xref:System.Windows.Controls.TextBox> ogni elemento è associato <xref:System.Windows.Controls.TextBlock> un elemento che funge da etichetta. Nella parte inferiore <xref:System.Windows.Controls.Button> sono presenti due elementi, **OK** e **Cancel**. Quando l'utente fa clic su uno di questi pulsanti, il controllo genera un evento personalizzato per restituire le informazioni all'host.  
  
#### <a name="basic-layout"></a>Layout di base  
 I vari [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi sono contenuti in un <xref:System.Windows.Controls.Grid> elemento. È possibile utilizzare <xref:System.Windows.Controls.Grid> per disporre il contenuto del controllo composito in modo analogo all'utilizzo di un `Table` elemento in HTML. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]dispone anche di <xref:System.Windows.Documents.Table> un elemento, <xref:System.Windows.Controls.Grid> ma è più leggero e più adatto per le semplici attività di layout.  
  
 Il codice XAML seguente illustra il layout di base. Questo codice XAML definisce la struttura complessiva del controllo specificando il numero di colonne e righe nell' <xref:System.Windows.Controls.Grid> elemento.  
  
 In MyControl1.xaml sostituire il codice XAML esistente con il seguente.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>Aggiunta di elementi TextBlock e TextBox alla griglia  
 Per inserire un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento nella griglia, impostare gli attributi <xref:System.Windows.Controls.Grid.RowProperty> e <xref:System.Windows.Controls.Grid.ColumnProperty> dell'elemento sul numero di riga e di colonna appropriato. Ricordare che la numerazione di righe e colonne e in base zero. È possibile fare in modo che un elemento si estenda <xref:System.Windows.Controls.Grid.ColumnSpanProperty> su più colonne impostando il relativo attributo. Per ulteriori informazioni sugli <xref:System.Windows.Controls.Grid> elementi, vedere [creare un elemento Grid](../controls/how-to-create-a-grid-element.md).  
  
 Il codice XAML seguente Mostra gli <xref:System.Windows.Controls.TextBox> elementi e <xref:System.Windows.Controls.TextBlock> del controllo composito con <xref:System.Windows.Controls.Grid.ColumnProperty> i relativi <xref:System.Windows.Controls.Grid.RowProperty> attributi e, impostati per inserire correttamente gli elementi nella griglia.  
  
 In MyControl1. XAML aggiungere il codice XAML seguente all'interno <xref:System.Windows.Controls.Grid> dell'elemento.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Applicazione di stili agli elementi dell'interfaccia utente  
 Molti degli elementi nel form di immissione dati hanno un aspetto simile, che significa che hanno impostazioni identiche per alcune delle loro proprietà. Anziché impostare separatamente gli attributi di ogni elemento, il codice XAML precedente <xref:System.Windows.Style> usa gli elementi per definire le impostazioni delle proprietà standard per le classi di elementi. Questo approccio riduce la complessità del controllo e consente di modificare l'aspetto di più elementi tramite un unico attributo di stile.  
  
 Gli <xref:System.Windows.Style> elementi sono contenuti nella <xref:System.Windows.FrameworkElement.Resources%2A> proprietà <xref:System.Windows.Controls.Grid> dell'elemento, in modo che possano essere usati da tutti gli elementi nel controllo. Se uno stile è denominato, lo si applica a un elemento aggiungendo un <xref:System.Windows.Style> elemento impostato sul nome dello stile. Gli stili che non sono denominati diventano lo stile predefinito per l'elemento. Per altre informazioni sugli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stili, vedere applicazione di stili [e modelli](../controls/styling-and-templating.md).  
  
 Il codice XAML seguente mostra <xref:System.Windows.Style> gli elementi per il controllo composito. Per visualizzare come gli stili vengono applicati agli elementi, vedere il codice XAML precedente. Ad esempio, l'ultimo <xref:System.Windows.Controls.TextBlock> elemento ha lo `inlineText` stile e l'ultimo <xref:System.Windows.Controls.TextBox> elemento usa lo stile predefinito.  
  
 In MyControl1. XAML aggiungere il codice XAML seguente subito dopo l' <xref:System.Windows.Controls.Grid> elemento iniziale.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Aggiunta dei pulsanti OK e Cancel  
 Gli elementi finali del controllo composito sono gli elementi **OK** e **Cancel** <xref:System.Windows.Controls.Button> , che occupano le prime due colonne <xref:System.Windows.Controls.Grid>dell'ultima riga di. Questi elementi usano un gestore eventi comune, `ButtonClicked`, e lo stile <xref:System.Windows.Controls.Button> predefinito definito nel codice XAML precedente.  
  
 In MyControl1. XAML aggiungere il codice XAML seguente dopo l'ultimo <xref:System.Windows.Controls.TextBox> elemento. La [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] parte del controllo composito è ora completata.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Implementazione del file code-behind  
 Il file code-behind, MyControl1.xaml.cs, implementa tre attività essenziali:
  
1. Gestisce l'evento che si verifica quando l'utente fa clic su uno dei pulsanti.  
  
2. Recupera i dati dagli <xref:System.Windows.Controls.TextBox> elementi e li impacchetta in un oggetto argomento dell'evento personalizzato.  
  
3. Genera l'evento `OnButtonClick` personalizzato, che invia una notifica all'host che l'utente ha terminato e passa i dati all'host.  
  
 Il controllo espone inoltre un numero di proprietà di colore e tipo di carattere che consentono di modificare l'aspetto. A differenza della <xref:System.Windows.Forms.Integration.WindowsFormsHost> classe, che viene utilizzata per ospitare un controllo Windows Forms, la <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Controls.Panel.Background%2A> classe espone solo la proprietà del controllo. Per mantenere la somiglianza tra questo esempio di codice e l'esempio illustrato [in procedura dettagliata: L'hosting di un controllo Windows Forms composito in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md), il controllo espone direttamente le proprietà rimanenti.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>Struttura di base del file code-behind  
 Il file code-behind è costituito da un singolo `MyControls`spazio dei nomi,, che conterrà `MyControlEventArgs`due classi, `MyControl1` e.  
  
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
  
 La prima classe, `MyControl1`, è una classe parziale contenente il codice che implementa la funzionalità [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di definita in MyControl1. XAML. Quando MyControl1. XAML viene analizzato, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene convertito nella stessa classe parziale e le due classi parziali vengono unite per formare il controllo compilato. Per questo motivo, il nome della classe nel file code-behind deve corrispondere al nome della classe assegnato a MyControl1.xaml e deve ereditare dall'elemento radice del controllo. La seconda classe, `MyControlEventArgs`, è una classe di argomenti di evento utilizzata per restituire i dati all'host.  
  
 Aprire MyControl1.xaml.cs. Modificare la dichiarazione di classe esistente in modo che abbia il nome seguente ed erediti <xref:System.Windows.Controls.Grid>da.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Inizializzazione del controllo  
 Il codice seguente implementa alcune attività di base:  
  
- Dichiara un evento privato, `OnButtonClick`, e il delegato associato,. `MyControlEventHandler`  
  
- Crea diverse variabili globali private che archiviano i dati dell'utente. Questi dati vengono esposti tramite le proprietà corrispondenti.  
  
- Implementa un gestore, `Init`, per l' <xref:System.Windows.FrameworkElement.Loaded> evento del controllo. Questo gestore inizializza le variabili globali assegnando loro i valori definiti in MyControl1.xaml. A tale scopo, usa l'oggetto <xref:System.Windows.FrameworkElement.Name%2A> assegnato a un elemento <xref:System.Windows.Controls.TextBlock> tipico, `nameLabel`, per accedere alle impostazioni delle proprietà di tale elemento.  
  
 Eliminare il costruttore esistente e aggiungere il codice seguente alla `MyControl1` classe.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Gestione degli eventi clic dei pulsanti  
 L'utente indica che l'attività di immissione dei dati è stata completata facendo clic sul pulsante **OK** o sul pulsante **Annulla** . Entrambi i pulsanti utilizzano lo <xref:System.Windows.Controls.Primitives.ButtonBase.Click> stesso gestore eventi `ButtonClicked`,. Entrambi i pulsanti hanno un nome `btnOK` , `btnCancel`o, che consente al gestore di determinare quale pulsante è stato selezionato esaminando il valore dell' `sender` argomento. Il gestore esegue le operazioni seguenti:  
  
- Crea un `MyControlEventArgs` oggetto che contiene i dati <xref:System.Windows.Controls.TextBox> dagli elementi.  
  
- Se l'utente ha `IsOK` fatto clic sul pulsante **Annulla** , imposta `MyControlEventArgs` la proprietà dell'oggetto `false`su.  
  
- Genera l' `OnButtonClick` evento per indicare all'host che l'utente ha terminato e passa di nuovo i dati raccolti.  
  
 Aggiungere il codice seguente alla `MyControl1` classe, dopo il `Init` metodo.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Creazione di proprietà  
 Il resto della classe espone semplicemente proprietà che corrispondono alle variabili globali precedentemente illustrate. Quando una proprietà viene modificata, la funzione di accesso impostata modifica l'aspetto del controllo cambiando le proprietà degli elementi corrispondenti e aggiornando le variabili globali sottostanti.  
  
 Aggiungere il codice seguente alla `MyControl1` classe.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Invio di dati di nuovo all'host  
 Il componente finale del file è la `MyControlEventArgs` classe, utilizzata per inviare i dati raccolti all'host.  
  
 Aggiungere il codice seguente allo `MyControls` spazio dei nomi. L'implementazione è semplice e non verrà ulteriormente illustrata.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Compilare la soluzione. La compilazione genererà una DLL denominata MyControls.dll.  
  
<a name="winforms_host_section"></a>   
## <a name="implementing-the-windows-forms-host-application"></a>Implementazione dell'applicazione host Windows Forms  
 L'applicazione host Windows Forms usa un <xref:System.Windows.Forms.Integration.ElementHost> oggetto per ospitare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito. L'applicazione gestisce l' `OnButtonClick` evento per ricevere i dati dal controllo composito. L'applicazione presenta anche un insieme di pulsanti di opzione che è possibile utilizzare per modificare l'aspetto del controllo. La figura seguente mostra l'applicazione.  

Nell'immagine seguente viene illustrato un controllo composito WPF ospitato in un Windows Forms Application "  

 ![Scteenshot che mostra un Windows Form che ospita il controllo Avalon.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>Creazione del progetto  
 Per avviare il progetto:  
  
1. Avviare [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]e aprire la finestra di dialogo **nuovo progetto** .  
  
2. In Visual C# e nella Categoria Windows selezionare il modello di **applicazione Windows Forms** .  
  
3. Assegnare il nome `WFHost` al nuovo progetto.  
  
4. Come percorso, specificare la stessa cartella di livello superiore che contiene il progetto MyControls.  
  
5. Fare clic su **OK** per creare il progetto.  
  
 È anche necessario aggiungere riferimenti alla dll che contiene `MyControl1` e ad altri assembly.  
  
1. Fare clic con il pulsante destro del mouse sul nome del progetto in Esplora soluzioni e scegliere **Aggiungi riferimento**.  
  
2. Fare clic sulla scheda **Sfoglia** e selezionare la cartella che contiene i controlli. dll. In questa procedura dettagliata la cartella è MyControls\bin\Debug.  
  
3. Selezionare controllo. dll e quindi fare clic su **OK**.  
  
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
  
3. Nell'angolo in alto a destra del form aggiungere un <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> controllo che contenga il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito.  
  
4. Aggiungere i controlli <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> seguenti al form.  
  
    |Nome|Testo|  
    |----------|----------|  
    |groupBox1|Colore di sfondo|  
    |groupBox2|Colore primo piano|  
    |groupBox3|Dimensione carattere|  
    |groupBox4|Famiglia di caratteri|  
    |groupBox5|Stile|  
    |groupBox6|Spessore carattere|  
    |groupBox7|Dati dal controllo|  
  
5. Aggiungere i controlli <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> seguenti <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> ai controlli.  
  
    |GroupBox|Nome|Testo|  
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
  
6. Aggiungere i controlli <xref:System.Windows.Forms.Label?displayProperty=nameWithType> seguenti all'ultima. <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> Questi controlli visualizzano i dati restituiti dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo composito.  
  
    |GroupBox|Nome|Testo|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Nome:|  
    |groupBox7|lblAddress|Indirizzo:|  
    |groupBox7|lblCity|Città:|  
    |groupBox7|lblState|Stato:|  
    |groupBox7|lblZip|CAP:|  
  
### <a name="initializing-the-form"></a>Inizializzazione del form  
 In genere si implementa il codice host nel gestore <xref:System.Windows.Forms.Form.Load> eventi del form. Il codice seguente illustra il <xref:System.Windows.Forms.Form.Load> gestore eventi, un gestore per l' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Loaded> evento del controllo composito e le dichiarazioni per diverse variabili globali che vengono usate in un secondo momento.  
  
 Nella progettazione Windows Form fare doppio clic sul form per creare un <xref:System.Windows.Forms.Form.Load> gestore eventi. Nella parte superiore di Form1.cs aggiungere le istruzioni seguenti `using` .  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Sostituire il contenuto della classe esistente `Form1` con il codice seguente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 Il `Form1_Load` metodo nel codice precedente Mostra la procedura generale per l'hosting di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un controllo:  
  
1. Creare un nuovo <xref:System.Windows.Forms.Integration.ElementHost> oggetto.  
  
2. Impostare la <xref:System.Windows.Forms.Control.Dock%2A> proprietà del controllo su <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>.  
  
3. Aggiungere il <xref:System.Windows.Forms.Integration.ElementHost> controllo <xref:System.Windows.Forms.Panel> alla <xref:System.Windows.Forms.Control.Controls%2A> raccolta del controllo.  
  
4. Creare un'istanza del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo.  
  
5. Ospitare il controllo composito nel form assegnando il controllo alla <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> proprietà del controllo.  
  
 Le due righe rimanenti nel `Form1_Load` metodo alleghino i gestori a due eventi di controllo:  
  
- `OnButtonClick`è un evento personalizzato che viene generato dal controllo composito quando l'utente fa clic sul pulsante **OK** o **Annulla** . Si gestisce l'evento per ottenere la risposta dell'utente e per raccogliere i dati specificati dall'utente.  
  
- <xref:System.Windows.FrameworkElement.Loaded>è un evento standard generato da un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo quando viene caricato completamente. L'evento è usato qui poiché nell'esempio è necessario inizializzare diverse variabili globali usando le proprietà del controllo. Al momento dell' <xref:System.Windows.Forms.Form.Load> evento del modulo, il controllo non è completamente caricato e tali valori sono ancora impostati su `null`. Prima di poter accedere a tali proprietà, <xref:System.Windows.FrameworkElement.Loaded> è necessario attendere che si verifichi l'evento del controllo.  
  
 Il <xref:System.Windows.FrameworkElement.Loaded> gestore eventi è illustrato nel codice precedente. Il `OnButtonClick` gestore verrà illustrato nella sezione successiva.  
  
### <a name="handling-onbuttonclick"></a>Gestione dell'evento OnButtonClick  
 L' `OnButtonClick` evento si verifica quando l'utente fa clic sul pulsante **OK** o **Annulla** .  
  
 Il gestore eventi controlla il `IsOK` campo dell'argomento dell'evento per determinare su quale pulsante è stato fatto clic. Le `lbl` *variabili di dati* corrispondono ai controllidescrittiinprecedenza.<xref:System.Windows.Forms.Label> Se l'utente fa clic sul pulsante **OK** , i dati dei <xref:System.Windows.Controls.TextBox> controlli del controllo vengono assegnati al controllo corrispondente. <xref:System.Windows.Forms.Label> Se l'utente fa clic su Annulla <xref:System.Windows.Forms.Label.Text%2A> , i valori vengono impostati sulle stringhe predefinite.  
  
 Aggiungere il codice del gestore eventi click del pulsante seguente `Form1` alla classe.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Compilare ed eseguire l'applicazione. Aggiungere il testo nel controllo composito WPF, quindi fare clic su **OK**. Il testo viene visualizzato nelle etichette. A questo punto, il codice non è stato aggiunto ai pulsanti di opzione.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Modifica dell'aspetto del controllo  
 I <xref:System.Windows.Forms.RadioButton> controlli nel form consentiranno all'utente di modificare i [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] colori di primo piano e di sfondo del controllo composito nonché diverse proprietà del tipo di carattere. Il colore di sfondo viene esposto dall' <xref:System.Windows.Forms.Integration.ElementHost> oggetto. Le proprietà restanti sono esposte come proprietà personalizzate del controllo.  
  
 Fare doppio clic su <xref:System.Windows.Forms.RadioButton> ogni controllo nel form per creare <xref:System.Windows.Forms.RadioButton.CheckedChanged> i gestori eventi. Sostituire i <xref:System.Windows.Forms.RadioButton.CheckedChanged> gestori eventi con il codice seguente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Compilare ed eseguire l'applicazione. Fare clic sui vari pulsanti di opzione per vedere l'effetto sul controllo composito WPF.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Procedura dettagliata: Hosting di un controllo Windows Forms composito in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettagliata: Hosting di un controllo composito 3D WPF in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
