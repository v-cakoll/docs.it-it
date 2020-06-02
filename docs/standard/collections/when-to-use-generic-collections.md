---
title: Quando utilizzare raccolte generiche
ms.date: 04/30/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- collections [.NET Framework], generic
- generic collections [.NET Framework]
ms.assetid: e7b868b1-11fe-4ac5-bed3-de68aca47739
ms.openlocfilehash: c59a125a8df95e3c4fe6e1839956d800bd6ee910
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290383"
---
# <a name="when-to-use-generic-collections"></a>Quando usare raccolte generiche

L'uso di raccolte generiche offre il vantaggio automatico di indipendenza dai tipi senza la necessità di derivare da un tipo di raccolta di base e implementare membri specifici del tipo. I tipi di raccolte generiche offrono anche prestazioni migliori rispetto ai tipi di raccolte non generiche corrispondenti (e migliori dei tipi derivati dai tipi di raccolte base non generiche) quando gli elementi della raccolta sono tipi di valore, perché con i generics non è necessario eseguire il box degli elementi.

Per i programmi destinati .NET Standard 1,0 o versioni successive, usare le classi di raccolte generiche nello <xref:System.Collections.Concurrent> spazio dei nomi quando più thread potrebbero aggiungere o rimuovere elementi dalla raccolta contemporaneamente. Inoltre, quando si desidera l'immutabilità, prendere in considerazione le classi di raccolte generiche nello <xref:System.Collections.Immutable> spazio dei nomi.

I seguenti tipi generici corrispondono ai tipi di raccolte esistenti:

- <xref:System.Collections.Generic.List%601> è la classe generica che corrisponde a <xref:System.Collections.ArrayList>.

- <xref:System.Collections.Generic.Dictionary%602> e <xref:System.Collections.Concurrent.ConcurrentDictionary%602> sono le classi generiche che corrispondono a <xref:System.Collections.Hashtable>.

- <xref:System.Collections.ObjectModel.Collection%601> è la classe generica che corrisponde a <xref:System.Collections.CollectionBase>. <xref:System.Collections.ObjectModel.Collection%601>può essere usato come classe di base, ma a differenza <xref:System.Collections.CollectionBase> di, non è astratto, che lo rende molto più semplice da usare.

- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> è la classe generica che corrisponde a <xref:System.Collections.ReadOnlyCollectionBase>. <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>non è astratto e dispone di un costruttore che semplifica l'esposizione di un oggetto esistente <xref:System.Collections.Generic.List%601> come raccolta di sola lettura.

- Le <xref:System.Collections.Generic.Queue%601> <xref:System.Collections.Concurrent.ConcurrentQueue%601> <xref:System.Collections.Immutable.ImmutableQueue%601> classi generiche,,,, <xref:System.Collections.Immutable.ImmutableArray%601> <xref:System.Collections.Generic.SortedList%602> e <xref:System.Collections.Immutable.ImmutableSortedSet%601> corrispondono alle rispettive classi non generiche con gli stessi nomi.

## <a name="additional-types"></a>Tipi aggiuntivi

Diversi tipi di raccolte generiche non hanno controparti non generiche. Essi includono quanto segue:

- <xref:System.Collections.Generic.LinkedList%601> è un elenco collegato di uso generale che fornisce le operazioni di inserimento e rimozione O(1).

- <xref:System.Collections.Generic.SortedDictionary%602> è un dizionario ordinato con operazioni di inserimento e recupero O(log `n`), che lo rende un'utile alternativa a <xref:System.Collections.Generic.SortedList%602>.

- <xref:System.Collections.ObjectModel.KeyedCollection%602> è un ibrido tra un elenco e un dizionario, che fornisce un metodo per memorizzare oggetti contenenti le loro stesse chiavi.

- <xref:System.Collections.Concurrent.BlockingCollection%601> implementa una classe di raccolta con funzionalità di delimitazione e blocco.

