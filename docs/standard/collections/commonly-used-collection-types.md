---
title: Tipi di raccolte comunemente usate
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- collections [.NET Framework], generic
- objects [.NET Framework], grouping in collections
- generics [.NET Framework], collections
- IList interface, grouping data in collections
- IDictionary interface, grouping data in collections
- grouping data in collections, generic collection types
- Collections classes
- generic collections
ms.assetid: f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55
ms.openlocfilehash: 1004a2f9a0594d9150d147dec1e16b56205e0d13
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711402"
---
# <a name="commonly-used-collection-types"></a>Tipi di raccolte comunemente usate
I tipi di raccolta sono le varianti comuni delle raccolte di dati, ad esempio tabelle hash, code, stack, contenitori, dizionari ed elenchi.  
  
 Le raccolte si basano sull'interfaccia <xref:System.Collections.ICollection>, l'interfaccia <xref:System.Collections.IList>, l'interfaccia <xref:System.Collections.IDictionary> oppure sulle relative controparti generiche. L'interfaccia <xref:System.Collections.IList> e l'interfaccia <xref:System.Collections.IDictionary> derivano entrambe dall'interfaccia <xref:System.Collections.ICollection>. Di conseguenza, tutte le raccolte sono basate direttamente o indirettamente sull'interfaccia <xref:System.Collections.ICollection>. Nelle raccolte basate sull'interfaccia <xref:System.Collections.IList> (come ad esempio <xref:System.Array>, <xref:System.Collections.ArrayList> o <xref:System.Collections.Generic.List%601>) oppure direttamente sull'interfaccia <xref:System.Collections.ICollection> (come ad esempio <xref:System.Collections.Queue>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Stack>, <xref:System.Collections.Concurrent.ConcurrentStack%601> o <xref:System.Collections.Generic.LinkedList%601>), ogni elemento contiene un valore. Nelle raccolte basate sull'interfaccia <xref:System.Collections.IDictionary> (come ad esempio le classi <xref:System.Collections.Hashtable> e <xref:System.Collections.SortedList>, le classi generiche <xref:System.Collections.Generic.Dictionary%602> e <xref:System.Collections.Generic.SortedList%602>), oppure sulle classi <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, ogni elemento contiene sia una chiave sia un valore.  La classe <xref:System.Collections.ObjectModel.KeyedCollection%602> è univoca perché è un elenco di valori con le chiavi incorporate nei valori e quindi funge da elenco e da dizionario.  
  
 Le raccolte generiche rappresentano la migliore soluzione per la tipizzazione forte. Tuttavia, se il linguaggio usato non supporta i generics, lo spazio dei nomi <xref:System.Collections> include le raccolte di base, come <xref:System.Collections.CollectionBase>, <xref:System.Collections.ReadOnlyCollectionBase> e <xref:System.Collections.DictionaryBase>, che sono classi di base astratte che possono essere estese in modo da creare classi di raccolta con tipizzazione forte. Quando è necessario accedere a raccolte con multithreading efficiente, usare le raccolte generiche nello spazio dei nomi <xref:System.Collections.Concurrent>.  
  
 Le raccolte possono variare a seconda di come vengono archiviati gli elementi, la modalità di ordinamento, la modalità di ricerca e confronto. La classe <xref:System.Collections.Queue> e la classe generica <xref:System.Collections.Generic.Queue%601> forniscono elenchi first-in-first-out, mentre la classe <xref:System.Collections.Stack> e la classe generica <xref:System.Collections.Generic.Stack%601> forniscono elenchi last-in-first-out. La classe <xref:System.Collections.SortedList> e la classe generica <xref:System.Collections.Generic.SortedList%602> rappresentano versioni ordinate della classe <xref:System.Collections.Hashtable> e della classe generica <xref:System.Collections.Generic.Dictionary%602>. Gli elementi di una <xref:System.Collections.Hashtable> o <xref:System.Collections.Generic.Dictionary%602> sono accessibili solo con la chiave dell'elemento, ma gli elementi di una <xref:System.Collections.SortedList> o <xref:System.Collections.ObjectModel.KeyedCollection%602> sono accessibili con la chiave oppure con l'indice dell'elemento. Gli indici di tutte le raccolte sono a base zero, ad eccezione di <xref:System.Array>, che consente matrici non a base zero.  
  
 La funzionalità LINQ to Objects consente di usare le query LINQ per accedere agli oggetti in memoria purché il tipo dell'oggetto implementi <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>. Le query LINQ forniscono un modello comune per l'accesso ai dati, sono in genere più concise e leggibili dei cicli standard `foreach` e forniscono funzioni di filtro, ordinamento e raggruppamento. Le query LINQ possono inoltre migliorare le prestazioni. Per altre informazioni, vedere [LINQ to Objects (C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md), [LINQ to Objects (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) e [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Raccolte e strutture di dati](../../../docs/standard/collections/index.md)|Vengono descritti i diversi tipi di raccolta disponibili in .NET Framework, compresi stack, code, elenchi, matrici e dizionari.|  
|[Tipi di Collection Hashtable e Dictionary](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|Vengono descritte le funzionalità dei tipi di dizionario basati su hash generici e non generici.|  
|[Tipi di raccolta ordinati](../../../docs/standard/collections/sorted-collection-types.md)|Vengono descritte le classi che forniscono funzionalità di ordinamento per elenchi e set.|  
|[Generics](../../../docs/standard/generics/index.md)|Viene descritta la funzionalità Generics, compresi delegati, interfacce e Collection generiche fornite da .NET Framework. Vengono forniti collegamenti alla documentazione sulle funzionalità per i linguaggi C#, Visual Basic e Visual C++ e a tecnologie di supporto come reflection.|  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Collections?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic?displayProperty=nameWithType>  
  
 <xref:System.Collections.ICollection?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic.ICollection%601?displayProperty=nameWithType>  
  
 <xref:System.Collections.IList?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic.IList%601?displayProperty=nameWithType>  
  
 <xref:System.Collections.IDictionary?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>
