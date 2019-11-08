---
title: 'Ottimizzazione delle prestazioni: associazione dati'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 9b302be3ed9f01ccd27470063f49966dc7d74708
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740804"
---
# <a name="optimizing-performance-data-binding"></a>Ottimizzazione delle prestazioni: associazione dati
Il data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] rappresenta per le applicazioni un modo semplice e coerente di presentare i dati e interagire con essi. Gli elementi possono essere associati a dati da un'ampia gamma di origini dati sotto forma di oggetti CLR e XML.  
  
 Questo argomento offre utili suggerimenti sulle prestazioni del data binding.  

<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>Risoluzione dei riferimenti di data binding  
 Prima di trattare i problemi di prestazioni del data binding, è opportuno scoprire come vengono risolti dal motore di data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] i riferimenti agli oggetti per il binding.  
  
 L'origine di un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] data binding può essere qualsiasi oggetto CLR. È possibile eseguire l'associazione a proprietà, sottoproprietà o indicizzatori di un oggetto CLR. I riferimenti di associazione vengono risolti tramite Microsoft .NET Reflection del Framework o una <xref:System.ComponentModel.ICustomTypeDescriptor>. Di seguito vengono descritti i tre metodi disponibili per risolvere riferimenti a oggetti per il data binding.  
  
 Il primo metodo prevede l'uso della reflection. In questo caso, l'oggetto <xref:System.Reflection.PropertyInfo> viene usato per individuare gli attributi della proprietà e fornisce l'accesso ai metadati della proprietà. Quando si usa l'interfaccia <xref:System.ComponentModel.ICustomTypeDescriptor>, il motore di data binding usa questa interfaccia per accedere ai valori delle proprietà. L'interfaccia <xref:System.ComponentModel.ICustomTypeDescriptor> è particolarmente utile nei casi in cui l'oggetto non dispone di un set statico di proprietà.  
  
 Le notifiche di modifica delle proprietà possono essere fornite implementando l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> o utilizzando le notifiche di modifica associate al <xref:System.ComponentModel.TypeDescriptor>. Tuttavia, la strategia consigliata per l'implementazione delle notifiche delle modifiche delle proprietà consiste nell'utilizzare <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Se l'oggetto di origine è un oggetto CLR e la proprietà di origine è una proprietà CLR, il motore di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] data binding deve innanzitutto utilizzare la reflection sull'oggetto di origine per ottenere il <xref:System.ComponentModel.TypeDescriptor>, quindi eseguire una query per una <xref:System.ComponentModel.PropertyDescriptor>. Questa sequenza di operazioni di reflection richiede potenzialmente molto tempo da un punto di vista delle prestazioni.  
  
 Il secondo metodo per la risoluzione dei riferimenti a oggetti comporta un oggetto di origine CLR che implementa l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> e una proprietà di origine che è una proprietà CLR. In questo caso, il motore di data binding usa direttamente la reflection sul tipo di origine e ottiene la proprietà necessaria. Sebbene presenti requisiti del working set inferiori rispetto al primo metodo, non si tratta ancora del metodo ottimale.  
  
 Il terzo metodo per la risoluzione dei riferimenti a oggetti prevede l'uso di un oggetto di origine che è un <xref:System.Windows.DependencyObject> e una proprietà di origine <xref:System.Windows.DependencyProperty>. In questo caso, non è necessario che il motore di data binding usi la reflection: il motore della proprietà e il motore di data binding risolvono il riferimento alla proprietà in modo indipendente. Si tratta del metodo ottimale per la risoluzione dei riferimenti a oggetti usati per il data binding.  
  
 Nella tabella seguente viene confrontata la velocità di data binding la proprietà <xref:System.Windows.Controls.TextBlock.Text%2A> di elementi <xref:System.Windows.Controls.TextBlock> 1000 usando questi tre metodi.  
  
