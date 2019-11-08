---
title: Cenni preliminari sulle origini del binding
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], binding sources
- data binding [WPF], binding source
- binding sources [WPF]
ms.assetid: 2df2cd11-6aac-4bdf-ab7b-ea5f464cd5ca
ms.openlocfilehash: e7546021fbfde3fceea7fd4f1eba10cdc90dff8b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740621"
---
# <a name="binding-sources-overview"></a>Cenni preliminari sulle origini del binding
Nel data binding l'oggetto origine del binding fa riferimento all'oggetto da cui si ottengono i dati. Questo argomento descrive i tipi di oggetti che è possibile usare come origine del binding.

<a name="binding_sources"></a>
## <a name="binding-source-types"></a>Tipi di origine del binding
 Il data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] supporta i tipi di origine del binding seguenti:

|Origine del binding|Descrizione|
|--------------------|-----------------|
|oggetti Common Language Runtime (CLR)|È possibile eseguire l'associazione a proprietà pubbliche, sottoproprietà e indicizzatori di qualsiasi oggetto Common Language Runtime (CLR). Il motore di associazione usa la reflection CLR per ottenere i valori delle proprietà. In alternativa, gli oggetti che implementano <xref:System.ComponentModel.ICustomTypeDescriptor> o hanno una <xref:System.ComponentModel.TypeDescriptionProvider> registrata funzionano anche con il motore di associazione.<br /><br /> Per altre informazioni su come implementare una classe che possa essere usata come origine del binding, vedere [Implementazione di una classe come origine del binding](#classes) più avanti in questo argomento.|
|oggetti dinamici|È possibile eseguire l'associazione alle proprietà e agli indicizzatori disponibili di un oggetto che implementa l'interfaccia <xref:System.Dynamic.IDynamicMetaObjectProvider>. Se è possibile accedere al membro nel codice, è possibile creare un'associazione a tale membro. Se ad esempio un oggetto dinamico consente di accedere a un membro nel codice tramite `someObjet.AProperty`, è possibile creare un'associazione al membro impostando il percorso di associazione su `AProperty`.|
|Oggetti ADO.NET|È possibile eseguire l'associazione a oggetti ADO.NET, ad esempio <xref:System.Data.DataTable>. Il <xref:System.Data.DataView> ADO.NET implementa l'interfaccia <xref:System.ComponentModel.IBindingList>, che fornisce le notifiche di modifica per le quali il motore di associazione è in ascolto.|
|Oggetti XML|È possibile associare ed eseguire query `XPath` su un <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlDocument>o <xref:System.Xml.XmlElement>. Un modo pratico per accedere ai dati XML che rappresenta l'origine del binding nel markup consiste nell'usare un oggetto <xref:System.Windows.Data.XmlDataProvider>. Per altre informazioni, vedere [Procedura: Eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).<br /><br /> È anche possibile eseguire l'associazione a un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>oppure effettuare l'associazione ai risultati delle query eseguite su oggetti di questi tipi usando LINQ to XML. Un modo pratico per usare LINQ to XML per accedere ai dati XML che rappresenta l'origine del binding nel markup consiste nell'usare un oggetto <xref:System.Windows.Data.ObjectDataProvider>. Per altre informazioni, vedere [Procedura: Eseguire l'associazione ai risultati di una query XDocument, XElement o LINQ to XML](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).|
|Oggetti <xref:System.Windows.DependencyObject>.|È possibile eseguire l'associazione alle proprietà di dipendenza di qualsiasi <xref:System.Windows.DependencyObject>. Per un esempio, vedere [Eseguire l'associazione delle proprietà di due controlli](how-to-bind-the-properties-of-two-controls.md).|

<a name="classes"></a>
## <a name="implementing-a-class-for-the-binding-source"></a>Implementazione di una classe come origine del binding
 È possibile creare origini del binding personalizzate. Questa sezione illustra i concetti necessari per l'implementazione di una classe da usare come origine del binding.

