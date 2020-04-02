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
# <a name="generic-types-overview"></a><span data-ttu-id="215cf-103">Panoramica dei tipi generici</span><span class="sxs-lookup"><span data-stu-id="215cf-103">Generic types overview</span></span>

<span data-ttu-id="215cf-104">Gli sviluppatori usano sempre generics in .NET, in modo implicito o esplicito.</span><span class="sxs-lookup"><span data-stu-id="215cf-104">Developers use generics all the time in .NET, whether implicitly or explicitly.</span></span> <span data-ttu-id="215cf-105">Quando si usa LINQ in .NET, forse non si è mai notato l'uso di <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="215cf-105">When you use LINQ in .NET, did you ever notice that you're working with <xref:System.Collections.Generic.IEnumerable%601>?</span></span> <span data-ttu-id="215cf-106">O se avete mai visto un esempio online di un "repository generico" per `IQueryable<T>`parlare con i database utilizzando Entity Framework, avete visto che la maggior parte dei metodi restituiscono ?</span><span class="sxs-lookup"><span data-stu-id="215cf-106">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return `IQueryable<T>`?</span></span> <span data-ttu-id="215cf-107">Probabilmente ci si sarà chiesti che cos'è la **T** in questi esempi e perché è presente.</span><span class="sxs-lookup"><span data-stu-id="215cf-107">You may have wondered what the **T** is in these examples and why it's in there.</span></span>

<span data-ttu-id="215cf-108">Introdotti per la prima volta in .NET Framework 2.0, i generics sono essenzialmente un "modello di codice" che permette agli sviluppatori di definire strutture dei dati [indipendenti dai tipi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) senza il commit in un tipo di dati effettivo.</span><span class="sxs-lookup"><span data-stu-id="215cf-108">First introduced in the .NET Framework 2.0, generics are essentially a "code template" that allows developers to define [type-safe](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hbzz1a9a(v=vs.100)) data structures without committing to an actual data type.</span></span> <span data-ttu-id="215cf-109">Ad <xref:System.Collections.Generic.List%601> esempio, è un [insieme generico](xref:System.Collections.Generic) che può essere `List<int>` `List<string>`dichiarato `List<Person>`e utilizzato con qualsiasi tipo, ad esempio , , o .</span><span class="sxs-lookup"><span data-stu-id="215cf-109">For example, <xref:System.Collections.Generic.List%601> is a [generic collection](xref:System.Collections.Generic) that can be declared and used with any type, such as `List<int>`, `List<string>`, or `List<Person>`.</span></span>

<span data-ttu-id="215cf-110">Per dimostrare l'utilità dei generics, verrà esaminata una classe specifica prima e dopo l'aggiunta di generics: <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="215cf-110">To understand why generics are useful, let's take a look at a specific class before and after adding generics: <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="215cf-111">In .NET Framework 1.0 gli elementi `ArrayList` sono di tipo <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="215cf-111">In .NET Framework 1.0, the `ArrayList` elements were of type <xref:System.Object>.</span></span> <span data-ttu-id="215cf-112">Questo significa che qualsiasi elemento aggiunto viene convertito automaticamente in `Object`.</span><span class="sxs-lookup"><span data-stu-id="215cf-112">This meant that any element added was silently converted into an `Object`.</span></span> <span data-ttu-id="215cf-113">Lo stesso avviene quando gli elementi vengono letti dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="215cf-113">The same would happen when reading the elements from the list.</span></span> <span data-ttu-id="215cf-114">Questo processo è noto come [conversioni boxing e unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md) e influisce sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="215cf-114">This process is known as [boxing and unboxing](../csharp/programming-guide/types/boxing-and-unboxing.md), and it impacts performance.</span></span> <span data-ttu-id="215cf-115">Soprattutto, tuttavia, non è possibile determinare in alcun modo il tipo di dati nell'elenco in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="215cf-115">More than that, however, there's no way to determine the type of data in the list at compile time.</span></span> <span data-ttu-id="215cf-116">E ciò crea un codice fragile.</span><span class="sxs-lookup"><span data-stu-id="215cf-116">This makes for some fragile code.</span></span> <span data-ttu-id="215cf-117">I generics risolvono il problema definendo il tipo di dati contenuto da ogni istanza dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="215cf-117">Generics solve this problem by defining the type of data each instance of list will contain.</span></span> <span data-ttu-id="215cf-118">Ad esempio, è possibile aggiungere numeri interi solo a `List<int>` e persone solo a `List<Person>`.</span><span class="sxs-lookup"><span data-stu-id="215cf-118">For example, you can only add integers to `List<int>` and only add Persons to `List<Person>`.</span></span>

