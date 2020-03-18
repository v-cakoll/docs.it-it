---
title: Passaggio di matrici come argomenti - Guida per programmatori C#
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 2e53008910a9062ada25680eb4b8e54a225fd226
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705691"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="eb1fd-102">Passaggio di matrici come argomenti (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="eb1fd-102">Passing arrays as arguments (C# Programming Guide)</span></span>

<span data-ttu-id="eb1fd-103">Le matrici possono essere passate come argomenti ai parametri di metodo.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="eb1fd-104">Le matrici, infatti, sono tipi di parametri e il metodo può quindi modificare il valore degli elementi.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-104">Because arrays are reference types, the method can change the value of the elements.</span></span>

## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="eb1fd-105">Passaggio di matrici unidimensionali come argomenti</span><span class="sxs-lookup"><span data-stu-id="eb1fd-105">Passing single-dimensional arrays as arguments</span></span>

<span data-ttu-id="eb1fd-106">È possibile passare una matrice unidimensionale inizializzata a un metodo.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="eb1fd-107">L'istruzione seguente, ad esempio, invia una matrice a un metodo di stampa.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-107">For example, the following statement sends an array to a print method.</span></span>

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

<span data-ttu-id="eb1fd-108">Nel codice seguente viene illustrata un'implementazione parziale del metodo di stampa.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-108">The following code shows a partial implementation of the print method.</span></span>

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

<span data-ttu-id="eb1fd-109">È possibile inizializzare e passare una nuova matrice in un passaggio, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a><span data-ttu-id="eb1fd-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="eb1fd-110">Example</span></span>

<span data-ttu-id="eb1fd-111">Nell'esempio seguente, una matrice di stringhe viene inizializzata e passata come argomento a un metodo `DisplayArray` per le stringhe.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-111">In the following example, an array of strings is initialized and passed as an argument to a `DisplayArray` method for strings.</span></span> <span data-ttu-id="eb1fd-112">Nel metodo vengono visualizzati gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-112">The method displays the elements of the array.</span></span> <span data-ttu-id="eb1fd-113">Successivamente, il metodo `ChangeArray` inverte gli elementi della matrice e quindi il metodo `ChangeArrayElements` consente di modificare i primi tre elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-113">Next, the `ChangeArray` method reverses the array elements, and then the `ChangeArrayElements` method modifies the first three elements of the array.</span></span> <span data-ttu-id="eb1fd-114">Al termine delle restituzioni di ogni metodo, il metodo `DisplayArray` mostra che il passaggio di una matrice per valore non impedisce le modifiche agli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-114">After each method returns, the `DisplayArray` method shows that passing an array by value doesn't prevent changes to the array elements.</span></span>

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="eb1fd-115">Passaggio di matrici multidimensionali come argomenti</span><span class="sxs-lookup"><span data-stu-id="eb1fd-115">Passing multidimensional arrays as arguments</span></span>

<span data-ttu-id="eb1fd-116">Una matrice multidimensionale inizializzata viene passata a un metodo nello stesso modo in cui viene passata una matrice unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-116">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

<span data-ttu-id="eb1fd-117">Nel codice seguente viene illustrata una dichiarazione parziale di un metodo di stampa che accetta una matrice bidimensionale come argomento.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-117">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

<span data-ttu-id="eb1fd-118">È possibile inizializzare e passare una nuova matrice in un passaggio, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="eb1fd-118">You can initialize and pass a new array in one step, as is shown in the following example:</span></span>

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a><span data-ttu-id="eb1fd-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="eb1fd-119">Example</span></span>

<span data-ttu-id="eb1fd-120">Nell'esempio seguente, una matrice bidimensionale di Integer viene inizializzata e passata al metodo `Print2DArray`.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-120">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="eb1fd-121">Nel metodo vengono visualizzati gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="eb1fd-121">The method displays the elements of the array.</span></span>

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a><span data-ttu-id="eb1fd-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb1fd-122">See also</span></span>

- [<span data-ttu-id="eb1fd-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="eb1fd-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="eb1fd-124">Matrici</span><span class="sxs-lookup"><span data-stu-id="eb1fd-124">Arrays</span></span>](index.md)
- [<span data-ttu-id="eb1fd-125">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="eb1fd-125">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="eb1fd-126">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="eb1fd-126">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="eb1fd-127">Matrici frastagliate</span><span class="sxs-lookup"><span data-stu-id="eb1fd-127">Jagged Arrays</span></span>](jagged-arrays.md)
