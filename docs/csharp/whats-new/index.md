---
title: "Novità di C# - Guida a C#"
description: Informazioni sull'evoluzione del linguaggio C#
keywords: "C#, funzionalità più recenti, novità, Roslyn"
author: BillWagner
ms.author: wiwagn
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: 719fbe826b0b115b19067dbaf0d04f14e6534890
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="whats-new-in-c"></a><span data-ttu-id="32322-104">Novità di C#</span><span class="sxs-lookup"><span data-stu-id="32322-104">What's new in C#</span></span> #

<span data-ttu-id="32322-105">Questa pagina offre un riepilogo delle nuove funzionalità in ogni versione principale del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="32322-105">This page provides a roadmap of new features in each major release of the C# language.</span></span> <span data-ttu-id="32322-106">I collegamenti seguenti forniscono informazioni dettagliate sulle principali funzionalità aggiunte in ogni versione.</span><span class="sxs-lookup"><span data-stu-id="32322-106">The following links provide detailed information on the major features added in each release.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32322-107">Il linguaggio C# si basa sui tipi e metodi in una *libreria standard* per alcune delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="32322-107">The C# language relies on types and methods in a *standard library* for some of the features.</span></span> <span data-ttu-id="32322-108">Un esempio è l'elaborazione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="32322-108">One example is exception processing.</span></span> <span data-ttu-id="32322-109">Ogni istruzione o espressione `throw` viene controllata per assicurarsi che l'oggetto generato derivi da <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="32322-109">Every `throw` statement or expression is checked to ensure the object being thrown is derived from <xref:System.Exception>.</span></span> <span data-ttu-id="32322-110">Analogamente, ogni istruzione `catch` viene controllata per verificare che il tipo intercettato derivi da <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="32322-110">Similarly, every `catch` is checked to ensure that the type being caught is derived from <xref:System.Exception>.</span></span> <span data-ttu-id="32322-111">In ogni versione potrebbero essere aggiunti nuovi requisiti.</span><span class="sxs-lookup"><span data-stu-id="32322-111">Each version may add new requirements.</span></span> <span data-ttu-id="32322-112">Per usare le funzionalità del linguaggio più recenti in ambienti meno recenti, potrebbe essere necessario installare librerie specifiche.</span><span class="sxs-lookup"><span data-stu-id="32322-112">To use the latest language features in older environments, you may need to install specific libraries.</span></span> <span data-ttu-id="32322-113">Queste dipendenze sono documentate nella pagina per ogni versione specifica.</span><span class="sxs-lookup"><span data-stu-id="32322-113">These dependencies are documented in the page for each specific version.</span></span> <span data-ttu-id="32322-114">Le informazioni sulle [relazioni tra linguaggio e libreria](relationships-between-language-and-library.md) possono essere utili per comprendere meglio questa dipendenza.</span><span class="sxs-lookup"><span data-stu-id="32322-114">You can learn more about the [relationships between language and library](relationships-between-language-and-library.md) for background on this dependency.</span></span> 


