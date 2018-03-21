---
title: Struct C# - Panoramica del linguaggio C#
description: Informazioni di base sui tipi di valori C# denominati struct
keywords: .NET, C#, struct, tipo valore
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 88a74571-f741-4a31-a2b5-1ccf165535b8
ms.openlocfilehash: fa840d80bba98889f75863db2612f196d78bd3c5
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2018
---
# <a name="structs"></a><span data-ttu-id="ea234-104">Struct</span><span class="sxs-lookup"><span data-stu-id="ea234-104">Structs</span></span>

<span data-ttu-id="ea234-105">Analogamente alle classi, i tipi ***struct*** sono strutture dati che possono contenere membri dati e membri funzione. A differenza delle classi, tuttavia, i tipi struct sono tipi valore e non richiedono l'allocazione dell'heap.</span><span class="sxs-lookup"><span data-stu-id="ea234-105">Like classes, ***structs*** are data structures that can contain data members and function members, but unlike classes, structs are value types and do not require heap allocation.</span></span> <span data-ttu-id="ea234-106">Una variabile di un tipo struct archivia direttamente i relativi dati, mentre una variabile di un tipo classe archivia un riferimento a un oggetto allocato in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="ea234-106">A variable of a struct type directly stores the data of the struct, whereas a variable of a class type stores a reference to a dynamically allocated object.</span></span> <span data-ttu-id="ea234-107">I tipi struct non supportano l'ereditarietà specificata dall'utente. Tutti i tipi struct ereditano implicitamente dal tipo <xref:System.ValueType>, che a sua volta eredita implicitamente da `object`.</span><span class="sxs-lookup"><span data-stu-id="ea234-107">Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type <xref:System.ValueType>, which in turn implicitly inherits from `object`.</span></span>

<span data-ttu-id="ea234-108">I tipi struct sono particolarmente utili per strutture dati di piccole dimensioni che hanno una semantica di valori.</span><span class="sxs-lookup"><span data-stu-id="ea234-108">Structs are particularly useful for small data structures that have value semantics.</span></span> <span data-ttu-id="ea234-109">I numeri complessi, i punti di un sistema di coordinate o le coppie chiave-valore di un dizionario sono buoni esempi di struct.</span><span class="sxs-lookup"><span data-stu-id="ea234-109">Complex numbers, points in a coordinate system, or key-value pairs in a dictionary are all good examples of structs.</span></span> <span data-ttu-id="ea234-110">L'uso dei tipi struct al posto delle classi può determinare una notevole differenza riguardo al numero di allocazioni di memoria eseguite da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ea234-110">The use of structs rather than classes for small data structures can make a large difference in the number of memory allocations an application performs.</span></span> <span data-ttu-id="ea234-111">Il programma seguente, ad esempio, crea e inizializza una matrice di 100 punti.</span><span class="sxs-lookup"><span data-stu-id="ea234-111">For example, the following program creates and initializes an array of 100 points.</span></span> <span data-ttu-id="ea234-112">Con `Point` implementato come classe, vengono create istanze di 101 oggetti separati, uno per la matrice e uno per ciascuno dei 100 elementi.</span><span class="sxs-lookup"><span data-stu-id="ea234-112">With `Point` implemented as a class, 101 separate objects are instantiated—one for the array and one each for the 100 elements.</span></span>

[!code-csharp[PointClassUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L5-L13)]

<span data-ttu-id="ea234-113">Un'alternativa consiste nel trasformare Point in un tipo struct.</span><span class="sxs-lookup"><span data-stu-id="ea234-113">An alternative is to make Point a struct.</span></span>

