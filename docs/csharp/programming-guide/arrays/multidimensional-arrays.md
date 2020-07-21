---
title: Matrici multidimensionali - Guida per programmatori C#
description: Le matrici in C# possono avere più di una dimensione. In questa dichiarazione di esempio viene creata una matrice bidimensionale di quattro righe e due colonne.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: a2f204c0866672b317569fbc620aa8af60829ffd
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475008"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="e319e-104">Matrici multidimensionali (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e319e-104">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="e319e-105">Le matrici possono avere più di una dimensione.</span><span class="sxs-lookup"><span data-stu-id="e319e-105">Arrays can have more than one dimension.</span></span> <span data-ttu-id="e319e-106">La dichiarazione seguente, ad esempio, crea una matrice bidimensionale di quattro righe e due colonne.</span><span class="sxs-lookup"><span data-stu-id="e319e-106">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#11)]  
  
 <span data-ttu-id="e319e-107">La dichiarazione seguente crea una matrice a tre dimensioni: 4, 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="e319e-107">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#12)]  
  
## <a name="array-initialization"></a><span data-ttu-id="e319e-108">Inizializzazione di una matrice</span><span class="sxs-lookup"><span data-stu-id="e319e-108">Array Initialization</span></span>

 <span data-ttu-id="e319e-109">È possibile inizializzare la matrice al momento della dichiarazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e319e-109">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#13)]  
  
 <span data-ttu-id="e319e-110">È anche possibile inizializzare la matrice senza specificare il rango.</span><span class="sxs-lookup"><span data-stu-id="e319e-110">You can also initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#14)]  
  
 <span data-ttu-id="e319e-111">Se si sceglie di dichiarare una variabile di matrice senza inizializzazione, è necessario usare l'operatore `new` per assegnare una matrice alla variabile.</span><span class="sxs-lookup"><span data-stu-id="e319e-111">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="e319e-112">L'utilizzo di `new` è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e319e-112">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#15)]  
  
 <span data-ttu-id="e319e-113">Nell'esempio seguente viene assegnato un valore a un elemento specifico della matrice.</span><span class="sxs-lookup"><span data-stu-id="e319e-113">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#16)]  
  
 <span data-ttu-id="e319e-114">Analogamente, nell'esempio seguente viene ottenuto il valore di un elemento specifico della matrice, che viene assegnato alla variabile `elementValue`.</span><span class="sxs-lookup"><span data-stu-id="e319e-114">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#42)]  
  
 <span data-ttu-id="e319e-115">Nell'esempio di codice seguente, gli elementi della matrice vengono inizializzati in base ai valori predefiniti (ad eccezione delle matrici di matrici).</span><span class="sxs-lookup"><span data-stu-id="e319e-115">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="e319e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e319e-116">See also</span></span>

- [<span data-ttu-id="e319e-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e319e-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e319e-118">Matrici</span><span class="sxs-lookup"><span data-stu-id="e319e-118">Arrays</span></span>](./index.md)
- [<span data-ttu-id="e319e-119">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="e319e-119">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="e319e-120">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="e319e-120">Jagged Arrays</span></span>](./jagged-arrays.md)
