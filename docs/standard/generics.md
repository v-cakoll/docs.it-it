---
title: Panoramica di tipi generici (generics)
description: Informazioni sul modo in cui i tipi generici (generics) vengono usati come modelli di codice che consentono di definire strutture di dati indipendenti dai tipi senza il commit di un tipo di dati effettivo.
keywords: .NET, .NET Core
author: kuhlenh
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: a315b111-8e48-446c-ab19-acb6405894a7
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f36bae495631db68afb1404398cbf43e890d4f33
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="generic-types-generics-overview"></a><span data-ttu-id="3a4a8-104">Panoramica di tipi generici (generics)</span><span class="sxs-lookup"><span data-stu-id="3a4a8-104">Generic Types (Generics) Overview</span></span>

<span data-ttu-id="3a4a8-105">I generics vengono usati sempre in C#, implicitamente o esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-105">We use generics all the time in C#, whether implicitly or explicitly.</span></span> <span data-ttu-id="3a4a8-106">Durante l'uso di LINQ in C#, si è mai notato che si stava usando IEnumerable<T>?</span><span class="sxs-lookup"><span data-stu-id="3a4a8-106">When you use LINQ in C#, did you ever notice that you are working with IEnumerable<T>?</span></span> <span data-ttu-id="3a4a8-107">Oppure, visualizzando un esempio online di un "repository generico" che comunica con database tramite Entity Framework, si è notato che la maggior parte dei metodi restituisce IQueryable<T>?</span><span class="sxs-lookup"><span data-stu-id="3a4a8-107">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return IQueryable<T>?</span></span> <span data-ttu-id="3a4a8-108">Molti utenti e sviluppatori si chiedono che cosa rappresenta la **T** in questi esempi e perché è presente?</span><span class="sxs-lookup"><span data-stu-id="3a4a8-108">You may have wondered what the **T** is in these examples and why is it in there?</span></span>

<span data-ttu-id="3a4a8-109">Introdotto per la prima volta in .NET Framework 2.0, i generics comportavano modifiche al linguaggio C# e a Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3a4a8-109">First introduced to the .NET Framework 2.0, generics involved changes to both the C# language and the Common Language Runtime (CLR).</span></span> <span data-ttu-id="3a4a8-110">I **generics** sono essenzialmente un "modello di codice" che consente agli sviluppatori di definire strutture di dati [indipendenti dai tipi](https://msdn.microsoft.com/library/hbzz1a9a.aspx) senza il commit di un tipo di dati effettivo.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-110">**Generics** are essentially a "code template" that allows developers to define [type-safe](https://msdn.microsoft.com/library/hbzz1a9a.aspx) data structures without committing to an actual data type.</span></span> <span data-ttu-id="3a4a8-111">Ad esempio, `List<T>` è una [raccolta generica](xref:System.Collections.Generic) che può essere dichiarata e usata con qualsiasi tipo: `List<int>`, `List<string>`, `List<Person>`, e così via.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-111">For example, `List<T>` is a [Generic Collection](xref:System.Collections.Generic) that can be declared and used with any type: `List<int>`, `List<string>`, `List<Person>`, etc.</span></span>

