---
title: Risoluzione dei problemi relativi ad applicazioni ibride
ms.date: 03/30/2017
helpviewer_keywords:
- overlapping controls [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid applications [WPF interoperability]
- message loops [WPF]
ms.assetid: f440c23f-fa5d-4d5a-852f-ba61150e6405
ms.openlocfilehash: 46d8f00f9328e9c0a4df596b709195ae42d651bf
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960123"
---
# <a name="troubleshooting-hybrid-applications"></a>Risoluzione dei problemi relativi ad applicazioni ibride
<a name="introduction"></a> Questo argomento illustra alcuni problemi comuni che possono verificarsi durante la creazione di applicazioni che usano tecnologie sia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], sia [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  

<a name="overlapping_controls"></a>   
## <a name="overlapping-controls"></a>Sovrapposizione di controlli  
 I controlli potrebbero sovrapporsi in maniera imprevista. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] usa un HWND separato per ogni controllo. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa un HWND per tutto il contenuto in una pagina. Questa differenza di implementazione provoca comportamenti di sovrapposizione imprevisti.  
  
 Un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene sempre visualizzato sopra il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto ospitato in un controllo <xref:System.Windows.Forms.Integration.ElementHost> viene visualizzato in corrispondenza dell'ordine z del controllo <xref:System.Windows.Forms.Integration.ElementHost>. È possibile sovrapporre <xref:System.Windows.Forms.Integration.ElementHost> controlli, ma il contenuto della [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitata non combina né interagisce.  
  
<a name="child_property"></a>   
## <a name="child-property"></a>Child Property  
 Le classi <xref:System.Windows.Forms.Integration.WindowsFormsHost> e <xref:System.Windows.Forms.Integration.ElementHost> possono ospitare solo un singolo controllo o elemento figlio. Per ospitarne più di uno, è necessario usare un contenitore come contenuto figlio. Ad esempio, è possibile aggiungere [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] pulsante e i controlli casella di controllo a un controllo <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> e quindi assegnare il pannello alla proprietà <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> di un controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Tuttavia, non è possibile aggiungere separatamente i controlli Button e check box allo stesso controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="scaling"></a>   
## <a name="scaling"></a>Ridimensionamento  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hanno modelli di ridimensionamento diversi. Alcune trasformazioni di ridimensionamento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hanno valore per i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], ma non tutte. Ad esempio, è possibile ridimensionare un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] fino a 0, ma se si prova a riportare lo stesso controllo su un valore diverso da 0, le dimensioni del controllo rimarranno invariate. Per altre informazioni, vedere [Considerazioni sul layout per l'elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>   
## <a name="adapter"></a>Adapter  
 È possibile che si verifichino confusione quando si utilizzano le classi <xref:System.Windows.Forms.Integration.WindowsFormsHost> e <xref:System.Windows.Forms.Integration.ElementHost>, perché includono un contenitore nascosto. Entrambe le classi <xref:System.Windows.Forms.Integration.WindowsFormsHost> e <xref:System.Windows.Forms.Integration.ElementHost> hanno un contenitore nascosto, denominato *Adapter*, che usano per ospitare il contenuto. Per l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, l'adapter deriva dalla classe <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType>. Per il controllo <xref:System.Windows.Forms.Integration.ElementHost>, l'adapter deriva dall'elemento <xref:System.Windows.Controls.DockPanel>. I riferimenti all'adattatore presenti in altri argomenti sull'interoperabilità alludono a tale contenitore.  
  
<a name="nesting"></a>   
## <a name="nesting"></a>Nidificazione  
 Annidamento di un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> all'interno di un controllo <xref:System.Windows.Forms.Integration.ElementHost> non supportato. Anche l'annidamento di un controllo <xref:System.Windows.Forms.Integration.ElementHost> all'interno di un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> non è supportato.  
  
<a name="focus"></a>   
## <a name="focus"></a>Stato attivo  
 Lo stato attivo funziona in maniera diversa in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Per questo motivo, in un'applicazione ibrida possono verificarsi problemi relativi allo stato attivo. Ad esempio, se lo stato attivo si trova all'interno di un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> e si riduce a icona e si ripristina la pagina o si visualizza una finestra di dialogo modale, lo stato attivo all'interno dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> può andare perduto. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> ha ancora lo stato attivo, ma il controllo all'interno di esso non può.  
  
 Lo stato attivo influisce anche sulla convalida dei dati. La convalida funziona in un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, ma non funziona quando si esce dalla tabulazione dell'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> o tra due elementi <xref:System.Windows.Forms.Integration.WindowsFormsHost> diversi.  
  
