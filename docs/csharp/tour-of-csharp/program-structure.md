---
title: Struttura del programma C# - Panoramica del linguaggio C#
description: Informazioni sui blocchi predefiniti di un programma C#
ms.date: 02/25/2020
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: 828146ba509daf9427e6dd1a4ebf3ad747ac7c39
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159117"
---
# <a name="program-structure"></a><span data-ttu-id="02cfb-103">Struttura del programma</span><span class="sxs-lookup"><span data-stu-id="02cfb-103">Program Structure</span></span>

<span data-ttu-id="02cfb-104">I concetti organizzativi chiave di C# sono i ***programmi***, gli ***spazi dei nomi***, i ***tipi***, i ***membri*** e gli ***assembly***.</span><span class="sxs-lookup"><span data-stu-id="02cfb-104">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="02cfb-105">I programmi C# sono costituiti da uno o più file di origine.</span><span class="sxs-lookup"><span data-stu-id="02cfb-105">C# programs consist of one or more source files.</span></span> <span data-ttu-id="02cfb-106">I programmi dichiarano i tipi, che contengono i membri e possono essere organizzati in spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="02cfb-106">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="02cfb-107">Le classi e le interfacce sono esempi di tipi.</span><span class="sxs-lookup"><span data-stu-id="02cfb-107">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="02cfb-108">I campi, i metodi, le proprietà e gli eventi sono esempi di membri.</span><span class="sxs-lookup"><span data-stu-id="02cfb-108">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="02cfb-109">Quando C# i programmi vengono compilati, vengono inseriti fisicamente in assembly.</span><span class="sxs-lookup"><span data-stu-id="02cfb-109">When C# programs are compiled, they're physically packaged into assemblies.</span></span> <span data-ttu-id="02cfb-110">Gli assembly in genere hanno l'estensione `.exe` o `.dll`, a seconda che implementino rispettivamente ***applicazioni*** o ***librerie***.</span><span class="sxs-lookup"><span data-stu-id="02cfb-110">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="02cfb-111">È possibile creare un progetto di libreria denominato *ACME* usando il comando `dotnet new`:</span><span class="sxs-lookup"><span data-stu-id="02cfb-111">You can create a library project named *acme* using the `dotnet new` command:</span></span>

```console
dotnet new classlib -o acme
```

<span data-ttu-id="02cfb-112">In tale progetto dichiarare una classe denominata `Stack` in uno spazio dei nomi denominato `Acme.Collections`:</span><span class="sxs-lookup"><span data-stu-id="02cfb-112">In that project, declare a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

<span data-ttu-id="02cfb-113">Il nome completo di questa classe è `Acme.Collections.Stack`.</span><span class="sxs-lookup"><span data-stu-id="02cfb-113">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="02cfb-114">La classe contiene vari membri: un campo `top`, due metodi `Push` e `Pop` e una classe annidata `Entry`.</span><span class="sxs-lookup"><span data-stu-id="02cfb-114">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="02cfb-115">La classe `Entry` contiene altri tre membri: un campo `next`, un campo `data` e un costruttore.</span><span class="sxs-lookup"><span data-stu-id="02cfb-115">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="02cfb-116">Il comando:</span><span class="sxs-lookup"><span data-stu-id="02cfb-116">The command:</span></span>

```console
dotnet build 
```

<span data-ttu-id="02cfb-117">compila l'esempio come libreria (codice senza un punto di ingresso `Main`) e genera un assembly denominato `acme.dll`.</span><span class="sxs-lookup"><span data-stu-id="02cfb-117">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

<span data-ttu-id="02cfb-118">Gli assembly contengono codice eseguibile sotto forma di istruzioni di linguaggio intermedio (Intermediate Language, IL) e informazioni simboliche sotto forma di metadati.</span><span class="sxs-lookup"><span data-stu-id="02cfb-118">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="02cfb-119">Prima che venga eseguita, il compilatore JIT (just-in-Time) di .NET Common Language Runtime converte il codice IL in un assembly in codice specifico del processore.</span><span class="sxs-lookup"><span data-stu-id="02cfb-119">Before it's executed, the Just-In-Time (JIT) compiler of .NET Common Language Runtime converts the IL code in an assembly to processor-specific code.</span></span>

<span data-ttu-id="02cfb-120">Poiché un assembly è un'unità di funzionalità autodescrittiva che contiene sia il codice che i metadati, non è necessario `#include` direttive e i file di intestazione C#in.</span><span class="sxs-lookup"><span data-stu-id="02cfb-120">Because an assembly is a self-describing unit of functionality containing both code and metadata, there's no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="02cfb-121">I membri e i tipi pubblici contenuti in un determinato assembly vengono resi disponibili in un programma C# semplicemente facendo riferimento a tale assembly durante la compilazione del programma.</span><span class="sxs-lookup"><span data-stu-id="02cfb-121">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="02cfb-122">Questo programma usa ad esempio la classe `Acme.Collections.Stack` dell'assembly `acme.dll`:</span><span class="sxs-lookup"><span data-stu-id="02cfb-122">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

<span data-ttu-id="02cfb-123">Il file *csproj* per il progetto del programma precedente deve includere un nodo di riferimento per C# il compilatore per risolvere i riferimenti alle classi nell'assembly `acme.dll`:</span><span class="sxs-lookup"><span data-stu-id="02cfb-123">The *csproj* file for the preceding program's project must include a reference node for the C# compiler to resolve references to the classes in the `acme.dll` assembly:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\acme\acme.csproj" />
  </ItemGroup>
```

<span data-ttu-id="02cfb-124">Successivamente, `dotnet build` crea un assembly eseguibile denominato `example.exe`, che, quando eseguito, produce l'output:</span><span class="sxs-lookup"><span data-stu-id="02cfb-124">After that addition, `dotnet build` creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```console
100
10
1
```

<span data-ttu-id="02cfb-125">C# consente di archiviare il testo di origine di un programma in vari file di origine.</span><span class="sxs-lookup"><span data-stu-id="02cfb-125">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="02cfb-126">Quando viene compilato un programma C# costituito da più file, tutti i file di origine vengono elaborati insieme e possono fare riferimento l'uno all'altro. A livello concettuale è come se tutti i file di origine fossero concatenati in un unico grande file prima di essere elaborati.</span><span class="sxs-lookup"><span data-stu-id="02cfb-126">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="02cfb-127">Le dichiarazioni con stato non sono mai C# necessarie in perché, con poche eccezioni, l'ordine di dichiarazione non è significativo.</span><span class="sxs-lookup"><span data-stu-id="02cfb-127">Forward declarations are never needed in C# because, with few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="02cfb-128">C# non limita un file di origine alla dichiarazione di un solo tipo pubblico e non richiede che il nome del file di origine corrisponda a un tipo dichiarato nel file di origine.</span><span class="sxs-lookup"><span data-stu-id="02cfb-128">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="02cfb-129">[Precedente](index.md)
>[Successivo](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="02cfb-129">[Previous](index.md)
[Next](types-and-variables.md)</span></span>