|**Binding della proprietà Text di un TextBlock**|**Tempo di binding (ms)**|**Tempo di rendering: include il binding (ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|A una proprietà di un oggetto CLR|115|314|  
|A una proprietà di un oggetto CLR che implementa <xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|A un <xref:System.Windows.DependencyProperty> di un <xref:System.Windows.DependencyObject>.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## <a name="binding-to-large-clr-objects"></a>Binding a oggetti CLR di grandi dimensioni  
 Quando si esegue l'associazione dati a un singolo oggetto CLR con migliaia di proprietà, si verifica un notevole impatto sulle prestazioni. È possibile ridurre questo effetto dividendo il singolo oggetto in più oggetti CLR con un minor numero di proprietà. La tabella mostra i tempi di binding e di rendering per data binding a un singolo oggetto CLR di grandi dimensioni rispetto a più oggetti più piccoli.  
  
|**Data binding di 1000 oggetti TextBlock**|**Tempo di binding (ms)**|**Tempo di rendering: include il binding (ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|A un oggetto CLR con proprietà 1000|950|1200|  
|Per 1000 oggetti CLR con una proprietà|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## <a name="binding-to-an-itemssource"></a>Binding a una proprietà ItemsSource  
 Si consideri uno scenario in cui è presente un oggetto <xref:System.Collections.Generic.List%601> CLR che contiene un elenco di dipendenti che si desidera visualizzare in una <xref:System.Windows.Controls.ListBox>. Per creare una corrispondenza tra questi due oggetti, è necessario associare l'elenco dei dipendenti alla proprietà <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> della <xref:System.Windows.Controls.ListBox>. Si supponga ora che un nuovo dipendente si unisca al gruppo. Si potrebbe pensare che, per inserire questo nuovo utente nei valori <xref:System.Windows.Controls.ListBox> associati, è sufficiente aggiungere tale persona all'elenco dei dipendenti e prevedere che questa modifica venga riconosciuta automaticamente dal motore di data binding. Tale presupposto risulterebbe false; in realtà, la modifica non verrà riflessa automaticamente nel <xref:System.Windows.Controls.ListBox>. Questo è dovuto al fatto che l'oggetto <xref:System.Collections.Generic.List%601> CLR non genera automaticamente un evento di modifica della raccolta. Per fare in modo che il <xref:System.Windows.Controls.ListBox> rilevi le modifiche, è necessario ricreare l'elenco dei dipendenti e ricollegarlo alla proprietà <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> dell'<xref:System.Windows.Controls.ListBox>. Questa soluzione funziona, ma incide considerevolmente sulle prestazioni. Ogni volta che si riassegna la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> di <xref:System.Windows.Controls.ListBox> a un nuovo oggetto, il <xref:System.Windows.Controls.ListBox> prima di tutto genera gli elementi precedenti e rigenera l'intero elenco. L'effetto sulle prestazioni viene ingrandito se il <xref:System.Windows.Controls.ListBox> viene mappato a un <xref:System.Windows.DataTemplate>complesso.  
  
 Una soluzione molto efficiente per questo problema consiste nel fare in modo che il dipendente elenchi un <xref:System.Collections.ObjectModel.ObservableCollection%601>. Un oggetto <xref:System.Collections.ObjectModel.ObservableCollection%601> genera una notifica di modifica che può essere ricevuta dal motore di data binding. L'evento aggiunge o rimuove un elemento da un <xref:System.Windows.Controls.ItemsControl> senza la necessità di rigenerare l'intero elenco.  
  
 La tabella seguente mostra il tempo necessario per aggiornare la <xref:System.Windows.Controls.ListBox> (con la virtualizzazione dell'interfaccia utente disattivata) quando viene aggiunto un elemento. Il numero nella prima riga rappresenta il tempo trascorso quando l'oggetto CLR <xref:System.Collections.Generic.List%601> viene associato al <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>di <xref:System.Windows.Controls.ListBox> elemento. Il numero nella seconda riga rappresenta il tempo trascorso quando un <xref:System.Collections.ObjectModel.ObservableCollection%601> viene associato al <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>dell'elemento del <xref:System.Windows.Controls.ListBox>. Si noti il notevole risparmio di tempo con la strategia di data binding <xref:System.Collections.ObjectModel.ObservableCollection%601>.  
  
|**Data binding della proprietà ItemsSource**|**Tempo di aggiornamento per 1 elemento (ms)**|  
|--------------------------------------|---------------------------------------|  
|A un oggetto <xref:System.Collections.Generic.List%601> CLR|1656|  
|A un <xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Binding di IList a ItemsControl non IEnumerable  
 Se è possibile scegliere tra associare un <xref:System.Collections.Generic.IList%601> o un <xref:System.Collections.IEnumerable> a un oggetto <xref:System.Windows.Controls.ItemsControl>, scegliere l'oggetto <xref:System.Collections.Generic.IList%601>. Il binding <xref:System.Collections.IEnumerable> a un <xref:System.Windows.Controls.ItemsControl> impone [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di creare un wrapper <xref:System.Collections.Generic.IList%601> oggetto, il che significa che le prestazioni sono influenzate dal sovraccarico superfluo di un secondo oggetto.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>Non convertire oggetti CLR in XML solo per il data binding  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di associare dati al contenuto XML; Tuttavia, data binding al contenuto XML è più lento rispetto data binding agli oggetti CLR. Non convertire i dati dell'oggetto CLR in XML se l'unico scopo è data binding.  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica bidimensionale e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamento dell'oggetto](optimizing-performance-object-behavior.md)
- [Risorse di applicazioni](optimizing-performance-application-resources.md)
- [Testo](optimizing-performance-text.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedura dettagliata: Memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF](walkthrough-caching-application-data-in-a-wpf-application.md)
