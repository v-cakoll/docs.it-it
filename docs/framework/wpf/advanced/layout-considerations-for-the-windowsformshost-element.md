---
title: Considerazioni sul layout per l'elemento WindowsFormsHost
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element layout considerations [WPF]
- dynamic layout [WPF interoperability]
- device-independent pixels
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
ms.openlocfilehash: 5856e710ad5a70fd740a5bb99ff241b8d9f2037a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518949"
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>Considerazioni sul layout per l'elemento WindowsFormsHost
Questo argomento viene descritto come la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento interagisce con il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di layout.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] supportano diversi, ma in modo analogo, per la logica per il ridimensionamento e posizionamento degli elementi in un form o pagina. Quando si crea un'interfaccia utente ibrida (UI) che ospita [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento integra i due schemi di layout.  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>Differenze nel Layout di WPF e Windows Form  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Usa layout indipendente dalla risoluzione. Tutti i [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le dimensioni di layout vengono specificate usando *device independent pixel*. Un pixel indipendenti dal dispositivo è il 90 un-sesto di un pollice in dimensioni e indipendente dalla risoluzione, pertanto si ottengono risultati simili indipendentemente dal fatto che si esegue il rendering a un monitor a 72 dpi o una stampante 19.200 dpi.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] si basa inoltre sul *layout dinamico*. Ciò significa che un elemento dell'interfaccia utente dispone di un form o pagina in base al relativo contenuto, il contenitore di layout del padre e la dimensione disponibile sullo schermo. Layout dinamico facilita la localizzazione regolando automaticamente le dimensioni e la posizione degli elementi dell'interfaccia utente quando le stringhe che contengono modifica lunghezza.  
  
 Layout in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] è dipendente dal dispositivo e più probabile che sia statico. In genere, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli vengono posizionati in modo assoluto in un form utilizzando le dimensioni specificate in pixel hardware. Tuttavia, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] supporta alcune funzionalità di layout dinamico, come riepilogato nella tabella seguente.  
  
|Funzionalità di layout|Descrizione|  
|--------------------|-----------------|  
|Ridimensionamento automatico|Alcuni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli ridimensionati automaticamente per visualizzare correttamente il rispettivo contenuto. Per altre informazioni, vedere [Cenni preliminari sulle proprietà AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).|  
|Ancoraggio e aggancio|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] i controlli supportano il posizionamento e ridimensionamento in base al contenitore padre. Per altre informazioni, vedere <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>.|  
|Scalabilità automatica|Controlli contenitore Ridimensiona se stessi e i relativi elementi figlio in base alla risoluzione del dispositivo di output o la dimensione, in pixel, del tipo di carattere contenitore predefinito. Per altre informazioni, vedere [scalabilità automatica in Windows Form](../../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md).|  
|Contenitori di layout|Il <xref:System.Windows.Forms.FlowLayoutPanel> e <xref:System.Windows.Forms.TableLayoutPanel> controlli dispongono i controlli figlio e si ridimensionano in base al relativo contenuto.|  
  
## <a name="layout-limitations"></a>Limitazioni di layout  
 In genere [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli non possono essere ridimensionati e trasformati per quanto possibile in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Nell'elenco seguente descrive le limitazioni note quando la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento tenta di integrare relativo ospitato [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] sul controllo nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di layout.  
  
-   In alcuni casi, i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non possono essere ridimensionati oppure possono essere ridimensionati solo in dimensioni specifiche. Ad esempio, un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> controllo supporta una sola altezza, definita dalla dimensione del carattere del controllo. In un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout dinamico in cui gli elementi possano essere ridimensionati verticalmente, un ambiente host <xref:System.Windows.Forms.ComboBox> controllo non verrà ridimensionato come previsto.  
  
-   I controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non possono essere ruotati o inclinati. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento genera il <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> eventi se si applica una trasformazione di inclinazione o una rotazione. Se non si gestisce il <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> evento, un <xref:System.InvalidOperationException> viene generato.  
  
-   Nella maggior parte dei casi, i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non supportano il ridimensionamento proporzionale. Anche se le dimensioni complessive del controllo vengono ridimensionate, i controlli figlio e gli elementi componente del controllo potrebbero non venire ridimensionati come previsto. Questa limitazione dipende dal modo in cui ogni controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] supporta il ridimensionamento. Inoltre, non è possibile ridimensionare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli fino a una dimensione pari a 0 pixel.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] i controlli supportano la scalabilità automatica, in cui il form viene ridimensionato automaticamente e i relativi controlli basati sulle dimensioni del carattere. In un'interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], modificando le dimensioni del carattere non si ridimensiona l'intero layout, anche se è possibile che vengano ridimensionati dinamicamente singoli elementi.  
  
