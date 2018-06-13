---
title: Architettura del componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
ms.openlocfilehash: b0334bd7a0bc5ff46c43fd7ee549422d98c35efe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529260"
---
# <a name="bindingsource-component-architecture"></a>Architettura del componente BindingSource
Con il <xref:System.Windows.Forms.BindingSource> componente, è possibile associare universalmente tutti i controlli Windows Form alle origini dati.  
  
 Il <xref:System.Windows.Forms.BindingSource> componente semplifica il processo di associazione di controlli a un'origine dati e fornisce i seguenti vantaggi rispetto all'associazione dati tradizionale:  
  
-   Consente l'associazione in fase di progettazione per gli oggetti business.  
  
-   Incapsula <xref:System.Windows.Forms.CurrencyManager> funzionalità ed espone <xref:System.Windows.Forms.CurrencyManager> eventi in fase di progettazione.  
  
-   Semplifica la creazione di un elenco che supporta il <xref:System.ComponentModel.IBindingList> interfaccia, fornendo la notifica di modifica nell'elenco per le origini dati che non supportano in modo nativo l'elenco di notifiche di modifica.  
  
-   Fornisce un punto di estensibilità per il <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> metodo.  
  
-   Fornisce un livello di riferimento indiretto tra l'origine dati e il controllo. Questo riferimento indiretto è importante quando l'origine dati potrebbe cambiare in fase di esecuzione.  
  
-   Interagisce con altri controlli Windows Form dati correlati, in particolare il <xref:System.Windows.Forms.BindingNavigator> e <xref:System.Windows.Forms.DataGridView> controlli.  
  
 Per questi motivi, il <xref:System.Windows.Forms.BindingSource> componente è il modo migliore per associare i controlli Windows Form alle origini dati.  
  
## <a name="bindingsource-features"></a>Funzionalità di BindingSource  
 Il <xref:System.Windows.Forms.BindingSource> componente fornisce diverse funzionalità per l'associazione di controlli ai dati. Con queste funzionalità, è possibile implementare la maggior parte degli scenari di associazione dati con quasi alcun codice da parte dell'utente.  
  
 Il <xref:System.Windows.Forms.BindingSource> componente esegue questa operazione fornendo un'interfaccia coerente per l'accesso a diversi tipi di origini dati. Ciò significa che utilizzare la stessa procedura per l'associazione a qualsiasi tipo. Ad esempio, è possibile collegare il <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà per un <xref:System.Data.DataSet> o a un oggetto business e in entrambi i casi è usare lo stesso set di proprietà, metodi ed eventi per modificare l'origine dati.  
  
 L'interfaccia coerenza fornita dal <xref:System.Windows.Forms.BindingSource> componente semplifica notevolmente il processo di associazione dati ai controlli. Per i tipi di origini che forniscono la notifica di modifica di <xref:System.Windows.Forms.BindingSource> componente comunica automaticamente le modifiche tra il controllo e l'origine dati. Per i tipi di origine dati che non forniscono la notifica delle modifiche, vengono forniti eventi che consentono di generare notifiche di modifica. L'elenco seguente illustra le funzionalità supportate dal <xref:System.Windows.Forms.BindingSource> componente:  
  
-   Riferimento indiretto.  
  
-   Gestione di valuta.  
  
-   Origine dati sotto forma di elenco.  
  
-   <xref:System.Windows.Forms.BindingSource> come un <xref:System.ComponentModel.IBindingList>.  
  
-   Creazione di un elemento personalizzato.  
  
-   Creazione di elementi transazionale.  
  
-   <xref:System.Collections.IEnumerable> supporto.  
  
-   Supporto in fase di progettazione.  
  
-   Statico <xref:System.Windows.Forms.ListBindingHelper> metodi.  
  
-   Ordinamento e filtro con il <xref:System.ComponentModel.IBindingListView> interfaccia.  
  
-   Integrazione con <xref:System.Windows.Forms.BindingNavigator>.  
  
### <a name="indirection"></a>Riferimento indiretto  
 Il <xref:System.Windows.Forms.BindingSource> componente fornisce un livello di riferimento indiretto tra un controllo e un'origine dati. Anziché associare un controllo direttamente a un'origine dati, associare il controllo a un <xref:System.Windows.Forms.BindingSource>, e si collega l'origine dati per il <xref:System.Windows.Forms.BindingSource> del componente <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà.  
  
 Con questo livello di riferimento indiretto, è possibile modificare l'origine dati senza reimpostare l'associazione del controllo. In questo modo le funzionalità seguenti:  
  
