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
ms.openlocfilehash: 89ed57a787b93a1326b4accd3bb1bc5ff9a825fd
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095151"
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>Considerazioni sul layout per l'elemento WindowsFormsHost
In questo argomento viene descritto il modo in cui l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> interagisce con il sistema di layout di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e Windows Forms supportano la logica diversa, ma simile, per il ridimensionamento e il posizionamento di elementi in un form o una pagina. Quando si crea un'interfaccia utente ibrida che ospita Windows Forms controlli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> integra i due schemi di layout.  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>Differenze nel layout tra WPF e Windows Forms  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa il layout indipendente dalla risoluzione. Tutte le dimensioni del layout [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono specificate usando i *pixel indipendenti dal dispositivo*. Un pixel indipendente dal dispositivo è un 90 ° di un pollice di dimensioni e indipendente dalla risoluzione, quindi si ottengono risultati simili indipendentemente dal fatto che venga eseguito il rendering in un monitor 72 dpi o in una stampante 19.200-dpi.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] si basa anche sul *layout dinamico*. Ciò significa che un elemento dell'interfaccia utente dispone di se stesso in un form o in una pagina in base al relativo contenuto, al relativo contenitore di layout padre e alle dimensioni dello schermo disponibili. Il layout dinamico semplifica la localizzazione regolando automaticamente le dimensioni e la posizione degli elementi dell'interfaccia utente quando le stringhe che contengono cambiano la lunghezza.  
  
 Il layout in Windows Forms è dipendente dal dispositivo e con maggiore probabilità è statico. In genere, i controlli Windows Forms sono posizionati in modo assoluto in un modulo che usa dimensioni specificate in pixel hardware. Tuttavia, Windows Forms supporta alcune funzionalità di layout dinamico, come riepilogato nella tabella seguente.  
  
|Funzionalità layout|Descrizione|  
|--------------------|-----------------|  
|Ridimensionamento automatico|Alcuni Windows Forms controlli si ridimensionano per visualizzare correttamente il contenuto. Per ulteriori informazioni, vedere [Panoramica delle proprietà AutoSize](../../winforms/controls/autosize-property-overview.md).|  
|Ancoraggio e ancoraggio|I controlli Windows Forms supportano il posizionamento e il ridimensionamento in base al contenitore padre. Per altre informazioni, vedere <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>.|  
|Scalabilità automatica|I controlli contenitore si ridimensionano e i relativi elementi figlio in base alla risoluzione del dispositivo di output o alle dimensioni, in pixel, del tipo di carattere del contenitore predefinito. Per ulteriori informazioni, vedere la pagina relativa [alla scalabilità automatica in Windows Forms](../../winforms/automatic-scaling-in-windows-forms.md).|  
|Contenitori di layout|I controlli <xref:System.Windows.Forms.FlowLayoutPanel> e <xref:System.Windows.Forms.TableLayoutPanel> dispongono i controlli figlio e le dimensioni stesse in base al relativo contenuto.|  
  
## <a name="layout-limitations"></a>Limitazioni del layout  
 In generale, i controlli Windows Forms non possono essere ridimensionati e trasformati nella misura massima consentita nell'[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Nell'elenco seguente vengono descritte le limitazioni note quando l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> tenta di integrare il controllo Windows Forms ospitato nel sistema di layout di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- In alcuni casi, i controlli Windows Forms non possono essere ridimensionati o possono essere ridimensionati solo a dimensioni specifiche. Ad esempio, un controllo Windows Forms <xref:System.Windows.Forms.ComboBox> supporta solo una singola altezza, che è definita dalle dimensioni del carattere del controllo. In un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout dinamico in cui gli elementi possono estendersi verticalmente, un controllo <xref:System.Windows.Forms.ComboBox> ospitato non si estenderà come previsto.  
  
- Non è possibile ruotare o inclinare i controlli Windows Forms. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> genera l'evento <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> se si applica una trasformazione di inclinazione o rotazione. Se non si gestisce l'evento <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>, viene generata un'<xref:System.InvalidOperationException>.  
  
- Nella maggior parte dei casi, i controlli Windows Forms non supportano la scalabilità proporzionale. Anche se le dimensioni complessive del controllo vengono ridimensionate, i controlli figlio e gli elementi componente del controllo potrebbero non venire ridimensionati come previsto. Questa limitazione dipende dal modo in cui ogni controllo Windows Forms supporta il ridimensionamento. Non è inoltre possibile ridimensionare Windows Forms controlli fino a una dimensione di 0 pixel.  
  
- I controlli Windows Forms supportano la scalabilità automatica, in cui il form si ridimensiona automaticamente e i controlli in base alle dimensioni del carattere. In un'interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], modificando le dimensioni del carattere non si ridimensiona l'intero layout, anche se è possibile che vengano ridimensionati dinamicamente singoli elementi.  
  
### <a name="z-order"></a>Ordine Z  
 In un'interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è possibile modificare l'ordine z degli elementi per controllare il comportamento di sovrapposizione. Un controllo Windows Forms ospitato viene disegnato in un HWND separato, pertanto viene sempre disegnato sopra gli elementi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Viene anche disegnato un controllo Windows Forms ospitato su tutti gli elementi di <xref:System.Windows.Documents.Adorner>.  
  
