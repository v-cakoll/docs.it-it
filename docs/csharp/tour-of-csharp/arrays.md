---
title: Matrici C# - Panoramica del linguaggio C#
description: Le matrici costituiscono il tipo di raccolta di base del linguaggio C#
keywords: .NET, csharp, matrice, raccolta
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a440704c-9e88-4c75-97dd-bfe30ca0fb97
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 82362a3675c431423a99d3d728fb8dd1da58c9c7
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="arrays"></a><span data-ttu-id="54f69-104">Matrici</span><span class="sxs-lookup"><span data-stu-id="54f69-104">Arrays</span></span>

<span data-ttu-id="54f69-105">Una ***matrice*** è una struttura di dati contenente una serie di variabili accessibili tramite indici calcolati.</span><span class="sxs-lookup"><span data-stu-id="54f69-105">An ***array*** is a data structure that contains a number of variables that are accessed through computed indices.</span></span> <span data-ttu-id="54f69-106">Le variabili contenute in una matrice, chiamate anche ***elementi*** della matrice, sono tutte dello stesso tipo, definito ***tipo di elemento*** della matrice.</span><span class="sxs-lookup"><span data-stu-id="54f69-106">The variables contained in an array, also called the ***elements*** of the array, are all of the same type, and this type is called the ***element type*** of the array.</span></span>

<span data-ttu-id="54f69-107">Poiché i tipi di matrice sono tipi di riferimento, la dichiarazione di una variabile di matrice si limita a riservare spazio per un riferimento a un'istanza di matrice.</span><span class="sxs-lookup"><span data-stu-id="54f69-107">Array types are reference types, and the declaration of an array variable simply sets aside space for a reference to an array instance.</span></span> <span data-ttu-id="54f69-108">Le istanze di matrice effettive vengono create dinamicamente in fase di esecuzione tramite l'operatore new.</span><span class="sxs-lookup"><span data-stu-id="54f69-108">Actual array instances are created dynamically at runtime using the new operator.</span></span> <span data-ttu-id="54f69-109">L'uso dell'operatore new consente di specificare la ***lunghezza*** della nuova istanza di matrice, che viene fissata per l'intera durata dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="54f69-109">The new operation specifies the ***length*** of the new array instance, which is then fixed for the lifetime of the instance.</span></span> <span data-ttu-id="54f69-110">Gli indici degli elementi di una matrice sono compresi tra `0` e `Length - 1`.</span><span class="sxs-lookup"><span data-stu-id="54f69-110">The indices of the elements of an array range from `0` to `Length - 1`.</span></span> <span data-ttu-id="54f69-111">L'operatore `new` inizializza automaticamente gli elementi di una matrice sul rispettivo valore predefinito che, ad esempio, equivale a zero per tutti i tipi numerici e a `null` per tutti i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="54f69-111">The `new` operator automatically initializes the elements of an array to their default value, which, for example, is zero for all numeric types and `null` for all reference types.</span></span>

<span data-ttu-id="54f69-112">Nell'esempio seguente viene creata una matrice di elementi `int`, viene inizializzata la matrice e ne viene stampato il contenuto.</span><span class="sxs-lookup"><span data-stu-id="54f69-112">The following example creates an array of `int` elements, initializes the array, and prints out the contents of the array.</span></span>