-   È possibile collegare il <xref:System.Windows.Forms.BindingSource> a origini dati diverse, mantenendo le associazioni del controllo corrente.  
  
-   È possibile modificare gli elementi nell'origine dati e inviare una notifica di controlli associati. Per ulteriori informazioni, vedere [procedura: riflettere gli aggiornamenti dell'origine dati in un controllo Windows Form con BindingSource](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md).  
  
-   È possibile associare a un <xref:System.Type> anziché un oggetto in memoria. Per ulteriori informazioni, vedere [procedura: associare un controllo Windows Form a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md). È quindi possibile associare a un oggetto in fase di esecuzione.  
  
### <a name="currency-management"></a>Gestione di valuta  
 Il <xref:System.Windows.Forms.BindingSource> componente implementa il <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaccia per la gestione per la gestione. Con il <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaccia, è inoltre possibile accedere all'oggetto CurrencyManager per un <xref:System.Windows.Forms.BindingSource>, oltre il gestore della valuta per un altro <xref:System.Windows.Forms.BindingSource> associati alla stessa <xref:System.Windows.Forms.BindingSource.DataMember%2A>.  
  
 Il <xref:System.Windows.Forms.BindingSource> componente incapsula <xref:System.Windows.Forms.CurrencyManager> funzionalità ed espone i più comuni <xref:System.Windows.Forms.CurrencyManager> proprietà ed eventi. Nella tabella seguente vengono descritti alcuni dei membri relativi alla gestione di valuta.  
  
 Proprietà <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>  
 Ottiene l'oggetto CurrencyManager associato il <xref:System.Windows.Forms.BindingSource>.  
  
 Metodo <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A>  
 Se esiste un altro <xref:System.Windows.Forms.BindingSource> associata al membro dati specificato, ottiene l'oggetto CurrencyManager.  
  
 Proprietà <xref:System.Windows.Forms.BindingSource.Current%2A>  
 Ottiene l'elemento corrente dell'origine dati.  
  
 Proprietà <xref:System.Windows.Forms.BindingSource.Position%2A>  
 Ottiene o imposta la posizione corrente nell'elenco sottostante.  
  
 Metodo <xref:System.Windows.Forms.BindingSource.EndEdit%2A>  
 Applica le modifiche in sospeso all'origine dati sottostante.  
  
 Metodo <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>  
 Annulla l'operazione di modifica corrente.  
  
### <a name="data-source-as-a-list"></a>Origine dati sotto forma di elenco  
 Il <xref:System.Windows.Forms.BindingSource> componente implementa il <xref:System.ComponentModel.IBindingListView> e <xref:System.ComponentModel.ITypedList> interfacce. Con questa implementazione, è possibile utilizzare il <xref:System.Windows.Forms.BindingSource> componente stesso come un'origine dati, senza archivio esterno.  
  
 Quando il <xref:System.Windows.Forms.BindingSource> componente è collegato a un'origine dati, che espone l'origine dati sotto forma di elenco.  
  
 Il <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà può essere impostata su diverse origini dati. Tra i tipi di oggetti e gli elenchi di tipi. L'origine dati risultante verrà esposta come elenco. Nella tabella seguente vengono illustrate alcune delle origini dati comuni e la valutazione dell'elenco risultante.  
  
|Proprietà DataSource|Elenco risultati|  
|-------------------------|------------------|  
|Riferimento null (`Nothing` in Visual Basic)|Un oggetto vuoto <xref:System.ComponentModel.IBindingList> di oggetti. Aggiunta di un elemento imposta l'elenco per il tipo dell'elemento aggiunto.|  
|Un riferimento null (`Nothing` in Visual Basic) con <xref:System.Windows.Forms.BindingSource.DataMember%2A> impostato|Non è supportato. Genera <xref:System.ArgumentException>.|  
|Tipo non di elenco o un oggetto di tipo "T"|Un oggetto vuoto <xref:System.ComponentModel.IBindingList> di tipo "T".|  
|Istanza di matrice|Un <xref:System.ComponentModel.IBindingList> contenente gli elementi della matrice.|  
|<xref:System.Collections.IEnumerable> Istanza|Un <xref:System.ComponentModel.IBindingList> contenente il <xref:System.Collections.IEnumerable> elementi|  
|Elenco contenente il tipo di istanza "T"|Un <xref:System.ComponentModel.IBindingList> istanza contenente il tipo "T".|  
  
 Inoltre, <xref:System.Windows.Forms.BindingSource.DataSource%2A> può essere impostata su altri tipi di elenco, ad esempio <xref:System.ComponentModel.IListSource> e <xref:System.ComponentModel.ITypedList>e <xref:System.Windows.Forms.BindingSource> li gestirà in modo appropriato. In questo caso, il tipo di contenuto nell'elenco deve avere un costruttore predefinito.  
  
