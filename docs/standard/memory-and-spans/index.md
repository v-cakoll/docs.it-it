---
title: Memoria e intervalli
ms.date: 10/03/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Memory<T>
- Span<T>
- buffers"
- pipeline processing
ms.openlocfilehash: c60c08d27c0e41228a15e8acdf01a9af28a23762
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201960"
---
# <a name="memory--and-span-related-types"></a><span data-ttu-id="ed221-102">Tipi correlati alla memoria e agli intervalli</span><span class="sxs-lookup"><span data-stu-id="ed221-102">Memory- and span-related types</span></span>

<span data-ttu-id="ed221-103">A partire da .NET Core 2,1, .NET include una serie di tipi correlati che rappresentano un'area contigua fortemente tipizzata della memoria arbitraria.</span><span class="sxs-lookup"><span data-stu-id="ed221-103">Starting with .NET Core 2.1, .NET includes a number of interrelated types that represent a contiguous, strongly typed region of arbitrary memory.</span></span> <span data-ttu-id="ed221-104">Tra queste sono incluse:</span><span class="sxs-lookup"><span data-stu-id="ed221-104">These include:</span></span>

- <span data-ttu-id="ed221-105"><xref:System.Span%601?displayProperty=nameWithType>, un tipo usato per accedere a un'area contigua di memoria.</span><span class="sxs-lookup"><span data-stu-id="ed221-105"><xref:System.Span%601?displayProperty=nameWithType>, a type that is used to access a contiguous region of memory.</span></span> <span data-ttu-id="ed221-106">Un'istanza di <xref:System.Span%601> può essere supportata da una matrice di tipo `T`, una classe <xref:System.String>, un buffer allocato con [stackalloc](../../csharp/language-reference/operators/stackalloc.md) o un puntatore alla memoria non gestita.</span><span class="sxs-lookup"><span data-stu-id="ed221-106">A <xref:System.Span%601> instance can be backed by an array of type `T`, a <xref:System.String>, a buffer allocated with [stackalloc](../../csharp/language-reference/operators/stackalloc.md), or a pointer to unmanaged memory.</span></span> <span data-ttu-id="ed221-107">Poiché deve essere allocato nello stack, presenta alcune restrizioni.</span><span class="sxs-lookup"><span data-stu-id="ed221-107">Because it has to be allocated on the stack, it has a number of restrictions.</span></span> <span data-ttu-id="ed221-108">Un campo in una classe, ad esempio, non può essere di tipo <xref:System.Span%601> e l'intervallo non può essere usato nelle operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="ed221-108">For example, a field in a class cannot be of type <xref:System.Span%601>, nor can span be used in asynchronous operations.</span></span>

- <span data-ttu-id="ed221-109"><xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, una versione non modificabile della struttura <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="ed221-109"><xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, an immutable version of the <xref:System.Span%601> structure.</span></span>

- <span data-ttu-id="ed221-110"><xref:System.Memory%601?displayProperty=nameWithType>, un'area contigua della memoria allocata nell'heap gestito invece che nello stack.</span><span class="sxs-lookup"><span data-stu-id="ed221-110"><xref:System.Memory%601?displayProperty=nameWithType>, a contiguous region of memory that is allocated on the managed heap rather than the stack.</span></span> <span data-ttu-id="ed221-111">Un'istanza di <xref:System.Memory%601> può essere supportata da una matrice di tipo `T` o da una classe <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ed221-111">A <xref:System.Memory%601> instance can be backed by an array of type `T` or a <xref:System.String>.</span></span> <span data-ttu-id="ed221-112">Poiché può essere archiviato nell'heap gestito, <xref:System.Memory%601> non presenta nessuna delle limitazioni di <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="ed221-112">Because it can be stored on the managed heap, <xref:System.Memory%601> has none of the limitations of <xref:System.Span%601>.</span></span>

- <span data-ttu-id="ed221-113"><xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>, una versione non modificabile della struttura <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="ed221-113"><xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>, an immutable version of the <xref:System.Memory%601> structure.</span></span>

