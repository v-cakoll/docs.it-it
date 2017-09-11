---
title: 'Procedura: incrementare e decrementare i puntatori (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: 20
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
ms.openlocfilehash: b474249ed9f7778e44981b292d51f29f46bc420d
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="636db-102">Procedura: incrementare e decrementare i puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="636db-102">How to: Increment and Decrement Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="636db-103">Gli operatori di incremento e decremento `++` e `--` consentono di modificare la posizione del puntatore in base a [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) per un puntatore di tipo pointer-type*.</span><span class="sxs-lookup"><span data-stu-id="636db-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) for a pointer of type pointer-type*.</span></span> <span data-ttu-id="636db-104">Il formato delle espressioni di incremento e decremento è il seguente:</span><span class="sxs-lookup"><span data-stu-id="636db-104">The increment and decrement expressions take the following form:</span></span>  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="636db-105">È possibile applicare gli operatori di incremento e decremento ai puntatori di qualsiasi tipo, ad eccezione del tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="636db-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="636db-106">Quando si applica l'operatore di incremento a un puntatore di tipo `pointer-type`, si aggiunge [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) all'indirizzo contenuto nella variabile del puntatore.</span><span class="sxs-lookup"><span data-stu-id="636db-106">The effect of applying the increment operator to a pointer of the type `pointer-type` is to add [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="636db-107">Quando si applica l'operatore di decremento a un puntatore di tipo `pointer-type`, si sottrae `sizeof` (`pointer-type`) dall'indirizzo contenuto nella variabile del puntatore.</span><span class="sxs-lookup"><span data-stu-id="636db-107">The effect of applying the decrement operator to a pointer of the type `pointer-type` is to subtract `sizeof` (`pointer-type`) from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="636db-108">Quando l'operazione causa un overflow del dominio del puntatore, non vengono generate eccezioni e il risultato dipende dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="636db-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="636db-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="636db-109">Example</span></span>  
 <span data-ttu-id="636db-110">Questo esempio mostra come passare da un elemento di una matrice all'altro incrementando il puntatore della dimensione di `int`.</span><span class="sxs-lookup"><span data-stu-id="636db-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="636db-111">A ogni passaggio vengono visualizzati l'indirizzo e il contenuto dell'elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="636db-111">With each step, you display the address and the content of the array element.</span></span>  
  
 <span data-ttu-id="636db-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="636db-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]</span></span>  
  
 <span data-ttu-id="636db-113">[!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="636db-113">[!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]</span></span>  
  
 <span data-ttu-id="636db-114">**Valore:0 @ Indirizzo:12860272**</span><span class="sxs-lookup"><span data-stu-id="636db-114">**Value:0 @ Address:12860272**</span></span>  
<span data-ttu-id="636db-115">**Valore:1 @ Indirizzo:12860276**</span><span class="sxs-lookup"><span data-stu-id="636db-115">**Value:1 @ Address:12860276**</span></span>  
<span data-ttu-id="636db-116">**Valore:2 @ Indirizzo:12860280**</span><span class="sxs-lookup"><span data-stu-id="636db-116">**Value:2 @ Address:12860280**</span></span>  
<span data-ttu-id="636db-117">**Valore:3 @ Indirizzo:12860284**</span><span class="sxs-lookup"><span data-stu-id="636db-117">**Value:3 @ Address:12860284**</span></span>  
<span data-ttu-id="636db-118">**Valore:4 @ Indirizzo:12860288**</span><span class="sxs-lookup"><span data-stu-id="636db-118">**Value:4 @ Address:12860288**</span></span>   
## <a name="see-also"></a><span data-ttu-id="636db-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="636db-119">See Also</span></span>  
 <span data-ttu-id="636db-120">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="636db-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="636db-121">[Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="636db-121">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="636db-122">[Operatori di C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="636db-122">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="636db-123">[Modifica dei puntatori](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span><span class="sxs-lookup"><span data-stu-id="636db-123">[Manipulating Pointers](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span></span>  
 <span data-ttu-id="636db-124">[Tipi di puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="636db-124">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="636db-125">[Tipi](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="636db-125">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="636db-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="636db-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="636db-127">[Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="636db-127">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="636db-128">stackalloc</span><span class="sxs-lookup"><span data-stu-id="636db-128">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

