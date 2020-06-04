---
title: Matrici unidimensionali - Guida per programmatori C#
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: e189253eedc21fa2d51e16407f04b034610bb57b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410244"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="388d1-102">Matrici unidimensionali (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="388d1-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="388d1-103">Si crea una matrice unidimensionale usando l'operatore [New](../../language-reference/operators/new-operator.md) che specifica il tipo di elemento della matrice e il numero di elementi.</span><span class="sxs-lookup"><span data-stu-id="388d1-103">You create a single-dimensional array using the [new](../../language-reference/operators/new-operator.md) operator specifying the array element type and the number of elements.</span></span> <span data-ttu-id="388d1-104">Nell'esempio seguente viene dichiarata una matrice di cinque Integer:</span><span class="sxs-lookup"><span data-stu-id="388d1-104">The following example declares an array of five integers:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

<span data-ttu-id="388d1-105">Questa matrice contiene gli elementi da `array[0]` a `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="388d1-105">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="388d1-106">Gli elementi della matrice vengono inizializzati sul valore predefinito del tipo di elemento, `0` per i numeri interi.</span><span class="sxs-lookup"><span data-stu-id="388d1-106">The elements of the array are initialized to the default value of the element type, `0` for integers.</span></span>

<span data-ttu-id="388d1-107">Le matrici possono archiviare qualsiasi tipo di elemento specificato, ad esempio l'esempio seguente che dichiara una matrice di stringhe:</span><span class="sxs-lookup"><span data-stu-id="388d1-107">Arrays can store any element type you specify, such as the following example that declares an array of strings:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a><span data-ttu-id="388d1-108">Inizializzazione di una matrice</span><span class="sxs-lookup"><span data-stu-id="388d1-108">Array Initialization</span></span>

<span data-ttu-id="388d1-109">È possibile inizializzare gli elementi di una matrice quando si dichiara la matrice.</span><span class="sxs-lookup"><span data-stu-id="388d1-109">You can initialize the elements of an array when you declare the array.</span></span> <span data-ttu-id="388d1-110">L'identificatore di lunghezza non è necessario perché è dedotto dal numero di elementi nell'elenco di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="388d1-110">The length specifier isn't needed because it's inferred by the number of elements in the initialization list.</span></span> <span data-ttu-id="388d1-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="388d1-111">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

<span data-ttu-id="388d1-112">Nel codice seguente viene illustrata una dichiarazione di una matrice di stringhe in cui ogni elemento della matrice viene inizializzato in base al nome di un giorno:</span><span class="sxs-lookup"><span data-stu-id="388d1-112">The following code shows a declaration of a string array where each array element is initialized by a name of a day:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
<span data-ttu-id="388d1-113">È possibile evitare l' `new` espressione e il tipo di matrice quando si Inizializza una matrice al momento della dichiarazione, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="388d1-113">You can avoid the `new` expression and the array type when you initialize an array upon declaration, as shown in the following code.</span></span> <span data-ttu-id="388d1-114">Si tratta di una [matrice tipizzata in modo implicito](implicitly-typed-arrays.md):</span><span class="sxs-lookup"><span data-stu-id="388d1-114">This is called an [implicitly typed array](implicitly-typed-arrays.md):</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

<span data-ttu-id="388d1-115">È possibile dichiarare una variabile di matrice senza crearla, ma è necessario usare l' `new` operatore quando si assegna una nuova matrice a questa variabile.</span><span class="sxs-lookup"><span data-stu-id="388d1-115">You can declare an array variable without creating it, but you must use the `new` operator when you assign a new array to this variable.</span></span> <span data-ttu-id="388d1-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="388d1-116">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="388d1-117">Matrici di tipo valore e di tipo riferimento</span><span class="sxs-lookup"><span data-stu-id="388d1-117">Value Type and Reference Type Arrays</span></span>

<span data-ttu-id="388d1-118">Considerare la dichiarazione di matrice seguente:</span><span class="sxs-lookup"><span data-stu-id="388d1-118">Consider the following array declaration:</span></span>  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

<span data-ttu-id="388d1-119">Il risultato di questa istruzione dipende dal fatto che `SomeType` sia un tipo valore o un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="388d1-119">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="388d1-120">Se è un tipo di valore, l'istruzione crea una matrice di 10 elementi, ognuno dei quali ha il tipo `SomeType` .</span><span class="sxs-lookup"><span data-stu-id="388d1-120">If it's a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="388d1-121">Se `SomeType` è un tipo riferimento, l'istruzione crea una matrice di 10 elementi, ognuno dei quali è inizializzato su un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="388d1-121">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span> <span data-ttu-id="388d1-122">In entrambe le istanze gli elementi vengono inizializzati sul valore predefinito per il tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="388d1-122">In both instances, the elements are initialized to the default value for the element type.</span></span> <span data-ttu-id="388d1-123">Per ulteriori informazioni sui tipi di valore e sui tipi di riferimento, vedere [tipi di valore](../../language-reference/builtin-types/value-types.md) e [tipi di riferimento](../../language-reference/keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="388d1-123">For more information about value types and reference types, see [Value types](../../language-reference/builtin-types/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="388d1-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="388d1-124">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="388d1-125">Matrici</span><span class="sxs-lookup"><span data-stu-id="388d1-125">Arrays</span></span>](./index.md)
- [<span data-ttu-id="388d1-126">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="388d1-126">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="388d1-127">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="388d1-127">Jagged Arrays</span></span>](./jagged-arrays.md)