- <span data-ttu-id="ed221-114"><xref:System.Buffers.MemoryPool%601?displayProperty=nameWithType>, che alloca i blocchi di memoria fortemente tipizzati da un pool di memoria a un proprietario.</span><span class="sxs-lookup"><span data-stu-id="ed221-114"><xref:System.Buffers.MemoryPool%601?displayProperty=nameWithType>, which allocates strongly typed blocks of memory from a memory pool to an owner.</span></span> <span data-ttu-id="ed221-115">Le istanze di <xref:System.Buffers.IMemoryOwner%601> possono essere noleggiate dal pool chiamando <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType> e restituite al pool chiamando <xref:System.Buffers.MemoryPool%601.Dispose?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ed221-115"><xref:System.Buffers.IMemoryOwner%601> instances can be rented from the pool by calling <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType> and released back to the pool by calling <xref:System.Buffers.MemoryPool%601.Dispose?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="ed221-116"><xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>, che rappresenta il proprietario di un blocco di memoria e controlla la gestione della durata.</span><span class="sxs-lookup"><span data-stu-id="ed221-116"><xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>, which represents the owner of a block of memory and controls its lifetime management.</span></span>

- <span data-ttu-id="ed221-117"><xref:System.Buffers.MemoryManager%601>, una classe di base astratta che può essere usata per sostituire l'implementazione di <xref:System.Memory%601> in modo che <xref:System.Memory%601> possa essere supportato da altri tipi, ad esempio handle sicuri.</span><span class="sxs-lookup"><span data-stu-id="ed221-117"><xref:System.Buffers.MemoryManager%601>, an abstract base class that can be used to replace the implementation of <xref:System.Memory%601> so that <xref:System.Memory%601> can be backed by additional types, such as safe handles.</span></span> <span data-ttu-id="ed221-118"><xref:System.Buffers.MemoryManager%601> è destinato a scenari avanzati.</span><span class="sxs-lookup"><span data-stu-id="ed221-118"><xref:System.Buffers.MemoryManager%601> is intended for advanced scenarios.</span></span>

- <span data-ttu-id="ed221-119"><xref:System.ArraySegment%601>, un wrapper per un determinato numero di elementi di matrice a partire da un determinato indice.</span><span class="sxs-lookup"><span data-stu-id="ed221-119"><xref:System.ArraySegment%601>, a wrapper for a particular number of array elements starting at a particular index.</span></span>

- <span data-ttu-id="ed221-120"><xref:System.MemoryExtensions?displayProperty=nameWithType>, una raccolta di metodi di estensione per convertire stringhe, matrici e segmenti di matrici in blocchi <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="ed221-120"><xref:System.MemoryExtensions?displayProperty=nameWithType>, a collection of extension methods for converting strings, arrays, and array segments to <xref:System.Memory%601> blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="ed221-121">Per i framework precedenti, <xref:System.Span%601> e <xref:System.Memory%601> sono disponibili nel [pacchetto NuGet System.Memory](https://www.nuget.org/packages/System.Memory/).</span><span class="sxs-lookup"><span data-stu-id="ed221-121">For earlier frameworks, <xref:System.Span%601> and <xref:System.Memory%601> are available in the [System.Memory NuGet package](https://www.nuget.org/packages/System.Memory/).</span></span>

<span data-ttu-id="ed221-122">Per altre informazioni, vedere lo spazio dei nomi <xref:System.Buffers?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ed221-122">For more information, see the <xref:System.Buffers?displayProperty=nameWithType> namespace.</span></span>

## <a name="working-with-memory-and-span"></a><span data-ttu-id="ed221-123">Uso di memoria e intervalli</span><span class="sxs-lookup"><span data-stu-id="ed221-123">Working with memory and span</span></span>

<span data-ttu-id="ed221-124">Poiché i tipi correlati alla memoria e agli intervalli vengono in genere usati per archiviare i dati in una pipeline di elaborazione, è importante che gli sviluppatori seguano una serie di procedure consigliate quando usano <xref:System.Span%601>, <xref:System.Memory%601> e i tipi correlati.</span><span class="sxs-lookup"><span data-stu-id="ed221-124">Because the memory- and span-related types are typically used to store data in a processing pipeline, it is important that developers follow a set of best practices when using <xref:System.Span%601>, <xref:System.Memory%601>, and related types.</span></span> <span data-ttu-id="ed221-125">Queste procedure consigliate sono documentate nelle [ \<T> \<T> linee guida sull'utilizzo di memoria e intervallo](memory-t-usage-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="ed221-125">These best practices are documented in [Memory\<T> and Span\<T> usage guidelines](memory-t-usage-guidelines.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ed221-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed221-126">See also</span></span>

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
- <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>
- <xref:System.Buffers?displayProperty=nameWithType>
