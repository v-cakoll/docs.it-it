---
title: Architettura del componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
ms.openlocfilehash: 54a23ba899ceb05701fe3580aefbb723c6b3f0fd
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364413"
---
# <a name="bindingsource-component-architecture"></a>Architettura del componente BindingSource
Con il <xref:System.Windows.Forms.BindingSource> componente è possibile associare in modo universale tutti i controlli Windows Forms alle origini dati.  
  
 Il <xref:System.Windows.Forms.BindingSource> componente semplifica il processo di associazione dei controlli a un'origine dati e offre i vantaggi seguenti rispetto ai data binding tradizionali:  
  
- Abilita l'associazione in fase di progettazione a oggetti business.  
  
- <xref:System.Windows.Forms.CurrencyManager> Incapsula la <xref:System.Windows.Forms.CurrencyManager> funzionalità ed espone gli eventi in fase di progettazione.  
  
- Semplifica la creazione di un elenco che supporta <xref:System.ComponentModel.IBindingList> l'interfaccia fornendo una notifica di modifica dell'elenco per le origini dati che non supportano in modo nativo la notifica di modifica dell'elenco.  
  
- Fornisce un punto di estendibilità <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> per il metodo.  
  
- Fornisce un livello di riferimento indiretto tra l'origine dati e il controllo. Questo riferimento indiretto è importante quando l'origine dati può cambiare in fase di esecuzione.  
  
- Interagisce con altri controlli Windows Forms correlati ai dati, in particolare i <xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.DataGridView> controlli e.  
  
 Per questi motivi, il <xref:System.Windows.Forms.BindingSource> componente è il modo migliore per associare i controlli Windows Forms alle origini dati.  
  
## <a name="bindingsource-features"></a>Funzionalità BindingSource  
 Il <xref:System.Windows.Forms.BindingSource> componente fornisce diverse funzionalità per l'associazione dei controlli ai dati. Grazie a queste funzionalità, è possibile implementare la maggior parte degli scenari di data binding con quasi nessuna codifica.  
  
 Questa operazione viene eseguita dal componentefornendoun'interfacciacoerenteperl'accessoamoltitipidiversidioriginidati.<xref:System.Windows.Forms.BindingSource> Ciò significa che si utilizza la stessa procedura per l'associazione a qualsiasi tipo. Ad esempio, è possibile aggiungere la <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà a un <xref:System.Data.DataSet> oggetto o a un oggetto business e in entrambi i casi si utilizza lo stesso set di proprietà, metodi ed eventi per modificare l'origine dati.  
  
 L'interfaccia coerente fornita dal <xref:System.Windows.Forms.BindingSource> componente semplifica notevolmente il processo di associazione dei dati ai controlli. Per i tipi di origine dati che forniscono notifiche di modifica <xref:System.Windows.Forms.BindingSource> , il componente comunica automaticamente le modifiche tra il controllo e l'origine dati. Per i tipi di origine dati che non forniscono notifiche di modifica, vengono forniti gli eventi che consentono di generare notifiche di modifica. Nell'elenco seguente vengono illustrate le funzionalità supportate <xref:System.Windows.Forms.BindingSource> dal componente:  
  
- Indirezione.  
  
- Gestione della valuta.  
  
- Origine dati sotto forma di elenco.  
  
- <xref:System.Windows.Forms.BindingSource><xref:System.ComponentModel.IBindingList>come.  
  
- Creazione di elementi personalizzati.  
  
- Creazione di elementi transazionali.  
  
- <xref:System.Collections.IEnumerable>supporto.  
  
- Supporto in fase di progettazione.  
  
- Metodi <xref:System.Windows.Forms.ListBindingHelper> statici.  
  
- Ordinamento e filtro con l' <xref:System.ComponentModel.IBindingListView> interfaccia.  
  
- Integrazione con <xref:System.Windows.Forms.BindingNavigator>.  
  
### <a name="indirection"></a>Riferimento indiretto  
 Il <xref:System.Windows.Forms.BindingSource> componente fornisce un livello di riferimento indiretto tra un controllo e un'origine dati. Anziché associare un controllo direttamente a un'origine dati, è necessario associare il controllo a un <xref:System.Windows.Forms.BindingSource>oggetto e associare l'origine dati <xref:System.Windows.Forms.BindingSource> alla <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà del componente.  
  
 Con questo livello di riferimento indiretto è possibile modificare l'origine dati senza reimpostare l'associazione del controllo. Ciò offre le funzionalità seguenti:  
  
