---
title: 'Ottimizzazione delle prestazioni: comportamento degli oggetti'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user interface virtualization [WPF]
- dependency properties [WPF], performance
- event handlers [WPF]
- object performance considerations [WPF]
- Freezable objects [WPF], performance
ms.assetid: 73aa2f47-1d73-439a-be1f-78dc4ba2b5bd
ms.openlocfilehash: 64e567cd28e9458b483b0963e0dedd924ad23bab
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094488"
---
# <a name="optimizing-performance-object-behavior"></a>Ottimizzazione delle prestazioni: comportamento degli oggetti
La comprensione del comportamento intrinseco degli oggetti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di trovare più facilmente il compromesso ideale tra funzionalità e prestazioni.  

<a name="Not_Removing_Event_Handlers"></a>   
## <a name="not-removing-event-handlers-on-objects-may-keep-objects-alive"></a>La mancata rimozione di gestori eventi dagli oggetti può mantenere gli oggetti attivi  
 Il delegato passato da un oggetto al relativo evento è di fatto un riferimento all'oggetto. I gestori eventi, quindi, possono mantenere gli oggetti attivi più a lungo del previsto. Quando si esegue la pulitura di un oggetto registrato per restare in ascolto di un evento dell'oggetto, è essenziale rimuovere il delegato prima di rilasciare l'oggetto. Mantenere attivi oggetti non necessari aumenta il consumo di memoria dell'applicazione, soprattutto se l'oggetto è la radice di un albero logico o di una struttura ad albero visuale.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è stato introdotto un modello di listener di eventi debole per eventi che possono rivelarsi utili in situazioni in cui è difficile tenere traccia delle relazioni di durata degli oggetti tra l'origine e il listener. Alcuni eventi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esistenti usano già questo modello, che può essere utile soprattutto per implementare oggetti con eventi personalizzati. Per informazioni dettagliate, vedere [Modelli di eventi deboli](weak-event-patterns.md).  
  
 Sono disponibili vari strumenti, ad esempio il profiler CLR e il visualizzatore del working set, in grado di fornire informazioni sul consumo di memoria di un determinato processo. Il profiler CLR include alcune visualizzazioni del profilo di allocazione molto utili, tra cui un istogramma dei tipi allocati, grafici delle allocazioni e delle chiamate, una cronologia delle operazioni di Garbage Collection di varie generazioni e lo stato dell'heap gestito che ne deriva e una struttura ad albero delle chiamate che mostra le allocazioni per metodo e i caricamenti degli assembly. Per altre informazioni, vedere [Prestazioni](https://docs.microsoft.com/previous-versions/aa497289(v=msdn.10)).  
  
<a name="DPs_and_Objects"></a>   
## <a name="dependency-properties-and-objects"></a>Proprietà e oggetti di dipendenza  
 In generale, l'accesso a una proprietà di dipendenza di un <xref:System.Windows.DependencyObject> non è più lento dell'accesso a una proprietà CLR. Sebbene si verifichi un lieve sovraccarico delle prestazioni per l'impostazione di un valore di proprietà, il recupero di un valore è rapido quanto il recupero del valore da una proprietà CLR. Il sovraccarico delle prestazioni, infatti, è compensato dalla capacità delle proprietà di dipendenza di supportare funzionalità avanzate come il data binding, l'animazione, l'ereditarietà e l'applicazione di stili. Per altre informazioni, vedere [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md).  
  
### <a name="dependencyproperty-optimizations"></a>Ottimizzazioni di DependencyProperty  
 È necessario definire le proprietà di dipendenza nell'applicazione con estrema attenzione. Se il <xref:System.Windows.DependencyProperty> interessa solo le opzioni dei metadati del tipo di rendering, anziché altre opzioni di metadati, ad esempio <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, è necessario contrassegnarlo come tale eseguendo l'override dei relativi metadati. Per altre informazioni sull'override dei metadati delle proprietà o su come ottenere i metadati delle proprietà, vedere [Metadati delle proprietà di dipendenza](dependency-property-metadata.md).  
  
 Nel caso in cui non tutte le modifiche alle proprietà influiscano effettivamente sulla misura, la disposizione e il rendering, può essere più vantaggioso avere un gestore delle modifiche alle proprietà che consenta di invalidare manualmente la misura, la disposizione e i passaggi di rendering. È possibile, ad esempio, decidere di eseguire nuovamente il rendering di uno sfondo solo se un valore è superiore a un limite impostato. In questo caso, il rendering verrebbe invalidato dal gestore delle modifiche alle proprietà solo se il valore supera il limite impostato.  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>Problemi legati alla possibilità di rendere ereditabile un oggetto DependencyProperty  
 Per impostazione predefinita, le proprietà di dipendenza registrate non sono ereditabili. È possibile tuttavia rendere ereditabile qualsiasi proprietà in modo esplicito. Sebbene possa essere utile, la conversione di una proprietà per renderla ereditabile incide sulle prestazioni, poiché aumenta la durata della procedura di annullamento della convalida della proprietà.  
  
