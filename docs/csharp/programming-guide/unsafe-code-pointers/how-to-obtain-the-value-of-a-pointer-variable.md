---
title: 'Procedura: ottenere il valore di una variabile puntatore (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: 17
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
ms.openlocfilehash: 4cff42de07f2edb279ddd1cafefe9f4b67a38ce1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="24a24-102">Procedura: ottenere il valore di una variabile puntatore (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="24a24-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="24a24-103">L'operatore di riferimento indiretto a puntatore consente di ottenere la variabile nella posizione indicata da un puntatore.</span><span class="sxs-lookup"><span data-stu-id="24a24-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="24a24-104">L'espressione ha il seguente formato, dove `p` è un tipo di puntatore:</span><span class="sxs-lookup"><span data-stu-id="24a24-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="24a24-105">Non è possibile usare l'operatore di riferimento indiretto unario o un'espressione di qualsiasi altro tipo diverso dal tipo puntatore.</span><span class="sxs-lookup"><span data-stu-id="24a24-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="24a24-106">Non è inoltre possibile applicarlo a un puntatore [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="24a24-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="24a24-107">Quando si applica l'operatore di riferimento indiretto a un puntatore [Null](../../../csharp/language-reference/keywords/null.md), il risultato dipende dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="24a24-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24a24-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="24a24-108">Example</span></span>  
 <span data-ttu-id="24a24-109">Nell'esempio seguente si accede a una variabile di tipo `char` usando puntatori di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="24a24-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="24a24-110">Si noti che l'indirizzo di `theChar` varia da un'esecuzione all'altra, perché l'indirizzo fisico allocato a una variabile può cambiare.</span><span class="sxs-lookup"><span data-stu-id="24a24-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 <span data-ttu-id="24a24-111">[!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="24a24-111">[!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]</span></span>  
  
 <span data-ttu-id="24a24-112">[!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="24a24-112">[!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]</span></span>  
  
 <span data-ttu-id="24a24-113">**Valore di theChar = Z** </span><span class="sxs-lookup"><span data-stu-id="24a24-113">**Value of theChar = Z** </span></span>  
<span data-ttu-id="24a24-114">**Indirizzo di theChar = 12F718**</span><span class="sxs-lookup"><span data-stu-id="24a24-114">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="24a24-115">**Valore di pChar = Z** </span><span class="sxs-lookup"><span data-stu-id="24a24-115">**Value of pChar = Z** </span></span>  
<span data-ttu-id="24a24-116">**Valore di pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="24a24-116">**Value of pInt = 90**</span></span>    
## <a name="see-also"></a><span data-ttu-id="24a24-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24a24-117">See Also</span></span>  
 <span data-ttu-id="24a24-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="24a24-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="24a24-119">[Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="24a24-119">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="24a24-120">[Tipi di puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="24a24-120">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="24a24-121">[Tipi](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="24a24-121">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="24a24-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="24a24-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="24a24-123">[Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="24a24-123">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="24a24-124">stackalloc</span><span class="sxs-lookup"><span data-stu-id="24a24-124">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

