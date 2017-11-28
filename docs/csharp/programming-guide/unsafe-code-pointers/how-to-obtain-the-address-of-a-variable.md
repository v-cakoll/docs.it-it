---
title: 'Procedura: ottenere l''indirizzo di una variabile (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d0969f7e62864c682660f08cd4198aa4032e0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="4897a-102">Procedura: ottenere l'indirizzo di una variabile (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="4897a-102">How to: Obtain the Address of a Variable (C# Programming Guide)</span></span>
<span data-ttu-id="4897a-103">Per ottenere l'indirizzo di un'espressione unaria, che restituisce una variabile fissa, usare l'operatore address-of:</span><span class="sxs-lookup"><span data-stu-id="4897a-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator:</span></span>  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="4897a-104">L'operatore address-of può essere applicato solo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="4897a-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="4897a-105">Se la variabile è spostabile, è possibile usare l'[istruzione fissa](../../../csharp/language-reference/keywords/fixed-statement.md) per fissare temporaneamente la variabile prima di ottenerne l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="4897a-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="4897a-106">È compito del programmatore garantire che la variabile sia inizializzata.</span><span class="sxs-lookup"><span data-stu-id="4897a-106">It is your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="4897a-107">Il compilatore non genererà un messaggio di errore se la variabile non è inizializzata.</span><span class="sxs-lookup"><span data-stu-id="4897a-107">The compiler will not issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="4897a-108">Non è possibile ottenere l'indirizzo di una costante o di un valore.</span><span class="sxs-lookup"><span data-stu-id="4897a-108">You cannot get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4897a-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="4897a-109">Example</span></span>  
 <span data-ttu-id="4897a-110">In questo esempio viene dichiarato un puntatore a `int`, `p`, e gli viene assegnato l'indirizzo di una variabile di tipo integer, `number`.</span><span class="sxs-lookup"><span data-stu-id="4897a-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="4897a-111">La variabile `number` viene inizializzata in seguito all'assegnazione a *p.</span><span class="sxs-lookup"><span data-stu-id="4897a-111">The variable `number` is initialized as a result of the assignment to *p.</span></span> <span data-ttu-id="4897a-112">Se si imposta l'istruzione di assegnazione come commento, l'inizializzazione della variabile `number` verrà rimossa, ma non verrà generato alcun errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4897a-112">If you make this assignment statement a comment, the initialization of the variable `number` will be removed, but no compile-time error is issued.</span></span> <span data-ttu-id="4897a-113">Si noti l'uso dell'operatore di [accesso ai membri](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) `->` per ottenere e visualizzare l'indirizzo archiviato nel puntatore.</span><span class="sxs-lookup"><span data-stu-id="4897a-113">Notice the use of the [Member Access](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) operator `->` to obtain and display the address stored in the pointer.</span></span>  
  
 [!code-csharp[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4897a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4897a-114">See Also</span></span>  
 [<span data-ttu-id="4897a-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4897a-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4897a-116">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="4897a-116">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="4897a-117">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="4897a-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="4897a-118">Tipi</span><span class="sxs-lookup"><span data-stu-id="4897a-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="4897a-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="4897a-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="4897a-120">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="4897a-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="4897a-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="4897a-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
