---
title: 'Ottimizzazione delle prestazioni: associazione dati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c420748a9361655eeb2df33ce8426d9f167d3414
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-performance-data-binding"></a>Ottimizzazione delle prestazioni: associazione dati
Il data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] rappresenta per le applicazioni un modo semplice e coerente di presentare i dati e interagire con essi. È possibile eseguire il data binding degli elementi a diverse origini dati sotto forma di oggetti [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] e [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  
  
 Questo argomento offre utili suggerimenti sulle prestazioni del data binding.  
  

  
<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>Risoluzione dei riferimenti di data binding  
 Prima di trattare i problemi di prestazioni del data binding, è opportuno scoprire come vengono risolti dal motore di data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] i riferimenti agli oggetti per il binding.  
  
 L'origine di un data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] può essere qualsiasi oggetto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. È possibile eseguire il binding a proprietà, proprietà secondarie o indici di un oggetto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. I riferimenti di associazione vengono risolti tramite [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] reflection o <xref:System.ComponentModel.ICustomTypeDescriptor>. Di seguito vengono descritti i tre metodi disponibili per risolvere riferimenti a oggetti per il data binding.  
  
 Il primo metodo prevede l'uso della reflection. In questo caso, il <xref:System.Reflection.PropertyInfo> oggetto viene utilizzato per individuare gli attributi della proprietà e fornisce l'accesso ai metadati della proprietà. Quando si utilizza il <xref:System.ComponentModel.ICustomTypeDescriptor> , il motore di associazione di dati utilizza questa interfaccia per accedere ai valori di proprietà. Il <xref:System.ComponentModel.ICustomTypeDescriptor> interfaccia risulta particolarmente utile nei casi in cui l'oggetto dispone di un set statico di proprietà.  
  
 Le notifiche di modifica di proprietà possono essere fornite mediante l'implementazione di <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia o mediante le notifiche di modifica associate il <xref:System.ComponentModel.TypeDescriptor>. Tuttavia, la strategia consigliata per l'implementazione di notifiche di modifica delle proprietà consiste nell'utilizzare <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Se l'oggetto di origine è un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] oggetto e la proprietà di origine è un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] proprietà, il [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] motore di associazione dati è prima di tutto usare la reflection sull'oggetto di origine per ottenere il <xref:System.ComponentModel.TypeDescriptor>, quindi eseguire una query per un <xref:System.ComponentModel.PropertyDescriptor>. Questa sequenza di operazioni di reflection richiede potenzialmente molto tempo da un punto di vista delle prestazioni.  
  
 Il secondo metodo per la risoluzione di riferimenti a oggetti richiede un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] oggetto di origine che implementa il <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia e una proprietà di origine è un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] proprietà. In questo caso, il motore di data binding usa direttamente la reflection sul tipo di origine e ottiene la proprietà necessaria. Sebbene presenti requisiti del working set inferiori rispetto al primo metodo, non si tratta ancora del metodo ottimale.  
  
 Il terzo metodo per la risoluzione di riferimenti a oggetti richiede un oggetto di origine che è un <xref:System.Windows.DependencyObject> e una proprietà di origine che è un <xref:System.Windows.DependencyProperty>. In questo caso, non è necessario che il motore di data binding usi la reflection: il motore della proprietà e il motore di data binding risolvono il riferimento alla proprietà in modo indipendente. Si tratta del metodo ottimale per la risoluzione dei riferimenti a oggetti usati per il data binding.  
  
 Nella tabella seguente confronta la velocità del data binding di <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà di mille <xref:System.Windows.Controls.TextBlock> elementi utilizzando questi tre metodi.  
  
|**Binding della proprietà Text di un TextBlock**|**Tempo di binding (ms)**|**Tempo di rendering: include il binding (ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|A una proprietà di un oggetto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]|115|314|  
|Per una proprietà di un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] oggetto che implementa<xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|Per un <xref:System.Windows.DependencyProperty> di un <xref:System.Windows.DependencyObject>.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## <a name="binding-to-large-clr-objects"></a>Binding a oggetti CLR di grandi dimensioni  
 L'esecuzione del data binding a un singolo oggetto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con migliaia di proprietà si ripercuote in modo significativo sulle prestazioni. Per limitare questo impatto è possibile dividere il singolo oggetto in più oggetti [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con un numero inferiore di proprietà. La tabella illustra i tempi di binding e di rendering per il data binding a un singolo oggetto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] di grandi dimensioni rispetto a più oggetti di dimensioni inferiori.  
  
