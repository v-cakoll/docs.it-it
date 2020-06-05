---
title: Scrivere un semplice programma parallelo usando Parallel.ForEach
description: In questo articolo viene illustrato come abilitare il parallelismo dei dati in .NET. Scrivere un ciclo Parallel. ForEach su qualsiasi origine dati IEnumerable o IEnumerable <T> .
ms.date: 02/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
ms.openlocfilehash: 59c8710a8e3fc878b2ceded8595f7f3319d4c953
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447199"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="8256c-104">Procedura: scrivere un ciclo Parallel. ForEach semplice</span><span class="sxs-lookup"><span data-stu-id="8256c-104">How to: Write a simple Parallel.ForEach loop</span></span>

<span data-ttu-id="8256c-105">Questo esempio mostra come usare un ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> per abilitare il parallelismo dei dati in un'origine dati <xref:System.Collections.IEnumerable?displayProperty=nameWithType> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8256c-105">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>

> [!NOTE]
> <span data-ttu-id="8256c-106">Le espressioni lambda sono usate nella documentazione per definire i delegati in PLINQ.</span><span class="sxs-lookup"><span data-stu-id="8256c-106">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="8256c-107">Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="8256c-107">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda expressions in PLINQ and TPL](lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="8256c-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="8256c-108">Example</span></span>

<span data-ttu-id="8256c-109">Questo esempio presuppone che diversi file con estensione jpg siano presenti in una cartella *C:\Users\Public\Pictures\Sample Pictures* e crea una nuova sottocartella con nome *Modified*.</span><span class="sxs-lookup"><span data-stu-id="8256c-109">This example assumes you have several .jpg files in a *C:\Users\Public\Pictures\Sample Pictures* folder and creates a new sub-folder named *Modified*.</span></span> <span data-ttu-id="8256c-110">Quando si esegue l'esempio, il codice ruota ogni immagine con estensione jpg in *Sample Pictures* e la salva in *Modified*.</span><span class="sxs-lookup"><span data-stu-id="8256c-110">When you run the example, it rotates each .jpg image in *Sample Pictures* and saves it to *Modified*.</span></span> <span data-ttu-id="8256c-111">È possibile modificare i due percorsi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8256c-111">You can modify the two paths as necessary.</span></span>

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

<span data-ttu-id="8256c-112">Un ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> funziona come un ciclo <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8256c-112">A <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop.</span></span> <span data-ttu-id="8256c-113">Il ciclo esegue il partizionamento della raccolta di origine e pianifica il lavoro in più thread in base all'ambiente di sistema.</span><span class="sxs-lookup"><span data-stu-id="8256c-113">The loop partitions the source collection and schedules the work on multiple threads based on the system environment.</span></span> <span data-ttu-id="8256c-114">Più processori ci sono nel sistema, più velocemente viene eseguito il metodo parallelo.</span><span class="sxs-lookup"><span data-stu-id="8256c-114">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="8256c-115">Per alcune raccolte di origine può risultare più veloce un ciclo sequenziale, a seconda delle dimensioni dell'origine e del tipo di attività svolta dal ciclo.</span><span class="sxs-lookup"><span data-stu-id="8256c-115">For some source collections, a sequential loop may be faster, depending on the size of the source and the kind of work the loop performs.</span></span> <span data-ttu-id="8256c-116">Per ulteriori informazioni sulle prestazioni, vedere [potenziali trappole nel parallelismo di dati e attività](potential-pitfalls-in-data-and-task-parallelism.md).</span><span class="sxs-lookup"><span data-stu-id="8256c-116">For more information about performance, see [Potential pitfalls in data and task parallelism](potential-pitfalls-in-data-and-task-parallelism.md).</span></span>

<span data-ttu-id="8256c-117">Per altre informazioni sui cicli paralleli, vedere [procedura: scrivere un ciclo Parallel. for semplice](how-to-write-a-simple-parallel-for-loop.md).</span><span class="sxs-lookup"><span data-stu-id="8256c-117">For more information about parallel loops, see [How to: Write a simple Parallel.For loop](how-to-write-a-simple-parallel-for-loop.md).</span></span>

<span data-ttu-id="8256c-118">Per usare <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> con una raccolta non generica, è possibile usare il metodo di estensione <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> per convertire la raccolta in una generica, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8256c-118">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

<span data-ttu-id="8256c-119">È anche possibile usare Parallel LINQ (PLINQ) per parallelizzare l'elaborazione di origini dati <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="8256c-119">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="8256c-120">PLINQ consente di usare la sintassi di query dichiarativa per esprimere il comportamento di ciclo.</span><span class="sxs-lookup"><span data-stu-id="8256c-120">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="8256c-121">Per altre informazioni, vedere [Parallel LINQ (PLINQ)](introduction-to-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="8256c-121">For more information, see [Parallel LINQ (PLINQ)](introduction-to-plinq.md).</span></span>

## <a name="compile-and-run-the-code"></a><span data-ttu-id="8256c-122">Compilare ed eseguire il codice</span><span class="sxs-lookup"><span data-stu-id="8256c-122">Compile and run the code</span></span>

<span data-ttu-id="8256c-123">È possibile compilare il codice come applicazione console per .NET Framework o come applicazione console per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8256c-123">You can compile the code as a console application for .NET Framework or as a console application for .NET Core.</span></span>

<span data-ttu-id="8256c-124">In Visual Studio esistono modelli di applicazione console Visual Basic e C# per Windows Desktop e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8256c-124">In Visual Studio, there are Visual Basic and C# console application templates for Windows Desktop and .NET Core.</span></span>

<span data-ttu-id="8256c-125">Dalla riga di comando è possibile usare i comandi di interfaccia della riga di comando di .NET Core (ad esempio, `dotnet new console` o `dotnet new console -lang vb` ) oppure è possibile creare il file e usare il compilatore da riga di comando per un'applicazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8256c-125">From the command line, you can use either the .NET Core CLI commands (for example, `dotnet new console` or `dotnet new console -lang vb`), or you can create the file and use the command-line compiler for a .NET Framework application.</span></span>

<span data-ttu-id="8256c-126">Per un progetto .NET Core è necessario fare riferimento al pacchetto NuGet **System.Drawing.Common**.</span><span class="sxs-lookup"><span data-stu-id="8256c-126">For a .NET Core project, you must reference the **System.Drawing.Common** NuGet package.</span></span> <span data-ttu-id="8256c-127">In Visual Studio usare Gestione pacchetti NuGet per installare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8256c-127">In Visual Studio, use the NuGet Package Manager to install the package.</span></span> <span data-ttu-id="8256c-128">In alternativa, è possibile aggiungere un riferimento al pacchetto nel file con estensione \*.csproj o \*.vbproj:</span><span class="sxs-lookup"><span data-stu-id="8256c-128">Alternatively, you can add a reference to the package in your \*.csproj or \*.vbproj file:</span></span>

```xml
<ItemGroup>
     <PackageReference Include="System.Drawing.Common" Version="4.5.1" />
</ItemGroup>
```

<span data-ttu-id="8256c-129">Per eseguire un'applicazione console .NET Core dalla riga di comando, usare `dotnet run` dalla cartella che contiene l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8256c-129">To run a .NET Core console application from the command line, use `dotnet run` from the folder that contains your application.</span></span>

<span data-ttu-id="8256c-130">Per eseguire l'applicazione console da Visual Studio, premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="8256c-130">To run your console application from Visual Studio, press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8256c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8256c-131">See also</span></span>

- [<span data-ttu-id="8256c-132">Parallelismo dei dati</span><span class="sxs-lookup"><span data-stu-id="8256c-132">Data parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="8256c-133">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="8256c-133">Parallel programming</span></span>](index.md)
- [<span data-ttu-id="8256c-134">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="8256c-134">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