- <xref:System.Collections.Concurrent.ConcurrentBag%601> permette di eseguire rapidamente le operazioni di inserimento e rimozione di elementi non ordinati.

### <a name="immutable-builders"></a>Generatori non modificabili

Quando si desidera la funzionalità di immutabilità nell'app, lo <xref:System.Collections.Immutable> spazio dei nomi offre tipi di raccolta generici che è possibile usare. Tutti i tipi di raccolta non modificabili offrono `Builder` classi che consentono di ottimizzare le prestazioni quando si eseguono più mutazioni. La `Builder` classe raggruppa le operazioni in uno stato modificabile. Quando tutte le mutazioni sono state completate, chiamare il `ToImmutable` metodo per "bloccare" tutti i nodi e creare una raccolta generica non modificabile, ad esempio, <xref:System.Collections.Immutable.ImmutableList%601> .

L' `Builder` oggetto può essere creato chiamando il metodo non generico `CreateBuilder()` . Da un' `Builder` istanza di è possibile chiamare `ToImmutable()` . Analogamente, dalla `Immutable*` raccolta, è possibile chiamare `ToBuilder()` per creare un'istanza del generatore dalla raccolta generica non modificabile. Di seguito sono riportati i diversi `Builder` tipi.

- <xref:System.Collections.Immutable.ImmutableArray%601.Builder>
- <xref:System.Collections.Immutable.ImmutableDictionary%602.Builder>
- <xref:System.Collections.Immutable.ImmutableHashSet%601.Builder>
- <xref:System.Collections.Immutable.ImmutableList%601.Builder>
- <xref:System.Collections.Immutable.ImmutableSortedDictionary%602.Builder>
- <xref:System.Collections.Immutable.ImmutableSortedSet%601.Builder>

## <a name="linq-to-objects"></a>LINQ to Objects

La funzionalità LINQ to Objects consente di usare le query LINQ per accedere agli oggetti in memoria purché il tipo dell'oggetto implementi l'interfaccia <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> . Le query LINQ forniscono un modello comune per l'accesso ai dati. sono in genere più concise e leggibili dei `foreach` cicli standard e forniscono funzionalità di filtro, ordinamento e raggruppamento. Le query LINQ possono inoltre migliorare le prestazioni. Per altre informazioni, vedere [LINQ to Objects (C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md), [LINQ to Objects (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) e [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md).

## <a name="additional-functionality"></a>Funzionalità aggiuntive
Alcuni tipi generici hanno funzionalità che non si trovano nei tipi di raccolte non generiche. Ad esempio, la classe <xref:System.Collections.Generic.List%601> , che corrisponde alla classe <xref:System.Collections.ArrayList> non generica, ha una serie di metodi che accettano i delegati generici, come ad esempio il delegato <xref:System.Predicate%601> che consente di specificare metodi per la ricerca nell'elenco, il delegato <xref:System.Action%601> che rappresenta metodi che agiscono su ciascun elemento dell'elenco e il delegato <xref:System.Converter%602> che consente di definire le conversioni tra tipi.

La classe <xref:System.Collections.Generic.List%601> consente di specificare le proprie implementazioni di interfaccia <xref:System.Collections.Generic.IComparer%601> generica per l'ordinamento e la ricerca nell'elenco. Anche le classi <xref:System.Collections.Generic.SortedDictionary%602> e <xref:System.Collections.Generic.SortedList%602> hanno la stessa capacità. Inoltre, queste classi consentono di specificare gli operatori di confronto quando viene creata la raccolta. In modo analogo, le classi <xref:System.Collections.Generic.Dictionary%602> e <xref:System.Collections.ObjectModel.KeyedCollection%602> consentono di specificare operatori di confronto di uguaglianza personalizzati.

## <a name="see-also"></a>Vedere anche

- [Raccolte e strutture di dati](index.md)
- [Tipi di raccolte comunemente usate](commonly-used-collection-types.md)
- [Generics](../generics/index.md)