### <a name="z-order"></a>Ordine Z  
 In un'interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è possibile modificare l'ordine z degli elementi per controllare il comportamento di sovrapposizione. Un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato viene disegnato in un elemento HWND separato, in modo che venga disegnato sempre sopra gli elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Hosting [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene creato anche a qualsiasi <xref:System.Windows.Documents.Adorner> elementi.  
  
## <a name="layout-behavior"></a>Comportamento di layout  
 Le sezioni seguenti descrivono alcuni aspetti specifici del comportamento di layout quando si ospitano [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>La scalabilità, la conversione di unità e l'indipendenza dai dispositivi  
 Ogni volta che il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento esegue le operazioni che coinvolgono [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] coinvolti dimensioni, due sistemi di coordinate: device independent pixel per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pixel hardware e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Pertanto, è necessario applicare unità appropriata e ridimensionamento conversioni per ottenere un layout coerente.  
  
 La conversione tra i sistemi di coordinate dipende dalla risoluzione del dispositivo corrente e qualsiasi layout o trasformazioni di rendering applicata al <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento o ai relativi predecessori.  
  
 Se il dispositivo di output è pari a 96 dpi e scalabilità non viene applicato il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento, un pixel indipendenti dal dispositivo è uguale a un pixel hardware.  
  
 Tutti gli altri casi richiedono il ridimensionamento di sistema di coordinate. Il controllo ospitato non viene ridimensionato. Al contrario, il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento tenta di ridimensionare il controllo ospitato e tutti i relativi controlli figlio. In quanto [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non supporta completamente la scalabilità, la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento ridimensiona il grado supportato da determinati controlli.  
  
 Eseguire l'override di <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> metodo per fornire un comportamento di ridimensionamento personalizzato per il controllo Windows Forms ospitato.  
  
 Oltre alla scalabilità, la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento gestisce i casi di arrotondamento e overflow come descritto nella tabella seguente.  
  
|Problema di conversione|Descrizione|  
|----------------------|-----------------|  
|Rounding|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dimensioni in pixel indipendenti dal dispositivo vengono specificate come `double`, e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] vengono specificate le dimensioni in pixel hardware come `int`. Nei casi in cui `double`-le dimensioni basate su vengono convertite `int`-basato su dimensioni, il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento viene applicato l'arrotondamento standard, in modo che valori frazionari minore di 0,5 vengono arrotondati per difetto a 0.|  
|Overflow|Quando la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento converte da `double` valori `int` overflow di valori, è possibile. I valori maggiori <xref:System.Int32.MaxValue> sono impostati su <xref:System.Int32.MaxValue>.|  
  
### <a name="layout-related-properties"></a>Proprietà correlate al layout  
 Le proprietà che controllano il comportamento di layout nella [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli elementi vengono mappati in modo appropriato per il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. Per altre informazioni, vedere [Mapping di proprietà di Windows Form e WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
### <a name="layout-changes-in-the-hosted-control"></a>Modifiche al layout nel controllo ospitato  
 Le modifiche di layout in ospitato [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo vengono propagati alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per attivare gli aggiornamenti del layout. Il <xref:System.Windows.UIElement.InvalidateMeasure%2A> metodo sul <xref:System.Windows.Forms.Integration.WindowsFormsHost> garantisce che le modifiche del layout nel controllo ospitato provochino il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l'esecuzione del motore di layout.  
  
### <a name="continuously-sized-windows-forms-controls"></a>Dimensioni in modo continuativo i controlli Windows Form  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] i controlli che supportano completamente la scala continua interagiscono con il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di layout. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento utilizza la <xref:System.Windows.FrameworkElement.MeasureOverride%2A> e <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi come di consueto per ridimensionare e disporre di hosting [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.  
  
### <a name="sizing-algorithm"></a>Algoritmo di ridimensionamento  
 Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento Usa la procedura seguente per ridimensionare il controllo ospitato:  
  
1.  Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> esegue l'override di elemento di <xref:System.Windows.FrameworkElement.MeasureOverride%2A> e <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi.  
  
2.  Per determinare le dimensioni del controllo ospitato, il <xref:System.Windows.FrameworkElement.MeasureOverride%2A> metodo chiama il controllo ospitato <xref:System.Windows.Forms.Control.GetPreferredSize%2A> metodo con un vincolo tradotto dal vincolo del passato per il <xref:System.Windows.FrameworkElement.MeasureOverride%2A> (metodo).  
  
3.  Il <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodo tenta di impostare il controllo ospitato per il vincolo delle dimensioni specificato.  
  
4.  Se il controllo ospitato <xref:System.Windows.Forms.Control.Size%2A> proprietà corrisponde al vincolo specificato, il controllo ospitato venga ridimensionato al vincolo.  
  
 Se il <xref:System.Windows.Forms.Control.Size%2A> proprietà non corrisponde al vincolo specificato, il controllo ospitato non supporta il ridimensionamento continuo. Ad esempio, il <xref:System.Windows.Forms.MonthCalendar> controllo consente solo dimensioni discrete. Le dimensioni consentite per questo controllo costituiti da numeri interi, che rappresenta il numero di mesi, per altezza e larghezza. In casi come questo, il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento si comporta come segue:  
  
-   Se il <xref:System.Windows.Forms.Control.Size%2A> dimensioni maggiori rispetto al vincolo specificato, viene restituita la il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento Taglia il controllo ospitato. Height e width vengono gestite separatamente, in modo che il controllo ospitato potrebbe essere ritagliato in entrambe le direzioni.  
  
-   Se il <xref:System.Windows.Forms.Control.Size%2A> dimensioni inferiori rispetto al vincolo specificato, viene restituita la <xref:System.Windows.Forms.Integration.WindowsFormsHost> accetta questo valore e restituisce il valore per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di layout.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Procedura dettagliata: Disposizione di controlli Windows Form in WPF](../../../../docs/framework/wpf/advanced/walkthrough-arranging-windows-forms-controls-in-wpf.md)  
 [I controlli di disposizione Windows Form in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971)  
 [Mapping di proprietà di Windows Form e WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [Migrazione e interoperabilità](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
