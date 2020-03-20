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
ms.openlocfilehash: b85a607d2e44d6253359a81118f90e6ee05d2d3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187318"
---
# <a name="troubleshooting-hybrid-applications"></a>Risoluzione dei problemi relativi ad applicazioni ibride
<a name="introduction"></a>In questo argomento vengono elencati alcuni problemi comuni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che possono verificarsi durante la creazione di applicazioni ibride, che utilizzano entrambe le tecnologie Windows Form.This topic lists some common problems that can occur when authoring hybrid applications, which use both and Windows Forms technologies.  

<a name="overlapping_controls"></a>
## <a name="overlapping-controls"></a>Sovrapposizione di controlli  
 I controlli potrebbero sovrapporsi in maniera imprevista. Windows Form utilizza un HWND separato per ogni controllo. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa un HWND per tutto il contenuto in una pagina. Questa differenza di implementazione provoca comportamenti di sovrapposizione imprevisti.  
  
 Un controllo Windows Form [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitato in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene sempre visualizzato sopra il contenuto.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]contenuto ospitato <xref:System.Windows.Forms.Integration.ElementHost> in un controllo viene visualizzato <xref:System.Windows.Forms.Integration.ElementHost> nell'ordine z del controllo. È possibile sovrapporsi <xref:System.Windows.Forms.Integration.ElementHost> ai [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli, ma il contenuto ospitato non combina né interagisce.  
  
<a name="child_property"></a>
## <a name="child-property"></a>Child Property  
 Le <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost> classi e possono ospitare un solo controllo figlio o elemento. Per ospitarne più di uno, è necessario usare un contenitore come contenuto figlio. Ad esempio, è possibile aggiungere controlli pulsante <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> e casella di controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> Windows Form <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> a un controllo e quindi assegnare il pannello alla proprietà di un controllo. Tuttavia, non è possibile aggiungere i controlli <xref:System.Windows.Forms.Integration.WindowsFormsHost> pulsante e casella di controllo separatamente allo stesso controllo.  
  
<a name="scaling"></a>
## <a name="scaling"></a>Scalabilità  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]e Windows Form hanno modelli di ridimensionamento diversi. Alcune [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] trasformazioni di ridimensionamento sono significative per i controlli Windows Form, ma altre no. Ad esempio, il ridimensionamento di un controllo Windows Form a 0 funzionerà, ma se si tenta di ridimensionare lo stesso controllo a un valore diverso da zero, le dimensioni del controllo rimangono 0.For example, scaling a Windows Forms control to 0 will work, but if you try to scale the same control back to a diverso da zero value, the control's size remains 0. Per altre informazioni, vedere [Considerazioni sul layout per l'elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>
## <a name="adapter"></a>Adattatore  
 Potrebbe esserci confusione <xref:System.Windows.Forms.Integration.WindowsFormsHost> durante <xref:System.Windows.Forms.Integration.ElementHost> il lavoro e classi, perché includono un contenitore nascosto. Entrambe <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost> le classi e dispongono di un contenitore nascosto, denominato *adattatore*, che vengono utilizzati per ospitare il contenuto. Per <xref:System.Windows.Forms.Integration.WindowsFormsHost> l'elemento, l'adattatore deriva dalla <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType> classe . Per <xref:System.Windows.Forms.Integration.ElementHost> il controllo, l'adattatore deriva dall'elemento. <xref:System.Windows.Controls.DockPanel> I riferimenti all'adattatore presenti in altri argomenti sull'interoperabilità alludono a tale contenitore.  
  
<a name="nesting"></a>
## <a name="nesting"></a>Annidamento  
 La nidificazione di un <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento all'interno di un <xref:System.Windows.Forms.Integration.ElementHost> controllo non è supportata. Anche la <xref:System.Windows.Forms.Integration.ElementHost> nidificazione <xref:System.Windows.Forms.Integration.WindowsFormsHost> di un controllo all'interno di un elemento non è supportata.  
  
<a name="focus"></a>
## <a name="focus"></a>Focus  
 Lo stato attivo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funziona in modo diverso in Windows Form e Windows Form, il che significa che possono verificarsi problemi di messa a fuoco in un'applicazione ibrida. Ad esempio, se si <xref:System.Windows.Forms.Integration.WindowsFormsHost> dispone di stato attivo all'interno di un elemento e <xref:System.Windows.Forms.Integration.WindowsFormsHost> si riduce a icona e ripristinare la pagina o visualizzare una finestra di dialogo modale, lo stato attivo all'interno dell'elemento potrebbe andare perso. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> ha ancora lo stato attivo, ma il controllo al suo interno potrebbe non.  
  
 Lo stato attivo influisce anche sulla convalida dei dati. La convalida <xref:System.Windows.Forms.Integration.WindowsFormsHost> funziona in un elemento, ma non <xref:System.Windows.Forms.Integration.WindowsFormsHost> funziona come si <xref:System.Windows.Forms.Integration.WindowsFormsHost> tabulazione all'esterno dell'elemento o tra due elementi diversi.  
  
