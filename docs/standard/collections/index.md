---
title: Raccolte e strutture di dati
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- grouping data in collections
- objects [.NET Framework], grouping in collections
- Array class, grouping data in collections
- threading [.NET Framework], safety
- Collections classes
- collections [.NET Framework]
ms.assetid: 60cc581f-1db5-445b-ba04-a173396bf872
ms.openlocfilehash: 3ca340e19d7340d7bea133fa62c6d8bbc3c0512a
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160391"
---
# <a name="collections-and-data-structures"></a>Raccolte e strutture di dati
Dati simili possono spesso essere gestiti in modo più efficiente quando memorizzati e modificati come una raccolta. È possibile usare la classe <xref:System.Array?displayProperty=nameWithType> o le classi negli spazi dei nomi <xref:System.Collections>, <xref:System.Collections.Generic>, <xref:System.Collections.Concurrent> e System.Collections.Immutable per aggiungere, rimuovere e modificare singoli elementi o un intervallo di elementi nella raccolta.  
  
 Esistono due tipi principali di raccolte: raccolte generiche e raccolte non generiche. Le raccolte generiche sono state aggiunte in.NET Framework 2.0 e sono indipendenti dai tipi in fase di compilazione. Per questo motivo, le raccolte generiche offrono in genere prestazioni migliori. Le raccolte generiche accettano un parametro di tipo quando vengono costruite e non è necessario eseguire il cast da e verso il tipo <xref:System.Object> quando si aggiungono o rimuovono elementi dalla raccolta.  Inoltre, la maggior parte delle raccolte generiche sono supportate nelle app di Windows Store. Le raccolte non generiche archiviano elementi come <xref:System.Object>, richiedono il cast e la maggior parte non sono supportate per lo sviluppo di applicazioni Windows Store. Tuttavia, si possono vedere raccolte non generiche nel codice precedente.  
  
 A partire da .NET Framework 4 le raccolte nello spazio dei nomi <xref:System.Collections.Concurrent> forniscono operazioni thread-safe efficienti per accedere agli elementi della raccolta da più thread. Le classi di raccolte non modificabili dello spazio dei nomi System.Collections.Immutable ([Pacchetto NuGet](https://www.nuget.org/packages/System.Collections.Immutable)) sono intrinsecamente thread-safe, perché le operazioni vengono eseguite su una copia della raccolta originale, che non può essere modificata.  

<a name="BKMK_Commoncollectionfeatures"></a>
## <a name="common-collection-features"></a>Funzionalità comuni delle raccolte  
 Tutte le raccolte forniscono metodi per l'aggiunta, la rimozione o la ricerca di elementi nella raccolta. In aggiunta, tutte le raccolte che implementano direttamente o indirettamente l'interfaccia <xref:System.Collections.ICollection> o l'interfaccia <xref:System.Collections.Generic.ICollection%601> condividono le funzionalità seguenti:  
  
- **La possibilità di enumerare la raccolta**  
  
     Le raccolte di .NET Framework implementano <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oppure <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> per consentire l'iterazione della raccolta. Un enumeratore può essere considerato come un puntatore che si sposta a qualsiasi elemento nella raccolta. Le istruzioni [foreach, in](../../csharp/language-reference/keywords/foreach-in.md) e [For Each...Next](../../visual-basic/language-reference/statements/for-each-next-statement.md) usano l'enumeratore esposto dal metodo <xref:System.Collections.IEnumerable.GetEnumerator%2A> e nascondono la complessità di gestione dell'enumeratore. Inoltre, qualsiasi raccolta che implementi <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> viene considerata un *tipo queryable* e può essere sottoposta a query con LINQ. Le query LINQ forniscono un modello comune per l'accesso ai dati. In genere sono più concise e leggibili dei cicli `foreach` standard e forniscono funzionalità di filtro, ordinamento e raggruppamento. Le query LINQ possono inoltre migliorare le prestazioni. Per altre informazioni, vedere [LINQ to Objects (C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md), [LINQ to Objects (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md), [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), [Introduzione alle query LINQ (C#)](../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) e [Operazioni di Query di base (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
- **La possibilità di copiare il contenuto della raccolta in una matrice**  
  
     Tutti le raccolte possono essere copiate in una matrice usando il metodo **CopyTo**. Tuttavia, l'ordine degli elementi nella nuova matrice si basa sulla sequenza in cui vengono restituiti dall'enumeratore. La matrice risultante è sempre unidimensionale con limite inferiore pari a zero.  
  
 Inoltre, molte classi di raccolte contengono le seguenti funzionalità:  
  
- **Proprietà capacità e conteggio**  
  
     La capacità di una raccolta è il numero di elementi che può contenere. Il conteggio di una raccolta è il numero di elementi che contiene effettivamente. Alcune raccolte nascondono la capacità o il conteggio oppure entrambi.  
  
     La capacità della maggior parte delle raccolte si espande automaticamente quando viene raggiunta la capacità corrente. La memoria viene riallocata e gli elementi vengono copiati dalla raccolta precedente a quella nuova. Ciò riduce la quantità di codice necessario per usare la raccolta. Tuttavia, le prestazioni della raccolta possono essere influenzate negativamente. Ad esempio, per <xref:System.Collections.Generic.List%601>, se <xref:System.Collections.Generic.List%601.Count%2A> è minore di <xref:System.Collections.Generic.List%601.Capacity%2A>, l'aggiunta di un elemento è un'operazione O(1). Se la capacità deve essere incrementata per far posto al nuovo elemento, l'aggiunta di un elemento diventa un'operazione O(n), dove n è <xref:System.Collections.Generic.List%601.Count%2A>. Il modo migliore per evitare una riduzione delle prestazioni causata da più riallocazioni consiste nell'impostare la capacità iniziale sulla dimensione prevista della raccolta.  
  
     Un <xref:System.Collections.BitArray> è un caso speciale: la sua capacità corrisponde alla sua lunghezza, che corrisponde al relativo conteggio.  
  
- **Un limite inferiore coerente**  
  
     Il limite inferiore di una raccolta è l'indice del primo elemento. Tutte le raccolte indicizzate negli spazi dei nomi <xref:System.Collections> hanno un limite inferiore pari a zero, ossia possono essere indicizzate da 0. <xref:System.Array> ha un limite inferiore pari a zero per impostazione predefinita, ma è possibile definire un limite inferiore differente durante la creazione di un'istanza della classe **Array** con <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType>.  
  
- **Sincronizzazione per l'accesso da più thread** (solo classi <xref:System.Collections>).  
  
     I tipi di raccolta non generica nello spazio dei nomi <xref:System.Collections> forniscono una determinata thread safety con la sincronizzazione, in genere esposte attraverso i membri <xref:System.Collections.ICollection.SyncRoot%2A> e <xref:System.Collections.ICollection.IsSynchronized%2A>. Queste raccolte non sono thread-safe per impostazione predefinita. Se si richiede un accesso multithreading scalabile ed efficiente a una raccolta, usare una delle classi nello spazio dei nomi <xref:System.Collections.Concurrent> o considerare l'uso di una raccolta non modificabile. Per altre informazioni, vedere [Raccolte thread-safe](../../../docs/standard/collections/thread-safe/index.md).  
  
<a name="BKMK_Choosingacollection"></a>
## <a name="choosing-a-collection"></a>Scelta di una raccolta  
 In generale, è necessario usare raccolte generiche. Nella tabella seguente vengono descritti alcuni scenari comuni di raccolta e le classi di raccolta che è possibile usare per gli scenari. Se si ha già familiarità con le raccolte generiche, questa tabella consente di scegliere la raccolta generica più adatta alla propria attività.  

|Si desidera...|Opzioni di raccolta generica|Opzioni di raccolta non generica|Opzioni di raccolta thread-safe o non modificabile|  
|-|-|-|-|  
|Archiviare gli elementi come coppie chiave/valore per la ricerca rapida dalla chiave|<xref:System.Collections.Generic.Dictionary%602>|<xref:System.Collections.Hashtable><br /><br /> (Una raccolta di coppie chiave/valore che sono organizzate in base al codice hash della chiave).|<xref:System.Collections.Concurrent.ConcurrentDictionary%602><br /><br /> <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602><br /><br /> <xref:System.Collections.Immutable.ImmutableDictionary%602>|  
|Accedere agli elementi in base all'indice|<xref:System.Collections.Generic.List%601>|<xref:System.Array><br /><br /> <xref:System.Collections.ArrayList>|<xref:System.Collections.Immutable.ImmutableList%601><br /><br /> <xref:System.Collections.Immutable.ImmutableArray>|  
|Usare gli elementi first-in-first-out (FIFO)|<xref:System.Collections.Generic.Queue%601>|<xref:System.Collections.Queue>|<xref:System.Collections.Concurrent.ConcurrentQueue%601><br /><br /> <xref:System.Collections.Immutable.ImmutableQueue%601>|  
|Usare i dati Last-In-First-Out (LIFO)|<xref:System.Collections.Generic.Stack%601>|<xref:System.Collections.Stack>|<xref:System.Collections.Concurrent.ConcurrentStack%601><br /><br /> <xref:System.Collections.Immutable.ImmutableStack%601>|  
|Accedere agli elementi in sequenza|<xref:System.Collections.Generic.LinkedList%601>|Nessuna raccomandazione|Nessuna raccomandazione|  
|Ricevere notifiche quando gli elementi vengono rimossi o aggiunti alla raccolta. (implementa <xref:System.ComponentModel.INotifyPropertyChanged> e <xref:System.Collections.Specialized.INotifyCollectionChanged>)|<xref:System.Collections.ObjectModel.ObservableCollection%601>|Nessuna raccomandazione|Nessuna raccomandazione|  
|Una raccolta ordinata|<xref:System.Collections.Generic.SortedList%602>|<xref:System.Collections.SortedList>|<xref:System.Collections.Immutable.ImmutableSortedDictionary%602><br /><br /> <xref:System.Collections.Immutable.ImmutableSortedSet%601>|  
|Un set di funzioni matematiche|<xref:System.Collections.Generic.HashSet%601><br /><br /> <xref:System.Collections.Generic.SortedSet%601>|Nessuna raccomandazione|<xref:System.Collections.Immutable.ImmutableHashSet%601><br /><br /> <xref:System.Collections.Immutable.ImmutableSortedSet%601>|  
  
<a name="BKMK_RelatedTopics"></a>
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Selezione di una classe Collection](../../../docs/standard/collections/selecting-a-collection-class.md)|Vengono descritte le diverse raccolte e come selezionarne una per lo scenario.|  
|[Tipi di raccolte comunemente utilizzate](../../../docs/standard/collections/commonly-used-collection-types.md)|Vengono descritti i tipi di raccolta generici e non generici comunemente usati, quali <xref:System.Array?displayProperty=nameWithType>, <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> e <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.|  
|[Quando utilizzare raccolte generiche](../../../docs/standard/collections/when-to-use-generic-collections.md)|Viene illustrato l'utilizzo di tipi di raccolta generici.|  
|[Confronti e ordinamenti all'interno delle raccolte](../../../docs/standard/collections/comparisons-and-sorts-within-collections.md)|Viene illustrato l'utilizzo di confronti di uguaglianza e ordinamento nelle raccolte.|  
|[Tipi di raccolta ordinati](../../../docs/standard/collections/sorted-collection-types.md)|Vengono descritte le caratteristiche e le prestazioni di raccolte ordinate|  
|[Tipi di Collection Hashtable e Dictionary](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|Vengono descritte le funzionalità dei tipi di dizionario basati su hash generici e non generici.|  
|[Raccolte thread-safe](../../../docs/standard/collections/thread-safe/index.md)|Vengono descritti i tipi di raccolta quali <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> e <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType> che supportano l'accesso simultaneo sicuro ed efficiente da più thread.|  
|System.Collections.Immutable|Introduce le raccolte non modificabili e fornisce collegamenti ai tipi di raccolta.|  
  
<a name="BKMK_Reference"></a>
## <a name="reference"></a>Riferimento  
 <xref:System.Array?displayProperty=nameWithType>  
 <xref:System.Collections?displayProperty=nameWithType>  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 <xref:System.Collections.Generic?displayProperty=nameWithType>  
 <xref:System.Collections.Specialized?displayProperty=nameWithType>  
 <xref:System.Linq?displayProperty=nameWithType>  
 <xref:System.Collections.Immutable>
