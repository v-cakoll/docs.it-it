---
title: Struttura del programma C# - Panoramica del linguaggio C#
description: Informazioni sui blocchi predefiniti di un programma C#
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: 8d8f443f8458cd392c75e9787e612ca1cc3518c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="program-structure"></a><span data-ttu-id="1e972-104">Struttura del programma</span><span class="sxs-lookup"><span data-stu-id="1e972-104">Program Structure</span></span>

<span data-ttu-id="1e972-105">I concetti organizzativi chiave di C# sono i ***programmi***, gli ***spazi dei nomi***, i ***tipi***, i ***membri*** e gli ***assembly***.</span><span class="sxs-lookup"><span data-stu-id="1e972-105">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="1e972-106">I programmi C# sono costituiti da uno o più file di origine.</span><span class="sxs-lookup"><span data-stu-id="1e972-106">C# programs consist of one or more source files.</span></span> <span data-ttu-id="1e972-107">I programmi dichiarano i tipi, che contengono i membri e possono essere organizzati in spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1e972-107">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="1e972-108">Le classi e le interfacce sono esempi di tipi.</span><span class="sxs-lookup"><span data-stu-id="1e972-108">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="1e972-109">I campi, i metodi, le proprietà e gli eventi sono esempi di membri.</span><span class="sxs-lookup"><span data-stu-id="1e972-109">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="1e972-110">Quando vengono compilati, i programmi C# vengono inseriti fisicamente in assembly.</span><span class="sxs-lookup"><span data-stu-id="1e972-110">When C# programs are compiled, they are physically packaged into assemblies.</span></span> <span data-ttu-id="1e972-111">Gli assembly in genere hanno l'estensione `.exe` o `.dll`, a seconda che implementino rispettivamente ***applicazioni*** o ***librerie***.</span><span class="sxs-lookup"><span data-stu-id="1e972-111">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="1e972-112">Nell'esempio viene dichiarata una classe denominata `Stack` in uno spazio dei nomi denominato `Acme.Collections`:</span><span class="sxs-lookup"><span data-stu-id="1e972-112">The example declares a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

<span data-ttu-id="1e972-113">Il nome completo di questa classe è `Acme.Collections.Stack`.</span><span class="sxs-lookup"><span data-stu-id="1e972-113">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="1e972-114">La classe contiene vari membri: un campo `top`, due metodi `Push` e `Pop` e una classe annidata `Entry`.</span><span class="sxs-lookup"><span data-stu-id="1e972-114">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="1e972-115">La classe `Entry` contiene altri tre membri: un campo `next`, un campo `data` e un costruttore.</span><span class="sxs-lookup"><span data-stu-id="1e972-115">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="1e972-116">Supponendo che il codice sorgente dell'esempio sia archiviato nel file `acme.cs`, la riga di comando</span><span class="sxs-lookup"><span data-stu-id="1e972-116">Assuming that the source code of the example is stored in the file `acme.cs`, the command line</span></span>

```
csc /t:library acme.cs
```

<span data-ttu-id="1e972-117">compila l'esempio come libreria (codice senza un punto di ingresso `Main`) e genera un assembly denominato `acme.dll`.</span><span class="sxs-lookup"><span data-stu-id="1e972-117">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e972-118">Negli esempi precedenti viene usato `csc` come compilatore C# della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="1e972-118">The examples above use `csc` as the command line C# compiler.</span></span> <span data-ttu-id="1e972-119">Questo compilatore è un eseguibile Windows.</span><span class="sxs-lookup"><span data-stu-id="1e972-119">This compiler is a windows executable.</span></span> <span data-ttu-id="1e972-120">Per usare C# in altre piattaforme, è necessario usare gli strumenti per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1e972-120">To use C# across other platforms, you should use the tools for .NET Core.</span></span> <span data-ttu-id="1e972-121">L'ecosistema .NET Core usa l'interfaccia della riga di comando `dotnet` per gestire le compilazioni della riga di comando</span><span class="sxs-lookup"><span data-stu-id="1e972-121">The .NET Core ecosystem uses the `dotnet` CLI to manage command line builds.</span></span> <span data-ttu-id="1e972-122">e anche per gestire le dipendenze e richiamare il compilatore C#.</span><span class="sxs-lookup"><span data-stu-id="1e972-122">This includes managing dependencies, and invoking the C# compiler.</span></span> <span data-ttu-id="1e972-123">Per una descrizione completa di tali strumenti sulle piattaforme supportate da .NET Core, vedere [questa esercitazione](../../core/tutorials/using-with-xplat-cli.md).</span><span class="sxs-lookup"><span data-stu-id="1e972-123">See [this tutorial](../../core/tutorials/using-with-xplat-cli.md) for a full description of those tools on the platforms supported by .NET Core.</span></span>

