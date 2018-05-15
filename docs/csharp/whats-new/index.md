---
title: Novità di C# - Guida a C#
description: Informazioni sull'evoluzione del linguaggio C#
ms.date: 11/13/2017
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: 3fc42809943b10d09d59780576dd9768d9e16ec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c"></a><span data-ttu-id="6bce2-103">Novità di C#</span><span class="sxs-lookup"><span data-stu-id="6bce2-103">What's new in C#</span></span> #

<span data-ttu-id="6bce2-104">Questa pagina offre un riepilogo delle nuove funzionalità in ogni versione principale del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="6bce2-104">This page provides a roadmap of new features in each major release of the C# language.</span></span> <span data-ttu-id="6bce2-105">I collegamenti seguenti forniscono informazioni dettagliate sulle principali funzionalità aggiunte in ogni versione.</span><span class="sxs-lookup"><span data-stu-id="6bce2-105">The following links provide detailed information on the major features added in each release.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6bce2-106">Il linguaggio C# si basa sui tipi e metodi in una *libreria standard* per alcune delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6bce2-106">The C# language relies on types and methods in a *standard library* for some of the features.</span></span> <span data-ttu-id="6bce2-107">Un esempio è l'elaborazione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="6bce2-107">One example is exception processing.</span></span> <span data-ttu-id="6bce2-108">Ogni istruzione o espressione `throw` viene controllata per assicurarsi che l'oggetto generato derivi da <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="6bce2-108">Every `throw` statement or expression is checked to ensure the object being thrown is derived from <xref:System.Exception>.</span></span> <span data-ttu-id="6bce2-109">Analogamente, ogni istruzione `catch` viene controllata per verificare che il tipo intercettato derivi da <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="6bce2-109">Similarly, every `catch` is checked to ensure that the type being caught is derived from <xref:System.Exception>.</span></span> <span data-ttu-id="6bce2-110">In ogni versione potrebbero essere aggiunti nuovi requisiti.</span><span class="sxs-lookup"><span data-stu-id="6bce2-110">Each version may add new requirements.</span></span> <span data-ttu-id="6bce2-111">Per usare le funzionalità del linguaggio più recenti in ambienti meno recenti, potrebbe essere necessario installare librerie specifiche.</span><span class="sxs-lookup"><span data-stu-id="6bce2-111">To use the latest language features in older environments, you may need to install specific libraries.</span></span> <span data-ttu-id="6bce2-112">Queste dipendenze sono documentate nella pagina per ogni versione specifica.</span><span class="sxs-lookup"><span data-stu-id="6bce2-112">These dependencies are documented in the page for each specific version.</span></span> <span data-ttu-id="6bce2-113">Le informazioni sulle [relazioni tra linguaggio e libreria](relationships-between-language-and-library.md) possono essere utili per comprendere meglio questa dipendenza.</span><span class="sxs-lookup"><span data-stu-id="6bce2-113">You can learn more about the [relationships between language and library](relationships-between-language-and-library.md) for background on this dependency.</span></span> 


