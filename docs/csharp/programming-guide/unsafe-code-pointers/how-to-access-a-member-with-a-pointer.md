---
title: 'Procedura: accedere a un membro mediante un puntatore (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: 20f0dd18bb5ca132d05335953958d8f747b6abc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332202"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a><span data-ttu-id="13271-102">Procedura: accedere a un membro mediante un puntatore (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="13271-102">How to: Access a Member with a Pointer (C# Programming Guide)</span></span>
<span data-ttu-id="13271-103">Per accedere a un membro di uno struct dichiarato in un contesto non sicuro, è possibile usare l'operatore di accesso ai membri, come illustrato nell'esempio seguente in cui `p` è un puntatore a uno [struct](../../../csharp/language-reference/keywords/struct.md) che contiene un membro `x`.</span><span class="sxs-lookup"><span data-stu-id="13271-103">To access a member of a struct that is declared in an unsafe context, you can use the member access operator as shown in the following example in which `p` is a pointer to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains a member `x`.</span></span>  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a><span data-ttu-id="13271-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="13271-104">Example</span></span>  
 <span data-ttu-id="13271-105">In questo esempio uno [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, che contiene le due coordinate `x` e `y` viene dichiarato e ne viene creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="13271-105">In this example, a [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, that contains the two coordinates `x` and `y` is declared and instantiated.</span></span> <span data-ttu-id="13271-106">Usando l'operatore di accesso ai membri `->` e un puntatore all'istanza di `home`, vengono assegnati i valori a `x` e `y`.</span><span class="sxs-lookup"><span data-stu-id="13271-106">By using the member access operator `->` and a pointer to the instance `home`, `x` and `y` are assigned values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13271-107">Si noti che l'espressione `p->x` è equivalente all'espressione `(*p).x` e che è possibile ottenere lo stesso risultato usando una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="13271-107">Notice that the expression `p->x` is equivalent to the expression `(*p).x`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 [!code-csharp[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="13271-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13271-108">See Also</span></span>  
 [<span data-ttu-id="13271-109">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="13271-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="13271-110">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="13271-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="13271-111">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="13271-111">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="13271-112">Tipi</span><span class="sxs-lookup"><span data-stu-id="13271-112">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="13271-113">unsafe</span><span class="sxs-lookup"><span data-stu-id="13271-113">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="13271-114">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="13271-114">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="13271-115">stackalloc</span><span class="sxs-lookup"><span data-stu-id="13271-115">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