<span data-ttu-id="1e972-124">Gli assembly contengono codice eseguibile sotto forma di istruzioni di linguaggio intermedio (Intermediate Language, IL) e informazioni simboliche sotto forma di metadati.</span><span class="sxs-lookup"><span data-stu-id="1e972-124">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="1e972-125">Prima di essere eseguito, il codice IL presente in un assembly viene convertito automaticamente nel codice specifico del processore dal compilatore JIT (Just-In-Time) di .NET Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="1e972-125">Before it is executed, the IL code in an assembly is automatically converted to processor-specific code by the Just-In-Time (JIT) compiler of .NET Common Language Runtime.</span></span>

<span data-ttu-id="1e972-126">Poiché un assembly è un'unità autodescrittiva di funzionalità contenente codice e metadati, in C# non sono necessari file di intestazione e direttive `#include`.</span><span class="sxs-lookup"><span data-stu-id="1e972-126">Because an assembly is a self-describing unit of functionality containing both code and metadata, there is no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="1e972-127">I membri e i tipi pubblici contenuti in un determinato assembly vengono resi disponibili in un programma C# semplicemente facendo riferimento a tale assembly durante la compilazione del programma.</span><span class="sxs-lookup"><span data-stu-id="1e972-127">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="1e972-128">Questo programma usa ad esempio la classe `Acme.Collections.Stack` dell'assembly `acme.dll`:</span><span class="sxs-lookup"><span data-stu-id="1e972-128">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

<span data-ttu-id="1e972-129">Se il programma è archiviato nel file `example.cs`, quando `example.cs` viene compilato è possibile fare riferimento all'assembly acme.dll usando l'opzione /r del compilatore:</span><span class="sxs-lookup"><span data-stu-id="1e972-129">If the program is stored in the file `example.cs`, when `example.cs` is compiled, the acme.dll assembly can be referenced using the compiler’s /r option:</span></span>

```
csc /r:acme.dll example.cs
```

<span data-ttu-id="1e972-130">In questo modo verrà creato un assembly eseguibile denominato `example.exe` che, quando viene eseguito, genera l'output:</span><span class="sxs-lookup"><span data-stu-id="1e972-130">This creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```
100
10
1
```

<span data-ttu-id="1e972-131">C# consente di archiviare il testo di origine di un programma in vari file di origine.</span><span class="sxs-lookup"><span data-stu-id="1e972-131">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="1e972-132">Quando viene compilato un programma C# costituito da più file, tutti i file di origine vengono elaborati insieme e possono fare riferimento l'uno all'altro. A livello concettuale è come se tutti i file di origine fossero concatenati in un unico grande file prima di essere elaborati.</span><span class="sxs-lookup"><span data-stu-id="1e972-132">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="1e972-133">Le dichiarazioni con prototipo non sono mai necessarie in C# perché, tranne che in rare eccezioni, l'ordine di dichiarazione non è significativo.</span><span class="sxs-lookup"><span data-stu-id="1e972-133">Forward declarations are never needed in C# because, with very few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="1e972-134">C# non limita un file di origine alla dichiarazione di un solo tipo pubblico e non richiede che il nome del file di origine corrisponda a un tipo dichiarato nel file di origine.</span><span class="sxs-lookup"><span data-stu-id="1e972-134">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="1e972-135">[Precedente](index.md)
[Successivo](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="1e972-135">[Previous](index.md)
[Next](types-and-variables.md)</span></span>
