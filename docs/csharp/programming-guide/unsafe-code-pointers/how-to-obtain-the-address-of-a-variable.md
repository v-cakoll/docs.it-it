---
title: 'Procedura: ottenere l''indirizzo di una variabile (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: 19
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
ms.openlocfilehash: 169f68cc80b7a27427a9987942e66e0ba9ed1a02
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="a5700-102">Procedura: ottenere l'indirizzo di una variabile (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a5700-102">How to: Obtain the Address of a Variable (C# Programming Guide)</span></span>
<span data-ttu-id="a5700-103">Per ottenere l'indirizzo di un'espressione unaria, che restituisce una variabile fissa, usare l'operatore address-of:</span><span class="sxs-lookup"><span data-stu-id="a5700-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator:</span></span>  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="a5700-104">L'operatore address-of può essere applicato solo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="a5700-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="a5700-105">Se la variabile è spostabile, è possibile usare l'[istruzione fissa](../../../csharp/language-reference/keywords/fixed-statement.md) per fissare temporaneamente la variabile prima di ottenerne l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="a5700-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="a5700-106">È compito del programmatore garantire che la variabile sia inizializzata.</span><span class="sxs-lookup"><span data-stu-id="a5700-106">It is your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="a5700-107">Il compilatore non genererà un messaggio di errore se la variabile non è inizializzata.</span><span class="sxs-lookup"><span data-stu-id="a5700-107">The compiler will not issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="a5700-108">Non è possibile ottenere l'indirizzo di una costante o di un valore.</span><span class="sxs-lookup"><span data-stu-id="a5700-108">You cannot get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5700-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5700-109">Example</span></span>  
 <span data-ttu-id="a5700-110">In questo esempio viene dichiarato un puntatore a `int`, `p`, e gli viene assegnato l'indirizzo di una variabile di tipo integer, `number`.</span><span class="sxs-lookup"><span data-stu-id="a5700-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="a5700-111">La variabile `number` viene inizializzata in seguito all'assegnazione a *p.</span><span class="sxs-lookup"><span data-stu-id="a5700-111">The variable `number` is initialized as a result of the assignment to *p.</span></span> <span data-ttu-id="a5700-112">Se si imposta l'istruzione di assegnazione come commento, l'inizializzazione della variabile `number` verrà rimossa, ma non verrà generato alcun errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a5700-112">If you make this assignment statement a comment, the initialization of the variable `number` will be removed, but no compile-time error is issued.</span></span> <span data-ttu-id="a5700-113">Si noti l'uso dell'operatore di [accesso ai membri](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) `->` per ottenere e visualizzare l'indirizzo archiviato nel puntatore.</span><span class="sxs-lookup"><span data-stu-id="a5700-113">Notice the use of the [Member Access](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) operator `->` to obtain and display the address stored in the pointer.</span></span>  
  
 <span data-ttu-id="a5700-114">[!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a5700-114">[!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]</span></span>  
  
 <span data-ttu-id="a5700-115">[!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a5700-115">[!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5700-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5700-116">See Also</span></span>  
 <span data-ttu-id="a5700-117">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a5700-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a5700-118">[Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="a5700-118">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="a5700-119">[Tipi di puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="a5700-119">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="a5700-120">[Tipi](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="a5700-120">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="a5700-121">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="a5700-121">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="a5700-122">[Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a5700-122">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="a5700-123">stackalloc</span><span class="sxs-lookup"><span data-stu-id="a5700-123">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

