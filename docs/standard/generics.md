---
title: Panoramica dei tipi generici (generics)
description: Informazioni sul modo in cui i tipi generici (generics) vengono usati come modelli di codice che consentono di definire strutture di dati indipendenti dai tipi senza il commit di un tipo di dati effettivo.
author: kuhlenh
ms.author: wiwagn
ms.date: 10/09/2018
ms.openlocfilehash: 0188e620a45462e7cc31391406ade9d57b1b0220
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588473"
---
# <a name="generic-types-overview"></a>Panoramica dei tipi generici

Gli sviluppatori usano sempre generics in .NET, in modo implicito o esplicito. Quando si usa LINQ in .NET, forse non si è mai notato l'uso di <xref:System.Collections.Generic.IEnumerable%601>. O se avete mai visto un esempio online di un "repository generico" per `IQueryable<T>`parlare con i database utilizzando Entity Framework, avete visto che la maggior parte dei metodi restituiscono ? Probabilmente ci si sarà chiesti che cos'è la **T** in questi esempi e perché è presente.

Introdotti per la prima volta in .NET Framework 2.0, i generics sono essenzialmente un "modello di codice" che permette agli sviluppatori di definire strutture dei dati [indipendenti dai tipi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) senza il commit in un tipo di dati effettivo. Ad <xref:System.Collections.Generic.List%601> esempio, è un [insieme generico](xref:System.Collections.Generic) che può essere `List<int>` `List<string>`dichiarato `List<Person>`e utilizzato con qualsiasi tipo, ad esempio , , o .

Per dimostrare l'utilità dei generics, verrà esaminata una classe specifica prima e dopo l'aggiunta di generics: <xref:System.Collections.ArrayList>. In .NET Framework 1.0 gli elementi `ArrayList` sono di tipo <xref:System.Object>. Questo significa che qualsiasi elemento aggiunto viene convertito automaticamente in `Object`. Lo stesso avviene quando gli elementi vengono letti dall'elenco. Questo processo è noto come [conversioni boxing e unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md) e influisce sulle prestazioni. Soprattutto, tuttavia, non è possibile determinare in alcun modo il tipo di dati nell'elenco in fase di compilazione. E ciò crea un codice fragile. I generics risolvono il problema definendo il tipo di dati contenuto da ogni istanza dell'elenco. Ad esempio, è possibile aggiungere numeri interi solo a `List<int>` e persone solo a `List<Person>`.

I generics sono disponibili anche in fase di esecuzione. Questo significa che il runtime riconosce il tipo di struttura dei dati usato e può archiviarlo in memoria in modo più efficiente.

L'esempio seguente è un piccolo programma che illustra l'efficienza di conoscere il tipo di struttura di dati in fase di esecuzione:The following example is a small program that illustrates the efficiency of knowing the data structure type at run time:

```csharp
  using System;
  using System.Collections;
  using System.Collections.Generic;
  using System.Diagnostics;

  namespace GenericsExample {
    class Program {
      static void Main(string[] args) {
        //generic list
        List<int> ListGeneric = new List<int> { 5, 9, 1, 4 };
        //non-generic list
        ArrayList ListNonGeneric = new ArrayList { 5, 9, 1, 4 };
        // timer for generic list sort
        Stopwatch s = Stopwatch.StartNew();
        ListGeneric.Sort();
        s.Stop();
        Console.WriteLine($"Generic Sort: {ListGeneric}  \n Time taken: {s.Elapsed.TotalMilliseconds}ms");

        //timer for non-generic list sort
        Stopwatch s2 = Stopwatch.StartNew();
        ListNonGeneric.Sort();
        s2.Stop();
        Console.WriteLine($"Non-Generic Sort: {ListNonGeneric}  \n Time taken: {s2.Elapsed.TotalMilliseconds}ms");
        Console.ReadLine();
      }
    }
  }
```

Questo programma produce un output simile al seguente:

```console
Generic Sort: System.Collections.Generic.List`1[System.Int32]
 Time taken: 0.0034ms
Non-Generic Sort: System.Collections.ArrayList
 Time taken: 0.2592ms
```

La prima cosa che si può notare è che l'ordinamento dell'elenco generico è notevolmente più veloce rispetto a quello dell'elenco non generico. È anche possibile notare che il tipo per un elenco generico è specifico ([System. Int32]), mentre il tipo per un elenco non generico è generalizzato. Poiché il runtime `List<int>` sa <xref:System.Int32>che il generico è di tipo , può archiviare `ArrayList` gli elementi dell'elenco in una matrice di interi sottostante in memoria, mentre il non generico deve eseguire il cast di ogni elemento dell'elenco a un oggetto . Come mostra l'esempio, i cast aggiuntivi richiedono tempo e rallentano l'ordinamento dell'elenco.

Un altro vantaggio della capacità del runtime di riconoscere il tipo dell'oggetto generico è una migliore esperienza di debug. Quando si esegue il debug di un tipo generico in C#, è possibile identificare il tipo di ogni elemento nella struttura dei dati. Senza i generics, questo non sarebbe possibile.

## <a name="see-also"></a>Vedere anche

- [Generics (Guida per programmatori C#)](../../docs/csharp/programming-guide/generics/index.md)