## <a name="layout-behavior"></a>Comportamento del layout  
 Nelle sezioni seguenti vengono descritti aspetti specifici del comportamento del layout quando si ospitano controlli Windows Forms in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>Ridimensionamento, conversione di unità e indipendenza dei dispositivi  
 Ogni volta che l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> esegue operazioni che coinvolgono [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e Windows Forms dimensioni, sono coinvolti due sistemi di Coordinate: i pixel indipendenti dal dispositivo per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e i pixel hardware per Windows Forms. Pertanto, per ottenere un layout coerente è necessario applicare le conversioni appropriate di unità e scalabilità.  
  
 La conversione tra i sistemi di coordinate dipende dalla risoluzione del dispositivo corrente e da eventuali trasformazioni di layout o rendering applicate all'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> o ai relativi predecessori.  
  
 Se il dispositivo di output è 96 dpi e non è stato applicato alcun ridimensionamento all'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, un pixel indipendente dal dispositivo è uguale a un pixel hardware.  
  
 Tutti gli altri casi richiedono la scalabilità del sistema di coordinate. Il controllo ospitato non viene ridimensionato. Al contrario, l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> tenta di ridimensionare il controllo ospitato e tutti i relativi controlli figlio. Poiché Windows Forms non supporta completamente il ridimensionamento, l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> viene ridimensionato in base al livello supportato da determinati controlli.  
  
 Eseguire l'override del metodo <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> per fornire un comportamento di ridimensionamento personalizzato per il controllo Windows Forms ospitato.  
  
 Oltre al ridimensionamento, l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> gestisce i case di arrotondamento e overflow, come descritto nella tabella seguente.  
  
|Problema di conversione|Descrizione|  
|----------------------|-----------------|  
|Arrotondamento|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dimensioni in pixel indipendenti dal dispositivo vengono specificate come `double`e Windows Forms dimensioni dei pixel hardware vengono specificate come `int`. Nei casi in cui le dimensioni basate su `double`vengono convertite in dimensioni basate su `int`, l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> usa l'arrotondamento standard, in modo che i valori frazionari minori di 0,5 siano arrotondati per difetto a 0.|  
|Overflow|Quando l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> converte da valori `double` a valori `int`, è possibile che l'overflow sia possibile. I valori maggiori di <xref:System.Int32.MaxValue> vengono impostati su <xref:System.Int32.MaxValue>.|  
  
### <a name="layout-related-properties"></a>Proprietà correlate al layout  
 Le proprietà che controllano il comportamento del layout nei controlli Windows Forms e negli elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono mappate in modo appropriato dall'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Per altre informazioni, vedere [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="layout-changes-in-the-hosted-control"></a>Modifiche del layout nel controllo ospitato  
 Le modifiche di layout nel controllo Windows Forms ospitato vengono propagate in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per attivare gli aggiornamenti del layout. Il metodo <xref:System.Windows.UIElement.InvalidateMeasure%2A> su <xref:System.Windows.Forms.Integration.WindowsFormsHost> garantisce che le modifiche apportate al layout nel controllo ospitato provochino l'esecuzione del motore di layout di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="continuously-sized-windows-forms-controls"></a>Controlli Windows Forms continuamente dimensionati  
 Windows Forms controlli che supportano il ridimensionamento continuo completamente interagiscono con il sistema di layout di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> usa i metodi <xref:System.Windows.FrameworkElement.MeasureOverride%2A> e <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> come di consueto per ridimensionare e disporre il controllo Windows Forms ospitato.  
  
### <a name="sizing-algorithm"></a>Algoritmo di dimensionamento  
 L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> utilizza la procedura seguente per ridimensionare il controllo ospitato:  
  
1. L'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> esegue l'override dei metodi <xref:System.Windows.FrameworkElement.MeasureOverride%2A> e <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.  
  
2. Per determinare le dimensioni del controllo ospitato, il metodo <xref:System.Windows.FrameworkElement.MeasureOverride%2A> chiama il metodo <xref:System.Windows.Forms.Control.GetPreferredSize%2A> del controllo ospitato con un vincolo convertito dal vincolo passato al metodo <xref:System.Windows.FrameworkElement.MeasureOverride%2A>.  
  
3. Il metodo <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> tenta di impostare il controllo ospitato sul vincolo di dimensione specificato.  
  
4. Se la proprietà <xref:System.Windows.Forms.Control.Size%2A> del controllo ospitato corrisponde al vincolo specificato, il controllo contenuto viene ridimensionato in modo da essere dimensionato per il vincolo.  
  
 Se la proprietà <xref:System.Windows.Forms.Control.Size%2A> non corrisponde al vincolo specificato, il controllo ospitato non supporta il ridimensionamento continuo. Ad esempio, il controllo <xref:System.Windows.Forms.MonthCalendar> consente solo dimensioni discrete. Le dimensioni consentite per questo controllo sono costituite da numeri interi (che rappresentano il numero di mesi) per altezza e larghezza. In casi come questo, l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> si comporta come segue:  
  
- Se la proprietà <xref:System.Windows.Forms.Control.Size%2A> restituisce una dimensione maggiore del vincolo specificato, l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> Ritaglia il controllo ospitato. L'altezza e la larghezza vengono gestite separatamente, quindi il controllo ospitato può essere ritagliato in entrambe le direzioni.  
  
- Se la proprietà <xref:System.Windows.Forms.Control.Size%2A> restituisce una dimensione inferiore a quella del vincolo specificato, <xref:System.Windows.Forms.Integration.WindowsFormsHost> accetta questo valore di dimensione e restituisce il valore al sistema di layout [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Procedura dettagliata: Disposizione di controlli Windows Form in WPF](walkthrough-arranging-windows-forms-controls-in-wpf.md)
- [Disposizione di controlli Windows Forms nell'esempio WPF](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml)
- [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md)
- [Migrazione e interoperabilità](migration-and-interoperability.md)