<a name="property_mapping"></a>   
## <a name="property-mapping"></a>Mapping proprietà  
 Alcuni mapping di proprietà richiedono un'interpretazione estensiva per integrare implementazioni dissimili tra le tecnologie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. I mapping di proprietà consentono al codice di rispondere alle modifiche apportate ai tipi di carattere, ai colori e ad altre proprietà. In generale, i mapping di proprietà funzionano rimanendo in ascolto di eventi *Property*Changed o chiamate On*Property*Changed e impostando le proprietà adeguate sul controllo figlio o sul relativo adattatore. Per altre informazioni, vedere [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>   
## <a name="layout-related-properties-on-hosted-content"></a>Proprietà relative al layout nel contenuto ospitato  
 Quando viene assegnata la proprietà <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType>, vengono impostate automaticamente diverse proprietà correlate al layout nel contenuto ospitato. La modifica di queste proprietà di contenuto può determinare comportamenti di layout imprevisti.  
  
 Il contenuto ospitato è ancorato in modo da riempire il <xref:System.Windows.Forms.Integration.WindowsFormsHost> e <xref:System.Windows.Forms.Integration.ElementHost> padre. Per abilitare questo comportamento di riempimento, durante l'impostazione della proprietà figlio vengono impostate varie proprietà. Nella tabella seguente sono elencate le proprietà di contenuto impostate dalle classi <xref:System.Windows.Forms.Integration.ElementHost> e <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
|Classe host|Proprietà di contenuto|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 Non impostare queste proprietà direttamente sul contenuto ospitato. Per altre informazioni, vedere [Considerazioni sul layout per l'elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>   
## <a name="navigation-applications"></a>Applicazioni di navigazione  
 Le applicazioni di navigazione potrebbero non mantenere lo stato dell'utente. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> ricrea i controlli quando viene utilizzato in un'applicazione di navigazione. La ricreazione di controlli figlio si verifica quando l'utente si sposta dalla pagina che ospita l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> e quindi torna al suo interno. Qualsiasi contenuto digitato dall'utente andrà perduto.  
  
<a name="message_loop_interoperation"></a>   
## <a name="message-loop-interoperation"></a>Interoperabilità del ciclo di messaggi  
 Quando si usano i cicli di messaggi [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], i messaggi potrebbero essere elaborati in modo diverso dal previsto. Il metodo <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> viene chiamato dal costruttore di <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Questo metodo aggiunge un filtro messaggi al ciclo di messaggi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Questo filtro chiama il metodo <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> se una <xref:System.Windows.Forms.Control?displayProperty=nameWithType> è la destinazione del messaggio e converte/invia il messaggio.  
  
 Se si visualizza un <xref:System.Windows.Window> in un ciclo di messaggi [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] con <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>, non è possibile digitare niente a meno che non si chiami il metodo <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>. Il metodo <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> accetta una <xref:System.Windows.Window> e aggiunge un <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>, che reindirizza i messaggi relativi alla chiave al ciclo di messaggi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per altre informazioni, vedere [Architettura di input per l'interoperabilità tra Windows Form e WPF](windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>   
## <a name="opacity-and-layering"></a>Opacità e sovrapposizione  
 La classe <xref:System.Windows.Interop.HwndHost> non supporta la sovrapposizione. Ciò significa che l'impostazione della proprietà <xref:System.Windows.UIElement.Opacity%2A> sull'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> non ha alcun effetto e che non si verificherà alcuna fusione con altre finestre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che hanno <xref:System.Windows.Window.AllowsTransparency%2A> impostato su `true`.  
  
<a name="dispose"></a>   
## <a name="dispose"></a>Dispose  
 L'eliminazione non corretta delle classi può determinare una perdita di risorse. Nelle applicazioni ibride verificare che le classi <xref:System.Windows.Forms.Integration.WindowsFormsHost> e <xref:System.Windows.Forms.Integration.ElementHost> vengano eliminate o che si verifichino perdite di risorse. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Elimina i controlli <xref:System.Windows.Forms.Integration.ElementHost> quando il padre <xref:System.Windows.Forms.Form> non modale viene chiuso. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elimina gli elementi <xref:System.Windows.Forms.Integration.WindowsFormsHost> quando l'applicazione viene arrestata. È possibile mostrare un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> in un <xref:System.Windows.Window> in un ciclo di messaggi di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. In questo caso, è possibile che il codice non riceva notifica della chiusura dell'applicazione.  
  
<a name="enabling_visual_styles"></a>   
## <a name="enabling-visual-styles"></a>Abilitazione degli stili di visualizzazione  
 Gli stili di visualizzazione di Microsoft Windows XP in un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] potrebbero non essere abilitati. Il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> viene chiamato nel modello per un'applicazione [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Sebbene questo metodo non venga chiamato per impostazione predefinita, se si utilizza Visual Studio per creare un progetto, si otterranno gli stili di visualizzazione di Microsoft Windows XP per i controlli, se è disponibile la versione 6,0 di Comctl32. dll. Prima di creare handle nel thread, è necessario chiamare il metodo <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>. Per altre informazioni, vedere [Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida](how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>   
## <a name="licensed-controls"></a>Controlli con licenza  
 I controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] con licenza che mostrano all'utente in una finestra di messaggio le informazioni relative alla licenza potrebbero determinare comportamenti imprevisti in un'applicazione ibrida. Alcuni controlli con licenza visualizzano una finestra di dialogo in risposta alla creazione di handle. Ad esempio, un controllo con licenza potrebbe informare l'utente che è richiesta una licenza oppure che sono consentiti ancora tre usi del controllo a scopo di valutazione.  
  
 L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> deriva dalla classe <xref:System.Windows.Interop.HwndHost> e l'handle del controllo figlio viene creato all'interno del <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> metodo. La classe <xref:System.Windows.Interop.HwndHost> non consente l'elaborazione dei messaggi nel metodo <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>, ma la visualizzazione di una finestra di dialogo comporta l'invio dei messaggi. Per abilitare questo scenario di gestione delle licenze, chiamare il metodo <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> sul controllo prima di assegnarlo come figlio dell'elemento di <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