* <span data-ttu-id="32322-115">[C# 7.2](csharp-7-2.md):</span><span class="sxs-lookup"><span data-stu-id="32322-115">[C# 7.2](csharp-7-2.md):</span></span>
    - <span data-ttu-id="32322-116">Questa pagina descrive le funzionalità più recenti del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="32322-116">This page describes the latest features in the C# language.</span></span> <span data-ttu-id="32322-117">C# 7.2 è attualmente disponibile in [Visual Studio 2017 versione 15.5](https://www.visualstudio.com/vs/whatsnew/) e in [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="32322-117">C# 7.2 is currently available in [Visual Studio 2017 version 15.5](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="32322-118">[C# 7.1](csharp-7-1.md):</span><span class="sxs-lookup"><span data-stu-id="32322-118">[C# 7.1](csharp-7-1.md):</span></span>
    - <span data-ttu-id="32322-119">Questa pagina descrive le funzionalità disponibili in C# 7.1.</span><span class="sxs-lookup"><span data-stu-id="32322-119">This page describes the features in C# 7.1.</span></span> <span data-ttu-id="32322-120">Queste funzionalità sono state aggiunte in [Visual Studio 2017 versione 15.3](https://www.visualstudio.com/vs/whatsnew/) e in [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="32322-120">These features were added in [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="32322-121">[C# 7](csharp-7.md):</span><span class="sxs-lookup"><span data-stu-id="32322-121">[C# 7](csharp-7.md):</span></span>
    - <span data-ttu-id="32322-122">Questa pagina descrive le funzionalità aggiunte in C# 7.</span><span class="sxs-lookup"><span data-stu-id="32322-122">This page describes the features added in C# 7.</span></span> <span data-ttu-id="32322-123">Queste funzionalità sono state aggiunte in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) e [.NET Core 1.0](../../core/whats-new/index.md) e versioni successive</span><span class="sxs-lookup"><span data-stu-id="32322-123">These features were added in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) and [.NET Core 1.0](../../core/whats-new/index.md) and later</span></span>
     
* <span data-ttu-id="32322-124">[C# 6](csharp-6.md):</span><span class="sxs-lookup"><span data-stu-id="32322-124">[C# 6](csharp-6.md):</span></span>
    - <span data-ttu-id="32322-125">Questa pagina descrive le funzionalità che sono state aggiunte in C# 6.</span><span class="sxs-lookup"><span data-stu-id="32322-125">This page describes the features that were added in C# 6.</span></span> <span data-ttu-id="32322-126">Queste funzionalità sono disponibili in Visual Studio 2015 per gli sviluppatori Windows e in .NET Core 1.0 per gli sviluppatori che vogliono esplorare il linguaggio C# in macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="32322-126">These features are available in Visual Studio 2015 for Windows developers, and on .NET Core 1.0 for developers exploring C# on macOS and Linux.</span></span>

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* <span data-ttu-id="32322-127">[Supporto per più piattaforme](../../core/index.md):</span><span class="sxs-lookup"><span data-stu-id="32322-127">[Cross Platform Support](../../core/index.md):</span></span>
    - <span data-ttu-id="32322-128">Grazie al supporto per .NET Core, è possibile eseguire C# su diverse piattaforme.</span><span class="sxs-lookup"><span data-stu-id="32322-128">C#, through .NET Core support, runs on multiple platforms.</span></span> <span data-ttu-id="32322-129">Gli utenti interessati a provare C# in macOS o su una delle diverse distribuzioni Linux supportate possono leggere le informazioni relative a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="32322-129">If you are interested in trying C# on macOS, or on one of the many supported Linux distributions, learn more about .NET Core.</span></span>

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a><span data-ttu-id="32322-130">Versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="32322-130">Previous Versions</span></span>
<span data-ttu-id="32322-131">Di seguito sono elencate le principali funzionalità introdotte in versioni precedenti del linguaggio C# e Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="32322-131">The following lists key features that were introduced in previous versions of the C# language and Visual Studio .NET.</span></span>  
  
 * <span data-ttu-id="32322-132">Visual Studio .NET 2013:</span><span class="sxs-lookup"><span data-stu-id="32322-132">Visual Studio .NET 2013:</span></span> 
     - <span data-ttu-id="32322-133">Questa versione di Visual Studio include correzioni di bug, miglioramenti delle prestazioni e Technology Preview di .NET Compiler Platform ("Roslyn") che è diventato .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span><span class="sxs-lookup"><span data-stu-id="32322-133">This version of Visual Studio included bug fixes, performance improvements, and technology previews of .NET Compiler Platform ("Roslyn") which became the .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span></span>

 * <span data-ttu-id="32322-134">C# 5, Visual Studio .NET 2012:</span><span class="sxs-lookup"><span data-stu-id="32322-134">C# 5, Visual Studio .NET 2012:</span></span> 
     - <span data-ttu-id="32322-135">`Async` / `await` e attributi delle [informazioni sul chiamante](../programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="32322-135">`Async` / `await`, and [caller information](../programming-guide/concepts/caller-information.md) attributes.</span></span>

 * <span data-ttu-id="32322-136">C# 4, Visual Studio .NET 2010:</span><span class="sxs-lookup"><span data-stu-id="32322-136">C# 4, Visual Studio .NET 2010:</span></span> 
     - <span data-ttu-id="32322-137">`Dynamic`, [argomenti denominati](../programming-guide/classes-and-structs/named-and-optional-arguments.md), parametri facoltativi, [covarianza e controvarianza](../programming-guide/concepts/covariance-contravariance/index.md) generiche.</span><span class="sxs-lookup"><span data-stu-id="32322-137">`Dynamic`, [named arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optional parameters, and generic [covariance and contra variance](../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

 * <span data-ttu-id="32322-138">C# 3, Visual Studio .NET 2008:</span><span class="sxs-lookup"><span data-stu-id="32322-138">C# 3, Visual Studio .NET 2008:</span></span> 
     - <span data-ttu-id="32322-139">Inizializzatori di oggetto e di raccolta, espressioni lambda, metodi di estensione, tipi anonimi, proprietà automatiche, inferenza del tipo `var` locale e [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="32322-139">Object and collection initializers, lambda expressions, extension methods, anonymous types, automatic properties, local `var` type inference, and [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span></span>

 * <span data-ttu-id="32322-140">C# 2, Visual Studio .NET 2005:</span><span class="sxs-lookup"><span data-stu-id="32322-140">C# 2, Visual Studio .NET 2005:</span></span> 
     - <span data-ttu-id="32322-141">Metodi anonimi, generics, tipi nullable, iteratori/yield, classi `static`, covarianza e controvarianza per i delegati.</span><span class="sxs-lookup"><span data-stu-id="32322-141">Anonymous methods, generics, nullable types, iterators/yield, `static` classes, and covariance and contra variance for delegates.</span></span>

 * <span data-ttu-id="32322-142">C# 1.1, Visual Studio .NET 2003:</span><span class="sxs-lookup"><span data-stu-id="32322-142">C# 1.1, Visual Studio .NET 2003:</span></span> 
     - <span data-ttu-id="32322-143">Pragma `#line` e commenti documento xml.</span><span class="sxs-lookup"><span data-stu-id="32322-143">`#line` pragma and xml doc comments.</span></span>

 * <span data-ttu-id="32322-144">C# 1, Visual Studio .NET 2002:</span><span class="sxs-lookup"><span data-stu-id="32322-144">C# 1, Visual Studio .NET 2002:</span></span> 
     - <span data-ttu-id="32322-145">La prima versione di [C#](../csharp.md).</span><span class="sxs-lookup"><span data-stu-id="32322-145">The first release of [C#](../csharp.md).</span></span>   
