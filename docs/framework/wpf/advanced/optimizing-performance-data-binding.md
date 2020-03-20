---
title: 'Ottimizzazione delle prestazioni: associazione dati'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 3128f453378f9d74f867b571e30f2be4e8add8a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186752"
---
# <a name="optimizing-performance-data-binding"></a>Ottimizzazione delle prestazioni: associazione dati
Il data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] rappresenta per le applicazioni un modo semplice e coerente di presentare i dati e interagire con essi. Gli elementi possono essere associati ai dati da un'ampia gamma di origini dati sotto forma di oggetti CLR e XML.  
  
 Questo argomento offre utili suggerimenti sulle prestazioni del data binding.  

<a name="HowDataBindingReferencesAreResolved"></a>
## <a name="how-data-binding-references-are-resolved"></a>Risoluzione dei riferimenti di data binding  
 Prima di trattare i problemi di prestazioni del data binding, è opportuno scoprire come vengono risolti dal motore di data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] i riferimenti agli oggetti per il binding.  
  
 L'origine [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] di un'associazione dati può essere qualsiasi oggetto CLR. È possibile eseguire l'associazione a proprietà, sottoproprietà o indicizzatori di un oggetto CLR. I riferimenti all'associazione vengono risolti utilizzando <xref:System.ComponentModel.ICustomTypeDescriptor>la reflection di Microsoft .NET Framework o un oggetto . Di seguito vengono descritti i tre metodi disponibili per risolvere riferimenti a oggetti per il data binding.  
  
 Il primo metodo prevede l'uso della reflection. In questo caso, l'oggetto <xref:System.Reflection.PropertyInfo> viene utilizzato per individuare gli attributi della proprietà e fornisce l'accesso ai metadati della proprietà. Quando si <xref:System.ComponentModel.ICustomTypeDescriptor> usa l'interfaccia , il motore di associazione dati utilizza questa interfaccia per accedere ai valori delle proprietà. L'interfaccia <xref:System.ComponentModel.ICustomTypeDescriptor> è particolarmente utile nei casi in cui l'oggetto non dispone di un set statico di proprietà.  
  
 Le notifiche di modifica delle <xref:System.ComponentModel.INotifyPropertyChanged> proprietà possono essere fornite implementando <xref:System.ComponentModel.TypeDescriptor>l'interfaccia o utilizzando le notifiche di modifica associate all'oggetto . Tuttavia, la strategia preferita per <xref:System.ComponentModel.INotifyPropertyChanged>l'implementazione delle notifiche di modifica delle proprietà consiste nell'utilizzare .  
  
 Se l'oggetto di origine è un oggetto CLR [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] e la proprietà di origine è una proprietà <xref:System.ComponentModel.TypeDescriptor>CLR, il <xref:System.ComponentModel.PropertyDescriptor>motore di associazione dati deve innanzitutto utilizzare la reflection sull'oggetto di origine per ottenere l'oggetto , quindi eseguire una query per un oggetto . Questa sequenza di operazioni di reflection richiede potenzialmente molto tempo da un punto di vista delle prestazioni.  
  
 Il secondo metodo per la risoluzione dei riferimenti <xref:System.ComponentModel.INotifyPropertyChanged> agli oggetti coinvolge un oggetto di origine CLR che implementa l'interfaccia e una proprietà di origine che è una proprietà CLR. In questo caso, il motore di data binding usa direttamente la reflection sul tipo di origine e ottiene la proprietà necessaria. Sebbene presenti requisiti del working set inferiori rispetto al primo metodo, non si tratta ancora del metodo ottimale.  
  
 Il terzo metodo per la risoluzione dei <xref:System.Windows.DependencyObject> riferimenti agli oggetti prevede <xref:System.Windows.DependencyProperty>un oggetto di origine che è una proprietà e una proprietà di origine che è un oggetto . In questo caso, non è necessario che il motore di data binding usi la reflection: il motore della proprietà e il motore di data binding risolvono il riferimento alla proprietà in modo indipendente. Si tratta del metodo ottimale per la risoluzione dei riferimenti a oggetti usati per il data binding.  
  
 Nella tabella seguente viene confrontata <xref:System.Windows.Controls.TextBlock.Text%2A> la velocità <xref:System.Windows.Controls.TextBlock> di associazione dati della proprietà di mille elementi utilizzando questi tre metodi.  
  
