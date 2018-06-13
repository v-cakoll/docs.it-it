---
title: 'Procedura: incrementare e decrementare i puntatori (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: e1c3ac12a126450781d0ce78e788f39c740b5279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324285"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="f4c9d-102">Procedura: incrementare e decrementare i puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f4c9d-102">How to: Increment and Decrement Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="f4c9d-103">Gli operatori di incremento e decremento `++` e `--` consentono di modificare la posizione del puntatore in base a [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) per un puntatore di tipo pointer-type\*.</span><span class="sxs-lookup"><span data-stu-id="f4c9d-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) for a pointer of type pointer-type\*.</span></span> <span data-ttu-id="f4c9d-104">Il formato delle espressioni di incremento e decremento è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f4c9d-104">The increment and decrement expressions take the following form:</span></span>  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="f4c9d-105">È possibile applicare gli operatori di incremento e decremento ai puntatori di qualsiasi tipo, ad eccezione del tipo `void*`.</span><span class="sxs-lookup"><span data-stu-id="f4c9d-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="f4c9d-106">Quando si applica l'operatore di incremento a un puntatore di tipo `pointer-type`, si aggiunge [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) all'indirizzo contenuto nella variabile del puntatore.</span><span class="sxs-lookup"><span data-stu-id="f4c9d-106">The effect of applying the increment operator to a pointer of the type `pointer-type` is to add [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="f4c9d-107">Quando si applica l'operatore di decremento a un puntatore di tipo `pointer-type`, si sottrae `sizeof` (`pointer-type`) dall'indirizzo contenuto nella variabile del puntatore.</span><span class="sxs-lookup"><span data-stu-id="f4c9d-107">The effect of applying the decrement operator to a pointer of the type `pointer-type` is to subtract `sizeof` (`pointer-type`) from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="f4c9d-108">Quando l'operazione causa un overflow del dominio del puntatore, non vengono generate eccezioni e il risultato dipende dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="f4c9d-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4c9d-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="f4c9d-109">Example</span></span>  
 <span data-ttu-id="f4c9d-110">Questo esempio mostra come passare da un elemento di una matrice all'altro incrementando il puntatore della dimensione di `int`.</span><span class="sxs-lookup"><span data-stu-id="f4c9d-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="f4c9d-111">A ogni passaggio vengono visualizzati l'indirizzo e il contenuto dell'elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="f4c9d-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
 <span data-ttu-id="f4c9d-112">**Valore:0 @ Indirizzo:12860272**</span><span class="sxs-lookup"><span data-stu-id="f4c9d-112">**Value:0 @ Address:12860272**</span></span>  
<span data-ttu-id="f4c9d-113">**Valore:1 @ Indirizzo:12860276**</span><span class="sxs-lookup"><span data-stu-id="f4c9d-113">**Value:1 @ Address:12860276**</span></span>  
<span data-ttu-id="f4c9d-114">**Valore:2 @ Indirizzo:12860280**</span><span class="sxs-lookup"><span data-stu-id="f4c9d-114">**Value:2 @ Address:12860280**</span></span>  
<span data-ttu-id="f4c9d-115">**Valore:3 @ Indirizzo:12860284**</span><span class="sxs-lookup"><span data-stu-id="f4c9d-115">**Value:3 @ Address:12860284**</span></span>  
<span data-ttu-id="f4c9d-116">**Valore:4 @ Indirizzo:12860288**</span><span class="sxs-lookup"><span data-stu-id="f4c9d-116">**Value:4 @ Address:12860288**</span></span>   
## <a name="see-also"></a><span data-ttu-id="f4c9d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4c9d-117">See Also</span></span>  
 [<span data-ttu-id="f4c9d-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f4c9d-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f4c9d-119">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="f4c9d-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="f4c9d-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="f4c9d-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="f4c9d-121">Modifica dei puntatori</span><span class="sxs-lookup"><span data-stu-id="f4c9d-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [<span data-ttu-id="f4c9d-122">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="f4c9d-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="f4c9d-123">Tipi</span><span class="sxs-lookup"><span data-stu-id="f4c9d-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="f4c9d-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="f4c9d-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="f4c9d-125">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="f4c9d-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="f4c9d-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="f4c9d-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