### <a name="bindingsource-as-an-ibindinglist"></a>BindingSource come un elemento IBindingList  
 Il <xref:System.Windows.Forms.BindingSource> componente fornisce membri per l'accesso e la manipolazione dei dati sottostanti come un <xref:System.ComponentModel.IBindingList>. Nella tabella seguente vengono descritti alcuni di questi membri.  
  
|Member|Descrizione|  
|------------|-----------------|  
|Proprietà <xref:System.Windows.Forms.BindingSource.List%2A>|Ottiene l'elenco risultante dalla valutazione del <xref:System.Windows.Forms.BindingSource.DataSource%2A> o <xref:System.Windows.Forms.BindingSource.DataMember%2A> proprietà.|  
|Metodo <xref:System.Windows.Forms.BindingSource.AddNew%2A>|Aggiunge un nuovo elemento all'elenco sottostante. Si applica a origini dati che implementano il <xref:System.ComponentModel.IBindingList> l'interfaccia e consentire l'aggiunta di elementi (vale a dire il <xref:System.Windows.Forms.BindingSource.AllowNew%2A> è impostata su `true`).|  
  
### <a name="custom-item-creation"></a>Creazione di un elemento personalizzato  
 È possibile gestire il <xref:System.Windows.Forms.BindingSource.AddingNew> evento per fornire la logica di creazione degli elementi. Il <xref:System.Windows.Forms.BindingSource.AddingNew> evento si verifica prima dell'aggiunta di un nuovo oggetto di <xref:System.Windows.Forms.BindingSource>. Questo evento viene generato dopo il <xref:System.Windows.Forms.BindingSource.AddNew%2A> metodo viene chiamato, ma prima che il nuovo elemento viene aggiunto all'elenco sottostante. La gestione dell'evento, è possibile fornire il comportamento di creazione di un elemento personalizzato senza derivazione da di <xref:System.Windows.Forms.BindingSource> classe. Per ulteriori informazioni, vedere [procedura: personalizzare aggiunta di elementi con BindingSource Windows Form](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md).  
  
### <a name="transactional-item-creation"></a>Creazione di elementi transazionale  
 Il <xref:System.Windows.Forms.BindingSource> componente implementa il <xref:System.ComponentModel.ICancelAddNew> interfaccia, che consente la creazione di un articolo transazionale. Dopo che è temporaneamente creato un nuovo elemento con una chiamata a <xref:System.Windows.Forms.BindingSource.AddNew%2A>, l'aggiunta può essere eseguito il commit o rollback nei modi seguenti:  
  
-   Il <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> metodo eseguirà il commit in modo esplicito l'aggiunta in sospeso.  
  
-   Esecuzione di un'altra operazione di raccolta, ad esempio un inserimento, rimozione o spostamento, in modo implicito eseguirà il commit dell'operazione di aggiunta.  
  
-   Il <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> metodo eseguirà il rollback dell'aggiunta in sospeso se il metodo non è già stato eseguito il commit.  
  
### <a name="ienumerable-support"></a>Supporto di IEnumerable  
 Il <xref:System.Windows.Forms.BindingSource> componente consente l'associazione dei controlli <xref:System.Collections.IEnumerable> origini dati. Con questo componente, è possibile associare a un'origine dati, ad esempio un <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType>.  
  
 Quando un <xref:System.Collections.IEnumerable> origine dati viene assegnata al <xref:System.Windows.Forms.BindingSource> componente, il <xref:System.Windows.Forms.BindingSource> crea un <xref:System.ComponentModel.IBindingList> e aggiunge il contenuto del <xref:System.Collections.IEnumerable> origine dati nell'elenco.  
  