- È possibile associare l' <xref:System.Windows.Forms.BindingSource> oggetto a origini dati diverse mantenendo le associazioni di controllo correnti.  
  
- È possibile modificare gli elementi nell'origine dati e inviare notifiche ai controlli associati. Per altre informazioni, vedere [Procedura: Riflette gli aggiornamenti dell'origine dati in un controllo Windows Forms con](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)BindingSource.  
  
- È possibile eseguire l'associazione <xref:System.Type> a un anziché a un oggetto in memoria. Per altre informazioni, vedere [Procedura: Associare un controllo Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md). È quindi possibile eseguire l'associazione a un oggetto in fase di esecuzione.  
  
### <a name="currency-management"></a>Gestione della valuta  
 Il <xref:System.Windows.Forms.BindingSource> componente implementa l' <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaccia per gestire la gestione della valuta. Con l' <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaccia, è anche possibile accedere al gestore della valuta per un <xref:System.Windows.Forms.BindingSource>, oltre al gestore della valuta per un altro <xref:System.Windows.Forms.BindingSource> associato allo stesso <xref:System.Windows.Forms.BindingSource.DataMember%2A>.  
  
 Il <xref:System.Windows.Forms.BindingSource> componente <xref:System.Windows.Forms.CurrencyManager> incapsula la funzionalità ed espone le proprietà e gli eventi più comuni. <xref:System.Windows.Forms.CurrencyManager> Nella tabella seguente vengono descritti alcuni dei membri correlati alla gestione della valuta.  
  
 Proprietà<xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>  
 Ottiene il gestore valute associato a <xref:System.Windows.Forms.BindingSource>.  
  
 Metodo <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A>  
 Se è presente un <xref:System.Windows.Forms.BindingSource> altro associato al membro dati specificato, ottiene il gestore della valuta.  
  
 Proprietà<xref:System.Windows.Forms.BindingSource.Current%2A>  
 Ottiene l'elemento corrente dell'origine dati.  
  
 Proprietà<xref:System.Windows.Forms.BindingSource.Position%2A>  
 Ottiene o imposta la posizione corrente nell'elenco sottostante.  
  
 Metodo <xref:System.Windows.Forms.BindingSource.EndEdit%2A>  
 Applica le modifiche in sospeso all'origine dati sottostante.  
  
 Metodo <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>  
 Annulla l'operazione di modifica corrente.  
  
### <a name="data-source-as-a-list"></a>Origine dati sotto forma di elenco  
 Il <xref:System.Windows.Forms.BindingSource> componente implementa le <xref:System.ComponentModel.IBindingListView> interfacce <xref:System.ComponentModel.ITypedList> e. Con questa implementazione, è possibile usare il <xref:System.Windows.Forms.BindingSource> componente stesso come origine dati, senza alcuna archiviazione esterna.  
  
 Quando il <xref:System.Windows.Forms.BindingSource> componente è associato a un'origine dati, espone l'origine dati come elenco.  
  
 La <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà può essere impostata su diverse origini dati. Sono inclusi tipi, oggetti ed elenchi di tipi. L'origine dati risultante verrà esposta come elenco. Nella tabella seguente vengono illustrate alcune delle origini dati comuni e la valutazione dell'elenco risultante.  
  
|Proprietà DataSource|Elencare i risultati|  
|-------------------------|------------------|  
|Riferimento null (`Nothing` in Visual Basic)|Oggetto vuoto <xref:System.ComponentModel.IBindingList> di oggetti. L'aggiunta di un elemento consente di impostare l'elenco sul tipo dell'elemento aggiunto.|  
|Riferimento null (`Nothing` in Visual Basic) con <xref:System.Windows.Forms.BindingSource.DataMember%2A> set|Non supportato. genera <xref:System.ArgumentException>.|  
|Tipo non elenco o oggetto di tipo "T"|Oggetto vuoto <xref:System.ComponentModel.IBindingList> di tipo "T".|  
|Istanza di matrice|Oggetto <xref:System.ComponentModel.IBindingList> contenente gli elementi della matrice.|  
|<xref:System.Collections.IEnumerable>istanza|Oggetto <xref:System.ComponentModel.IBindingList> contenente gli <xref:System.Collections.IEnumerable> elementi|  
|Istanza di elenco che contiene il tipo "T"|Istanza <xref:System.ComponentModel.IBindingList> di che contiene il tipo "T".|  
  
 Inoltre, <xref:System.Windows.Forms.BindingSource.DataSource%2A> può essere impostato su altri tipi di elenco, <xref:System.ComponentModel.IListSource> ad esempio <xref:System.ComponentModel.ITypedList>e, e <xref:System.Windows.Forms.BindingSource> l'oggetto li gestirà in modo appropriato. In questo caso, il tipo contenuto nell'elenco deve avere un costruttore senza parametri.  
  
