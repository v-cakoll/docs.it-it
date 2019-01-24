---
title: "Ottimizzazione delle prestazioni: Comportamento dell'oggetto"
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
ms.openlocfilehash: 45e93e1ce7d4cca21019cd0be4547bdaa220c301
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631217"
---
# <a name="optimizing-performance-object-behavior"></a>Ottimizzazione delle prestazioni: Comportamento dell'oggetto
La comprensione del comportamento intrinseco degli oggetti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di trovare più facilmente il compromesso ideale tra funzionalità e prestazioni.  
  

  
<a name="Not_Removing_Event_Handlers"></a>   
## <a name="not-removing-event-handlers-on-objects-may-keep-objects-alive"></a>La mancata rimozione di gestori eventi dagli oggetti può mantenere gli oggetti attivi  
 Il delegato passato da un oggetto al relativo evento è di fatto un riferimento all'oggetto. I gestori eventi, quindi, possono mantenere gli oggetti attivi più a lungo del previsto. Quando si esegue la pulitura di un oggetto registrato per restare in ascolto di un evento dell'oggetto, è essenziale rimuovere il delegato prima di rilasciare l'oggetto. Mantenere attivi oggetti non necessari aumenta il consumo di memoria dell'applicazione, soprattutto se l'oggetto è la radice di un albero logico o di una struttura ad albero visuale.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è stato introdotto un modello di listener di eventi debole per eventi che possono rivelarsi utili in situazioni in cui è difficile tenere traccia delle relazioni di durata degli oggetti tra l'origine e il listener. Alcuni eventi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esistenti usano già questo modello, che può essere utile soprattutto per implementare oggetti con eventi personalizzati. Per informazioni dettagliate, vedere [Modelli di eventi deboli](../../../../docs/framework/wpf/advanced/weak-event-patterns.md).  
  
 Sono disponibili vari strumenti, ad esempio il profiler CLR e il visualizzatore del working set, in grado di fornire informazioni sul consumo di memoria di un determinato processo. Il profiler CLR include alcune visualizzazioni del profilo di allocazione molto utili, tra cui un istogramma dei tipi allocati, grafici delle allocazioni e delle chiamate, una cronologia delle operazioni di Garbage Collection di varie generazioni e lo stato dell'heap gestito che ne deriva e una struttura ad albero delle chiamate che mostra le allocazioni per metodo e i caricamenti degli assembly. Per altre informazioni, vedere [.NET Framework Developer Center](https://go.microsoft.com/fwlink/?LinkId=117435) (Centro sviluppatori per .NET Framework).  
  
