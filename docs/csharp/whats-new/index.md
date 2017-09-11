---
title: "Novità di C# - Guida a C#"
description: Informazioni sull'evoluzione del linguaggio C#
keywords: "C#, funzionalità più recenti, novità, Roslyn"
author: BillWagner
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.translationtype: HT
ms.sourcegitcommit: df0438dd742db802bb0f935d840006236d5d9bf9
ms.openlocfilehash: 0a328f62a02aea223340fcc00e839e841041a7d6
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---

# <a name="whats-new-in-c"></a><span data-ttu-id="df661-104">Novità di C#</span><span class="sxs-lookup"><span data-stu-id="df661-104">What's new in C#</span></span> #

<span data-ttu-id="df661-105">Questa pagina offre un riepilogo delle nuove funzionalità in ogni versione principale del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="df661-105">This page provides a roadmap of new features in each major release of the C# language.</span></span> <span data-ttu-id="df661-106">I collegamenti seguenti indirizzano a informazioni dettagliate sulle funzionalità principali aggiunte in ogni versione.</span><span class="sxs-lookup"><span data-stu-id="df661-106">The links below provide detailed information on the major features added in each release.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df661-107">Il linguaggio C# si basa sui tipi e metodi in una *libreria standard* per alcune delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="df661-107">The C# language relies on types and methods in a *standard library* for some of the features.</span></span> <span data-ttu-id="df661-108">Un esempio è l'elaborazione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="df661-108">One example is exception processing.</span></span> <span data-ttu-id="df661-109">Ogni istruzione o espressione `throw` viene controllata per assicurarsi che l'oggetto generato derivi da @System.Exception.</span><span class="sxs-lookup"><span data-stu-id="df661-109">Every `throw` statement or expression is checked to ensure the object being thrown is derived from @System.Exception.</span></span> <span data-ttu-id="df661-110">Analogamente, ogni istruzione `catch` viene controllata per verificare che il tipo intercettato derivi da @System.Exception.</span><span class="sxs-lookup"><span data-stu-id="df661-110">Similarly, every `catch` is checked to ensure that the type being caught is derived from @System.Exception.</span></span> <span data-ttu-id="df661-111">In ogni versione potrebbero essere aggiunti nuovi requisiti.</span><span class="sxs-lookup"><span data-stu-id="df661-111">Each version may add new requirements.</span></span> <span data-ttu-id="df661-112">Per usare le funzionalità del linguaggio più recenti in ambienti meno recenti, potrebbe essere necessario installare librerie specifiche.</span><span class="sxs-lookup"><span data-stu-id="df661-112">To use the latest language features in older environments, you may need to install specific libraries.</span></span> <span data-ttu-id="df661-113">Questi requisiti sono documentati nella pagina per ogni versione specifica.</span><span class="sxs-lookup"><span data-stu-id="df661-113">These are documented in the page for each specific version.</span></span> <span data-ttu-id="df661-114">Le informazioni sulle [relazioni tra linguaggio e libreria](relationships-between-language-and-library.md) possono essere utili per comprendere meglio questa dipendenza.</span><span class="sxs-lookup"><span data-stu-id="df661-114">You can learn more about the [relationships between language and library](relationships-between-language-and-library.md) for background on this dependency.</span></span> 