|**Binding della proprietà Text di un TextBlock**|**Tempo di binding (ms)**|**Tempo di rendering: include il binding (ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|A una proprietà di un oggetto CLR|115|314|  
|A una proprietà di un oggetto CLR che implementa<xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|A <xref:System.Windows.DependencyProperty> un <xref:System.Windows.DependencyObject>file .|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>
## <a name="binding-to-large-clr-objects"></a>Binding a oggetti CLR di grandi dimensioni  
 Si verifica un impatto significativo sulle prestazioni quando si esegue l'associazione dati a un singolo oggetto CLR con migliaia di proprietà. È possibile ridurre al minimo questo impatto suddividendo il singolo oggetto in più oggetti CLR con un numero inferiore di proprietà. La tabella mostra i tempi di associazione e rendering dei dati per l'associazione dati a un singolo oggetto CLR di grandi dimensioni rispetto a più oggetti più piccoli.  
  
|**Data binding di 1000 oggetti TextBlock**|**Tempo di binding (ms)**|**Tempo di rendering: include il binding (ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|A un oggetto CLR con 1000 proprietà|950|1200|  
|A 1000 oggetti CLR con una proprietà|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>
## <a name="binding-to-an-itemssource"></a>Binding a una proprietà ItemsSource  
 Si consideri uno scenario <xref:System.Collections.Generic.List%601> in cui si dispone di un oggetto <xref:System.Windows.Controls.ListBox>CLR che contiene un elenco di dipendenti che si desidera visualizzare in un file . Per creare una corrispondenza tra questi due oggetti, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> è <xref:System.Windows.Controls.ListBox>necessario associare l'elenco dei dipendenti alla proprietà dell'oggetto . Si supponga ora che un nuovo dipendente si unisca al gruppo. Si potrebbe pensare che per inserire questa <xref:System.Windows.Controls.ListBox> nuova persona nei valori associati, è sufficiente aggiungere questa persona all'elenco dei dipendenti e aspettarsi che questa modifica venga riconosciuta automaticamente dal motore di associazione dati. Tale ipotesi si rivelerebbe falsa; in realtà, la modifica non si <xref:System.Windows.Controls.ListBox> rifletterà automaticamente nel campo. Ciò è <xref:System.Collections.Generic.List%601> dovuto al fatto che l'oggetto CLR non genera automaticamente un evento di raccolta modificato. Al fine di <xref:System.Windows.Controls.ListBox> ottenere il per raccogliere le modifiche, si dovrebbe ricreare l'elenco dei dipendenti e ricollegarlo alla <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.ListBox>. Questa soluzione funziona, ma incide considerevolmente sulle prestazioni. Ogni volta che <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> si <xref:System.Windows.Controls.ListBox> riassegna la <xref:System.Windows.Controls.ListBox> di a un nuovo oggetto, il primo butta via gli elementi precedenti e rigenera l'intero elenco. L'impatto sulle prestazioni viene <xref:System.Windows.Controls.ListBox> ingrandito <xref:System.Windows.DataTemplate>se il mapping a un complesso .  
  
 Una soluzione molto efficiente a questo problema <xref:System.Collections.ObjectModel.ObservableCollection%601>è quello di rendere la vostra lista dei dipendenti un . Un <xref:System.Collections.ObjectModel.ObservableCollection%601> oggetto genera una notifica di modifica che il motore di associazione dati può ricevere. L'evento aggiunge o rimuove <xref:System.Windows.Controls.ItemsControl> un elemento da un oggetto senza la necessità di rigenerare l'intero elenco.  
  
 La tabella seguente mostra il tempo <xref:System.Windows.Controls.ListBox> necessario per aggiornare la (con la virtualizzazione dell'interfaccia utente disattivata) quando viene aggiunto un elemento. Il numero nella prima riga rappresenta il tempo <xref:System.Collections.Generic.List%601> trascorso quando <xref:System.Windows.Controls.ListBox> l'oggetto CLR è associato a <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Il numero nella seconda riga rappresenta il <xref:System.Collections.ObjectModel.ObservableCollection%601> tempo trascorso <xref:System.Windows.Controls.ListBox> quando un <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>oggetto viene associato all'oggetto . Si noti il notevole risparmio di tempo utilizzando la <xref:System.Collections.ObjectModel.ObservableCollection%601> strategia di associazione dati.  
  
|**Data binding della proprietà ItemsSource**|**Tempo di aggiornamento per 1 elemento (ms)**|  
|--------------------------------------|---------------------------------------|  
|A un <xref:System.Collections.Generic.List%601> oggetto CLR|1656|  
|A un<xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Binding di IList a ItemsControl non IEnumerable  
 Se si dispone di <xref:System.Collections.Generic.IList%601> una <xref:System.Collections.IEnumerable> scelta <xref:System.Windows.Controls.ItemsControl> tra l'associazione di un oggetto o un oggetto, scegliere l'oggetto <xref:System.Collections.Generic.IList%601> . Associazione <xref:System.Collections.IEnumerable> <xref:System.Windows.Controls.ItemsControl> a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un forza <xref:System.Collections.Generic.IList%601> di creare un oggetto wrapper, il che significa che le prestazioni sono influenzate dall'overhead non necessario di un secondo oggetto.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>Non convertire oggetti CLR in XML solo per il data binding  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]consente di eseguire l'associazione dati al contenuto XML; Tuttavia, l'associazione dati al contenuto XML è più lenta dell'associazione dati a oggetti CLR. Non convertire i dati degli oggetti CLR in XML se l'unico scopo è per l'associazione dati.  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica 2D e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamento degli oggetti](optimizing-performance-object-behavior.md)
- [Risorse dell'applicazione](optimizing-performance-application-resources.md)
- [Testo](optimizing-performance-text.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
- [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedura dettagliata: Memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF](walkthrough-caching-application-data-in-a-wpf-application.md)
