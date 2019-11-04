---
title: 'Ottimizzazione delle prestazioni: associazione dati'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 31fdc3c31c8792fea5f3e71dedb7370ebd63c98e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458555"
---
# <a name="optimizing-performance-data-binding"></a>Ottimizzazione delle prestazioni: associazione dati
Il data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] rappresenta per le applicazioni un modo semplice e coerente di presentare i dati e interagire con essi. Elements can be bound to data from a variety of data sources in the form of CLR objects and [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  
  
 Questo argomento offre utili suggerimenti sulle prestazioni del data binding.  

<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>Risoluzione dei riferimenti di data binding  
 Prima di trattare i problemi di prestazioni del data binding, è opportuno scoprire come vengono risolti dal motore di data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] i riferimenti agli oggetti per il binding.  
  
 The source of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] data binding can be any CLR object. You can bind to properties, sub-properties, or indexers of a CLR object. The binding references are resolved by using either Microsoft .NET Framework reflection or an <xref:System.ComponentModel.ICustomTypeDescriptor>. Di seguito vengono descritti i tre metodi disponibili per risolvere riferimenti a oggetti per il data binding.  
  
 Il primo metodo prevede l'uso della reflection. In this case, the <xref:System.Reflection.PropertyInfo> object is used to discover the attributes of the property and provides access to property metadata. When using the <xref:System.ComponentModel.ICustomTypeDescriptor> interface, the data binding engine uses this interface to access the property values. The <xref:System.ComponentModel.ICustomTypeDescriptor> interface is especially useful in cases where the object does not have a static set of properties.  
  
 Property change notifications can be provided either by implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface or by using the change notifications associated with the <xref:System.ComponentModel.TypeDescriptor>. However, the preferred strategy for implementing property change notifications is to use <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 If the source object is a CLR object and the source property is a CLR property, the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] data binding engine has to first use reflection on the source object to get the <xref:System.ComponentModel.TypeDescriptor>, and then query for a <xref:System.ComponentModel.PropertyDescriptor>. Questa sequenza di operazioni di reflection richiede potenzialmente molto tempo da un punto di vista delle prestazioni.  
  
 The second method for resolving object references involves a CLR source object that implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface, and a source property that is a CLR property. In questo caso, il motore di data binding usa direttamente la reflection sul tipo di origine e ottiene la proprietà necessaria. Sebbene presenti requisiti del working set inferiori rispetto al primo metodo, non si tratta ancora del metodo ottimale.  
  
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
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di eseguire il binding dei dati [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] contenuto; Tuttavia, data binding per [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] contenuto è più lento del data binding agli oggetti CLR. Non convertire i dati dell'oggetto CLR in XML se l'unico scopo è data binding.  
  
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