<span data-ttu-id="54f69-113">[!code-csharp[ArraySample](../../../samples/snippets/csharp/tour/arrays/Program.cs#L3-L18)]</span><span class="sxs-lookup"><span data-stu-id="54f69-113">[!code-csharp[ArraySample](../../../samples/snippets/csharp/tour/arrays/Program.cs#L3-L18)]</span></span>

<span data-ttu-id="54f69-114">In questo esempio viene creata e usata una ***matrice unidimensionale***.</span><span class="sxs-lookup"><span data-stu-id="54f69-114">This example creates and operates on a ***single-dimensional array***.</span></span> <span data-ttu-id="54f69-115">C# supporta anche ***matrici multidimensionali***.</span><span class="sxs-lookup"><span data-stu-id="54f69-115">C# also supports ***multi-dimensional arrays***.</span></span> <span data-ttu-id="54f69-116">Il numero di dimensioni di un tipo di matrice, chiamato anche ***rango*** del tipo di matrice, è pari a uno più il numero di virgole tra parentesi quadre del tipo di matrice.</span><span class="sxs-lookup"><span data-stu-id="54f69-116">The number of dimensions of an array type, also known as the ***rank*** of the array type, is one plus the number of commas written between the square brackets of the array type.</span></span> <span data-ttu-id="54f69-117">Nell'esempio seguente vengono allocate, rispettivamente, una matrice unidimensionale, una bidimensionale e una tridimensionale.</span><span class="sxs-lookup"><span data-stu-id="54f69-117">The following example allocates a single-dimensional, a two-dimensional, and a three-dimensional array, respectively.</span></span>

<span data-ttu-id="54f69-118">[!code-csharp[ArrayRank](../../../samples/snippets/csharp/tour/arrays/Program.cs#L24-L26)]</span><span class="sxs-lookup"><span data-stu-id="54f69-118">[!code-csharp[ArrayRank](../../../samples/snippets/csharp/tour/arrays/Program.cs#L24-L26)]</span></span>

<span data-ttu-id="54f69-119">La matrice `a1` contiene 10 elementi, la matrice `a2` contiene 50 (10 × 5) elementi e la `a3` matrice contiene 100 (10 × 5 × 2) elementi.</span><span class="sxs-lookup"><span data-stu-id="54f69-119">The `a1` array contains 10 elements, the `a2` array contains 50 (10 × 5) elements, and the `a3` array contains 100 (10 × 5 × 2) elements.</span></span>
<span data-ttu-id="54f69-120">L'elemento di una matrice può essere di qualsiasi tipo, anche di tipo matrice.</span><span class="sxs-lookup"><span data-stu-id="54f69-120">The element type of an array can be any type, including an array type.</span></span> <span data-ttu-id="54f69-121">Una matrice con elementi di tipo matrice viene chiamata talvolta ***matrice di matrici***, poiché le lunghezze delle matrici elemento non devono essere tutte uguali.</span><span class="sxs-lookup"><span data-stu-id="54f69-121">An array with elements of an array type is sometimes called a ***jagged array*** because the lengths of the element arrays do not all have to be the same.</span></span> <span data-ttu-id="54f69-122">Nell'esempio seguente viene allocata una matrice di matrici di `int`:</span><span class="sxs-lookup"><span data-stu-id="54f69-122">The following example allocates an array of arrays of `int`:</span></span>

<span data-ttu-id="54f69-123">[!code-csharp[ArrayAllocation](../../../samples/snippets/csharp/tour/arrays/Program.cs#L31-L34)]</span><span class="sxs-lookup"><span data-stu-id="54f69-123">[!code-csharp[ArrayAllocation](../../../samples/snippets/csharp/tour/arrays/Program.cs#L31-L34)]</span></span>

<span data-ttu-id="54f69-124">La prima riga crea una matrice con tre elementi, ognuno di tipo `int[]` e con un valore iniziale di `null`.</span><span class="sxs-lookup"><span data-stu-id="54f69-124">The first line creates an array with three elements, each of type `int[]` and each with an initial value of `null`.</span></span> <span data-ttu-id="54f69-125">Le righe successive inizializzano quindi i tre elementi con riferimenti a singole istanze di matrice di lunghezza variabile.</span><span class="sxs-lookup"><span data-stu-id="54f69-125">The subsequent lines then initialize the three elements with references to individual array instances of varying lengths.</span></span>

<span data-ttu-id="54f69-126">L'operatore new consente di specificare i valori iniziali degli elementi di matrice usando un ***inizializzatore di matrice***, ovvero un elenco di espressioni scritte tra i delimitatori `{` e `}`.</span><span class="sxs-lookup"><span data-stu-id="54f69-126">The new operator permits the initial values of the array elements to be specified using an ***array initializer***, which is a list of expressions written between the delimiters `{` and `}`.</span></span> <span data-ttu-id="54f69-127">Nell'esempio seguente viene allocata e inizializzata una matrice `int[]` con tre elementi.</span><span class="sxs-lookup"><span data-stu-id="54f69-127">The following example allocates and initializes an `int[]` with three elements.</span></span>

<span data-ttu-id="54f69-128">[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L39-L39)]</span><span class="sxs-lookup"><span data-stu-id="54f69-128">[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L39-L39)]</span></span>

<span data-ttu-id="54f69-129">La lunghezza della matrice viene dedotta dal numero di espressioni comprese tra { e }.</span><span class="sxs-lookup"><span data-stu-id="54f69-129">Note that the length of the array is inferred from the number of expressions between { and }.</span></span> <span data-ttu-id="54f69-130">Per evitare di ridefinire il tipo di matrice, è possibile abbreviare le dichiarazioni di campo e variabile locale.</span><span class="sxs-lookup"><span data-stu-id="54f69-130">Local variable and field declarations can be shortened further such that the array type does not have to be restated.</span></span>

<span data-ttu-id="54f69-131">[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L44-L44)]</span><span class="sxs-lookup"><span data-stu-id="54f69-131">[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L44-L44)]</span></span>

<span data-ttu-id="54f69-132">Entrambi gli esempi precedenti equivalgono a quello seguente:</span><span class="sxs-lookup"><span data-stu-id="54f69-132">Both of the previous examples are equivalent to the following:</span></span>

<span data-ttu-id="54f69-133">[!code-csharp[ArrayAssignment](../../../samples/snippets/csharp/tour/arrays/Program.cs#L49-L53)]</span><span class="sxs-lookup"><span data-stu-id="54f69-133">[!code-csharp[ArrayAssignment](../../../samples/snippets/csharp/tour/arrays/Program.cs#L49-L53)]</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="54f69-134">[Precedente](structs.md)
[Successivo](interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="54f69-134">[Previous](structs.md)
[Next](interfaces.md)</span></span>

