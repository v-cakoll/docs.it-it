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
ms.openlocfilehash: 67184db7fc1459e83ac7b1e6ff09ef56e43f0ca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187071"
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
 In generale, l'accesso a <xref:System.Windows.DependencyObject> una proprietà di dipendenza di un oggetto non è più lento dell'accesso a una proprietà CLR. Mentre c'è un piccolo sovraccarico delle prestazioni per l'impostazione di un valore di proprietà, ottenere un valore è veloce come ottenere il valore da una proprietà CLR. Il sovraccarico delle prestazioni, infatti, è compensato dalla capacità delle proprietà di dipendenza di supportare funzionalità avanzate come il data binding, l'animazione, l'ereditarietà e l'applicazione di stili. Per altre informazioni, vedere [Panoramica  sulle proprietà di dipendenza](dependency-properties-overview.md).  
  
### <a name="dependencyproperty-optimizations"></a>Ottimizzazioni di DependencyProperty  
 È necessario definire le proprietà di dipendenza nell'applicazione con estrema attenzione. Se <xref:System.Windows.DependencyProperty> l'opzione esegue il rendering delle opzioni <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>dei metadati del tipo, anziché di altre opzioni di metadati, ad esempio , è necessario contrassegnarla come tale eseguendo l'override dei relativi metadati. Per altre informazioni sull'override dei metadati delle proprietà o su come ottenere i metadati delle proprietà, vedere [Metadati delle proprietà di dipendenza](dependency-property-metadata.md).  
  
 Nel caso in cui non tutte le modifiche alle proprietà influiscano effettivamente sulla misura, la disposizione e il rendering, può essere più vantaggioso avere un gestore delle modifiche alle proprietà che consenta di invalidare manualmente la misura, la disposizione e i passaggi di rendering. È possibile, ad esempio, decidere di eseguire nuovamente il rendering di uno sfondo solo se un valore è superiore a un limite impostato. In questo caso, il rendering verrebbe invalidato dal gestore delle modifiche alle proprietà solo se il valore supera il limite impostato.  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>Problemi legati alla possibilità di rendere ereditabile un oggetto DependencyProperty  
 Per impostazione predefinita, le proprietà di dipendenza registrate non sono ereditabili. È possibile tuttavia rendere ereditabile qualsiasi proprietà in modo esplicito. Sebbene possa essere utile, la conversione di una proprietà per renderla ereditabile incide sulle prestazioni, poiché aumenta la durata della procedura di annullamento della convalida della proprietà.  
  
### <a name="use-registerclasshandler-carefully"></a>Uso corretto di RegisterClassHandler  
 Mentre <xref:System.Windows.EventManager.RegisterClassHandler%2A> la chiamata consente di salvare lo stato dell'istanza, è importante tenere presente che il gestore viene chiamato su ogni istanza, che può causare problemi di prestazioni. Utilizzare <xref:System.Windows.EventManager.RegisterClassHandler%2A> solo quando l'applicazione richiede il salvataggio dello stato dell'istanza.  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>Impostazione del valore predefinito di un oggetto DependencyProperty durante le registrazione  
 Quando si <xref:System.Windows.DependencyProperty> crea un oggetto che richiede un valore predefinito, impostare il valore utilizzando i metadati predefiniti passati come parametro sul <xref:System.Windows.DependencyProperty.Register%2A> metodo dell'oggetto <xref:System.Windows.DependencyProperty>. Usare questa tecnica, anziché impostare il valore della proprietà, in un costruttore o in ogni istanza di un elemento.  
  
### <a name="set-the-propertymetadata-value-using-register"></a>Impostazione del valore PropertyMetadata usando Register  
 Quando si <xref:System.Windows.DependencyProperty>crea un oggetto , <xref:System.Windows.PropertyMetadata> è <xref:System.Windows.DependencyProperty.Register%2A> possibile <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> impostare i metodi o . Anche se l'oggetto potrebbe <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>avere un costruttore statico da chiamare , questa non è la soluzione ottimale e influirà sulle prestazioni. Per ottenere prestazioni <xref:System.Windows.PropertyMetadata> ottimali, <xref:System.Windows.DependencyProperty.Register%2A>impostare durante la chiamata a .  
  
