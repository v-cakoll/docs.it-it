---
title: Passaggio di matrici come argomenti (Guida per programmatori C#)
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 0289297be9d7b4989cc95d2b50b92dae9ee831f7
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2018
ms.locfileid: "42911799"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="778bb-102">Passaggio di matrici come argomenti (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="778bb-102">Passing arrays as arguments (C# Programming Guide)</span></span>

<span data-ttu-id="778bb-103">Le matrici possono essere passate come argomenti ai parametri di metodo.</span><span class="sxs-lookup"><span data-stu-id="778bb-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="778bb-104">Le matrici, infatti, sono tipi di parametri e il metodo può quindi modificare il valore degli elementi.</span><span class="sxs-lookup"><span data-stu-id="778bb-104">Because arrays are reference types, the method can change the value of the elements.</span></span>

## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="778bb-105">Passaggio di matrici unidimensionali come argomenti</span><span class="sxs-lookup"><span data-stu-id="778bb-105">Passing single-dimensional arrays as arguments</span></span>

<span data-ttu-id="778bb-106">È possibile passare una matrice unidimensionale inizializzata a un metodo.</span><span class="sxs-lookup"><span data-stu-id="778bb-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="778bb-107">L'istruzione seguente, ad esempio, invia una matrice a un metodo di stampa.</span><span class="sxs-lookup"><span data-stu-id="778bb-107">For example, the following statement sends an array to a print method.</span></span>

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

<span data-ttu-id="778bb-108">Nel codice seguente viene illustrata un'implementazione parziale del metodo di stampa.</span><span class="sxs-lookup"><span data-stu-id="778bb-108">The following code shows a partial implementation of the print method.</span></span>

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

<span data-ttu-id="778bb-109">È possibile inizializzare e passare una nuova matrice in un passaggio, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="778bb-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a><span data-ttu-id="778bb-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="778bb-110">Example</span></span>

<span data-ttu-id="778bb-111">Nell'esempio seguente, una matrice di stringhe viene inizializzata e passata come argomento a un metodo `DisplayArray` per le stringhe.</span><span class="sxs-lookup"><span data-stu-id="778bb-111">In the following example, an array of strings is initialized and passed as an argument to a `DisplayArray` method for strings.</span></span> <span data-ttu-id="778bb-112">Nel metodo vengono visualizzati gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="778bb-112">The method displays the elements of the array.</span></span> <span data-ttu-id="778bb-113">Successivamente, il metodo `ChangeArray` inverte gli elementi della matrice e quindi il metodo `ChangeArrayElements` consente di modificare i primi tre elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="778bb-113">Next, the `ChangeArray` method reverses the array elements, and then the `ChangeArrayElements` method modifies the first three elements of the array.</span></span> <span data-ttu-id="778bb-114">Al termine delle restituzioni di ogni metodo, il metodo `DisplayArray` mostra che il passaggio di una matrice per valore non impedisce le modifiche agli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="778bb-114">After each method returns, the `DisplayArray` method shows that passing an array by value doesn't prevent changes to the array elements.</span></span>

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="778bb-115">Passaggio di matrici multidimensionali come argomenti</span><span class="sxs-lookup"><span data-stu-id="778bb-115">Passing multidimensional arrays as arguments</span></span>

<span data-ttu-id="778bb-116">Una matrice multidimensionale inizializzata viene passata a un metodo nello stesso modo in cui viene passata una matrice unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="778bb-116">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

<span data-ttu-id="778bb-117">Nel codice seguente viene illustrata una dichiarazione parziale di un metodo di stampa che accetta una matrice bidimensionale come argomento.</span><span class="sxs-lookup"><span data-stu-id="778bb-117">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

<span data-ttu-id="778bb-118">È possibile inizializzare e passare una nuova matrice in un passaggio, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="778bb-118">You can initialize and pass a new array in one step, as is shown in the following example:</span></span>

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a><span data-ttu-id="778bb-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="778bb-119">Example</span></span>

<span data-ttu-id="778bb-120">Nell'esempio seguente, una matrice bidimensionale di Integer viene inizializzata e passata al metodo `Print2DArray`.</span><span class="sxs-lookup"><span data-stu-id="778bb-120">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="778bb-121">Nel metodo vengono visualizzati gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="778bb-121">The method displays the elements of the array.</span></span>

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a><span data-ttu-id="778bb-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="778bb-122">See also</span></span>

[<span data-ttu-id="778bb-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="778bb-123">C# Programming Guide</span></span>](../index.md)  
[<span data-ttu-id="778bb-124">Array</span><span class="sxs-lookup"><span data-stu-id="778bb-124">Arrays</span></span>](index.md)  
[<span data-ttu-id="778bb-125">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="778bb-125">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)  
[<span data-ttu-id="778bb-126">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="778bb-126">Multidimensional Arrays</span></span>](multidimensional-arrays.md)  
[<span data-ttu-id="778bb-127">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="778bb-127">Jagged Arrays</span></span>](jagged-arrays.md)  