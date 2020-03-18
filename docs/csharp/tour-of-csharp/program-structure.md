---
title: Struttura del programma C# - Panoramica del linguaggio C#
description: Informazioni sui blocchi predefiniti di un programma C#
ms.date: 02/25/2020
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: c09c11a4dd957b29b2adb7aaa8d68a50f30620b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156831"
---
# <a name="program-structure"></a><span data-ttu-id="ff230-103">Struttura del programma</span><span class="sxs-lookup"><span data-stu-id="ff230-103">Program Structure</span></span>

<span data-ttu-id="ff230-104">I concetti organizzativi chiave di C# sono i ***programmi***, gli ***spazi dei nomi***, i ***tipi***, i ***membri*** e gli ***assembly***.</span><span class="sxs-lookup"><span data-stu-id="ff230-104">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="ff230-105">I programmi C# sono costituiti da uno o più file di origine.</span><span class="sxs-lookup"><span data-stu-id="ff230-105">C# programs consist of one or more source files.</span></span> <span data-ttu-id="ff230-106">I programmi dichiarano i tipi, che contengono i membri e possono essere organizzati in spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ff230-106">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="ff230-107">Le classi e le interfacce sono esempi di tipi.</span><span class="sxs-lookup"><span data-stu-id="ff230-107">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="ff230-108">I campi, i metodi, le proprietà e gli eventi sono esempi di membri.</span><span class="sxs-lookup"><span data-stu-id="ff230-108">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="ff230-109">Quando vengono compilati i programmi di C, vengono fisicamente inclusi nel pacchetto in assembly.</span><span class="sxs-lookup"><span data-stu-id="ff230-109">When C# programs are compiled, they're physically packaged into assemblies.</span></span> <span data-ttu-id="ff230-110">Gli assembly in genere hanno l'estensione `.exe` o `.dll`, a seconda che implementino rispettivamente ***applicazioni*** o ***librerie***.</span><span class="sxs-lookup"><span data-stu-id="ff230-110">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="ff230-111">È possibile creare un progetto di `dotnet new` libreria denominato *acme* utilizzando il comando:</span><span class="sxs-lookup"><span data-stu-id="ff230-111">You can create a library project named *acme* using the `dotnet new` command:</span></span>

```console
dotnet new classlib -o acme
```

<span data-ttu-id="ff230-112">In tale progetto dichiarare `Stack` una classe `Acme.Collections`denominata in uno spazio dei nomi denominato :</span><span class="sxs-lookup"><span data-stu-id="ff230-112">In that project, declare a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

<span data-ttu-id="ff230-113">Il nome completo di questa classe è `Acme.Collections.Stack`.</span><span class="sxs-lookup"><span data-stu-id="ff230-113">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="ff230-114">La classe contiene vari membri: un campo `top`, due metodi `Push` e `Pop` e una classe annidata `Entry`.</span><span class="sxs-lookup"><span data-stu-id="ff230-114">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="ff230-115">La classe `Entry` contiene altri tre membri: un campo `next`, un campo `data` e un costruttore.</span><span class="sxs-lookup"><span data-stu-id="ff230-115">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="ff230-116">Il comando:</span><span class="sxs-lookup"><span data-stu-id="ff230-116">The command:</span></span>

```console
dotnet build
```

<span data-ttu-id="ff230-117">compila l'esempio come libreria (codice senza un punto di ingresso `Main`) e genera un assembly denominato `acme.dll`.</span><span class="sxs-lookup"><span data-stu-id="ff230-117">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

<span data-ttu-id="ff230-118">Gli assembly contengono codice eseguibile sotto forma di istruzioni di linguaggio intermedio (Intermediate Language, IL) e informazioni simboliche sotto forma di metadati.</span><span class="sxs-lookup"><span data-stu-id="ff230-118">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="ff230-119">Prima dell'esecuzione, il compilatore JIT (Just-In-Time) di .NET Common Language Runtime converte il codice IL in un assembly in codice specifico del processore.</span><span class="sxs-lookup"><span data-stu-id="ff230-119">Before it's executed, the Just-In-Time (JIT) compiler of .NET Common Language Runtime converts the IL code in an assembly to processor-specific code.</span></span>

<span data-ttu-id="ff230-120">Poiché un assembly è un'unità di funzionalità autodescrittiva che `#include` contiene sia codice che metadati, non è necessario che le direttive e i file di intestazione siano presenti in C.</span><span class="sxs-lookup"><span data-stu-id="ff230-120">Because an assembly is a self-describing unit of functionality containing both code and metadata, there's no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="ff230-121">I membri e i tipi pubblici contenuti in un determinato assembly vengono resi disponibili in un programma C# semplicemente facendo riferimento a tale assembly durante la compilazione del programma.</span><span class="sxs-lookup"><span data-stu-id="ff230-121">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="ff230-122">Questo programma usa ad esempio la classe `Acme.Collections.Stack` dell'assembly `acme.dll`:</span><span class="sxs-lookup"><span data-stu-id="ff230-122">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

<span data-ttu-id="ff230-123">Il file *csproj* per il progetto del programma precedente deve includere un nodo di riferimento `acme.dll` per il compilatore C , per risolvere i riferimenti alle classi nell'assembly:</span><span class="sxs-lookup"><span data-stu-id="ff230-123">The *csproj* file for the preceding program's project must include a reference node for the C# compiler to resolve references to the classes in the `acme.dll` assembly:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\acme\acme.csproj" />
  </ItemGroup>
```

<span data-ttu-id="ff230-124">Dopo tale `dotnet build` addizione, `example.exe`viene creato un assembly eseguibile denominato , che, quando eseguito, produce l'output:</span><span class="sxs-lookup"><span data-stu-id="ff230-124">After that addition, `dotnet build` creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```console
100
10
1
```

<span data-ttu-id="ff230-125">C# consente di archiviare il testo di origine di un programma in vari file di origine.</span><span class="sxs-lookup"><span data-stu-id="ff230-125">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="ff230-126">Quando viene compilato un programma C# costituito da più file, tutti i file di origine vengono elaborati insieme e possono fare riferimento l'uno all'altro. A livello concettuale è come se tutti i file di origine fossero concatenati in un unico grande file prima di essere elaborati.</span><span class="sxs-lookup"><span data-stu-id="ff230-126">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="ff230-127">Le dichiarazioni con prototipo non sono mai necessarie in C, perché, con poche eccezioni, l'ordine di dichiarazione è insignificante.</span><span class="sxs-lookup"><span data-stu-id="ff230-127">Forward declarations are never needed in C# because, with few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="ff230-128">C# non limita un file di origine alla dichiarazione di un solo tipo pubblico e non richiede che il nome del file di origine corrisponda a un tipo dichiarato nel file di origine.</span><span class="sxs-lookup"><span data-stu-id="ff230-128">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ff230-129">[Successivo](index.md)
>[precedente](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="ff230-129">[Previous](index.md)
[Next](types-and-variables.md)</span></span>
