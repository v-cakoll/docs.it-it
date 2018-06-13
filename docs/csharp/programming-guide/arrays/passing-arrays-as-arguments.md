---
title: Passaggio di matrici come argomenti (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: d863cdc33a8a1a844aabbea9ba5876614e6e8dba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33315516"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="7fed1-102">Passaggio di matrici come argomenti (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7fed1-102">Passing Arrays as Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="7fed1-103">Le matrici possono essere passate come argomenti ai parametri di metodo.</span><span class="sxs-lookup"><span data-stu-id="7fed1-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="7fed1-104">Le matrici, infatti, sono tipi di parametri e il metodo può quindi modificare il valore degli elementi.</span><span class="sxs-lookup"><span data-stu-id="7fed1-104">Because arrays are reference types, the method can change the value of the elements.</span></span>  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="7fed1-105">Passaggio di matrici unidimensionali come parametri</span><span class="sxs-lookup"><span data-stu-id="7fed1-105">Passing Single-Dimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="7fed1-106">È possibile passare una matrice unidimensionale inizializzata a un metodo.</span><span class="sxs-lookup"><span data-stu-id="7fed1-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="7fed1-107">L'istruzione seguente, ad esempio, invia una matrice a un metodo di stampa.</span><span class="sxs-lookup"><span data-stu-id="7fed1-107">For example, the following statement sends an array to a print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 <span data-ttu-id="7fed1-108">Nel codice seguente viene illustrata un'implementazione parziale del metodo di stampa.</span><span class="sxs-lookup"><span data-stu-id="7fed1-108">The following code shows a partial implementation of the print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 <span data-ttu-id="7fed1-109">È possibile inizializzare e passare una nuova matrice in un passaggio, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7fed1-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="7fed1-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fed1-110">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7fed1-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fed1-111">Description</span></span>  
 <span data-ttu-id="7fed1-112">Nell'esempio seguente, una matrice di stringhe viene inizializzata e passata come argomento a un metodo `PrintArray` per le stringhe.</span><span class="sxs-lookup"><span data-stu-id="7fed1-112">In the following example, an array of strings is initialized and passed as an argument to a `PrintArray` method for strings.</span></span> <span data-ttu-id="7fed1-113">Nel metodo vengono visualizzati gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="7fed1-113">The method displays the elements of the array.</span></span> <span data-ttu-id="7fed1-114">Vengono quindi chiamati i metodi `ChangeArray` e `ChangeArrayElement` per dimostrare che l'invio di un argomento di matrice per valore non impedisce eventuali modifiche agli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="7fed1-114">Next, methods `ChangeArray` and `ChangeArrayElement` are called to demonstrate that sending an array argument by value does not prevent changes to the array elements.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7fed1-115">Codice</span><span class="sxs-lookup"><span data-stu-id="7fed1-115">Code</span></span>  
 [!code-csharp[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="7fed1-116">Passaggio di matrici multidimensionali come parametri</span><span class="sxs-lookup"><span data-stu-id="7fed1-116">Passing Multidimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="7fed1-117">Una matrice multidimensionale inizializzata viene passata a un metodo nello stesso modo in cui viene passata una matrice unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="7fed1-117">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 <span data-ttu-id="7fed1-118">Nel codice seguente viene illustrata una dichiarazione parziale di un metodo di stampa che accetta una matrice bidimensionale come argomento.</span><span class="sxs-lookup"><span data-stu-id="7fed1-118">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>  
  
 [!code-csharp[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 <span data-ttu-id="7fed1-119">È possibile inizializzare e passare una nuova matrice in un passaggio, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7fed1-119">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a><span data-ttu-id="7fed1-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fed1-120">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7fed1-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fed1-121">Description</span></span>  
 <span data-ttu-id="7fed1-122">Nell'esempio seguente, una matrice bidimensionale di Integer viene inizializzata e passata al metodo `Print2DArray`.</span><span class="sxs-lookup"><span data-stu-id="7fed1-122">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="7fed1-123">Nel metodo vengono visualizzati gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="7fed1-123">The method displays the elements of the array.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7fed1-124">Codice</span><span class="sxs-lookup"><span data-stu-id="7fed1-124">Code</span></span>  
 [!code-csharp[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7fed1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fed1-125">See Also</span></span>  
 [<span data-ttu-id="7fed1-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7fed1-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7fed1-127">Array</span><span class="sxs-lookup"><span data-stu-id="7fed1-127">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="7fed1-128">Matrici unidimensionali</span><span class="sxs-lookup"><span data-stu-id="7fed1-128">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="7fed1-129">Matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="7fed1-129">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="7fed1-130">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="7fed1-130">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