### <a name="design-time-support"></a>Supporto in fase di progettazione  
 Alcuni tipi di oggetto non possono essere creati in fase di progettazione, ad esempio gli oggetti creati da una classe factory o gli oggetti restituiti da un servizio Web. In alcuni casi è possibile associare i controlli a questi tipi in fase di progettazione, anche se è presente alcun oggetto in memoria a cui è possibile associare i controlli. Potrebbe, ad esempio, devi etichettare le intestazioni di colonna di un <xref:System.Windows.Forms.DataGridView> controllo con i nomi delle proprietà pubbliche del tipo personalizzato.  
  
 Per supportare questo scenario, il <xref:System.Windows.Forms.BindingSource> componente supporta l'associazione a un <xref:System.Type>. Quando si assegna un <xref:System.Type> per il <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà, il <xref:System.Windows.Forms.BindingSource> componente crea un oggetto vuoto <xref:System.ComponentModel.BindingList%601> di <xref:System.Type> elementi. Tutti i controlli associati a successivamente il <xref:System.Windows.Forms.BindingSource> componente riceverà un avviso per la presenza delle proprietà dello schema del tipo in fase di progettazione o in fase di esecuzione. Per ulteriori informazioni, vedere [procedura: associare un controllo Windows Form a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md).  
  
### <a name="static-listbindinghelper-methods"></a>Metodi ListBindingHelper static  
 Il <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>, <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType>, e <xref:System.Windows.Forms.BindingSource> tipi condividono tutti una logica comune per generare un elenco da un `DataSource` / `DataMember` coppia. Inoltre, questa logica comune viene esposta pubblicamente per l'utilizzo dagli autori di controllo e di terze parti nell'esempio seguente `static` metodi:  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>Ordinamento e filtro con l'interfaccia IBindingListView  
 Il <xref:System.Windows.Forms.BindingSource> componente implementa il <xref:System.ComponentModel.IBindingListView> interfaccia, che estende il <xref:System.ComponentModel.IBindingList> interfaccia. Il <xref:System.ComponentModel.IBindingList> offre una singola colonna di ordinamento e il <xref:System.ComponentModel.IBindingListView> offre avanzate di ordinamento e filtro. Con <xref:System.ComponentModel.IBindingListView>, è possibile ordinare e filtrare gli elementi nell'origine dati, se l'origine dati anche implementa una di queste interfacce. Il <xref:System.Windows.Forms.BindingSource> componente non fornisce un'implementazione di riferimento di questi membri. Al contrario, le chiamate vengono inoltrate all'elenco sottostante.  
  
 Nella tabella seguente vengono descritte le proprietà utilizzate per l'ordinamento e filtro.  
  
|Member|Descrizione|  
|------------|-----------------|  
|Proprietà <xref:System.Windows.Forms.BindingSource.Filter%2A>|Se l'origine dati è un <xref:System.ComponentModel.IBindingListView>, ottiene o imposta l'espressione usata per filtrare le righe da visualizzare.|  
|Proprietà <xref:System.Windows.Forms.BindingSource.Sort%2A>|Se l'origine dati è un <xref:System.ComponentModel.IBindingList>, ottiene o imposta un nome di colonna usato per l'ordinamento e il criterio di ordinamento.<br /><br /> oppure<br /><br /> Se l'origine dati è un <xref:System.ComponentModel.IBindingListView> e supporta l'ordinamento avanzato, ottiene più nomi di colonna usati per l'ordinamento e di ordinamento|  
  
### <a name="integration-with-bindingnavigator"></a>Integrazione con BindingNavigator  
 È possibile utilizzare il <xref:System.Windows.Forms.BindingSource> componente per associare qualsiasi controllo Windows Form a un'origine dati, ma la <xref:System.Windows.Forms.BindingNavigator> controllo è progettato specificamente per l'utilizzo di <xref:System.Windows.Forms.BindingSource> componente. Il <xref:System.Windows.Forms.BindingNavigator> controllo fornisce un'interfaccia utente per il controllo di <xref:System.Windows.Forms.BindingSource> elemento corrente del componente. Per impostazione predefinita, il <xref:System.Windows.Forms.BindingNavigator> controllo fornisce pulsanti che corrispondono ai metodi di navigazione nel <xref:System.Windows.Forms.BindingSource> componente. Per ulteriori informazioni, vedere [procedura: passare dati con il controllo BindingNavigator Windows Form](../../../../docs/framework/winforms/controls/how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [Cenni preliminari sul componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)  
 [Controllo BindingNavigator](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [Data binding in Windows Form](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Procedura: Associare un controllo di Windows Form a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [Procedura: riflettere gli aggiornamenti dell'origine dati in un controllo Windows Form con BindingSource](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