<span data-ttu-id="215cf-119">I generics sono disponibili anche in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="215cf-119">Generics are also available at run time.</span></span> <span data-ttu-id="215cf-120">Questo significa che il runtime riconosce il tipo di struttura dei dati usato e può archiviarlo in memoria in modo più efficiente.</span><span class="sxs-lookup"><span data-stu-id="215cf-120">This means the runtime knows what type of data structure you're using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="215cf-121">L'esempio seguente è un piccolo programma che illustra l'efficienza di conoscere il tipo di struttura di dati in fase di esecuzione:The following example is a small program that illustrates the efficiency of knowing the data structure type at run time:</span><span class="sxs-lookup"><span data-stu-id="215cf-121">The following example is a small program that illustrates the efficiency of knowing the data structure type at run time:</span></span>

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

<span data-ttu-id="215cf-122">Questo programma produce un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="215cf-122">This program produces output similar to the following:</span></span>

```console
Generic Sort: System.Collections.Generic.List`1[System.Int32]
 Time taken: 0.0034ms
Non-Generic Sort: System.Collections.ArrayList
 Time taken: 0.2592ms
```

<span data-ttu-id="215cf-123">La prima cosa che si può notare è che l'ordinamento dell'elenco generico è notevolmente più veloce rispetto a quello dell'elenco non generico.</span><span class="sxs-lookup"><span data-stu-id="215cf-123">The first thing you can notice here is that sorting the generic list is significantly faster than sorting the non-generic list.</span></span> <span data-ttu-id="215cf-124">È anche possibile notare che il tipo per un elenco generico è specifico ([System. Int32]), mentre il tipo per un elenco non generico è generalizzato.</span><span class="sxs-lookup"><span data-stu-id="215cf-124">You might also notice that the type for the generic list is distinct ([System.Int32]), whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="215cf-125">Poiché il runtime `List<int>` sa <xref:System.Int32>che il generico è di tipo , può archiviare `ArrayList` gli elementi dell'elenco in una matrice di interi sottostante in memoria, mentre il non generico deve eseguire il cast di ogni elemento dell'elenco a un oggetto .</span><span class="sxs-lookup"><span data-stu-id="215cf-125">Because the runtime knows the generic `List<int>` is of type <xref:System.Int32>, it can store the list elements in an underlying integer array in memory, while the non-generic `ArrayList` has to cast each list element to an object.</span></span> <span data-ttu-id="215cf-126">Come mostra l'esempio, i cast aggiuntivi richiedono tempo e rallentano l'ordinamento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="215cf-126">As this example shows, the extra casts take up time and slow down the list sort.</span></span>

<span data-ttu-id="215cf-127">Un altro vantaggio della capacità del runtime di riconoscere il tipo dell'oggetto generico è una migliore esperienza di debug.</span><span class="sxs-lookup"><span data-stu-id="215cf-127">An additional advantage of the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="215cf-128">Quando si esegue il debug di un tipo generico in C#, è possibile identificare il tipo di ogni elemento nella struttura dei dati.</span><span class="sxs-lookup"><span data-stu-id="215cf-128">When you're debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="215cf-129">Senza i generics, questo non sarebbe possibile.</span><span class="sxs-lookup"><span data-stu-id="215cf-129">Without generics, you would have no idea what type each element was.</span></span>

## <a name="see-also"></a><span data-ttu-id="215cf-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="215cf-130">See also</span></span>

- [<span data-ttu-id="215cf-131">Generics (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="215cf-131">C# Programming Guide - Generics</span></span>](../../docs/csharp/programming-guide/generics/index.md)