### <a name="use-registerclasshandler-carefully"></a>Uso corretto di RegisterClassHandler  
 Quando si chiama <xref:System.Windows.EventManager.RegisterClassHandler%2A> consente di salvare lo stato dell'istanza, è importante tenere presente che il gestore viene chiamato su ogni istanza, che può causare problemi di prestazioni. Usare <xref:System.Windows.EventManager.RegisterClassHandler%2A> solo quando l'applicazione richiede di salvare lo stato dell'istanza.  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>Impostazione del valore predefinito di un oggetto DependencyProperty durante le registrazione  
 Quando si crea un <xref:System.Windows.DependencyProperty> che richiede un valore predefinito, impostare il valore utilizzando i metadati predefiniti passati come parametro al metodo <xref:System.Windows.DependencyProperty.Register%2A> della <xref:System.Windows.DependencyProperty>. Usare questa tecnica, anziché impostare il valore della proprietà, in un costruttore o in ogni istanza di un elemento.  
  
### <a name="set-the-propertymetadata-value-using-register"></a>Impostazione del valore PropertyMetadata usando Register  
 Quando si crea una <xref:System.Windows.DependencyProperty>, è possibile impostare l'<xref:System.Windows.PropertyMetadata> utilizzando i metodi <xref:System.Windows.DependencyProperty.Register%2A> o <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>. Sebbene l'oggetto possa avere un costruttore statico per chiamare <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>, questa non è la soluzione ottimale e avrà un effetto sulle prestazioni. Per ottenere prestazioni ottimali, impostare il <xref:System.Windows.PropertyMetadata> durante la chiamata al <xref:System.Windows.DependencyProperty.Register%2A>.  
  
