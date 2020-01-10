---
title: Matrici multidimensionali - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: eb49f4386b6106328f1613b5ec70794ac26fc9b7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715042"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="b2eea-102">Matrici multidimensionali (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b2eea-102">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="b2eea-103">Le matrici possono avere più di una dimensione.</span><span class="sxs-lookup"><span data-stu-id="b2eea-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="b2eea-104">La dichiarazione seguente, ad esempio, crea una matrice bidimensionale di quattro righe e due colonne.</span><span class="sxs-lookup"><span data-stu-id="b2eea-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#11)]  
  
 <span data-ttu-id="b2eea-105">La dichiarazione seguente crea una matrice a tre dimensioni: 4, 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="b2eea-105">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#12)]  
  
## <a name="array-initialization"></a><span data-ttu-id="b2eea-106">Inizializzazione di una matrice</span><span class="sxs-lookup"><span data-stu-id="b2eea-106">Array Initialization</span></span>

 <span data-ttu-id="b2eea-107">È possibile inizializzare la matrice al momento della dichiarazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b2eea-107">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#13)]  
  
 <span data-ttu-id="b2eea-108">È possibile anche inizializzare la matrice senza specificarne il numero di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b2eea-108">You also can initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#14)]  
  
 <span data-ttu-id="b2eea-109">Se si sceglie di dichiarare una variabile di matrice senza inizializzazione, è necessario usare l'operatore `new` per assegnare una matrice alla variabile.</span><span class="sxs-lookup"><span data-stu-id="b2eea-109">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="b2eea-110">L'utilizzo di `new` è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b2eea-110">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#15)]  
  
 <span data-ttu-id="b2eea-111">Nell'esempio seguente viene assegnato un valore a un elemento specifico della matrice.</span><span class="sxs-lookup"><span data-stu-id="b2eea-111">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#16)]  
  
 <span data-ttu-id="b2eea-112">Analogamente, nell'esempio seguente viene ottenuto il valore di un elemento specifico della matrice, che viene assegnato alla variabile `elementValue`.</span><span class="sxs-lookup"><span data-stu-id="b2eea-112">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#42)]  
  
 <span data-ttu-id="b2eea-113">Nell'esempio di codice seguente, gli elementi della matrice vengono inizializzati in base ai valori predefiniti (ad eccezione delle matrici di matrici).</span><span class="sxs-lookup"><span data-stu-id="b2eea-113">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="b2eea-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2eea-114">See also</span></span>

- [<span data-ttu-id="b2eea-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b2eea-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b2eea-116">Matrici</span><span class="sxs-lookup"><span data-stu-id="b2eea-116">Arrays</span></span>](./index.md)
- [<span data-ttu-id="b2eea-117">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="b2eea-117">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="b2eea-118">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="b2eea-118">Jagged Arrays</span></span>](./jagged-arrays.md)
