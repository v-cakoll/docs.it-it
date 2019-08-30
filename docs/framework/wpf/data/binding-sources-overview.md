---
title: Cenni preliminari sulle origini del binding
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], binding sources
- data binding [WPF], binding source
- binding sources [WPF]
ms.assetid: 2df2cd11-6aac-4bdf-ab7b-ea5f464cd5ca
ms.openlocfilehash: 4b7a5681840bf70eaebc824ff3d0dbeef3d1d799
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2019
ms.locfileid: "70169099"
---
# <a name="binding-sources-overview"></a>Cenni preliminari sulle origini del binding
Nel data binding l'oggetto origine del binding fa riferimento all'oggetto da cui si ottengono i dati. Questo argomento descrive i tipi di oggetti che è possibile usare come origine del binding.  

<a name="binding_sources"></a>   
## <a name="binding-source-types"></a>Tipi di origine del binding  
 Il data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] supporta i tipi di origine del binding seguenti:  
  
|Origine del binding|Descrizione|  
|--------------------|-----------------|  
|oggetti Common Language Runtime (CLR)|È possibile eseguire l'associazione a proprietà pubbliche, sottoproprietà e indicizzatori di qualsiasi oggetto Common Language Runtime (CLR). Il motore di associazione usa la reflection CLR per ottenere i valori delle proprietà. In alternativa, gli oggetti che <xref:System.ComponentModel.ICustomTypeDescriptor> implementano o hanno <xref:System.ComponentModel.TypeDescriptionProvider> un registrato funzionano anche con il motore di associazione.<br /><br /> Per altre informazioni su come implementare una classe che possa essere usata come origine del binding, vedere [Implementazione di una classe come origine del binding](#classes) più avanti in questo argomento.|  
|oggetti dinamici|È possibile eseguire l'associazione alle proprietà e agli indicizzatori disponibili di un oggetto <xref:System.Dynamic.IDynamicMetaObjectProvider> che implementa l'interfaccia. Se è possibile accedere al membro nel codice, è possibile creare un'associazione a tale membro. Se ad esempio un oggetto dinamico consente di accedere a un membro nel codice tramite `someObjet.AProperty`, è possibile creare un'associazione al membro impostando il percorso di associazione su `AProperty`.|  
|Oggetti ADO.NET|È possibile eseguire l'associazione a oggetti ADO.NET, <xref:System.Data.DataTable>ad esempio. ADO.NET <xref:System.Data.DataView> implementa l' <xref:System.ComponentModel.IBindingList> interfaccia, che fornisce le notifiche di modifica per le quali il motore di associazione è in ascolto.|  
|Oggetti [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].|È possibile associare ed `XPath` eseguire query su un oggetto <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlDocument>o. <xref:System.Xml.XmlElement> Un modo pratico per accedere [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ai dati che rappresenta l'origine del binding nel markup consiste nell' <xref:System.Windows.Data.XmlDataProvider> usare un oggetto. Per altre informazioni, vedere [Procedura: Eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).<br /><br /> È anche possibile eseguire l'associazione <xref:System.Xml.Linq.XElement> a <xref:System.Xml.Linq.XDocument>un oggetto o oppure eseguire un'associazione ai risultati delle query eseguite su oggetti di questi tipi usando LINQ to XML. Un modo pratico per usare LINQ to XML per accedere ai dati XML che rappresenta l'origine del binding nel markup consiste nell' <xref:System.Windows.Data.ObjectDataProvider> usare un oggetto. Per altre informazioni, vedere [Procedura: Eseguire l'associazione ai risultati di una query XDocument, XElement o LINQ to XML](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).|  
|Oggetti <xref:System.Windows.DependencyObject>.|È possibile eseguire l'associazione alle proprietà di <xref:System.Windows.DependencyObject>dipendenza di qualsiasi. Per un esempio, vedere [Eseguire l'associazione delle proprietà di due controlli](how-to-bind-the-properties-of-two-controls.md).|  
  
<a name="classes"></a>   
## <a name="implementing-a-class-for-the-binding-source"></a>Implementazione di una classe come origine del binding  
 È possibile creare origini del binding personalizzate. Questa sezione illustra i concetti necessari per l'implementazione di una classe da usare come origine del binding.  
  
### <a name="providing-change-notifications"></a>Invio di notifiche delle modifiche  
 Se si utilizza <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> binding (perché si desidera che il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] venga aggiornato quando le proprietà di origine del binding cambiano in modo dinamico), è necessario implementare un meccanismo di notifica appropriato modificato per la proprietà. Il meccanismo consigliato prevede che la classe CLR o dinamica implementi l' <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia. Per altre informazioni, vedere [Implementare la notifica di modifiche alle proprietà](how-to-implement-property-change-notification.md).  
  
 Se si crea un oggetto CLR che non implementa <xref:System.ComponentModel.INotifyPropertyChanged>, è necessario disporre di un sistema di notifica personalizzato per assicurarsi che i dati utilizzati in un'associazione rimangano aggiornati. È possibile offrire notifiche delle modifiche tramite il supporto del modello `PropertyChanged` per ogni proprietà per cui si desidera impostarle. Per supportare questo modello, definire un evento *NomeProprietà*Changed per ogni proprietà, dove *NomeProprietà* è il nome della proprietà. L'evento viene generato a ogni modifica della proprietà.  
  
 Se l'origine del binding implementa uno di questi meccanismi di notifica, gli aggiornamenti della destinazione vengono eseguiti automaticamente. Se per qualsiasi motivo l'origine del binding non fornisce le notifiche appropriate per la modifica delle proprietà, è possibile usare il <xref:System.Windows.Data.BindingExpression.UpdateTarget%2A> metodo per aggiornare in modo esplicito la proprietà di destinazione.  
  
