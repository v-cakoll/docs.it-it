---
title: Operazioni aritmetiche sui puntatori (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
caps.latest.revision: 18
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
ms.openlocfilehash: d40d44f8be590a909ff059b0fa84efb598fcf263
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="3f413-102">Operazioni aritmetiche sui puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3f413-102">Arithmetic Operations on Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="3f413-103">Questo argomento illustra l'uso degli operatori aritmetici `+` e **-** per modificare i puntatori.</span><span class="sxs-lookup"><span data-stu-id="3f413-103">This topic discusses using the arithmetic operators `+` and **-** to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f413-104">È possibile eseguire qualsiasi operazione aritmetica sui puntatori void.</span><span class="sxs-lookup"><span data-stu-id="3f413-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="3f413-105">Aggiunta e sottrazione di valori numerici dai puntatori</span><span class="sxs-lookup"><span data-stu-id="3f413-105">Adding and Subtracting Numeric Values to or From Pointers</span></span>  
 <span data-ttu-id="3f413-106">È possibile aggiungere un valore `n` di tipo [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) a un puntatore `p` di qualsiasi tipo, ad eccezione di `void*`.</span><span class="sxs-lookup"><span data-stu-id="3f413-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer, `p`,of any type except `void*`.</span></span> <span data-ttu-id="3f413-107">`p+n` è il puntatore risultante dall'aggiunta di `n * sizeof(p) to the address of p`.</span><span class="sxs-lookup"><span data-stu-id="3f413-107">The result `p+n` is the pointer resulting from adding `n * sizeof(p) to the address of p`.</span></span> <span data-ttu-id="3f413-108">Analogamente, `p-n` è il puntatore risultante dalla sottrazione di `n * sizeof(p)` dall'indirizzo di `p`.</span><span class="sxs-lookup"><span data-stu-id="3f413-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(p)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="3f413-109">Sottrazione di puntatori</span><span class="sxs-lookup"><span data-stu-id="3f413-109">Subtracting Pointers</span></span>  
 <span data-ttu-id="3f413-110">È anche possibile sottrarre puntatori dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="3f413-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="3f413-111">Il risultato è sempre il tipo `long`.</span><span class="sxs-lookup"><span data-stu-id="3f413-111">The result is always of the type `long`.</span></span> <span data-ttu-id="3f413-112">Ad esempio, se `p1` e `p2` sono puntatori di tipo `pointer-type*`, l'espressione `p1-p2` è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="3f413-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 <span data-ttu-id="3f413-113">Non viene generata nessuna eccezione quando l'operazione aritmetica supera il dominio del puntatore e il risultato dipende dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="3f413-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f413-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f413-114">Example</span></span>  
 <span data-ttu-id="3f413-115">[!code-cs[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3f413-115">[!code-cs[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]</span></span>  
  
 <span data-ttu-id="3f413-116">[!code-cs[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3f413-116">[!code-cs[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3f413-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3f413-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3f413-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f413-118">See Also</span></span>  
 <span data-ttu-id="3f413-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f413-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3f413-120">[Codice di tipo unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f413-120">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="3f413-121">[Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="3f413-121">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="3f413-122">[Operatori di C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f413-122">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="3f413-123">[Modifica dei puntatori](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span><span class="sxs-lookup"><span data-stu-id="3f413-123">[Manipulating Pointers](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span></span>  
 <span data-ttu-id="3f413-124">[Tipi di puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="3f413-124">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="3f413-125">[Tipi](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="3f413-125">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="3f413-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="3f413-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="3f413-127">[Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="3f413-127">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="3f413-128">stackalloc</span><span class="sxs-lookup"><span data-stu-id="3f413-128">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

