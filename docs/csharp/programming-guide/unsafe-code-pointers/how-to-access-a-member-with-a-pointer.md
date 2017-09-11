---
title: 'Procedura: accedere a un membro mediante un puntatore (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
caps.latest.revision: 16
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
ms.openlocfilehash: ca24b7d930e7b6c61a3db89a431f1ec3aaec77c8
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a><span data-ttu-id="87ba9-102">Procedura: accedere a un membro mediante un puntatore (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="87ba9-102">How to: Access a Member with a Pointer (C# Programming Guide)</span></span>
<span data-ttu-id="87ba9-103">Per accedere a un membro di uno struct dichiarato in un contesto non sicuro, è possibile usare l'operatore di accesso ai membri, come illustrato nell'esempio seguente in cui `p` è un puntatore a uno [struct](../../../csharp/language-reference/keywords/struct.md) che contiene un membro `x`.</span><span class="sxs-lookup"><span data-stu-id="87ba9-103">To access a member of a struct that is declared in an unsafe context, you can use the member access operator as shown in the following example in which `p` is a pointer to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains a member `x`.</span></span>  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a><span data-ttu-id="87ba9-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="87ba9-104">Example</span></span>  
 <span data-ttu-id="87ba9-105">In questo esempio uno [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, che contiene le due coordinate `x` e `y` viene dichiarato e ne viene creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="87ba9-105">In this example, a [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, that contains the two coordinates `x` and `y` is declared and instantiated.</span></span> <span data-ttu-id="87ba9-106">Usando l'operatore di accesso ai membri `->` e un puntatore all'istanza di `home`, vengono assegnati i valori a `x` e `y`.</span><span class="sxs-lookup"><span data-stu-id="87ba9-106">By using the member access operator `->` and a pointer to the instance `home`, `x` and `y` are assigned values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87ba9-107">Si noti che l'espressione `p->x` è equivalente all'espressione `(*p).x` e che è possibile ottenere lo stesso risultato usando una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="87ba9-107">Notice that the expression `p->x` is equivalent to the expression `(*p).x`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 <span data-ttu-id="87ba9-108">[!code-cs[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="87ba9-108">[!code-cs[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]</span></span>  
  
 <span data-ttu-id="87ba9-109">[!code-cs[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="87ba9-109">[!code-cs[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87ba9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87ba9-110">See Also</span></span>  
 <span data-ttu-id="87ba9-111">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="87ba9-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="87ba9-112">[Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="87ba9-112">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="87ba9-113">[Tipi di puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="87ba9-113">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="87ba9-114">[Tipi](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="87ba9-114">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="87ba9-115">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="87ba9-115">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="87ba9-116">[Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="87ba9-116">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="87ba9-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="87ba9-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