### <a name="providing-change-notifications"></a>Invio di notifiche delle modifiche
 Se si utilizza <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> binding (perché si desidera che il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] venga aggiornato quando le proprietà di origine del binding cambiano in modo dinamico), è necessario implementare un meccanismo di notifica appropriato modificato della proprietà. Il meccanismo consigliato prevede che la classe CLR o dinamica implementi l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>. Per altre informazioni, vedere [Implementare la notifica di modifiche alle proprietà](how-to-implement-property-change-notification.md).

 Se si crea un oggetto CLR che non implementa <xref:System.ComponentModel.INotifyPropertyChanged>, è necessario disporre di un sistema di notifica personalizzato per assicurarsi che i dati utilizzati in un'associazione rimangano aggiornati. È possibile offrire notifiche delle modifiche tramite il supporto del modello `PropertyChanged` per ogni proprietà per cui si desidera impostarle. Per supportare questo modello, definire un evento *NomeProprietà*Changed per ogni proprietà, dove *NomeProprietà* è il nome della proprietà. L'evento viene generato a ogni modifica della proprietà.

 Se l'origine del binding implementa uno di questi meccanismi di notifica, gli aggiornamenti della destinazione vengono eseguiti automaticamente. Se per qualsiasi motivo l'origine del binding non fornisce le notifiche appropriate per la modifica delle proprietà, è possibile usare il metodo <xref:System.Windows.Data.BindingExpression.UpdateTarget%2A> per aggiornare in modo esplicito la proprietà di destinazione.

### <a name="other-characteristics"></a>Altre caratteristiche
 L'elenco seguente indica altri punti importanti.

- Se si desidera creare l'oggetto in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è necessario che la classe disponga di un costruttore senza parametri. In alcuni linguaggi .NET, ad esempio C#, il costruttore senza parametri potrebbe essere creato automaticamente.

- Le proprietà usate come proprietà di origine del binding per un binding devono essere proprietà pubbliche della classe. Non è possibile accedere alle proprietà dell'interfaccia definite in modo esplicito a scopo di associazione né alle proprietà protette, private, interne o virtuali prive di un'implementazione di base.

- Non è possibile stabilire l'associazione a campi pubblici.

- Il tipo della proprietà dichiarata nella classe è il tipo passato al binding. Il tipo usato in ultima analisi dal binding dipende tuttavia dal tipo della proprietà della destinazione del binding, non della proprietà di origine del binding. Se è presente una differenza nel tipo, è necessario scrivere un convertitore per gestire la modalità di passaggio iniziale della proprietà personalizzata al binding. Per ulteriori informazioni, vedere <xref:System.Windows.Data.IValueConverter>.

<a name="objects"></a>
## <a name="using-entire-objects-as-a-binding-source"></a>Uso di oggetti interi come origine del binding
 È possibile usare un oggetto intero come origine del binding. È possibile specificare un'origine di associazione usando la proprietà <xref:System.Windows.Data.Binding.Source%2A> o <xref:System.Windows.FrameworkElement.DataContext%2A>, quindi fornire una dichiarazione di binding vuota: `{Binding}`. Alcuni scenari per i quali questa possibilità risulta utile sono l'associazione a oggetti di tipo stringa, l'associazione a oggetti con più proprietà di interesse o l'associazione a oggetti Collection. Per un esempio di associazione a un intero oggetto Collection, vedere [Usare il modello Master-Detail con dati gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).

 Affinché i dati siano significativi per la proprietà di destinazione associata, può essere necessario applicare logica personalizzata. La logica personalizzata può essere sotto forma di convertitore personalizzato (se la conversione di tipo predefinita non esiste) o di un <xref:System.Windows.DataTemplate>. Per altre informazioni sui convertitori, vedere la sezione sulla conversione dei dati in [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md). Per altre informazioni sui modelli di dati, vedere [Cenni preliminari sui modelli di dati](data-templating-overview.md).