### <a name="other-characteristics"></a>Altre caratteristiche  
 L'elenco seguente indica altri punti importanti.  
  
- Se si desidera creare l'oggetto in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], la classe deve avere un costruttore senza parametri. In alcuni linguaggi .NET, ad esempio C#, il costruttore senza parametri potrebbe essere creato automaticamente.  
  
- Le proprietà usate come proprietà di origine del binding per un binding devono essere proprietà pubbliche della classe. Non è possibile accedere alle proprietà dell'interfaccia definite in modo esplicito a scopo di associazione né alle proprietà protette, private, interne o virtuali prive di un'implementazione di base.  
  
- Non è possibile stabilire l'associazione a campi pubblici.  
  
- Il tipo della proprietà dichiarata nella classe è il tipo passato al binding. Il tipo usato in ultima analisi dal binding dipende tuttavia dal tipo della proprietà della destinazione del binding, non della proprietà di origine del binding. Se è presente una differenza nel tipo, è necessario scrivere un convertitore per gestire la modalità di passaggio iniziale della proprietà personalizzata al binding. Per altre informazioni, vedere <xref:System.Windows.Data.IValueConverter>.  
  
<a name="objects"></a>   
## <a name="using-entire-objects-as-a-binding-source"></a>Uso di oggetti interi come origine del binding  
 È possibile usare un oggetto intero come origine del binding. È possibile specificare un'origine di associazione usando la <xref:System.Windows.Data.Binding.Source%2A> <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà o, quindi fornire una dichiarazione di binding vuota: `{Binding}`. Alcuni scenari per i quali questa possibilità risulta utile sono l'associazione a oggetti di tipo stringa, l'associazione a oggetti con più proprietà di interesse o l'associazione a oggetti Collection. Per un esempio di associazione a un intero oggetto Collection, vedere [Usare il modello Master-Detail con dati gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  
  
 Affinché i dati siano significativi per la proprietà di destinazione associata, può essere necessario applicare logica personalizzata. La logica personalizzata può essere sotto forma di convertitore personalizzato (se la conversione di <xref:System.Windows.DataTemplate>tipo predefinita non esiste) o. Per altre informazioni sui convertitori, vedere la sezione sulla conversione dei dati in [Panoramica sul data binding](data-binding-overview.md). Per altre informazioni sui modelli di dati, vedere [Cenni preliminari sui modelli di dati](data-templating-overview.md).  
  
<a name="collections"></a>   
## <a name="using-collection-objects-as-a-binding-source"></a>Uso di oggetti Collection come origine del binding  
 L'oggetto da usare come origine del binding corrisponde a una raccolta di oggetti personalizzati. Ogni oggetto funge da origine per un'istanza di un binding ripetuto. Se ad esempio si dispone di una raccolta `CustomerOrders` che include di oggetti `CustomerOrder`, l'applicazione scorrerà la raccolta per determinare il numero di ordini inclusi e i dati contenuti in ognuno di essi.  
  
 È possibile enumerare qualsiasi raccolta che implementi <xref:System.Collections.IEnumerable> l'interfaccia. Tuttavia, per configurare i binding dinamici in modo che gli inserimenti o le eliminazioni nella raccolta [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aggiornino automaticamente l'oggetto, la <xref:System.Collections.Specialized.INotifyCollectionChanged> raccolta deve implementare l'interfaccia. Questa interfaccia espone un evento che deve essere generato a ogni modifica della raccolta sottostante.  
  
 La <xref:System.Collections.ObjectModel.ObservableCollection%601> classe è un'implementazione incorporata di una raccolta di dati che espone l' <xref:System.Collections.Specialized.INotifyCollectionChanged> interfaccia. I singoli oggetti dati nella raccolta devono soddisfare i requisiti descritti nelle sezioni precedenti. Per un esempio, vedere [Procedura: Creare ed eseguire l'associazione a una classe ObservableCollection](how-to-create-and-bind-to-an-observablecollection.md). Prima di implementare una raccolta personalizzata, prendere <xref:System.Collections.ObjectModel.ObservableCollection%601> in <xref:System.Collections.Generic.List%601>considerazione l'uso di o di una delle classi di <xref:System.Collections.ObjectModel.Collection%601>raccolte esistenti <xref:System.ComponentModel.BindingList%601>, ad esempio, e, tra molte altre.  
  
 WPF non esegue mai direttamente l'associazione a una raccolta. Se si specifica una raccolta come origine del binding, WPF esegue effettivamente il binding alla visualizzazione predefinita della raccolta stessa. Per informazioni sulle visualizzazioni predefinite, vedere [Panoramica sul data binding](data-binding-overview.md).  
  
 Se si dispone di uno scenario avanzato e si desidera implementare una raccolta personalizzata, è consigliabile utilizzare <xref:System.Collections.IList> l'interfaccia. <xref:System.Collections.IList>fornisce una raccolta non generica di oggetti a cui è possibile accedere singolarmente in base all'indice, che può migliorare le prestazioni.  
  
<a name="permissions"></a>   
## <a name="permission-requirements-in-data-binding"></a>Requisiti di autorizzazione in un data binding  
 Quando si crea un data binding, è necessario considerare il livello di attendibilità dell'applicazione. La tabella seguente riepiloga i tipi di proprietà a cui è possibile stabilire l'associazione in un'applicazione eseguita con attendibilità totale o parziale.  
  
|Tipo di proprietà<br /><br /> (tutti i modificatori di accesso)|Proprietà dell'oggetto dinamico|Proprietà dell'oggetto dinamico|Proprietà CLR|Proprietà CLR|Proprietà di dipendenza|Proprietà di dipendenza|  
|------------------------------------------------|-----------------------------|-----------------------------|------------------|------------------|-------------------------|-------------------------|  
|**Livello di attendibilità**|**Attendibilità totale**|**Attendibilità parziale**|**Attendibilità totale**|**Attendibilità parziale**|**Attendibilità totale**|**Attendibilità parziale**|  
|Classe pubblica|Yes|Sì|Sì|Sì|Sì|Sì|  
|Classe non pubblica|Sì|No|Sì|No|Yes|Yes|  
  
 Questa tabella descrive punti importanti relativi ai requisiti di autorizzazione per il data binding.  
  
- Per le proprietà CLR, data binding funziona purché il motore di associazione sia in grado di accedere alla proprietà di origine del binding mediante reflection. In caso contrario, viene generato un avviso relativo all'impossibilità di trovare la proprietà e viene usato il valore di fallback o quello predefinito, se disponibile.  
  
- È possibile creare associazioni alle proprietà degli oggetti dinamici definiti in fase di compilazione o di esecuzione.  
  
- È sempre possibile stabilire l'associazione alle proprietà di dipendenza.  
  
 Il requisito di autorizzazione per l'associazione [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] è analogo. In una sandbox con attendibilità parziale <xref:System.Windows.Data.XmlDataProvider> , ha esito negativo quando non dispone delle autorizzazioni per accedere ai dati specificati.  
  
 Gli oggetti con un tipo anonimo sono interni. È possibile creare associazioni a proprietà di tipi anonimi solo in fase di esecuzione con attendibilità totale. Per altre informazioni sui tipi anonimi, vedere [Tipi anonimi (Guida per programmatori C#)](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) o [Tipi anonimi (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
 Per altre informazioni sulla sicurezza con attendibilità parziale, vedere [Sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.ObjectDataProvider>
- <xref:System.Windows.Data.XmlDataProvider>
- [Specificare l'origine di associazione](how-to-specify-the-binding-source.md)
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
- [Panoramica dei data binding WPF con LINQ to XML](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)
- [Data binding](../advanced/optimizing-performance-data-binding.md)