### <a name="bindingsource-as-an-ibindinglist"></a>BindingSource come IBindingList  
 Il <xref:System.Windows.Forms.BindingSource> componente fornisce i membri per l'accesso e la modifica dei dati sottostanti <xref:System.ComponentModel.IBindingList>come. Nella tabella seguente vengono descritti alcuni di questi membri.  
  
|Member|Descrizione|  
|------------|-----------------|  
|Proprietà<xref:System.Windows.Forms.BindingSource.List%2A>|Ottiene l'elenco risultante dalla valutazione delle <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà o. <xref:System.Windows.Forms.BindingSource.DataMember%2A>|  
|Metodo <xref:System.Windows.Forms.BindingSource.AddNew%2A>|Aggiunge un nuovo elemento all'elenco sottostante. Si applica alle origini dati che implementano l' <xref:System.ComponentModel.IBindingList> interfaccia e consentono l'aggiunta di elementi (ovvero la <xref:System.Windows.Forms.BindingSource.AllowNew%2A> proprietà è `true`impostata su).|  
  
### <a name="custom-item-creation"></a>Creazione di elementi personalizzati  
 È possibile gestire l' <xref:System.Windows.Forms.BindingSource.AddingNew> evento per fornire la logica di creazione dell'elemento. L' <xref:System.Windows.Forms.BindingSource.AddingNew> evento si verifica prima <xref:System.Windows.Forms.BindingSource>che un nuovo oggetto venga aggiunto a. Questo evento viene generato dopo la <xref:System.Windows.Forms.BindingSource.AddNew%2A> chiamata del metodo, ma prima che il nuovo elemento venga aggiunto all'elenco sottostante. Gestendo questo evento, è possibile fornire un comportamento personalizzato per la <xref:System.Windows.Forms.BindingSource> creazione di elementi senza derivare dalla classe. Per altre informazioni, vedere [Procedura: Personalizzare l'aggiunta di elementi con il](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)Windows Forms BindingSource.  
  
### <a name="transactional-item-creation"></a>Creazione di elementi transazionali  
 Il <xref:System.Windows.Forms.BindingSource> componente implementa l' <xref:System.ComponentModel.ICancelAddNew> interfaccia, che consente la creazione di elementi transazionali. Dopo la creazione provvisoria di un nuovo elemento tramite una chiamata a <xref:System.Windows.Forms.BindingSource.AddNew%2A>, è possibile eseguire il commit o il rollback dell'aggiunta nei modi seguenti:  
  
- Il <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> metodo eseguirà il commit esplicito dell'addizione in sospeso.  
  
- L'esecuzione di un'altra operazione di raccolta, ad esempio l'inserimento, la rimozione o lo spostamento, eseguirà in modo implicito il commit dell'aggiunta in sospeso.  
  
- Se <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> non è già stato eseguito il commit del metodo, il metodo eseguirà il rollback dell'aggiunta in sospeso.  
  
### <a name="ienumerable-support"></a>Supporto di IEnumerable  
 Il <xref:System.Windows.Forms.BindingSource> componente consente di associare i <xref:System.Collections.IEnumerable> controlli alle origini dati. Con questo componente è possibile eseguire l'associazione a un'origine dati, ad <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType>esempio.  
  
 Quando un' <xref:System.Collections.IEnumerable> origine dati viene assegnata <xref:System.Windows.Forms.BindingSource> al <xref:System.ComponentModel.IBindingList> componente, <xref:System.Windows.Forms.BindingSource> <xref:System.Collections.IEnumerable> crea e aggiunge il contenuto dell'origine dati all'elenco.  
  
### <a name="design-time-support"></a>Supporto della fase di progettazione  
 Non è possibile creare alcuni tipi di oggetto in fase di progettazione, ad esempio oggetti creati da una classe factory o oggetti restituiti da un servizio Web. Talvolta è necessario associare i controlli a questi tipi in fase di progettazione, anche se non è presente alcun oggetto in memoria a cui è possibile associare i controlli. È possibile, ad esempio, etichettare le intestazioni di colonna di un <xref:System.Windows.Forms.DataGridView> controllo con i nomi delle proprietà pubbliche del tipo personalizzato.  
  
 Per supportare questo scenario, il <xref:System.Windows.Forms.BindingSource> componente supporta l'associazione a <xref:System.Type>un. Quando si assegna un <xref:System.Type> oggetto <xref:System.Windows.Forms.BindingSource.DataSource%2A> alla proprietà, il <xref:System.Windows.Forms.BindingSource> componente crea un oggetto <xref:System.ComponentModel.BindingList%601> vuoto <xref:System.Type> di elementi. Tutti i controlli che successivamente vengono associati <xref:System.Windows.Forms.BindingSource> al componente verranno avvisati della presenza delle proprietà o dello schema del tipo in fase di progettazione o in fase di esecuzione. Per altre informazioni, vedere [Procedura: Associare un controllo Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md).  
  
### <a name="static-listbindinghelper-methods"></a>Metodi ListBindingHelper statici  
 I <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>tipi <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType>, `DataMember` e <xref:System.Windows.Forms.BindingSource> condividono la logica comune per generare un elenco da una `DataSource` / coppia. Questa logica comune è inoltre esposta pubblicamente per l'uso da parte degli autori di controlli e di terze parti nei metodi seguenti `static` :  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
- [https://login.microsoftonline.com/consumers/](<xref:System.Windows.Forms.ListBindingHelper.GetList%2A>).  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>Ordinamento e filtro con l'interfaccia IBindingListView  
 Il <xref:System.Windows.Forms.BindingSource> componente implementa l' <xref:System.ComponentModel.IBindingListView> interfaccia, che estende l' <xref:System.ComponentModel.IBindingList> interfaccia. Offre <xref:System.ComponentModel.IBindingList> l'ordinamento a colonna singola <xref:System.ComponentModel.IBindingListView> e offre funzionalità avanzate di ordinamento e filtro. Con <xref:System.ComponentModel.IBindingListView>è possibile ordinare e filtrare gli elementi nell'origine dati, se l'origine dati implementa anche una di queste interfacce. Il <xref:System.Windows.Forms.BindingSource> componente non fornisce un'implementazione di riferimento di questi membri. Al contrario, le chiamate vengono trasmesse all'elenco sottostante.  
  
 Nella tabella seguente vengono descritte le proprietà utilizzate per l'ordinamento e il filtro.  
  
|Member|Descrizione|  
|------------|-----------------|  
|Proprietà<xref:System.Windows.Forms.BindingSource.Filter%2A>|Se l'origine dati è un <xref:System.ComponentModel.IBindingListView>, ottiene o imposta l'espressione usata per filtrare le righe da visualizzare.|  
|Proprietà<xref:System.Windows.Forms.BindingSource.Sort%2A>|Se l'origine dati è un <xref:System.ComponentModel.IBindingList>, ottiene o imposta un nome di colonna usato per l'ordinamento e il criterio di ordinamento.<br /><br /> -oppure-<br /><br /> Se l'origine dati è un <xref:System.ComponentModel.IBindingListView> oggetto e supporta l'ordinamento avanzato, ottiene più nomi di colonna usati per l'ordinamento e l'ordinamento|  
  
### <a name="integration-with-bindingnavigator"></a>Integrazione con BindingNavigator  
 È possibile utilizzare il <xref:System.Windows.Forms.BindingSource> componente per associare qualsiasi controllo Windows Forms a un'origine dati, ma il <xref:System.Windows.Forms.BindingNavigator> controllo è progettato specificamente per l'utilizzo con <xref:System.Windows.Forms.BindingSource> il componente. Il <xref:System.Windows.Forms.BindingNavigator> controllo fornisce un'interfaccia utente per il controllo <xref:System.Windows.Forms.BindingSource> dell'elemento corrente del componente. Per impostazione predefinita, <xref:System.Windows.Forms.BindingNavigator> il controllo fornisce pulsanti che corrispondono ai metodi di navigazione <xref:System.Windows.Forms.BindingSource> sul componente. Per altre informazioni, vedere [Procedura: Esplorare i dati con il controllo](how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md)BindingNavigator Windows Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Cenni preliminari sul componente BindingSource](bindingsource-component-overview.md)
- [Controllo BindingNavigator](bindingnavigator-control-windows-forms.md)
- [Data binding in Windows Form](../windows-forms-data-binding.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Procedura: Associare un controllo Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Procedura: Riflettere gli aggiornamenti dell'origine dati in un controllo Windows Forms con BindingSource](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