[!code-csharp[PointStruct](../../../samples/snippets/csharp/tour/structs/Point.cs#L3-L11)]

<span data-ttu-id="ea234-114">Viene ora creata un'istanza di un solo oggetto, quello relativo alla matrice, e le istanze di `Point` vengono memorizzate inline nella matrice.</span><span class="sxs-lookup"><span data-stu-id="ea234-114">Now, only one object is instantiated—the one for the array—and the `Point` instances are stored in-line in the array.</span></span>

<span data-ttu-id="ea234-115">Con il nuovo operatore vengono chiamati i costruttori di struct, ma questo non implica l'allocazione della memoria.</span><span class="sxs-lookup"><span data-stu-id="ea234-115">Struct constructors are invoked with the new operator, but that does not imply that memory is being allocated.</span></span> <span data-ttu-id="ea234-116">Anziché allocare dinamicamente un oggetto e restituire un riferimento a quest'ultimo, un costruttore di struct restituisce semplicemente il valore del tipo struct (in genere una posizione temporanea nello stack), che viene quindi copiato in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ea234-116">Instead of dynamically allocating an object and returning a reference to it, a struct constructor simply returns the struct value itself (typically in a temporary location on the stack), and this value is then copied as necessary.</span></span>

<span data-ttu-id="ea234-117">Con le classi, due variabili possono fare riferimento allo stesso oggetto e pertanto le operazioni su una variabile possono influire sull'oggetto a cui fa riferimento l'altra.</span><span class="sxs-lookup"><span data-stu-id="ea234-117">With classes, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable.</span></span> <span data-ttu-id="ea234-118">Con i tipi struct, ogni variabile ha una propria copia dei dati e le operazioni su una variabile non possono influire sull'altra.</span><span class="sxs-lookup"><span data-stu-id="ea234-118">With structs, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other.</span></span> <span data-ttu-id="ea234-119">Ad esempio, l'output generato dal segmento di codice seguente dipende dal fatto che l'oggetto Point sia una classe o un tipo struct.</span><span class="sxs-lookup"><span data-stu-id="ea234-119">For example, the output produced by the following code fragment depends on whether Point is a class or a struct.</span></span>

[!code-csharp[PointUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L19-L22)]

<span data-ttu-id="ea234-120">Se `Point` è una classe, l'output è 20 perché a e b fanno riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="ea234-120">If `Point` is a class, the output is 20 because a and b reference the same object.</span></span> <span data-ttu-id="ea234-121">Se Point è un tipo struct, l'output è 10 perché l'assegnazione di `a` a `b` crea una copia del valore e tale copia non è interessata dalla successiva assegnazione a `a.x`.</span><span class="sxs-lookup"><span data-stu-id="ea234-121">If Point is a struct, the output is 10 because the assignment of `a` to `b` creates a copy of the value, and this copy is unaffected by the subsequent assignment to `a.x`.</span></span>

<span data-ttu-id="ea234-122">L'esempio precedente evidenzia due delle limitazioni dei tipi struct.</span><span class="sxs-lookup"><span data-stu-id="ea234-122">The previous example highlights two of the limitations of structs.</span></span> <span data-ttu-id="ea234-123">In primo luogo, la copia di un intero tipo struct è in genere meno efficiente della copia di un riferimento all'oggetto. Di conseguenza, il passaggio dei parametri di assegnazione e valore può risultare molto più costoso con i tipi struct che con i tipi riferimento.</span><span class="sxs-lookup"><span data-stu-id="ea234-123">First, copying an entire struct is typically less efficient than copying an object reference, so assignment and value parameter passing can be more expensive with structs than with reference types.</span></span> <span data-ttu-id="ea234-124">In secondo luogo, ad eccezione dei parametri `in`, `ref` e `out`, non è possibile creare riferimenti ai tipi struct e questa condizione che ne limita l'uso in varie situazioni.</span><span class="sxs-lookup"><span data-stu-id="ea234-124">Second, except for `in`, `ref`, and `out` parameters, it is not possible to create references to structs, which rules out their usage in a number of situations.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="ea234-125">[Precedente](classes-and-objects.md)
[Successivo](arrays.md)</span><span class="sxs-lookup"><span data-stu-id="ea234-125">[Previous](classes-and-objects.md)
[Next](arrays.md)</span></span>