* <span data-ttu-id="6bce2-114">[C# 7.2](csharp-7-2.md):</span><span class="sxs-lookup"><span data-stu-id="6bce2-114">[C# 7.2](csharp-7-2.md):</span></span>
    - <span data-ttu-id="6bce2-115">Questa pagina descrive le funzionalità più recenti del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="6bce2-115">This page describes the latest features in the C# language.</span></span> <span data-ttu-id="6bce2-116">C# 7.2 è attualmente disponibile in [Visual Studio 2017 versione 15.5](https://www.visualstudio.com/vs/whatsnew/) e in [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="6bce2-116">C# 7.2 is currently available in [Visual Studio 2017 version 15.5](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="6bce2-117">[C# 7.1](csharp-7-1.md):</span><span class="sxs-lookup"><span data-stu-id="6bce2-117">[C# 7.1](csharp-7-1.md):</span></span>
    - <span data-ttu-id="6bce2-118">Questa pagina descrive le funzionalità disponibili in C# 7.1.</span><span class="sxs-lookup"><span data-stu-id="6bce2-118">This page describes the features in C# 7.1.</span></span> <span data-ttu-id="6bce2-119">Queste funzionalità sono state aggiunte in [Visual Studio 2017 versione 15.3](https://www.visualstudio.com/vs/whatsnew/) e in [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="6bce2-119">These features were added in [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="6bce2-120">[C# 7.0](csharp-7.md):</span><span class="sxs-lookup"><span data-stu-id="6bce2-120">[C# 7.0](csharp-7.md):</span></span>
    - <span data-ttu-id="6bce2-121">Questa pagina descrive le funzionalità aggiunte in C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="6bce2-121">This page describes the features added in C# 7.0.</span></span> <span data-ttu-id="6bce2-122">Queste funzionalità sono state aggiunte in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) e [.NET Core 1.0](../../core/whats-new/index.md) e versioni successive</span><span class="sxs-lookup"><span data-stu-id="6bce2-122">These features were added in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) and [.NET Core 1.0](../../core/whats-new/index.md) and later</span></span>
     
* <span data-ttu-id="6bce2-123">[C# 6](csharp-6.md):</span><span class="sxs-lookup"><span data-stu-id="6bce2-123">[C# 6](csharp-6.md):</span></span>
    - <span data-ttu-id="6bce2-124">Questa pagina descrive le funzionalità che sono state aggiunte in C# 6.</span><span class="sxs-lookup"><span data-stu-id="6bce2-124">This page describes the features that were added in C# 6.</span></span> <span data-ttu-id="6bce2-125">Queste funzionalità sono disponibili in Visual Studio 2015 per gli sviluppatori Windows e in .NET Core 1.0 per gli sviluppatori che vogliono esplorare il linguaggio C# in macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="6bce2-125">These features are available in Visual Studio 2015 for Windows developers, and on .NET Core 1.0 for developers exploring C# on macOS and Linux.</span></span>

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* <span data-ttu-id="6bce2-126">[Supporto per più piattaforme](../../core/index.md):</span><span class="sxs-lookup"><span data-stu-id="6bce2-126">[Cross Platform Support](../../core/index.md):</span></span>
    - <span data-ttu-id="6bce2-127">Grazie al supporto per .NET Core, è possibile eseguire C# su diverse piattaforme.</span><span class="sxs-lookup"><span data-stu-id="6bce2-127">C#, through .NET Core support, runs on multiple platforms.</span></span> <span data-ttu-id="6bce2-128">Gli utenti interessati a provare C# in macOS o su una delle diverse distribuzioni Linux supportate possono leggere le informazioni relative a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6bce2-128">If you are interested in trying C# on macOS, or on one of the many supported Linux distributions, learn more about .NET Core.</span></span>

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a><span data-ttu-id="6bce2-129">Versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="6bce2-129">Previous Versions</span></span>
<span data-ttu-id="6bce2-130">Di seguito sono elencate le principali funzionalità introdotte in versioni precedenti del linguaggio C# e Visual Studio .NET.</span><span class="sxs-lookup"><span data-stu-id="6bce2-130">The following lists key features that were introduced in previous versions of the C# language and Visual Studio .NET.</span></span>  
  
 * <span data-ttu-id="6bce2-131">Visual Studio .NET 2013:</span><span class="sxs-lookup"><span data-stu-id="6bce2-131">Visual Studio .NET 2013:</span></span> 
     - <span data-ttu-id="6bce2-132">Questa versione di Visual Studio include correzioni di bug, miglioramenti delle prestazioni e Technology Preview di .NET Compiler Platform ("Roslyn") che è diventato .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span><span class="sxs-lookup"><span data-stu-id="6bce2-132">This version of Visual Studio included bug fixes, performance improvements, and technology previews of .NET Compiler Platform ("Roslyn") which became the .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span></span>

 * <span data-ttu-id="6bce2-133">C# 5, Visual Studio .NET 2012:</span><span class="sxs-lookup"><span data-stu-id="6bce2-133">C# 5, Visual Studio .NET 2012:</span></span> 
     - <span data-ttu-id="6bce2-134">`Async` / `await` e attributi delle [informazioni sul chiamante](../programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="6bce2-134">`Async` / `await`, and [caller information](../programming-guide/concepts/caller-information.md) attributes.</span></span>

 * <span data-ttu-id="6bce2-135">C# 4, Visual Studio .NET 2010:</span><span class="sxs-lookup"><span data-stu-id="6bce2-135">C# 4, Visual Studio .NET 2010:</span></span> 
     - <span data-ttu-id="6bce2-136">`Dynamic`, [argomenti denominati](../programming-guide/classes-and-structs/named-and-optional-arguments.md), parametri facoltativi, [covarianza e controvarianza](../programming-guide/concepts/covariance-contravariance/index.md) generiche.</span><span class="sxs-lookup"><span data-stu-id="6bce2-136">`Dynamic`, [named arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optional parameters, and generic [covariance and contra variance](../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

 * <span data-ttu-id="6bce2-137">C# 3, Visual Studio .NET 2008:</span><span class="sxs-lookup"><span data-stu-id="6bce2-137">C# 3, Visual Studio .NET 2008:</span></span> 
     - <span data-ttu-id="6bce2-138">Inizializzatori di oggetto e di raccolta, espressioni lambda, metodi di estensione, tipi anonimi, proprietà automatiche, inferenza del tipo `var` locale e [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="6bce2-138">Object and collection initializers, lambda expressions, extension methods, anonymous types, automatic properties, local `var` type inference, and [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span></span>

 * <span data-ttu-id="6bce2-139">C# 2, Visual Studio .NET 2005:</span><span class="sxs-lookup"><span data-stu-id="6bce2-139">C# 2, Visual Studio .NET 2005:</span></span> 
     - <span data-ttu-id="6bce2-140">Metodi anonimi, generics, tipi nullable, iteratori/yield, classi `static`, covarianza e controvarianza per i delegati.</span><span class="sxs-lookup"><span data-stu-id="6bce2-140">Anonymous methods, generics, nullable types, iterators/yield, `static` classes, and covariance and contra variance for delegates.</span></span>

 * <span data-ttu-id="6bce2-141">C# 1.1, Visual Studio .NET 2003:</span><span class="sxs-lookup"><span data-stu-id="6bce2-141">C# 1.1, Visual Studio .NET 2003:</span></span> 
     - <span data-ttu-id="6bce2-142">Pragma `#line` e commenti documento xml.</span><span class="sxs-lookup"><span data-stu-id="6bce2-142">`#line` pragma and xml doc comments.</span></span>

 * <span data-ttu-id="6bce2-143">C# 1, Visual Studio .NET 2002:</span><span class="sxs-lookup"><span data-stu-id="6bce2-143">C# 1, Visual Studio .NET 2002:</span></span> 
     - <span data-ttu-id="6bce2-144">La prima versione di [C#](../csharp.md).</span><span class="sxs-lookup"><span data-stu-id="6bce2-144">The first release of [C#](../csharp.md).</span></span>   
