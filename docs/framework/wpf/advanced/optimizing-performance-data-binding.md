---
title: 'Ottimizzazione delle prestazioni: Data binding'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 25c0906e9f23948476732b10b2c5fb10fe4eb55f
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401460"
---
# <a name="optimizing-performance-data-binding"></a>Ottimizzazione delle prestazioni: Data binding
Il data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] rappresenta per le applicazioni un modo semplice e coerente di presentare i dati e interagire con essi. Gli elementi possono essere associati a dati da un'ampia gamma di origini dati sotto forma di oggetti CLR [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]e.  
  
 Questo argomento offre utili suggerimenti sulle prestazioni del data binding.  

<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>Risoluzione dei riferimenti di data binding  
 Prima di trattare i problemi di prestazioni del data binding, è opportuno scoprire come vengono risolti dal motore di data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] i riferimenti agli oggetti per il binding.  
  
 L'origine di un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Data Binding può essere qualsiasi oggetto CLR. È possibile eseguire l'associazione a proprietà, sottoproprietà o indicizzatori di un oggetto CLR. I riferimenti di associazione vengono risolti tramite Microsoft .NET Reflection del Framework o <xref:System.ComponentModel.ICustomTypeDescriptor>. Di seguito vengono descritti i tre metodi disponibili per risolvere riferimenti a oggetti per il data binding.  
  
 Il primo metodo prevede l'uso della reflection. In questo caso, l' <xref:System.Reflection.PropertyInfo> oggetto viene usato per individuare gli attributi della proprietà e fornisce l'accesso ai metadati della proprietà. Quando si usa <xref:System.ComponentModel.ICustomTypeDescriptor> l'interfaccia, il motore di Data Binding Usa questa interfaccia per accedere ai valori delle proprietà. L' <xref:System.ComponentModel.ICustomTypeDescriptor> interfaccia è particolarmente utile nei casi in cui l'oggetto non dispone di un set statico di proprietà.  
  
 Le notifiche di modifica delle proprietà possono essere fornite implementando l' <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia o utilizzando le notifiche di modifica associate <xref:System.ComponentModel.TypeDescriptor>a. Tuttavia, la strategia consigliata per l'implementazione delle notifiche delle modifiche <xref:System.ComponentModel.INotifyPropertyChanged>delle proprietà consiste nell'utilizzare.  
  
 Se l'oggetto di origine è un oggetto CLR e la proprietà di origine è una proprietà CLR [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] , il motore di data binding deve innanzitutto utilizzare la reflection sull'oggetto di origine <xref:System.ComponentModel.TypeDescriptor>per ottenere, quindi eseguire una <xref:System.ComponentModel.PropertyDescriptor>query per. Questa sequenza di operazioni di reflection richiede potenzialmente molto tempo da un punto di vista delle prestazioni.  
  
 Il secondo metodo per la risoluzione dei riferimenti a oggetti comporta un oggetto di origine CLR che <xref:System.ComponentModel.INotifyPropertyChanged> implementa l'interfaccia e una proprietà di origine che è una proprietà CLR. In questo caso, il motore di data binding usa direttamente la reflection sul tipo di origine e ottiene la proprietà necessaria. Sebbene presenti requisiti del working set inferiori rispetto al primo metodo, non si tratta ancora del metodo ottimale.  
  
 Il terzo metodo per la risoluzione dei riferimenti a oggetti prevede l'uso di un oggetto <xref:System.Windows.DependencyObject> di origine che è un oggetto e <xref:System.Windows.DependencyProperty>una proprietà di origine che è un oggetto. In questo caso, non è necessario che il motore di data binding usi la reflection: il motore della proprietà e il motore di data binding risolvono il riferimento alla proprietà in modo indipendente. Si tratta del metodo ottimale per la risoluzione dei riferimenti a oggetti usati per il data binding.  
  
 La tabella seguente confronta la velocità di data binding la <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà degli elementi 1000 <xref:System.Windows.Controls.TextBlock> usando questi tre metodi.  
  