|**Data binding di 1000 oggetti TextBlock**|**Tempo di binding (ms)**|**Tempo di rendering: include il binding (ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|A un oggetto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con 1000 proprietà|950|1200|  
|A 1000 oggetti [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con una proprietà|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## <a name="binding-to-an-itemssource"></a>Binding a una proprietà ItemsSource  
 Si consideri uno scenario in cui è presente un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> oggetto che contiene un elenco di dipendenti che si desidera visualizzare in un <xref:System.Windows.Controls.ListBox>. Per creare una corrispondenza tra questi due oggetti, è necessario associare l'elenco dei dipendenti per il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.ListBox>. Si supponga ora che un nuovo dipendente si unisca al gruppo. Si potrebbe pensare che per inserire l'associazione di questo nuovo dipendente <xref:System.Windows.Controls.ListBox> valori, è semplicemente aggiungerlo all'elenco dei dipendenti e attendere che tale modifica venga riconosciuta automaticamente dal motore di associazione dati. Questo presupposto per rivelarsi false. in realtà, la modifica non verrà verrà riflessa nel <xref:System.Windows.Controls.ListBox> automaticamente. In questo modo il [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> oggetto non genera automaticamente un evento modificato della raccolta. Per ottenere il <xref:System.Windows.Controls.ListBox> per rendere effettive le modifiche, è necessario ricreare l'elenco dei dipendenti e ricollegarlo al <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.ListBox>. Questa soluzione funziona, ma incide considerevolmente sulle prestazioni. Ogni volta che il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> di <xref:System.Windows.Controls.ListBox> a un nuovo oggetto, il <xref:System.Windows.Controls.ListBox> innanzitutto genera un'eccezione gli elementi precedenti e rigenera l'intero elenco. L'impatto sulle prestazioni risulta maggiore se il <xref:System.Windows.Controls.ListBox> esegue il mapping a un oggetto complesso <xref:System.Windows.DataTemplate>.  
  
 Una soluzione molto efficace per questo problema consiste nel rendere l'elenco dei dipendenti un <xref:System.Collections.ObjectModel.ObservableCollection%601>. Un <xref:System.Collections.ObjectModel.ObservableCollection%601> oggetto genera una notifica di modifica che può ricevere dal motore di associazione dati. L'evento aggiunge o rimuove un elemento da un <xref:System.Windows.Controls.ItemsControl> senza la necessità di rigenerare l'intero elenco.  
  
 Nella tabella riportata di seguito mostra il tempo necessario per aggiornare il <xref:System.Windows.Controls.ListBox> (con la virtualizzazione dell'interfaccia utente disattivata) quando viene aggiunto un elemento. Il numero della prima riga rappresenta il tempo trascorso durante il [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> è associato l'oggetto <xref:System.Windows.Controls.ListBox> dell'elemento <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Il numero nella seconda riga rappresenta il tempo trascorso quando un <xref:System.Collections.ObjectModel.ObservableCollection%601> è associato il <xref:System.Windows.Controls.ListBox> dell'elemento <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Si noti il risparmio di molto tempo usando il <xref:System.Collections.ObjectModel.ObservableCollection%601> strategia di associazione dati.  
  
|**Data binding della proprietà ItemsSource**|**Tempo di aggiornamento per 1 elemento (ms)**|  
|--------------------------------------|---------------------------------------|  
|Per un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> oggetto|1656|  
|Per un<xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>Binding di IList a ItemsControl non IEnumerable  
 Se si dispone di una scelta tra l'associazione un <xref:System.Collections.Generic.IList%601> o <xref:System.Collections.IEnumerable> per un <xref:System.Windows.Controls.ItemsControl> oggetto, scegliere il <xref:System.Collections.Generic.IList%601> oggetto. Associazione <xref:System.Collections.IEnumerable> per un <xref:System.Windows.Controls.ItemsControl> forza [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per creare un wrapper <xref:System.Collections.Generic.IList%601> oggetto, con conseguente calo delle prestazioni per l'overhead superfluo di un secondo oggetto.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>Non convertire oggetti CLR in XML solo per il data binding  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di eseguire il data binding a contenuti [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]; il data binding a contenuti [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)], tuttavia, è più lento rispetto al data binding a oggetti [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. Non convertire dati di oggetti [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] a XML se l'unico scopo è il data binding.  
  
## <a name="see-also"></a>Vedere anche  
 [Ottimizzazione delle prestazioni di applicazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Pianificazione delle prestazioni dell'applicazione](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Sfruttare appieno l'hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Ottimizzazione delle prestazioni: layout e progettazione](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Comportamento dell'oggetto](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Risorse di applicazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [per](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Altri suggerimenti relativi alle prestazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedura dettagliata: Memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