<a name="collections"></a>
## <a name="using-collection-objects-as-a-binding-source"></a>Uso di oggetti Collection come origine del binding
 L'oggetto da usare come origine del binding corrisponde a una raccolta di oggetti personalizzati. Ogni oggetto funge da origine per un'istanza di un binding ripetuto. Se ad esempio si dispone di una raccolta `CustomerOrders` che include di oggetti `CustomerOrder`, l'applicazione scorrerà la raccolta per determinare il numero di ordini inclusi e i dati contenuti in ognuno di essi.

 È possibile enumerare qualsiasi raccolta che implementi l'interfaccia <xref:System.Collections.IEnumerable>. Tuttavia, per configurare i binding dinamici in modo che gli inserimenti o le eliminazioni nella raccolta aggiornino automaticamente il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], è necessario che la raccolta implementi l'interfaccia <xref:System.Collections.Specialized.INotifyCollectionChanged>. Questa interfaccia espone un evento che deve essere generato a ogni modifica della raccolta sottostante.

 La classe <xref:System.Collections.ObjectModel.ObservableCollection%601> è un'implementazione incorporata di una raccolta di dati che espone l'interfaccia <xref:System.Collections.Specialized.INotifyCollectionChanged>. I singoli oggetti dati nella raccolta devono soddisfare i requisiti descritti nelle sezioni precedenti. Per un esempio, vedere [Procedura: Creare ed eseguire l'associazione a una classe ObservableCollection](how-to-create-and-bind-to-an-observablecollection.md). Prima di implementare una raccolta personalizzata, provare a usare <xref:System.Collections.ObjectModel.ObservableCollection%601> o una delle classi di raccolte esistenti, ad esempio <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601>e <xref:System.ComponentModel.BindingList%601>, tra molti altri.

 WPF non esegue mai direttamente l'associazione a una raccolta. Se si specifica una raccolta come origine del binding, WPF esegue effettivamente il binding alla visualizzazione predefinita della raccolta stessa. Per informazioni sulle visualizzazioni predefinite, vedere [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md).

 Se si dispone di uno scenario avanzato e si desidera implementare una raccolta personalizzata, è consigliabile utilizzare l'interfaccia <xref:System.Collections.IList>. <xref:System.Collections.IList> fornisce una raccolta non generica di oggetti a cui è possibile accedere singolarmente in base all'indice, che può migliorare le prestazioni.

<a name="permissions"></a>
## <a name="permission-requirements-in-data-binding"></a>Requisiti di autorizzazione in un data binding
 Quando si crea un data binding, è necessario considerare il livello di attendibilità dell'applicazione. La tabella seguente riepiloga i tipi di proprietà a cui è possibile stabilire l'associazione in un'applicazione eseguita con attendibilità totale o parziale.

|Tipo di proprietà<br /><br /> (tutti i modificatori di accesso)|Proprietà dell'oggetto dinamico|Proprietà dell'oggetto dinamico|Proprietà CLR|Proprietà CLR|Proprietà di dipendenza|Proprietà di dipendenza|
|------------------------------------------------|-----------------------------|-----------------------------|------------------|------------------|-------------------------|-------------------------|
|**Livello di attendibilità**|**Attendibilità totale**|**Attendibilità parziale**|**Attendibilità totale**|**Attendibilità parziale**|**Attendibilità totale**|**Attendibilità parziale**|
|Classe pubblica|Yes|Yes|Yes|Yes|Yes|Yes|
|Classe non pubblica|Yes|No|Yes|No|Yes|Yes|

 Questa tabella descrive punti importanti relativi ai requisiti di autorizzazione per il data binding.

- Per le proprietà CLR, data binding funziona purché il motore di associazione sia in grado di accedere alla proprietà di origine del binding mediante reflection. In caso contrario, viene generato un avviso relativo all'impossibilità di trovare la proprietà e viene usato il valore di fallback o quello predefinito, se disponibile.

- È possibile creare associazioni alle proprietà degli oggetti dinamici definiti in fase di compilazione o di esecuzione.

- È sempre possibile stabilire l'associazione alle proprietà di dipendenza.

 Il requisito di autorizzazione per l'associazione XML è simile. In una sandbox con attendibilità parziale, <xref:System.Windows.Data.XmlDataProvider> ha esito negativo quando non dispone delle autorizzazioni per accedere ai dati specificati.

 Gli oggetti con un tipo anonimo sono interni. È possibile creare associazioni a proprietà di tipi anonimi solo in fase di esecuzione con attendibilità totale. Per altre informazioni sui tipi anonimi, vedere [Tipi anonimi (Guida per programmatori C#)](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) o [Tipi anonimi (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

 Per altre informazioni sulla sicurezza con attendibilità parziale, vedere [Sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.ObjectDataProvider>
- <xref:System.Windows.Data.XmlDataProvider>
- [Specificare l'origine di associazione](how-to-specify-the-binding-source.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Panoramica dei data binding WPF con LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md)
- [Ottimizzare le prestazioni di data binding](../advanced/optimizing-performance-data-binding.md)
