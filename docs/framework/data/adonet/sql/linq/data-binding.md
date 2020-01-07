---
title: Data binding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cbec8b02-a1e8-4ae8-a83b-bb5190413ac5
ms.openlocfilehash: c7048d292bdf5c1372d5f8f174f7f0e84efa7593
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634716"
---
# <a name="data-binding"></a>Data binding

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta l'associazione a controlli comuni, ad esempio i controlli griglia. In particolare, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] definisce i modelli di base per l'associazione a una griglia di dati e la gestione del binding Master-Details, sia per quanto riguarda la visualizzazione che l'aggiornamento.

## <a name="underlying-principle"></a>Principio sottostante

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] converte le query LINQ in SQL per l'esecuzione in un database. I risultati sono costituiti da oggetti `IEnumerable` fortemente tipizzati. Poiché si tratta di oggetti di Common Language Runtime ordinari (CLR), è possibile usare l'data binding di oggetti ordinaria per visualizzare i risultati. Al contrario, le operazioni di modifica (inserimenti, aggiornamenti ed eliminazioni) richiedono passaggi aggiuntivi.

## <a name="operation"></a>Operazione

L'associazione implicita ai controlli Windows Form viene eseguita implementando <xref:System.ComponentModel.IListSource>. Le origini dati <xref:System.Data.Linq.Table%601> generici ( C#`Table<T>` in o `Table(Of T)` in Visual Basic) e i `DataQuery` generici sono stati aggiornati per implementare <xref:System.ComponentModel.IListSource>. I motori di associazione dati dell'interfaccia utente (Windows Form e Windows Presentation Foundation) verificano se le relative origini dati implementano <xref:System.ComponentModel.IListSource>. Pertanto, la scrittura di un'influenza diretta di una query in un'origine dati di un controllo chiama in modo implicito [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generazione della raccolta, come nell'esempio seguente:

[!code-csharp[DLinqDataBinding#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#1)]
[!code-vb[DLinqDataBinding#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#1)]

Lo stesso comportamento si verifica con Windows Presentation Foundation:

[!code-csharp[DLinqDataBinding#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#2)]
[!code-vb[DLinqDataBinding#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#2)]

Le generazioni di raccolte vengono implementate dall'oggetto generico <xref:System.Data.Linq.Table%601> e dall'oggetto generico `DataQuery` in <xref:System.ComponentModel.IListSource.GetList%2A>.

## <a name="ilistsource-implementation"></a>Implementazione di IListSource

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementa <xref:System.ComponentModel.IListSource> in due posizioni:

- L'origine dati è un <xref:System.Data.Linq.Table%601>: [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Sfoglia la tabella per riempire una raccolta di `DataBindingList` che mantiene un riferimento alla tabella.

- L'origine dati è un oggetto <xref:System.Linq.IQueryable%601>. Gli scenari sono due:

  - Se [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] trova l'<xref:System.Data.Linq.Table%601> sottostante dalla <xref:System.Linq.IQueryable%601>, l'origine consente l'edizione e la situazione è identica a quella del primo punto.

  - Se [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non riesce a trovare l'<xref:System.Data.Linq.Table%601>sottostante, l'origine non consente l'edizione (ad esempio, `groupby`). [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Esplora la query per compilare un `SortableBindingList`generico, ovvero una semplice <xref:System.ComponentModel.BindingList%601> che implementa la funzionalità di ordinamento per le entità T per una determinata proprietà.

## <a name="specialized-collections"></a>Raccolte specializzate

Per molte funzionalità descritte in questo documento, <xref:System.ComponentModel.BindingList%601> è stato specializzato per alcune classi diverse. Tali classi, `SortableBindingList` e `DataBindingList`, sono di tipo generico e vengono entrambe dichiarate come interne.

### <a name="generic-sortablebindinglist"></a>SortableBindingList generica

Questa classe eredita da <xref:System.ComponentModel.BindingList%601> ed è una versione ordinabile di <xref:System.ComponentModel.BindingList%601>. L'ordinamento è una soluzione in memoria e non effettua mai la connessione al database. <xref:System.ComponentModel.BindingList%601> implementa <xref:System.ComponentModel.IBindingList> ma non supporta l'ordinamento per impostazione predefinita. Tuttavia, <xref:System.ComponentModel.BindingList%601> implementa <xref:System.ComponentModel.IBindingList> con i metodi di *base* virtuali. È possibile eseguire facilmente l'override di questi metodi. La classe generica `SortableBindingList` esegue l'override di <xref:System.ComponentModel.BindingList%601.SupportsSortingCore%2A>, <xref:System.ComponentModel.BindingList%601.SortPropertyCore%2A>, <xref:System.ComponentModel.BindingList%601.SortDirectionCore%2A> e <xref:System.ComponentModel.BindingList%601.ApplySortCore%2A>. `ApplySortCore` viene chiamato da <xref:System.ComponentModel.IBindingList.ApplySort%2A> e ordina l'elenco di elementi T per una determinata proprietà.

Se la proprietà non appartiene a T, viene generata un'eccezione.

Per ottenere l'ordinamento, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea una classe di `SortableBindingList.PropertyComparer` generica che eredita da <xref:System.Collections.Generic.Comparer%601.System%23Collections%23IComparer%23Compare%2A> generici e implementa un operatore di confronto predefinito per un tipo specificato T, un `PropertyDescriptor`e una direzione. Questa classe crea dinamicamente un oggetto `Comparer` di T, dove T è `PropertyType` di `PropertyDescriptor`. L'operatore di confronto predefinito viene quindi recuperato dall'oggetto statico generico `Comparer`. Usando la reflection si ottiene un'istanza predefinita.

La classe generica `SortableBindingList` è anche la classe base per `DataBindingList`. La classe generica `SortableBindingList` offre due metodi virtuali per sospendere o riprendere il rilevamento dell'aggiunta o rimozione di elementi. Questi due metodi possono essere usati per funzionalità di base come l'ordinamento, ma saranno effettivamente implementati dalle classi superiori come `DataBindingList` generico.

### <a name="generic-databindinglist"></a>DataBindingList generica

Questa classe eredita dalla classe generica `SortableBindingLIst`. La classe generica `DataBindingList` mantiene un riferimento all'oggetto generico `Table` sottostante dell'oggetto generico `IQueryable` usato per il riempimento iniziale della raccolta. La classe generica `DatabindingList` aggiunge il rilevamento dell'aggiunta o rimozione degli elementi alla raccolta eseguendo l'override di `InsertItem`() e `RemoveItem`(). Implementa inoltre la funzionalità di rilevamento della sospensione o ripresa di elementi astratti per rendere condizionale il rilevamento. Questa funzionalità consente alla classe generica `DataBindingList` di sfruttare completamente l'uso polimorfico della funzionalità di rilevamento delle classi padre.

## <a name="binding-to-entitysets"></a>Associazione a EntitySet

L'associazione a `EntitySet` è un caso speciale perché `EntitySet` è già una raccolta che implementa <xref:System.ComponentModel.IBindingList>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aggiunge il supporto per l'ordinamento e l'annullamento (<xref:System.ComponentModel.ICancelAddNew>). Una classe `EntitySet` usa un elenco interno per archiviare entità. Tale elenco è una raccolta di basso livello basato su una matrice generica, la classe `ItemList` generica.

### <a name="adding-a-sorting-feature"></a>Aggiunta di una funzionalità di ordinamento

Le matrici offrono un metodo di ordinamento (`Array.Sort()`) che può essere utilizzato con un oggetto `Comparer` di T. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizza la classe generica `SortableBindingList.PropertyComparer` descritta in questo argomento per ottenere questo oggetto `Comparer` per la proprietà e la direzione di ordinamento. Per chiamare questa funzionalità, viene aggiunto un metodo `ApplySort` all'oggetto generico `ItemList`.

Sul lato `EntitySet` è necessario dichiarare il supporto dell'ordinamento:

- <xref:System.ComponentModel.IBindingList.SupportsSorting%2A> restituisce `true`.

- <xref:System.ComponentModel.IBindingList.ApplySort%2A> chiama `entities.ApplySort()`, quindi `OnListChanged()`.

- Le proprietà <xref:System.ComponentModel.IBindingList.SortDirection%2A> e <xref:System.ComponentModel.IBindingList.SortProperty%2A> espongono la definizione di ordinamento corrente, che viene archiviata nei membri locali.

Quando si usa un oggetto System. Windows. Forms. BindingSource e si associa un elemento EntitySet\<TEntity > a System. Windows. Forms. BindingSource. DataSource, è necessario chiamare EntitySet\<TEntity >. GetNewBindingList per aggiornare BindingSource. list.

Se si usa un oggetto System. Windows. Forms. BindingSource e si imposta la proprietà BindingSource. DataMember e si imposta BindingSource. DataSource su una classe che dispone di una proprietà denominata in BindingSource. DataMember che espone EntitySet\<TEntity >, non è necessario chiamare EntitySet\<TEntity >. GetNewBindingList per aggiornare BindingSource. list ma si perde la funzionalità di ordinamento.

## <a name="caching"></a>Memorizzazione nella cache

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query implementano <xref:System.ComponentModel.IListSource.GetList%2A>. Quando la classe BindingSource di Windows Form individua questa interfaccia, chiama GetList() tre volte per una sola connessione. Per ovviare a questa situazione, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementa una cache per ogni istanza per archiviare e restituire sempre la stessa raccolta generata.

## <a name="cancellation"></a>Annullamento

<xref:System.ComponentModel.IBindingList> definisce un metodo <xref:System.ComponentModel.IBindingList.AddNew%2A> usato dai controlli per creare un nuovo elemento da una raccolta associata. Il controllo `DataGridView` mostra molto chiaramente questa funzionalità quando nell'intestazione dell'ultima riga visibile è presente un asterisco. L'asterisco indica che è possibile aggiungere un nuovo elemento.

Oltre a questa funzionalità, una raccolta consente di implementare <xref:System.ComponentModel.ICancelAddNew>. Tale funzionalità consente ai controlli di annullare o di convalidare che il nuovo elemento modificato è stato o meno convalidato.

<xref:System.ComponentModel.ICancelAddNew> viene implementato in tutte le raccolte [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] con associazione a dati (`SortableBindingList` e `EntitySet` generici). In entrambe le implementazioni il codice viene eseguito come segue:

- Consente l'inserimento e la successiva rimozione di elementi dalla raccolta.

- Non tiene traccia delle modifiche finché non ne viene eseguito il commit dall'interfaccia utente.

- Non tiene traccia delle modifiche se queste vengono annullate (<xref:System.ComponentModel.ICancelAddNew.CancelNew%2A>).

- Consente di registrare quando viene eseguito il commit della modifica (<xref:System.ComponentModel.ICancelAddNew.EndNew%2A>).

- Consente alla raccolta di comportarsi normalmente se il nuovo elemento non proviene da <xref:System.ComponentModel.IBindingList.AddNew%2A>.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Questa sezione descrive alcuni elementi che potrebbero facilitare la risoluzione dei problemi relativi alle applicazioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] con data binding.

- È necessario usare proprietà; non è sufficiente usare solo campi. Questo tipo di uso è obbligatorio in Windows Form.

- Per impostazione predefinita, i tipi di database `image`, `varbinary`e `timestamp` vengono mappati a una matrice di byte. Poiché `ToString()` non è supportato in questo scenario, questi oggetti non possono essere visualizzati.

- Un membro di classe mappato a una chiave primaria dispone di un setter, ma [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non supporta la modifica dell'identità dell'oggetto. Non è quindi possibile aggiornare la chiave primaria/univoca usata per il mapping nel database. Una modifica nella griglia genera un'eccezione quando si chiama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.

- Se un'entità è associata in due griglie separate, ad esempio una di dettaglio e una master, un'operazione `Delete` nella griglia master non viene propagata alla griglia di dettaglio.

## <a name="see-also"></a>Vedere anche

- [Informazioni di base](background-information.md)
