---
title: Matrici unidimensionali - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: bd4ab53a9cb53e5cf636601bff5ac64a10a310a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170351"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="5cf8d-102">Matrici unidimensionali (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="5cf8d-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="5cf8d-103">È possibile dichiarare una matrice unidimensionale di cinque valori integer, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5cf8d-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#4)]  
  
 <span data-ttu-id="5cf8d-104">Questa matrice contiene gli elementi da `array[0]` a `array[4]`.</span><span class="sxs-lookup"><span data-stu-id="5cf8d-104">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="5cf8d-105">L'operatore [new](../../language-reference/operators/new-operator.md) viene usato per creare la matrice e inizializzare gli elementi della matrice ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="5cf8d-105">The [new](../../language-reference/operators/new-operator.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="5cf8d-106">In questo esempio, tutti gli elementi della matrice vengono inizializzati su zero.</span><span class="sxs-lookup"><span data-stu-id="5cf8d-106">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="5cf8d-107">È possibile dichiarare una matrice che archivia elementi stringa nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="5cf8d-107">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="5cf8d-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5cf8d-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#5)]  
  
## <a name="array-initialization"></a><span data-ttu-id="5cf8d-109">Inizializzazione di una matrice</span><span class="sxs-lookup"><span data-stu-id="5cf8d-109">Array Initialization</span></span>

 <span data-ttu-id="5cf8d-110">È possibile inizializzare una matrice al momento della dichiarazione. In tal caso, l'identificatore della lunghezza non è necessario perché è già fornito dal numero di elementi nell'elenco di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="5cf8d-110">It is possible to initialize an array upon declaration, in which case, the length specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="5cf8d-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5cf8d-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#6)]  
  
 <span data-ttu-id="5cf8d-112">Una matrice di stringhe può essere inizializzata nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="5cf8d-112">A string array can be initialized in the same way.</span></span> <span data-ttu-id="5cf8d-113">Di seguito è riportata una dichiarazione di una matrice di stringhe in cui ogni elemento della matrice viene inizializzato da un nome di un giorno:</span><span class="sxs-lookup"><span data-stu-id="5cf8d-113">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  

 ```csharp
 string[] weekDays = new string[] { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
 ```
  
 <span data-ttu-id="5cf8d-114">Durante l'inizializzazione di una matrice al momento della dichiarazione, è possibile usare i collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5cf8d-114">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 [!code-csharp[csProgGuideArrays#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#8)]  
  
 <span data-ttu-id="5cf8d-115">È possibile dichiarare una variabile di matrice senza inizializzazione, ma è necessario usare l'operatore `new` quando si assegna una matrice a questa variabile.</span><span class="sxs-lookup"><span data-stu-id="5cf8d-115">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="5cf8d-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5cf8d-116">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#9)]  
  
 <span data-ttu-id="5cf8d-117">In C# 3.0 sono state introdotte le matrici tipizzate in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="5cf8d-117">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="5cf8d-118">Per altre informazioni, vedere [Matrici tipizzate in modo implicito](./implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="5cf8d-118">For more information, see [Implicitly Typed Arrays](./implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="5cf8d-119">Matrici di tipo valore e di tipo riferimento</span><span class="sxs-lookup"><span data-stu-id="5cf8d-119">Value Type and Reference Type Arrays</span></span>

 <span data-ttu-id="5cf8d-120">Considerare la dichiarazione di matrice seguente:</span><span class="sxs-lookup"><span data-stu-id="5cf8d-120">Consider the following array declaration:</span></span>  
  
 [!code-csharp[csProgGuideArrays#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#10)]  
  
 <span data-ttu-id="5cf8d-121">Il risultato di questa istruzione dipende dal fatto che `SomeType` sia un tipo valore o un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="5cf8d-121">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="5cf8d-122">Se è un tipo valore, l'istruzione crea una matrice di 10 elementi, ognuno dei quali ha il tipo `SomeType`.</span><span class="sxs-lookup"><span data-stu-id="5cf8d-122">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="5cf8d-123">Se `SomeType` è un tipo riferimento, l'istruzione crea una matrice di 10 elementi, ognuno dei quali è inizializzato su un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="5cf8d-123">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
<span data-ttu-id="5cf8d-124">Per ulteriori informazioni sui tipi di valore e sui tipi di riferimento, vedere [Tipi di valore](../../language-reference/builtin-types/value-types.md) e Tipi di [riferimento](../../language-reference/keywords/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="5cf8d-124">For more information about value types and reference types, see [Value types](../../language-reference/builtin-types/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5cf8d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cf8d-125">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="5cf8d-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5cf8d-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5cf8d-127">Matrici</span><span class="sxs-lookup"><span data-stu-id="5cf8d-127">Arrays</span></span>](./index.md)
- [<span data-ttu-id="5cf8d-128">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="5cf8d-128">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="5cf8d-129">Matrici frastagliate</span><span class="sxs-lookup"><span data-stu-id="5cf8d-129">Jagged Arrays</span></span>](./jagged-arrays.md)