<a name="property_mapping"></a>
## <a name="property-mapping"></a>Mapping di proprietà  
 Alcuni mapping di proprietà richiedono un'interpretazione completa [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per colmare implementazioni diverse tra le tecnologie Windows Form e Windows. I mapping di proprietà consentono al codice di rispondere alle modifiche apportate ai tipi di carattere, ai colori e ad altre proprietà. In generale, i mapping di proprietà funzionano rimanendo in ascolto di eventi *Property*Changed o chiamate On*Property*Changed e impostando le proprietà adeguate sul controllo figlio o sul relativo adattatore. Per altre informazioni, vedere [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>
## <a name="layout-related-properties-on-hosted-content"></a>Proprietà relative al layout nel contenuto ospitato  
 Quando <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> viene <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType> assegnata la proprietà o , vengono impostate automaticamente diverse proprietà relative al layout nel contenuto ospitato. La modifica di queste proprietà di contenuto può determinare comportamenti di layout imprevisti.  
  
 Il contenuto ospitato è ancorato <xref:System.Windows.Forms.Integration.ElementHost> per riempire l'oggetto e l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> padre. Per abilitare questo comportamento di riempimento, durante l'impostazione della proprietà figlio vengono impostate varie proprietà. Nella tabella seguente sono elencate le <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost> proprietà di contenuto impostate dalle classi e .  
  