<a name="wpf_designer"></a>   
## <a name="wpf-designer"></a>WPF Designer  
 È possibile progettare il contenuto WPF utilizzando WPF Designer per Visual Studio. Nelle sezioni seguenti sono elencati alcuni problemi comuni che possono verificarsi durante la creazione di applicazioni ibride con WPF Designer.  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>Proprietà BackColorTransparent ignorata in fase di progettazione  
 Il <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> proprietà potrebbe non funzionare come previsto in fase di progettazione.  
  
 Se un controllo WPF non si trova in un elemento padre visibile, il runtime WPF ignorerà il valore <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>. Il motivo per cui <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> possibile ignorare è che <xref:System.Windows.Forms.Integration.ElementHost> oggetto viene creato in un <xref:System.AppDomain>separato. Tuttavia, quando si esegue l'applicazione, <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> funziona come previsto.  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>Visualizzazione dell'elenco errori della fase di progettazione quando viene eliminata la cartella obj  
 Se la cartella obj viene eliminata, viene visualizzato l'elenco errori della fase di progettazione.  
  
 Quando si progetta usando <xref:System.Windows.Forms.Integration.ElementHost>, il Progettazione Windows Form usa i file generati nella cartella debug o versione all'interno della cartella obj del progetto. Se si eliminano questi file, viene visualizzato l'elenco errori della fase di progettazione. Per risolvere questo problema, ricompilare il progetto. Per altre informazioni, vedere [Errori in fase di progettazione in Progettazione Windows Form](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>   
## <a name="elementhost-and-ime"></a>ElementHost e IME  
 I controlli WPF ospitati in un <xref:System.Windows.Forms.Integration.ElementHost> attualmente non supportano la proprietà <xref:System.Windows.Forms.Control.ImeMode%2A>. Le modifiche apportate al <xref:System.Windows.Forms.Control.ImeMode%2A> verranno ignorate dai controlli ospitati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interoperabilità in WPF Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628658(v=vs.100))
- [Architettura di input per l'interoperabilità tra Windows Form e WPF](windows-forms-and-wpf-interoperability-input-architecture.md)
- [Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida](how-to-enable-visual-styles-in-a-hybrid-application.md)
- [Considerazioni sul layout per l'elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md)
- [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md)
- [Errori in fase di progettazione in Progettazione Windows Form](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)
- [Migrazione e interoperabilità](migration-and-interoperability.md)
