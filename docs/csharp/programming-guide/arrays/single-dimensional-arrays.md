---
title: Matrici unidimensionali - Guida per programmatori C#
description: Creare una matrice unidimensionale in C# usando l'operatore New che specifica il tipo di elemento della matrice e il numero di elementi.
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: ada01262d57cbfebc8bfa1a5fee0639a10db5a4b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474592"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="99077-103">Matrici unidimensionali (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="99077-103">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="99077-104">Si crea una matrice unidimensionale usando l'operatore [New](../../language-reference/operators/new-operator.md) che specifica il tipo di elemento della matrice e il numero di elementi.</span><span class="sxs-lookup"><span data-stu-id="99077-104">You create a single-dimensional array using the [new](../../language-reference/operators/new-operator.md) operator specifying the array element type and the number of elements.</span></span> <span data-ttu-id="99077-105">Nell'esempio seguente viene dichiarata una matrice di cinque Integer:</span><span class="sxs-lookup"><span data-stu-id="99077-105">The following example declares an array of five integers:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

<span data-ttu-id="99077-106">Questa matrice contiene gli elementi da `array[0]` a `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="99077-106">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="99077-107">Gli elementi della matrice vengono inizializzati sul valore predefinito del tipo di elemento, `0` per i numeri interi.</span><span class="sxs-lookup"><span data-stu-id="99077-107">The elements of the array are initialized to the default value of the element type, `0` for integers.</span></span>

<span data-ttu-id="99077-108">Le matrici possono archiviare qualsiasi tipo di elemento specificato, ad esempio l'esempio seguente che dichiara una matrice di stringhe:</span><span class="sxs-lookup"><span data-stu-id="99077-108">Arrays can store any element type you specify, such as the following example that declares an array of strings:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a><span data-ttu-id="99077-109">Inizializzazione di una matrice</span><span class="sxs-lookup"><span data-stu-id="99077-109">Array Initialization</span></span>

<span data-ttu-id="99077-110">È possibile inizializzare gli elementi di una matrice quando si dichiara la matrice.</span><span class="sxs-lookup"><span data-stu-id="99077-110">You can initialize the elements of an array when you declare the array.</span></span> <span data-ttu-id="99077-111">L'identificatore di lunghezza non è necessario perché è dedotto dal numero di elementi nell'elenco di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="99077-111">The length specifier isn't needed because it's inferred by the number of elements in the initialization list.</span></span> <span data-ttu-id="99077-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="99077-112">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

<span data-ttu-id="99077-113">Nel codice seguente viene illustrata una dichiarazione di una matrice di stringhe in cui ogni elemento della matrice viene inizializzato in base al nome di un giorno:</span><span class="sxs-lookup"><span data-stu-id="99077-113">The following code shows a declaration of a string array where each array element is initialized by a name of a day:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
<span data-ttu-id="99077-114">È possibile evitare l' `new` espressione e il tipo di matrice quando si Inizializza una matrice al momento della dichiarazione, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="99077-114">You can avoid the `new` expression and the array type when you initialize an array upon declaration, as shown in the following code.</span></span> <span data-ttu-id="99077-115">Si tratta di una [matrice tipizzata in modo implicito](implicitly-typed-arrays.md):</span><span class="sxs-lookup"><span data-stu-id="99077-115">This is called an [implicitly typed array](implicitly-typed-arrays.md):</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

<span data-ttu-id="99077-116">È possibile dichiarare una variabile di matrice senza crearla, ma è necessario usare l' `new` operatore quando si assegna una nuova matrice a questa variabile.</span><span class="sxs-lookup"><span data-stu-id="99077-116">You can declare an array variable without creating it, but you must use the `new` operator when you assign a new array to this variable.</span></span> <span data-ttu-id="99077-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="99077-117">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="99077-118">Matrici di tipo valore e di tipo riferimento</span><span class="sxs-lookup"><span data-stu-id="99077-118">Value Type and Reference Type Arrays</span></span>

<span data-ttu-id="99077-119">Considerare la dichiarazione di matrice seguente:</span><span class="sxs-lookup"><span data-stu-id="99077-119">Consider the following array declaration:</span></span>  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

<span data-ttu-id="99077-120">Il risultato di questa istruzione dipende dal fatto che `SomeType` sia un tipo valore o un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="99077-120">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="99077-121">Se è un tipo di valore, l'istruzione crea una matrice di 10 elementi, ognuno dei quali ha il tipo `SomeType` .</span><span class="sxs-lookup"><span data-stu-id="99077-121">If it's a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="99077-122">Se `SomeType` è un tipo riferimento, l'istruzione crea una matrice di 10 elementi, ognuno dei quali è inizializzato su un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="99077-122">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span> <span data-ttu-id="99077-123">In entrambe le istanze gli elementi vengono inizializzati sul valore predefinito per il tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="99077-123">In both instances, the elements are initialized to the default value for the element type.</span></span> <span data-ttu-id="99077-124">Per ulteriori informazioni sui tipi di valore e sui tipi di riferimento, vedere [tipi di valore](../../language-reference/builtin-types/value-types.md) e [tipi di riferimento](../../language-reference/keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="99077-124">For more information about value types and reference types, see [Value types](../../language-reference/builtin-types/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99077-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99077-125">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="99077-126">Matrici</span><span class="sxs-lookup"><span data-stu-id="99077-126">Arrays</span></span>](./index.md)
- [<span data-ttu-id="99077-127">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="99077-127">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="99077-128">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="99077-128">Jagged Arrays</span></span>](./jagged-arrays.md)
