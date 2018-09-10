---
title: Operazioni aritmetiche sui puntatori (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: 3694699466f7a200eecd5eef85f60fa19f9584a8
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43862303"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="8b955-102">Operazioni aritmetiche sui puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="8b955-102">Arithmetic Operations on Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="8b955-103">Questo argomento illustra l'uso degli operatori aritmetici `+` e **-** per modificare i puntatori.</span><span class="sxs-lookup"><span data-stu-id="8b955-103">This topic discusses using the arithmetic operators `+` and **-** to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b955-104">È possibile eseguire qualsiasi operazione aritmetica sui puntatori void.</span><span class="sxs-lookup"><span data-stu-id="8b955-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="8b955-105">Aggiunta e sottrazione di valori numerici dai puntatori</span><span class="sxs-lookup"><span data-stu-id="8b955-105">Adding and Subtracting Numeric Values to or From Pointers</span></span>  
 <span data-ttu-id="8b955-106">È possibile aggiungere un valore `n` di tipo [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) a un puntatore `p` di qualsiasi tipo, ad eccezione di `void*`.</span><span class="sxs-lookup"><span data-stu-id="8b955-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer, `p`,of any type except `void*`.</span></span> <span data-ttu-id="8b955-107">`p+n` è il puntatore risultante dall'aggiunta di `n * sizeof(p) to the address of p`.</span><span class="sxs-lookup"><span data-stu-id="8b955-107">The result `p+n` is the pointer resulting from adding `n * sizeof(p) to the address of p`.</span></span> <span data-ttu-id="8b955-108">Analogamente, `p-n` è il puntatore risultante dalla sottrazione di `n * sizeof(p)` dall'indirizzo di `p`.</span><span class="sxs-lookup"><span data-stu-id="8b955-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(p)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="8b955-109">Sottrazione di puntatori</span><span class="sxs-lookup"><span data-stu-id="8b955-109">Subtracting Pointers</span></span>  
 <span data-ttu-id="8b955-110">È anche possibile sottrarre puntatori dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="8b955-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="8b955-111">Il risultato è sempre il tipo `long`.</span><span class="sxs-lookup"><span data-stu-id="8b955-111">The result is always of the type `long`.</span></span> <span data-ttu-id="8b955-112">Ad esempio, se `p1` e `p2` sono puntatori di tipo `pointer-type*`, l'espressione `p1-p2` è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="8b955-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 <span data-ttu-id="8b955-113">Non viene generata nessuna eccezione quando l'operazione aritmetica supera il dominio del puntatore e il risultato dipende dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="8b955-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b955-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="8b955-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8b955-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="8b955-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8b955-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b955-116">See Also</span></span>

- [<span data-ttu-id="8b955-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8b955-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="8b955-118">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="8b955-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="8b955-119">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="8b955-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="8b955-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="8b955-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="8b955-121">Modifica dei puntatori</span><span class="sxs-lookup"><span data-stu-id="8b955-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="8b955-122">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="8b955-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="8b955-123">Tipi</span><span class="sxs-lookup"><span data-stu-id="8b955-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="8b955-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="8b955-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="8b955-125">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="8b955-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="8b955-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="8b955-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