<span data-ttu-id="3a4a8-112">Quindi?</span><span class="sxs-lookup"><span data-stu-id="3a4a8-112">So, what’s the point?</span></span> <span data-ttu-id="3a4a8-113">Perché i generics sono utili?</span><span class="sxs-lookup"><span data-stu-id="3a4a8-113">Why are generics useful?</span></span> <span data-ttu-id="3a4a8-114">Per capire meglio questo meccanismo, è necessario esaminare una classe specifica prima e dopo l'aggiunta dei generics.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-114">In order to understand this, we need to take a look at a specific class before and after adding generics.</span></span> <span data-ttu-id="3a4a8-115">Viene esaminata la classe `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-115">Let’s look at the `ArrayList`.</span></span> <span data-ttu-id="3a4a8-116">In C# 1.0, gli elementi `ArrayList` erano di tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-116">In C# 1.0, the `ArrayList` elements were of type `object`.</span></span> <span data-ttu-id="3a4a8-117">Ciò vuol dire che qualsiasi elemento aggiunto veniva convertito automaticamente nel tipo `object`; la stessa cosa accade durante la lettura degli elementi dall'elenco (questo processo è noto come [conversione boxing](../../docs/csharp/programming-guide/types/boxing-and-unboxing.md) e unboxing rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="3a4a8-117">This meant that any element that was added was silently converted into an `object`; same thing happens on reading the elements from the list (this process is known as [boxing](../../docs/csharp/programming-guide/types/boxing-and-unboxing.md) and unboxing respectively).</span></span> <span data-ttu-id="3a4a8-118">Le conversioni boxing e unboxing influiscono sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-118">Boxing and unboxing have an impact of performance.</span></span> <span data-ttu-id="3a4a8-119">Non è possibile tuttavia individuare in fase di compilazione il tipo effettivo dei dati nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-119">More than that, however, there is no way to tell at compile time what is the actual type of the data in the list.</span></span> <span data-ttu-id="3a4a8-120">E ciò crea un codice fragile.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-120">This makes for some fragile code.</span></span> <span data-ttu-id="3a4a8-121">I generics risolvono il problema, offrendo informazioni aggiuntive sul tipo di dati contenuti in ogni istanza dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-121">Generics solve this problem by providing additional information the type of data each instance of list will contain.</span></span> <span data-ttu-id="3a4a8-122">In parole semplici, è possibile aggiungere solo numeri interi al tipo `List<int>` e persone al tipo `List<Person>`, e così via.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-122">Put simply, you can only add integers to `List<int>` and only add Persons to `List<Person>`, etc.</span></span>

<span data-ttu-id="3a4a8-123">I generics sono anche disponibili in fase di esecuzione o **reified**.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-123">Generics are also available at runtime, or **reified**.</span></span> <span data-ttu-id="3a4a8-124">Ciò significa che il runtime sa quale tipo di struttura dei dati si sta usando e può eseguire un'archiviazione in memoria in modo più efficiente.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-124">This means the runtime knows what type of data structure you are using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="3a4a8-125">Questo è un breve programma che illustra l'efficienza di conoscere il tipo di struttura dei dati in fase di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="3a4a8-125">Here is a small program that illustrates the efficiency of knowing the data structure type at runtime:</span></span>

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

<span data-ttu-id="3a4a8-126">Il programma produce l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="3a4a8-126">This program yields the following output:</span></span>

```console
Generic Sort: System.Collections.Generic.List\`1[System.Int32] Time taken: 0.0789ms
Non-Generic Sort: System.Collections.ArrayList Time taken: 2.4324ms
```

<span data-ttu-id="3a4a8-127">La prima cosa che si può notare è che l'ordinamento dell'elenco generico è notevolmente più veloce dell'elenco non generico.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-127">The first thing you notice here is that sorting the generic list is significantly faster than for the non-generic list.</span></span> <span data-ttu-id="3a4a8-128">È anche possibile notare che il tipo per un elenco generico è specifico ([System. Int32]), mentre il tipo per un elenco non generico è generalizzato.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-128">You might also notice that the type for the generic list is distinct ([System.Int32]) whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="3a4a8-129">Poiché il runtime riconosce che il tipo generico `List<int>` è di tipo int, può archiviare gli elementi dell'elenco in una matrice sottostante di integer in memoria, mentre il tipo `ArrayList` non generico deve eseguire il cast di ogni elemento dell'elenco come oggetto archiviato in una matrice di oggetti in memoria.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-129">Because the runtime knows the generic `List<int>` is of type int, it can store the list elements in an underlying integer array in memory while the non-generic `ArrayList` has to cast each list element as an object as stored in an object array in memory.</span></span> <span data-ttu-id="3a4a8-130">Come illustrato in questo esempio, i cast aggiuntivi richiedono tempo e rallentano l'ordinamento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-130">As shown through this example, the extra castings take up time and slow down the list sort.</span></span>

<span data-ttu-id="3a4a8-131">Se il runtime riconosce il tipo generico, offre una migliore esperienza di debug.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-131">The last useful thing about the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="3a4a8-132">Quando si esegue il debug di un tipo generico in C#, si può sapere di quale tipo è ogni elemento nella struttura dei dati.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-132">When you are debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="3a4a8-133">Senza i generics, questo non sarebbe possibile.</span><span class="sxs-lookup"><span data-stu-id="3a4a8-133">Without generics, you would have no idea what type each element was.</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="3a4a8-134">Altre informazioni e risorse</span><span class="sxs-lookup"><span data-stu-id="3a4a8-134">Further reading and resources</span></span>

*   [<span data-ttu-id="3a4a8-135">Introduzione ai generics per C#</span><span class="sxs-lookup"><span data-stu-id="3a4a8-135">An Introduction to C# Generics</span></span>](https://msdn.microsoft.com/library/ms379564.aspx)
*   [<span data-ttu-id="3a4a8-136">Generics (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3a4a8-136">C# Programming Guide - Generics</span></span>](../../docs/csharp/programming-guide/generics/index.md)