|Classe host|Proprietà di contenuto|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 Non impostare queste proprietà direttamente sul contenuto ospitato. Per altre informazioni, vedere [Considerazioni sul layout per l'elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>
## <a name="navigation-applications"></a>Applicazioni di navigazione  
 Le applicazioni di navigazione potrebbero non mantenere lo stato dell'utente. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> ricrea i controlli quando viene utilizzato in un'applicazione di navigazione. La ricreazione dei controlli figlio si verifica quando <xref:System.Windows.Forms.Integration.WindowsFormsHost> l'utente esce dalla pagina che ospita l'elemento e quindi vi ritorna. Qualsiasi contenuto digitato dall'utente andrà perduto.  
  
<a name="message_loop_interoperation"></a>
## <a name="message-loop-interoperation"></a>Interoperabilità del ciclo di messaggi  
 Quando si lavora con i cicli di messaggi di Windows Form, i messaggi potrebbero non essere elaborati come previsto. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> metodo viene <xref:System.Windows.Forms.Integration.WindowsFormsHost> chiamato dal costruttore. Questo metodo aggiunge un filtro messaggi al ciclo di messaggi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Questo filtro <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> chiama il <xref:System.Windows.Forms.Control?displayProperty=nameWithType> metodo se un oggetto è la destinazione del messaggio e lo converte o invia il messaggio.  
  
 Se si <xref:System.Windows.Window> visualizza un in un <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>ciclo di messaggi di <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> Windows Form con , non è possibile digitare nulla a meno che non si chiami il metodo . Il <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> metodo <xref:System.Windows.Window> accetta e <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>aggiunge un oggetto , che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reindirizza i messaggi relativi ai tasti al ciclo di messaggi. Per altre informazioni, vedere [Architettura di input per l'interoperabilità tra Windows Form e WPF](windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>
## <a name="opacity-and-layering"></a>Opacità e sovrapposizione  
 La <xref:System.Windows.Interop.HwndHost> classe non supporta la stratificazione. Ciò significa <xref:System.Windows.UIElement.Opacity%2A> che l'impostazione della proprietà <xref:System.Windows.Forms.Integration.WindowsFormsHost> sull'elemento non [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ha <xref:System.Windows.Window.AllowsTransparency%2A> alcun `true`effetto e non verrà eseguita alcuna fusione con altre finestre che sono state impostate su .  
  
<a name="dispose"></a>
## <a name="dispose"></a>Dispose  
 L'eliminazione non corretta delle classi può determinare una perdita di risorse. Nelle applicazioni ibride, assicurarsi che le <xref:System.Windows.Forms.Integration.WindowsFormsHost> classi e <xref:System.Windows.Forms.Integration.ElementHost> vengono eliminate, altrimenti è possibile causare perdite di risorse. Windows Form <xref:System.Windows.Forms.Integration.ElementHost> elimina i controlli <xref:System.Windows.Forms.Form> quando il padre non modale viene chiuso. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]elimina <xref:System.Windows.Forms.Integration.WindowsFormsHost> gli elementi quando l'applicazione viene arrestata. È possibile visualizzare <xref:System.Windows.Forms.Integration.WindowsFormsHost> un elemento <xref:System.Windows.Window> in un in un ciclo di messaggi di Windows Form.It is possible to show a element in a in a Windows Forms message loop. In questo caso, è possibile che il codice non riceva notifica della chiusura dell'applicazione.  
  
<a name="enabling_visual_styles"></a>
## <a name="enabling-visual-styles"></a>Abilitazione degli stili di visualizzazione  
 Gli stili di visualizzazione di Microsoft Windows XP in un controllo Windows Form potrebbero non essere abilitati. Il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> metodo viene chiamato nel modello per un'applicazione Windows Form.The method is called in the template for a Windows Forms application. Anche se questo metodo non viene chiamato per impostazione predefinita, se si utilizza Visual Studio per creare un progetto, si otterranno gli stili di visualizzazione di Microsoft Windows XP per i controlli, se è disponibile la versione 6.0 di Comctl32.dll. È necessario <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> chiamare il metodo prima che gli handle vengano creati nel thread. Per altre informazioni, vedere [Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida](how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>
## <a name="licensed-controls"></a>Controlli con licenza  
 I controlli Windows Form con licenza che visualizzano informazioni sulle licenze in una finestra di messaggio all'utente potrebbero causare un comportamento imprevisto per un'applicazione ibrida. Alcuni controlli con licenza visualizzano una finestra di dialogo in risposta alla creazione di handle. Ad esempio, un controllo con licenza potrebbe informare l'utente che è richiesta una licenza oppure che sono consentiti ancora tre usi del controllo a scopo di valutazione.  
  
 L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> deriva <xref:System.Windows.Interop.HwndHost> dalla classe e l'handle del controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> figlio viene creato all'interno del metodo. La <xref:System.Windows.Interop.HwndHost> classe non consente l'elaborazione dei messaggi nel metodo , ma la <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> visualizzazione di una finestra di dialogo causa l'invio di messaggi. Per abilitare questo scenario <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> di gestione delle licenze, <xref:System.Windows.Forms.Integration.WindowsFormsHost> chiamare il metodo sul controllo prima di assegnarlo come figlio dell'elemento.  
  
<a name="wpf_designer"></a>
## <a name="wpf-designer"></a>WPF Designer  
 È possibile progettare il contenuto WPFWPF usando WPF Designer per Visual Studio.You can design your WPFWPF content by using the WPF Designer for Visual Studio. Nelle sezioni seguenti sono elencati alcuni problemi comuni che possono verificarsi durante la creazione di applicazioni ibride con WPF Designer.  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>Proprietà BackColorTransparent ignorata in fase di progettazione  
 La <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> proprietà potrebbe non funzionare come previsto in fase di progettazione.  
  
 Se un controllo WPFWPF non si trova in <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> un elemento padre visibile, il runtime WPFWPF ignora il valore. Il motivo che <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> potrebbe <xref:System.Windows.Forms.Integration.ElementHost> essere ignorato <xref:System.AppDomain>è perché l'oggetto viene creato in un file . Tuttavia, quando si <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> esegue l'applicazione, funziona come previsto.  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>Visualizzazione dell'elenco errori della fase di progettazione quando viene eliminata la cartella obj  
 Se la cartella obj viene eliminata, viene visualizzato l'elenco errori della fase di progettazione.  
  
 Quando si <xref:System.Windows.Forms.Integration.ElementHost>progetta utilizzando , Progettazione Windows Form utilizza i file generati nella cartella Debug o Release all'interno della cartella obj del progetto. Se si eliminano questi file, viene visualizzato l'elenco errori della fase di progettazione. Per risolvere questo problema, ricompilare il progetto. Per altre informazioni, vedere [Errori in fase di progettazione in Progettazione Windows Form](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>
## <a name="elementhost-and-ime"></a>ElementHost e IME  
 I controlli WPF <xref:System.Windows.Forms.Integration.ElementHost> ospitati in <xref:System.Windows.Forms.Control.ImeMode%2A> un oggetto attualmente non supportano la proprietà. Le <xref:System.Windows.Forms.Control.ImeMode%2A> modifiche apportate verranno ignorate dai controlli ospitati.  
  
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