<a name="Freezable_Objects"></a>
## <a name="freezable-objects"></a>Oggetti Freezable  
 A <xref:System.Windows.Freezable> è un tipo speciale di oggetto che ha due stati: non bloccato e congelato. Bloccare gli oggetti ogni volta che è possibile migliora le prestazioni dell'applicazione e ne riduce il working set. Per altre informazioni, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).  
  
 Ognuno <xref:System.Windows.Freezable> <xref:System.Windows.Freezable.Changed> ha un evento che viene generato ogni volta che cambia. Le notifiche di modifica, tuttavia, sono molto dispendiose in termini di prestazioni dell'applicazione.  
  
 Si consideri l'esempio seguente in cui ognuno utilizza lo stesso oggetto:Consider the following example in which each <xref:System.Windows.Shapes.Rectangle> uses the same <xref:System.Windows.Media.Brush> object:  
  
 [!code-csharp[Performance#PerformanceSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 Per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] impostazione predefinita, fornisce <xref:System.Windows.Media.SolidColorBrush> un <xref:System.Windows.Freezable.Changed> gestore eventi per <xref:System.Windows.Shapes.Rectangle> l'evento <xref:System.Windows.Shapes.Shape.Fill%2A> dell'oggetto per invalidare la proprietà dell'oggetto. In questo caso, <xref:System.Windows.Media.SolidColorBrush> ogni volta <xref:System.Windows.Freezable.Changed> che deve generare il proprio <xref:System.Windows.Shapes.Rectangle>evento è necessario richiamare la funzione di callback per ogni, ovvero l'accumulo di queste chiamate di funzione di callback impone una riduzione significativa delle prestazioni. Ma non solo: per aggiungere e rimuovere gestori in questa fase, l'applicazione deve scorrere tutto l'elenco, con un considerevole dispendio di prestazioni. Se lo scenario dell'applicazione non modifica mai <xref:System.Windows.Media.SolidColorBrush> <xref:System.Windows.Freezable.Changed> il , si pagherà il costo della gestione dei gestori eventi inutilmente.  
  
 Il <xref:System.Windows.Freezable> blocco di un può migliorare le prestazioni, perché non è più necessario spendere risorse per la gestione delle notifiche di modifica. La tabella seguente mostra le <xref:System.Windows.Media.SolidColorBrush> dimensioni <xref:System.Windows.Freezable.IsFrozen%2A> di un `true`elemento semplice quando la relativa proprietà è impostata su , rispetto a quando non lo è. Si presuppone l'applicazione di <xref:System.Windows.Shapes.Shape.Fill%2A> un <xref:System.Windows.Shapes.Rectangle> pennello alla proprietà di dieci oggetti.  
  
|**Stato**|**Dimensione**|  
|---------------|--------------|  
|Congelato<xref:System.Windows.Media.SolidColorBrush>|212 byte|  
|Non congelato<xref:System.Windows.Media.SolidColorBrush>|972 byte|  
  
 Nell'esempio di codice seguente viene dimostrato questo concetto:  
  
 [!code-csharp[Performance#PerformanceSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>Gestori modificati su oggetti Freezable non bloccati possono mantenere gli oggetti attivi  
 Il delegato che un <xref:System.Windows.Freezable> oggetto passa <xref:System.Windows.Freezable.Changed> all'evento di un oggetto è effettivamente un riferimento a tale oggetto. Pertanto, <xref:System.Windows.Freezable.Changed> i gestori eventi possono mantenere gli oggetti attivi più a lungo del previsto. Quando si esegue la pulizia di un <xref:System.Windows.Freezable> oggetto registrato <xref:System.Windows.Freezable.Changed> per l'ascolto dell'evento di un oggetto, è essenziale rimuovere tale delegato prima di rilasciare l'oggetto.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]aggancia <xref:System.Windows.Freezable.Changed> gli eventi internamente. Ad esempio, tutte le <xref:System.Windows.Freezable> proprietà di dipendenza <xref:System.Windows.Freezable.Changed> che accettano come valore ascolteranno automaticamente gli eventi. La <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà , <xref:System.Windows.Media.Brush>che accetta un oggetto , illustra questo concetto.  
  
 [!code-csharp[Performance#PerformanceSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 Nell'assegnazione `myBrush` `myRectangle.Fill`di a , un <xref:System.Windows.Shapes.Rectangle> delegato che punta <xref:System.Windows.Media.SolidColorBrush> all'oggetto <xref:System.Windows.Freezable.Changed> verrà aggiunto all'evento dell'oggetto. Nel codice seguente, quindi, `myRect` non viene reso idoneo per operazioni di Garbage Collection:  
  
 [!code-csharp[Performance#PerformanceSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 In questo `myBrush` caso `myRectangle` è ancora attivo e richiamerà <xref:System.Windows.Freezable.Changed> ad esso quando viene generato il suo evento. Si noti `myBrush` che <xref:System.Windows.Shapes.Shape.Fill%2A> l'assegnazione alla proprietà di un nuovo <xref:System.Windows.Shapes.Rectangle> aggiungerà semplicemente un altro gestore eventi a `myBrush`.  
  
 Il modo consigliato per pulire questi tipi <xref:System.Windows.Media.Brush> di <xref:System.Windows.Shapes.Shape.Fill%2A> oggetti consiste nel rimuovere <xref:System.Windows.Freezable.Changed> l'oggetto dalla proprietà, che a sua volta rimuoverà il gestore eventi.  
  
 [!code-csharp[Performance#PerformanceSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>
## <a name="user-interface-virtualization"></a>Virtualizzazione dell'interfaccia utente  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce inoltre una <xref:System.Windows.Controls.StackPanel> variante dell'elemento che "virtualizza" automaticamente il contenuto figlio associato a dati. In questo contesto il termine virtualizzare si riferisce a una tecnica grazie alla quale, a partire da un numero più elevato di elementi dati, viene generato un subset di oggetti in base agli elementi visibili sullo schermo. La generazione di un elevato numero di elementi dell'interfaccia utente, quando solo alcuni possono essere visualizzati sullo schermo in un momento specifico, richiede un consumo intensivo di risorse in termini sia di memoria sia di processore. <xref:System.Windows.Controls.VirtualizingStackPanel>(tramite la <xref:System.Windows.Controls.VirtualizingPanel>funzionalità fornita da ) <xref:System.Windows.Controls.ItemContainerGenerator> calcola <xref:System.Windows.Controls.ItemsControl> gli <xref:System.Windows.Controls.ListBox> elementi <xref:System.Windows.Controls.ListView>visibili e utilizza l'oggetto da un (ad esempio o ) per creare elementi solo per gli elementi visibili.  
  
 Per ottimizzare le prestazioni, gli oggetti visivi per questi elementi vengono generati o mantenuti attivi solo se sono visibili sullo schermo. Quando non si trovano più nell'area visualizzabile del controllo, gli oggetti visibili possono essere rimossi. Questa operazione non deve essere confusa con la virtualizzazione dei dati, in cui gli oggetti dati non sono tutti presenti nella raccolta locale, ma trasmessi a seconda delle esigenze.  
  
 La tabella seguente mostra il tempo trascorso aggiungendo <xref:System.Windows.Controls.TextBlock> e visualizzando 5000 elementi a a <xref:System.Windows.Controls.StackPanel> e a <xref:System.Windows.Controls.VirtualizingStackPanel>. In questo scenario, le misure rappresentano il tempo che <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> intersea va dall'associazione di una stringa di testo alla proprietà di un <xref:System.Windows.Controls.ItemsControl> oggetto e al momento in cui gli elementi del pannello visualizzano la stringa di testo.  
  
|**Pannello host**|**Tempo di rendering (ms)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica 2D e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Risorse dell'applicazione](optimizing-performance-application-resources.md)
- [Testo](optimizing-performance-text.md)
- [Associazione dati](optimizing-performance-data-binding.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