* <span data-ttu-id="df661-115">[C# 7.1](csharp-7-1.md):</span><span class="sxs-lookup"><span data-stu-id="df661-115">[C# 7.1](csharp-7-1.md):</span></span>
    - <span data-ttu-id="df661-116">Questa pagina descrive le funzionalità più recenti del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="df661-116">This page describes the latest features in the C# language.</span></span> <span data-ttu-id="df661-117">La descrizione riguarda C# 7.1, attualmente disponibile in [Visual Studio 2017 versione 15.3](https://www.visualstudio.com/vs/whatsnew/) e in [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="df661-117">This covers C# 7.1, currently available in [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="df661-118">[C# 7](csharp-7.md):</span><span class="sxs-lookup"><span data-stu-id="df661-118">[C# 7](csharp-7.md):</span></span>
    - <span data-ttu-id="df661-119">Questa pagina descrive le funzionalità aggiunte in C# 7.</span><span class="sxs-lookup"><span data-stu-id="df661-119">This page describes the features added in C# 7.</span></span> <span data-ttu-id="df661-120">Questi elementi sono stati aggiunti in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) e [.NET Core 1.0](../../core/whats-new/index.md) e versioni successive</span><span class="sxs-lookup"><span data-stu-id="df661-120">Theses were added in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) and [.NET Core 1.0](../../core/whats-new/index.md) and later</span></span>
     
* <span data-ttu-id="df661-121">[C# 6](csharp-6.md):</span><span class="sxs-lookup"><span data-stu-id="df661-121">[C# 6](csharp-6.md):</span></span>
    - <span data-ttu-id="df661-122">Questa pagina descrive le funzionalità che sono state aggiunte in C# 6.</span><span class="sxs-lookup"><span data-stu-id="df661-122">This page describes the features that were added in C# 6.</span></span> <span data-ttu-id="df661-123">Queste funzionalità sono disponibili in Visual Studio 2015 per gli sviluppatori Windows e in .NET Core 1.0 per gli sviluppatori che vogliono esplorare il linguaggio C# in macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="df661-123">These features are available in Visual Studio 2015 for Windows developers, and on .NET Core 1.0 for developers exploring C# on macOS and Linux.</span></span>

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* <span data-ttu-id="df661-124">[Supporto per più piattaforme](../../core/index.md):</span><span class="sxs-lookup"><span data-stu-id="df661-124">[Cross Platform Support](../../core/index.md):</span></span>
    - <span data-ttu-id="df661-125">Grazie al supporto per .NET Core, è possibile eseguire C# su diverse piattaforme.</span><span class="sxs-lookup"><span data-stu-id="df661-125">C#, through .NET Core support, runs on multiple platforms.</span></span> <span data-ttu-id="df661-126">Gli utenti interessati a provare C# in macOS o su una delle diverse distribuzioni Linux supportate possono leggere le informazioni relative a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="df661-126">If you are interested in trying C# on macOS, or on one of the many supported Linux distributions, learn more about .NET Core.</span></span>

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a><span data-ttu-id="df661-127">Versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="df661-127">Previous Versions</span></span>
<span data-ttu-id="df661-128">Di seguito sono elencate le principali funzionalità introdotte in versioni precedenti del linguaggio C# e Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="df661-128">The following lists key features that were introduced in previous versions of the C# language and Visual Studio .NET.</span></span>  
  
 * <span data-ttu-id="df661-129">Visual Studio .NET 2013:</span><span class="sxs-lookup"><span data-stu-id="df661-129">Visual Studio .NET 2013:</span></span> 
     - <span data-ttu-id="df661-130">Questa versione di Visual Studio include correzioni di bug, miglioramenti delle prestazioni e Technology Preview di .NET Compiler Platform ("Roslyn") che è diventato .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span><span class="sxs-lookup"><span data-stu-id="df661-130">This version of Visual Studio included bug fixes, performance improvements, and technology previews of .NET Compiler Platform ("Roslyn") which became the .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span></span>

 * <span data-ttu-id="df661-131">C# 5, Visual Studio .NET 2012:</span><span class="sxs-lookup"><span data-stu-id="df661-131">C# 5, Visual Studio .NET 2012:</span></span> 
     - <span data-ttu-id="df661-132">`Async` / `await` e attributi delle [informazioni sul chiamante](../programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="df661-132">`Async` / `await`, and [caller information](../programming-guide/concepts/caller-information.md) attributes.</span></span>

 * <span data-ttu-id="df661-133">C# 4, Visual Studio .NET 2010:</span><span class="sxs-lookup"><span data-stu-id="df661-133">C# 4, Visual Studio .NET 2010:</span></span> 
     - <span data-ttu-id="df661-134">`Dynamic`, [argomenti denominati](../programming-guide/classes-and-structs/named-and-optional-arguments.md), parametri facoltativi, [covarianza e controvarianza](../programming-guide/concepts/covariance-contravariance/index.md) generiche.</span><span class="sxs-lookup"><span data-stu-id="df661-134">`Dynamic`, [named arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optional parameters, and generic [covariance and contra variance](../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

 * <span data-ttu-id="df661-135">C# 3, Visual Studio .NET 2008:</span><span class="sxs-lookup"><span data-stu-id="df661-135">C# 3, Visual Studio .NET 2008:</span></span> 
     - <span data-ttu-id="df661-136">Inizializzatori di oggetto e di raccolta, espressioni lambda, metodi di estensione, tipi anonimi, proprietà automatiche, inferenza del tipo `var` locale e [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="df661-136">Object and collection initializers, lambda expressions, extension methods, anonymous types, automatic properties, local `var` type inference, and [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span></span>

 * <span data-ttu-id="df661-137">C# 2, Visual Studio .NET 2005:</span><span class="sxs-lookup"><span data-stu-id="df661-137">C# 2, Visual Studio .NET 2005:</span></span> 
     - <span data-ttu-id="df661-138">Metodi anonimi, generics, tipi nullable, iteratori/yield, classi `static`, covarianza e controvarianza per i delegati.</span><span class="sxs-lookup"><span data-stu-id="df661-138">Anonymous methods, generics, nullable types, iterators/yield, `static` classes, and covariance and contra variance for delegates.</span></span>

 * <span data-ttu-id="df661-139">C# 1.1, Visual Studio .NET 2003:</span><span class="sxs-lookup"><span data-stu-id="df661-139">C# 1.1, Visual Studio .NET 2003:</span></span> 
     - <span data-ttu-id="df661-140">Pragma `#line` e commenti documento xml.</span><span class="sxs-lookup"><span data-stu-id="df661-140">`#line` pragma and xml doc comments.</span></span>

 * <span data-ttu-id="df661-141">C# 1, Visual Studio .NET 2002:</span><span class="sxs-lookup"><span data-stu-id="df661-141">C# 1, Visual Studio .NET 2002:</span></span> 
     - <span data-ttu-id="df661-142">La prima versione di [C#](../csharp.md).</span><span class="sxs-lookup"><span data-stu-id="df661-142">The first release of [C#](../csharp.md).</span></span>   