<a name="Freezable_Objects"></a>   
## <a name="freezable-objects"></a>Oggetti Freezable  
 Un <xref:System.Windows.Freezable> è un tipo speciale di oggetto con due stati: non bloccato e bloccato. Bloccare gli oggetti ogni volta che è possibile migliora le prestazioni dell'applicazione e ne riduce il working set. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).  
  
 Ogni <xref:System.Windows.Freezable> dispone di un evento <xref:System.Windows.Freezable.Changed> che viene generato ogni volta che viene modificato. Le notifiche di modifica, tuttavia, sono molto dispendiose in termini di prestazioni dell'applicazione.  
  
 Si consideri l'esempio seguente in cui ogni <xref:System.Windows.Shapes.Rectangle> utilizza lo stesso oggetto <xref:System.Windows.Media.Brush>:  
  
 [!code-csharp[Performance#PerformanceSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 Per impostazione predefinita, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un gestore eventi per l'evento <xref:System.Windows.Freezable.Changed> dell'oggetto <xref:System.Windows.Media.SolidColorBrush> per invalidare la proprietà <xref:System.Windows.Shapes.Shape.Fill%2A> dell'oggetto <xref:System.Windows.Shapes.Rectangle>. In questo caso, ogni volta che il <xref:System.Windows.Media.SolidColorBrush> deve generare l'evento <xref:System.Windows.Freezable.Changed>, è necessario richiamare la funzione di callback per ogni <xref:System.Windows.Shapes.Rectangle>: l'accumulo di queste chiamate di funzione di callback impone una riduzione significativa delle prestazioni. Ma non solo: per aggiungere e rimuovere gestori in questa fase, l'applicazione deve scorrere tutto l'elenco, con un considerevole dispendio di prestazioni. Se lo scenario dell'applicazione non modifica mai il <xref:System.Windows.Media.SolidColorBrush>, si pagherà il costo della gestione inutilmente dei gestori di eventi <xref:System.Windows.Freezable.Changed>.  
  
 Il blocco di un <xref:System.Windows.Freezable> può migliorare le prestazioni, perché non è più necessario spendere risorse per la gestione delle notifiche di modifica. Nella tabella seguente viene illustrata la dimensione di una semplice <xref:System.Windows.Media.SolidColorBrush> quando la relativa proprietà <xref:System.Windows.Freezable.IsFrozen%2A> è impostata su `true`, rispetto a quando non lo è. In questo modo si presuppone l'applicazione di un pennello alla proprietà <xref:System.Windows.Shapes.Shape.Fill%2A> di dieci oggetti <xref:System.Windows.Shapes.Rectangle>.  
  
|**State**|**Dimensione**|  
|---------------|--------------|  
|<xref:System.Windows.Media.SolidColorBrush> bloccati|212 byte|  
|<xref:System.Windows.Media.SolidColorBrush> non bloccati|972 byte|  
  
 Nell'esempio di codice seguente viene dimostrato questo concetto:  
  
 [!code-csharp[Performance#PerformanceSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>Gestori modificati su oggetti Freezable non bloccati possono mantenere gli oggetti attivi  
 Il delegato passato da un oggetto a un evento <xref:System.Windows.Freezable.Changed> dell'oggetto <xref:System.Windows.Freezable> è effettivamente un riferimento a tale oggetto. I gestori eventi <xref:System.Windows.Freezable.Changed> possono pertanto mantengono gli oggetti attivi più a lungo del previsto. Quando si esegue la pulizia di un oggetto che è stato registrato per restare in ascolto di un evento <xref:System.Windows.Freezable.Changed> dell'oggetto <xref:System.Windows.Freezable>, è essenziale rimuovere il delegato prima di rilasciare l'oggetto.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] associa anche gli eventi <xref:System.Windows.Freezable.Changed> internamente. Ad esempio, tutte le proprietà di dipendenza che accettano <xref:System.Windows.Freezable> come valore ascolteranno automaticamente <xref:System.Windows.Freezable.Changed> eventi. La proprietà <xref:System.Windows.Shapes.Shape.Fill%2A>, che accetta un <xref:System.Windows.Media.Brush>, illustra questo concetto.  
  
 [!code-csharp[Performance#PerformanceSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 Nell'assegnazione di `myBrush` `myRectangle.Fill`, un delegato che fa riferimento all'oggetto <xref:System.Windows.Shapes.Rectangle> verrà aggiunto all'evento <xref:System.Windows.Freezable.Changed> dell'oggetto <xref:System.Windows.Media.SolidColorBrush>. Nel codice seguente, quindi, `myRect` non viene reso idoneo per operazioni di Garbage Collection:  
  
 [!code-csharp[Performance#PerformanceSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 In questo caso `myBrush` mantiene sempre `myRectangle` attivo e richiamerà il computer quando genera il relativo evento di <xref:System.Windows.Freezable.Changed>. Si noti che l'assegnazione di `myBrush` alla proprietà <xref:System.Windows.Shapes.Shape.Fill%2A> di un nuovo <xref:System.Windows.Shapes.Rectangle> aggiungerà semplicemente un altro gestore eventi a `myBrush`.  
  
 Il metodo consigliato per pulire questi tipi di oggetti consiste nel rimuovere il <xref:System.Windows.Media.Brush> dalla proprietà <xref:System.Windows.Shapes.Shape.Fill%2A>, che a sua volta rimuoverà il gestore dell'evento <xref:System.Windows.Freezable.Changed>.  
  
 [!code-csharp[Performance#PerformanceSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## <a name="user-interface-virtualization"></a>Virtualizzazione dell'interfaccia utente  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce inoltre una variante dell'elemento <xref:System.Windows.Controls.StackPanel> che "virtualizza" automaticamente il contenuto figlio associato a dati. In questo contesto il termine virtualizzare si riferisce a una tecnica grazie alla quale, a partire da un numero più elevato di elementi dati, viene generato un subset di oggetti in base agli elementi visibili sullo schermo. La generazione di un elevato numero di elementi dell'interfaccia utente, quando solo alcuni possono essere visualizzati sullo schermo in un momento specifico, richiede un consumo intensivo di risorse sia in termini di memoria che di processore. <xref:System.Windows.Controls.VirtualizingStackPanel> (tramite la funzionalità fornita da <xref:System.Windows.Controls.VirtualizingPanel>) calcola gli elementi visibili e utilizza il <xref:System.Windows.Controls.ItemContainerGenerator> da un <xref:System.Windows.Controls.ItemsControl> (ad esempio <xref:System.Windows.Controls.ListBox> o <xref:System.Windows.Controls.ListView>) per creare solo elementi per gli elementi visibili.  
  
 Per ottimizzare le prestazioni, gli oggetti visivi per questi elementi vengono generati o mantenuti attivi solo se sono visibili sullo schermo. Quando non si trovano più nell'area visualizzabile del controllo, gli oggetti visibili possono essere rimossi. Questa operazione non deve essere confusa con la virtualizzazione dei dati, in cui gli oggetti dati non sono tutti presenti nella raccolta locale, ma trasmessi a seconda delle esigenze.  
  
 La tabella seguente mostra il tempo trascorso per l'aggiunta e il rendering di 5000 elementi <xref:System.Windows.Controls.TextBlock> a una <xref:System.Windows.Controls.StackPanel> e a un <xref:System.Windows.Controls.VirtualizingStackPanel>. In questo scenario, le misurazioni rappresentano il tempo che intercorre tra la connessione di una stringa di testo alla proprietà <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> di un oggetto <xref:System.Windows.Controls.ItemsControl> al momento in cui gli elementi del pannello visualizzano la stringa di testo.  
  
|**Pannello host**|**Tempo di rendering (ms)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica bidimensionale e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Risorse di applicazioni](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Data binding](optimizing-performance-data-binding.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
