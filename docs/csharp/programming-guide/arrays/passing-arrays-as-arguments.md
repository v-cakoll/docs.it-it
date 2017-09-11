---
title: Passaggio di matrici come argomenti (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5e83c0c119bc1448be76f83416098158c7f5d684
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="1f006-102">Passaggio di matrici come argomenti (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="1f006-102">Passing Arrays as Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="1f006-103">Le matrici possono essere passate come argomenti ai parametri di metodo.</span><span class="sxs-lookup"><span data-stu-id="1f006-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="1f006-104">Le matrici, infatti, sono tipi di parametri e il metodo può quindi modificare il valore degli elementi.</span><span class="sxs-lookup"><span data-stu-id="1f006-104">Because arrays are reference types, the method can change the value of the elements.</span></span>  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="1f006-105">Passaggio di matrici unidimensionali come parametri</span><span class="sxs-lookup"><span data-stu-id="1f006-105">Passing Single-Dimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="1f006-106">È possibile passare una matrice unidimensionale inizializzata a un metodo.</span><span class="sxs-lookup"><span data-stu-id="1f006-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="1f006-107">L'istruzione seguente, ad esempio, invia una matrice a un metodo di stampa.</span><span class="sxs-lookup"><span data-stu-id="1f006-107">For example, the following statement sends an array to a print method.</span></span>  
  
 <span data-ttu-id="1f006-108">[!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1f006-108">[!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]</span></span>  
  
 <span data-ttu-id="1f006-109">Nel codice seguente viene illustrata un'implementazione parziale del metodo di stampa.</span><span class="sxs-lookup"><span data-stu-id="1f006-109">The following code shows a partial implementation of the print method.</span></span>  
  
 <span data-ttu-id="1f006-110">[!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1f006-110">[!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]</span></span>  
  
 <span data-ttu-id="1f006-111">È possibile inizializzare e passare una nuova matrice in un passaggio, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1f006-111">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 <span data-ttu-id="1f006-112">[!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1f006-112">[!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f006-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="1f006-113">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="1f006-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f006-114">Description</span></span>  
 <span data-ttu-id="1f006-115">Nell'esempio seguente, una matrice di stringhe viene inizializzata e passata come argomento a un metodo `PrintArray` per le stringhe.</span><span class="sxs-lookup"><span data-stu-id="1f006-115">In the following example, an array of strings is initialized and passed as an argument to a `PrintArray` method for strings.</span></span> <span data-ttu-id="1f006-116">Nel metodo vengono visualizzati gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="1f006-116">The method displays the elements of the array.</span></span> <span data-ttu-id="1f006-117">Vengono quindi chiamati i metodi `ChangeArray` e `ChangeArrayElement` per dimostrare che l'invio di un argomento di matrice per valore non impedisce eventuali modifiche agli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="1f006-117">Next, methods `ChangeArray` and `ChangeArrayElement` are called to demonstrate that sending an array argument by value does not prevent changes to the array elements.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1f006-118">Codice</span><span class="sxs-lookup"><span data-stu-id="1f006-118">Code</span></span>  
 <span data-ttu-id="1f006-119">[!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="1f006-119">[!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]</span></span>  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="1f006-120">Passaggio di matrici multidimensionali come parametri</span><span class="sxs-lookup"><span data-stu-id="1f006-120">Passing Multidimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="1f006-121">Una matrice multidimensionale inizializzata viene passata a un metodo nello stesso modo in cui viene passata una matrice unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="1f006-121">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>  
  
 <span data-ttu-id="1f006-122">[!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="1f006-122">[!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]</span></span>  
  
 <span data-ttu-id="1f006-123">Nel codice seguente viene illustrata una dichiarazione parziale di un metodo di stampa che accetta una matrice bidimensionale come argomento.</span><span class="sxs-lookup"><span data-stu-id="1f006-123">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>  
  
 <span data-ttu-id="1f006-124">[!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="1f006-124">[!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]</span></span>  
  
 <span data-ttu-id="1f006-125">È possibile inizializzare e passare una nuova matrice in un passaggio, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1f006-125">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 <span data-ttu-id="1f006-126">[!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="1f006-126">[!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f006-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="1f006-127">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="1f006-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f006-128">Description</span></span>  
 <span data-ttu-id="1f006-129">Nell'esempio seguente, una matrice bidimensionale di Integer viene inizializzata e passata al metodo `Print2DArray`.</span><span class="sxs-lookup"><span data-stu-id="1f006-129">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="1f006-130">Nel metodo vengono visualizzati gli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="1f006-130">The method displays the elements of the array.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1f006-131">Codice</span><span class="sxs-lookup"><span data-stu-id="1f006-131">Code</span></span>  
 <span data-ttu-id="1f006-132">[!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="1f006-132">[!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f006-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f006-133">See Also</span></span>  
 <span data-ttu-id="1f006-134">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1f006-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1f006-135">[Matrici](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="1f006-135">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="1f006-136">[Matrici unidimensionali](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="1f006-136">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="1f006-137">[Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="1f006-137">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="1f006-138">Matrici irregolari</span><span class="sxs-lookup"><span data-stu-id="1f006-138">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