<a name="DPs_and_Objects"></a>   
## <a name="dependency-properties-and-objects"></a>Proprietà e oggetti di dipendenza  
 In generale, l'accesso a una proprietà di dipendenza di un <xref:System.Windows.DependencyObject> non è più lento dell'accesso un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] proprietà. Nonostante un leggero sovraccarico delle prestazioni per l'impostazione del valore di una proprietà, è possibile ottenere un valore con la stessa rapidità con cui si ottiene il valore da una proprietà [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. Il sovraccarico delle prestazioni, infatti, è compensato dalla capacità delle proprietà di dipendenza di supportare funzionalità avanzate come il data binding, l'animazione, l'ereditarietà e l'applicazione di stili. Per altre informazioni, vedere [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
### <a name="dependencyproperty-optimizations"></a>Ottimizzazioni di DependencyProperty  
 È necessario definire le proprietà di dipendenza nell'applicazione con estrema attenzione. Se il <xref:System.Windows.DependencyProperty> influisce solo su rendering le opzioni dei metadati di tipo, anziché altre opzioni di metadati, ad esempio <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, è necessario contrassegnarlo come tale eseguendo l'override dei metadati. Per altre informazioni sull'override dei metadati delle proprietà o su come ottenere i metadati delle proprietà, vedere [Metadati delle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
 Nel caso in cui non tutte le modifiche alle proprietà influiscano effettivamente sulla misura, la disposizione e il rendering, può essere più vantaggioso avere un gestore delle modifiche alle proprietà che consenta di invalidare manualmente la misura, la disposizione e i passaggi di rendering. È possibile, ad esempio, decidere di eseguire nuovamente il rendering di uno sfondo solo se un valore è superiore a un limite impostato. In questo caso, il rendering verrebbe invalidato dal gestore delle modifiche alle proprietà solo se il valore supera il limite impostato.  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>Problemi legati alla possibilità di rendere ereditabile un oggetto DependencyProperty  
 Per impostazione predefinita, le proprietà di dipendenza registrate non sono ereditabili. È possibile tuttavia rendere ereditabile qualsiasi proprietà in modo esplicito. Sebbene possa essere utile, la conversione di una proprietà per renderla ereditabile incide sulle prestazioni, poiché aumenta la durata della procedura di annullamento della convalida della proprietà.  
  
### <a name="use-registerclasshandler-carefully"></a>Uso corretto di RegisterClassHandler  
 Durante la chiamata <xref:System.Windows.EventManager.RegisterClassHandler%2A> consente di salvare lo stato dell'istanza, è importante tenere presente che il gestore viene chiamato in ogni istanza, che può causare problemi di prestazioni. Usare solo <xref:System.Windows.EventManager.RegisterClassHandler%2A> quando l'applicazione è necessario salvare lo stato dell'istanza.  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>Impostazione del valore predefinito di un oggetto DependencyProperty durante le registrazione  
 Quando si crea una <xref:System.Windows.DependencyProperty> che richiede un valore predefinito, impostare il valore usando i metadati predefiniti passati come parametro per il <xref:System.Windows.DependencyProperty.Register%2A> metodo del <xref:System.Windows.DependencyProperty>. Usare questa tecnica, anziché impostare il valore della proprietà, in un costruttore o in ogni istanza di un elemento.  
  
### <a name="set-the-propertymetadata-value-using-register"></a>Impostazione del valore PropertyMetadata usando Register  
 Durante la creazione di un <xref:System.Windows.DependencyProperty>, è disponibile l'opzione di impostazione la <xref:System.Windows.PropertyMetadata> usando la <xref:System.Windows.DependencyProperty.Register%2A> o <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> metodi. Anche se l'oggetto può avere un costruttore statico da chiamare <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>, questo non è una soluzione ottimale e influirà sulle prestazioni. Per prestazioni ottimali, impostare il <xref:System.Windows.PropertyMetadata> durante la chiamata a <xref:System.Windows.DependencyProperty.Register%2A>.  
  
<a name="Freezable_Objects"></a>   
## <a name="freezable-objects"></a>Oggetti Freezable  
 Oggetto <xref:System.Windows.Freezable> è un tipo speciale di oggetto che dispone di due stati: non bloccato e bloccato. Bloccare gli oggetti ogni volta che è possibile migliora le prestazioni dell'applicazione e ne riduce il working set. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Ciascuna <xref:System.Windows.Freezable> ha un <xref:System.Windows.Freezable.Changed> evento generato quando viene modificato. Le notifiche di modifica, tuttavia, sono molto dispendiose in termini di prestazioni dell'applicazione.  
  
 Si consideri l'esempio seguente in cui ogni <xref:System.Windows.Shapes.Rectangle> Usa lo stesso <xref:System.Windows.Media.Brush> oggetto:  
  
 [!code-csharp[Performance#PerformanceSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 Per impostazione predefinita [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un gestore eventi per il <xref:System.Windows.Media.SolidColorBrush> dell'oggetto <xref:System.Windows.Freezable.Changed> evento per poter invalidare la <xref:System.Windows.Shapes.Rectangle> dell'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà. In questo caso, ogni volta che il <xref:System.Windows.Media.SolidColorBrush> deve essere generato da relativo <xref:System.Windows.Freezable.Changed> , è necessario richiamare la funzione di callback per ogni evento <xref:System.Windows.Shapes.Rectangle>, ovvero l'accumulo di queste chiamate alla funzione di callback impongano una riduzione significativa delle prestazioni. Ma non solo: per aggiungere e rimuovere gestori in questa fase, l'applicazione deve scorrere tutto l'elenco, con un considerevole dispendio di prestazioni. Se lo scenario dell'applicazione non cambi mai il <xref:System.Windows.Media.SolidColorBrush>, si sosterranno spese i costi di manutenzione <xref:System.Windows.Freezable.Changed> gestori eventi inutilmente.  
  
 Il blocco di un <xref:System.Windows.Freezable> può migliorare le prestazioni, poiché non è più necessario impiegare risorse nella gestione delle notifiche di modifica. La tabella seguente mostra le dimensioni di una semplice <xref:System.Windows.Media.SolidColorBrush> quando relativi <xref:System.Windows.Freezable.IsFrozen%2A> è impostata su `true`, rispetto a quando non è. Si presuppone l'applicazione di un pennello per il <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà fino a dieci volte <xref:System.Windows.Shapes.Rectangle> oggetti.  
  
|**Stato**|**Dimensione**|  
|---------------|--------------|  
|Bloccato <xref:System.Windows.Media.SolidColorBrush>|212 byte|  
|Non bloccato <xref:System.Windows.Media.SolidColorBrush>|972 byte|  
  
 Nell'esempio di codice seguente viene dimostrato questo concetto:  
  
 [!code-csharp[Performance#PerformanceSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>Gestori modificati su oggetti Freezable non bloccati possono mantenere gli oggetti attivi  
 Il delegato passato da un oggetto a un <xref:System.Windows.Freezable> dell'oggetto <xref:System.Windows.Freezable.Changed> evento è effettivamente un riferimento a tale oggetto. Pertanto, <xref:System.Windows.Freezable.Changed> gestori di eventi possono mantenere oggetti attivi più a lungo del previsto. Quando si esegue la pulitura di un oggetto che ha registrato per l'ascolto di un <xref:System.Windows.Freezable> dell'oggetto <xref:System.Windows.Freezable.Changed> evento, è essenziale rimuovere il delegato prima di rilasciare l'oggetto.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue anche l'associazione <xref:System.Windows.Freezable.Changed> eventi internamente. Ad esempio, tutte le proprietà di dipendenza che accettano <xref:System.Windows.Freezable> come un valore resterà in ascolto <xref:System.Windows.Freezable.Changed> eventi automaticamente. Il <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà, che accetta un <xref:System.Windows.Media.Brush>, viene illustrato questo concetto.  
  
 [!code-csharp[Performance#PerformanceSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 Per l'assegnazione di `myBrush` a `myRectangle.Fill`, un delegato che punta al <xref:System.Windows.Shapes.Rectangle> oggetto verrà aggiunto al <xref:System.Windows.Media.SolidColorBrush> dell'oggetto <xref:System.Windows.Freezable.Changed> evento. Nel codice seguente, quindi, `myRect` non viene reso idoneo per operazioni di Garbage Collection:  
  
 [!code-csharp[Performance#PerformanceSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 In questo caso `myBrush` mantiene `myRectangle` attivo e lo richiama ad esso quando viene attivato il <xref:System.Windows.Freezable.Changed> evento. Si noti che l'assegnazione `myBrush` per il <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà di un nuovo <xref:System.Windows.Shapes.Rectangle> aggiunga semplicemente un altro gestore eventi per `myBrush`.  
  
 Il metodo consigliato per la pulizia di questi tipi di oggetti consiste nel rimuovere la <xref:System.Windows.Media.Brush> dal <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà, che a sua volta rimuoverà il <xref:System.Windows.Freezable.Changed> gestore dell'evento.  
  
 [!code-csharp[Performance#PerformanceSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## <a name="user-interface-virtualization"></a>Virtualizzazione dell'interfaccia utente  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce inoltre una variazione del <xref:System.Windows.Controls.StackPanel> elemento che virtualizza automaticamente "il" contenuto figlio associato a dati. In questo contesto il termine virtualizzare si riferisce a una tecnica grazie alla quale, a partire da un numero più elevato di elementi dati, viene generato un subset di oggetti in base agli elementi visibili sullo schermo. La generazione di un elevato numero di elementi dell'interfaccia utente, quando solo alcuni possono essere visualizzati sullo schermo in un momento specifico, richiede un consumo intensivo di risorse in termini sia di memoria sia di processore. <xref:System.Windows.Controls.VirtualizingStackPanel> (tramite la funzionalità fornita da <xref:System.Windows.Controls.VirtualizingPanel>) calcola gli elementi visibili e funziona con il <xref:System.Windows.Controls.ItemContainerGenerator> da un <xref:System.Windows.Controls.ItemsControl> (ad esempio <xref:System.Windows.Controls.ListBox> o <xref:System.Windows.Controls.ListView>) soltanto di creare gli elementi per gli elementi visibili.  
  
 Per ottimizzare le prestazioni, gli oggetti visivi per questi elementi vengono generati o mantenuti attivi solo se sono visibili sullo schermo. Quando non si trovano più nell'area visualizzabile del controllo, gli oggetti visibili possono essere rimossi. Questa operazione non deve essere confusa con la virtualizzazione dei dati, in cui gli oggetti dati non sono tutti presenti nella raccolta locale, ma trasmessi a seconda delle esigenze.  
  
 La tabella seguente mostra il tempo trascorso aggiunta e il rendering di 5000 <xref:System.Windows.Controls.TextBlock> elementi da un <xref:System.Windows.Controls.StackPanel> e un <xref:System.Windows.Controls.VirtualizingStackPanel>. In questo scenario, le misure rappresentano il tempo compreso tra il collegamento di una stringa di testo per il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà di un <xref:System.Windows.Controls.ItemsControl> oggetto e il tempo quando gli elementi del pannello Visualizza la stringa di testo.  
  
|**Pannello host**|**Tempo di rendering (ms)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>Vedere anche
- [Ottimizzazione delle prestazioni di applicazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
- [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Risorse di applicazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)
- [per](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)
- [Data binding](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Altri suggerimenti relativi alle prestazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