|**Binding della proprietà Text di un TextBlock**|**Tempo di binding (ms)**|**Tempo di rendering: include il binding (ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|A una proprietà di un oggetto CLR|115|314|  
|A una proprietà di un oggetto CLR che implementa<xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|A un <xref:System.Windows.DependencyProperty> oggetto di <xref:System.Windows.DependencyObject>un oggetto.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## <a name="binding-to-large-clr-objects"></a>Binding a oggetti CLR di grandi dimensioni  
 Quando si esegue l'associazione dati a un singolo oggetto CLR con migliaia di proprietà, si verifica un notevole impatto sulle prestazioni. È possibile ridurre questo effetto dividendo il singolo oggetto in più oggetti CLR con un minor numero di proprietà. La tabella mostra i tempi di binding e di rendering per data binding a un singolo oggetto CLR di grandi dimensioni rispetto a più oggetti più piccoli.  
  
|**Data binding di 1000 oggetti TextBlock**|**Tempo di binding (ms)**|**Tempo di rendering: include il binding (ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|A un oggetto CLR con proprietà 1000|950|1200|  
|Per 1000 oggetti CLR con una proprietà|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## <a name="binding-to-an-itemssource"></a>Binding a una proprietà ItemsSource  
 Si consideri uno scenario in cui è <xref:System.Collections.Generic.List%601> presente un oggetto CLR che contiene un elenco di dipendenti che si desidera visualizzare <xref:System.Windows.Controls.ListBox>in un. Per creare una corrispondenza tra questi due oggetti, è necessario associare l'elenco <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox>dei dipendenti alla proprietà di. Si supponga ora che un nuovo dipendente si unisca al gruppo. Si potrebbe pensare che, per inserire questo nuovo utente nei valori associati <xref:System.Windows.Controls.ListBox> , è sufficiente aggiungere tale persona all'elenco dei dipendenti e prevedere che questa modifica venga riconosciuta automaticamente dal motore di data binding. Tale presupposto risulterebbe false; in realtà, la modifica non verrà applicata <xref:System.Windows.Controls.ListBox> automaticamente. Questo perché l'oggetto CLR <xref:System.Collections.Generic.List%601> non genera automaticamente un evento di modifica della raccolta. Per fare in modo che <xref:System.Windows.Controls.ListBox> il rilevi le modifiche, è necessario ricreare l'elenco dei dipendenti e ricollegarlo <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> alla proprietà di <xref:System.Windows.Controls.ListBox>. Questa soluzione funziona, ma incide considerevolmente sulle prestazioni. Ogni volta che si riassegna <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> la <xref:System.Windows.Controls.ListBox> proprietà di a un nuovo oggetto <xref:System.Windows.Controls.ListBox> , il primo elimina gli elementi precedenti e rigenera l'intero elenco. L'effetto sulle prestazioni viene ingrandito <xref:System.Windows.Controls.ListBox> se si esegue il <xref:System.Windows.DataTemplate>mapping a un complesso.  
  
 Una soluzione molto efficiente per questo problema consiste nel fare in modo che il <xref:System.Collections.ObjectModel.ObservableCollection%601>dipendente elenchi un. Un <xref:System.Collections.ObjectModel.ObservableCollection%601> oggetto genera una notifica di modifica che il motore di data binding può ricevere. L'evento aggiunge o rimuove un elemento da un <xref:System.Windows.Controls.ItemsControl> oggetto senza la necessità di rigenerare l'intero elenco.  
  
 La tabella seguente mostra il tempo necessario per aggiornare (con <xref:System.Windows.Controls.ListBox> la virtualizzazione dell'interfaccia utente disattivata) quando viene aggiunto un elemento. Il numero nella prima riga rappresenta il tempo trascorso quando l'oggetto CLR <xref:System.Collections.Generic.List%601> è associato a <xref:System.Windows.Controls.ListBox> un elemento <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Il numero nella seconda riga rappresenta il tempo trascorso quando un oggetto <xref:System.Collections.ObjectModel.ObservableCollection%601> viene associato <xref:System.Windows.Controls.ListBox> all'oggetto dell'elemento <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Si noti il notevole risparmio di tempo <xref:System.Collections.ObjectModel.ObservableCollection%601> con la strategia Data Binding.  
  
|**Data binding della proprietà ItemsSource**|**Tempo di aggiornamento per 1 elemento (ms)**|  
|--------------------------------------|---------------------------------------|  
|A un oggetto <xref:System.Collections.Generic.List%601> CLR|1656|  
|A un<xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Binding di IList a ItemsControl non IEnumerable  
 Se è possibile scegliere se associare <xref:System.Collections.Generic.IList%601> un oggetto <xref:System.Collections.IEnumerable> o a <xref:System.Windows.Controls.ItemsControl> un oggetto, scegliere l' <xref:System.Collections.Generic.IList%601> oggetto. Il <xref:System.Collections.IEnumerable> binding a <xref:System.Windows.Controls.ItemsControl> una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] forza per la creazione <xref:System.Collections.Generic.IList%601> di un oggetto wrapper, il che significa che le prestazioni sono influenzate dal sovraccarico superfluo di un secondo oggetto.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>Non convertire oggetti CLR in XML solo per il data binding  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]consente di associare dati al [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] contenuto. Tuttavia, data binding al [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] contenuto è più lento rispetto data binding agli oggetti CLR. Non convertire i dati dell'oggetto CLR in XML se l'unico scopo è data binding.  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica bidimensionale e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamento dell'oggetto](optimizing-performance-object-behavior.md)
- [Risorse di applicazioni](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Procedura dettagliata: Memorizzazione nella cache dei dati dell'applicazione in un'applicazione WPF](walkthrough-caching-application-data-in-a-wpf-application.md)
