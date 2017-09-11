---
title: Passaggio di parametri di tipo di riferimento (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], reference types
- parameters [C#], reference
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
caps.latest.revision: 14
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
ms.openlocfilehash: 3f57dc9f0de6fae6da3ec8e6e6cfdc3a21baeaea
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="passing-reference-type-parameters-c-programming-guide"></a><span data-ttu-id="c2d62-102">Passaggio di parametri di tipo di riferimento (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c2d62-102">Passing Reference-Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="c2d62-103">Una variabile di un [tipo riferimento](../../../csharp/language-reference/keywords/reference-types.md) non contiene direttamente i dati, ma solo un riferimento a essi.</span><span class="sxs-lookup"><span data-stu-id="c2d62-103">A variable of a [reference type](../../../csharp/language-reference/keywords/reference-types.md) does not contain its data directly; it contains a reference to its data.</span></span> <span data-ttu-id="c2d62-104">Quando si passa un parametro di tipo riferimento per valore, è possibile modificare i dati associati al riferimento, ad esempio il valore del membro di una classe.</span><span class="sxs-lookup"><span data-stu-id="c2d62-104">When you pass a reference-type parameter by value, it is possible to change the data pointed to by the reference, such as the value of a class member.</span></span> <span data-ttu-id="c2d62-105">Non è tuttavia possibile modificare il valore del riferimento stesso, ovvero non è possibile usare il riferimento per allocare memoria per una nuova classe e fare in modo che sia persistente anche all'esterno del blocco.</span><span class="sxs-lookup"><span data-stu-id="c2d62-105">However, you cannot change the value of the reference itself; that is, you cannot use the same reference to allocate memory for a new class and have it persist outside the block.</span></span> <span data-ttu-id="c2d62-106">In questo caso, è necessario passare il parametro usando la parola chiave [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out.md).</span><span class="sxs-lookup"><span data-stu-id="c2d62-106">To do that, pass the parameter using the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) keyword.</span></span> <span data-ttu-id="c2d62-107">Per semplicità, negli esempi seguenti viene usato `ref`.</span><span class="sxs-lookup"><span data-stu-id="c2d62-107">For simplicity, the following examples use `ref`.</span></span>  
  
## <a name="passing-reference-types-by-value"></a><span data-ttu-id="c2d62-108">Passaggio di tipi riferimento per valore</span><span class="sxs-lookup"><span data-stu-id="c2d62-108">Passing Reference Types by Value</span></span>  
 <span data-ttu-id="c2d62-109">Nell'esempio seguente viene illustrato il passaggio per valore di un parametro di tipo riferimento, `arr`, a un metodo, `Change`.</span><span class="sxs-lookup"><span data-stu-id="c2d62-109">The following example demonstrates passing a reference-type parameter, `arr`, by value, to a method, `Change`.</span></span> <span data-ttu-id="c2d62-110">Poiché il parametro è un riferimento a `arr`, è possibile modificare i valori degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="c2d62-110">Because the parameter is a reference to `arr`, it is possible to change the values of the array elements.</span></span> <span data-ttu-id="c2d62-111">Il tentativo di riassegnare il parametro a una diversa posizione in memoria, tuttavia, è efficace solo all'interno del metodo e non ha alcun effetto sulla variabile originale `arr`.</span><span class="sxs-lookup"><span data-stu-id="c2d62-111">However, the attempt to reassign the parameter to a different memory location only works inside the method and does not affect the original variable, `arr`.</span></span>  
  
 <span data-ttu-id="c2d62-112">[!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c2d62-112">[!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="c2d62-113">Nell'esempio precedente, la matrice `arr`, che rappresenta un tipo riferimento, viene passata al metodo senza il parametro `ref`.</span><span class="sxs-lookup"><span data-stu-id="c2d62-113">In the preceding example, the array, `arr`, which is a reference type, is passed to the method without the `ref` parameter.</span></span> <span data-ttu-id="c2d62-114">In questo caso, al metodo viene passata una copia del riferimento che punta a `arr`.</span><span class="sxs-lookup"><span data-stu-id="c2d62-114">In such a case, a copy of the reference, which points to `arr`, is passed to the method.</span></span> <span data-ttu-id="c2d62-115">L'output indica che il metodo ha la possibilità di modificare il contenuto di un elemento della matrice (da `1` a `888`).</span><span class="sxs-lookup"><span data-stu-id="c2d62-115">The output shows that it is possible for the method to change the contents of an array element, in this case from `1` to `888`.</span></span> <span data-ttu-id="c2d62-116">L'allocazione di una nuova porzione di memoria usando l'operatore [new](../../../csharp/language-reference/keywords/new.md) nel metodo `Change`, tuttavia, fa sì che la variabile `pArray` faccia riferimento a una nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="c2d62-116">However, allocating a new portion of memory by using the [new](../../../csharp/language-reference/keywords/new.md) operator inside the `Change` method makes the variable `pArray` reference a new array.</span></span> <span data-ttu-id="c2d62-117">In questo modo, eventuali modifiche successive non avranno effetto sulla matrice originale `arr`, creata in `Main`.</span><span class="sxs-lookup"><span data-stu-id="c2d62-117">Thus, any changes after that will not affect the original array, `arr`, which is created inside `Main`.</span></span> <span data-ttu-id="c2d62-118">In realtà, in questo esempio vengono create due matrici: una in `Main` e una nel metodo `Change`.</span><span class="sxs-lookup"><span data-stu-id="c2d62-118">In fact, two arrays are created in this example, one inside `Main` and one inside the `Change` method.</span></span>  
  
## <a name="passing-reference-types-by-reference"></a><span data-ttu-id="c2d62-119">Passaggio di tipi riferimento per riferimento</span><span class="sxs-lookup"><span data-stu-id="c2d62-119">Passing Reference Types by Reference</span></span>  
 <span data-ttu-id="c2d62-120">L'esempio seguente è identico a quello precedente, tranne per il fatto che la parola chiave `ref` viene aggiunta all'intestazione e alla chiamata del metodo.</span><span class="sxs-lookup"><span data-stu-id="c2d62-120">The following example is the same as the previous example, except that the `ref` keyword is added to the method header and call.</span></span> <span data-ttu-id="c2d62-121">Tutte le modifiche apportate nel metodo si ripercuotono sulla variabile originale nel programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="c2d62-121">Any changes that take place in the method affect the original variable in the calling program.</span></span>  
  
 <span data-ttu-id="c2d62-122">[!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c2d62-122">[!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]</span></span>  
  
 <span data-ttu-id="c2d62-123">Tutte le modifiche apportate all'interno del metodo si ripercuotono sulla variabile originale in `Main`.</span><span class="sxs-lookup"><span data-stu-id="c2d62-123">All of the changes that take place inside the method affect the original array in `Main`.</span></span> <span data-ttu-id="c2d62-124">In realtà, la matrice originale viene riallocata mediante l'operatore `new`.</span><span class="sxs-lookup"><span data-stu-id="c2d62-124">In fact, the original array is reallocated using the `new` operator.</span></span> <span data-ttu-id="c2d62-125">Dopo la chiamata al metodo `Change`, quindi, i riferimenti a `arr` puntano alla matrice a cinque elementi creata nel metodo `Change`.</span><span class="sxs-lookup"><span data-stu-id="c2d62-125">Thus, after calling the `Change` method, any reference to `arr` points to the five-element array, which is created in the `Change` method.</span></span>  
  
## <a name="swapping-two-strings"></a><span data-ttu-id="c2d62-126">Scambio di due stringhe</span><span class="sxs-lookup"><span data-stu-id="c2d62-126">Swapping Two Strings</span></span>  
 <span data-ttu-id="c2d62-127">Lo scambio di stringhe è un buon esempio per illustrare il passaggio per riferimento di parametri di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="c2d62-127">Swapping strings is a good example of passing reference-type parameters by reference.</span></span> <span data-ttu-id="c2d62-128">In questo esempio, due stringhe, `str1` e `str2`, vengono inizializzate in `Main` e passate al metodo `SwapStrings` come parametri modificati dalla parola chiave `ref`.</span><span class="sxs-lookup"><span data-stu-id="c2d62-128">In the example, two strings, `str1` and `str2`, are initialized in `Main` and passed to the `SwapStrings` method as parameters modified by the `ref` keyword.</span></span> <span data-ttu-id="c2d62-129">Le due stringhe vengono scambiate all'interno del metodo e all'interno di `Main`.</span><span class="sxs-lookup"><span data-stu-id="c2d62-129">The two strings are swapped inside the method and inside `Main` as well.</span></span>  
  
 <span data-ttu-id="c2d62-130">[!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c2d62-130">[!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]</span></span>  
  
 <span data-ttu-id="c2d62-131">In questo esempio è necessario passare i parametri per riferimento perché abbiano effetto sulle variabili del programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="c2d62-131">In this example, the parameters need to be passed by reference to affect the variables in the calling program.</span></span> <span data-ttu-id="c2d62-132">Se si rimuove la parola chiave `ref` sia dall'intestazione del metodo che dalla chiamata al metodo, nel programma chiamante non avrà luogo alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="c2d62-132">If you remove the `ref` keyword from both the method header and the method call, no changes will take place in the calling program.</span></span>  
  
 <span data-ttu-id="c2d62-133">Per altre informazioni sulle stringhe, vedere [Stringhe](../../../csharp/language-reference/keywords/string.md).</span><span class="sxs-lookup"><span data-stu-id="c2d62-133">For more information about strings, see [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d62-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2d62-134">See Also</span></span>  
 <span data-ttu-id="c2d62-135">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c2d62-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c2d62-136">[Passaggio di parametri](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="c2d62-136">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 <span data-ttu-id="c2d62-137">[Passaggio di matrici usando ref e out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md) </span><span class="sxs-lookup"><span data-stu-id="c2d62-137">[Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md) </span></span>  
 <span data-ttu-id="c2d62-138">[ref](../../../csharp/language-reference/keywords/ref.md) </span><span class="sxs-lookup"><span data-stu-id="c2d62-138">[ref](../../../csharp/language-reference/keywords/ref.md) </span></span>  
 [<span data-ttu-id="c2d62-139">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="c2d62-139">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)

