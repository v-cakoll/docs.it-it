---
title: Operazioni aritmetiche sui puntatori (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: 91e621e7cddce50e97b061ecd7d77dae6f7ef3cb
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129948"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="7573f-102">Operazioni aritmetiche sui puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7573f-102">Arithmetic operations on pointers (C# Programming Guide)</span></span>
<span data-ttu-id="7573f-103">Questo argomento illustra l'uso degli operatori aritmetici `+` e `-` per modificare i puntatori.</span><span class="sxs-lookup"><span data-stu-id="7573f-103">This topic discusses using the arithmetic operators `+` and `-` to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7573f-104">È possibile eseguire qualsiasi operazione aritmetica sui puntatori void.</span><span class="sxs-lookup"><span data-stu-id="7573f-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="7573f-105">Aggiunta e sottrazione di valori numerici ai o dai puntatori</span><span class="sxs-lookup"><span data-stu-id="7573f-105">Adding and subtracting numeric values to or from pointers</span></span>  
 <span data-ttu-id="7573f-106">È possibile aggiungere un valore `n` di tipo [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) a un puntatore.</span><span class="sxs-lookup"><span data-stu-id="7573f-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer.</span></span> <span data-ttu-id="7573f-107">Se `p` è un puntatore di tipo `pointer-type*`, il risultato `p+n` è il puntatore risultante dall'aggiunta di `n * sizeof(pointer-type)` all'indirizzo di `p`.</span><span class="sxs-lookup"><span data-stu-id="7573f-107">If `p` is a pointer of the type `pointer-type*`, the result `p+n` is the pointer resulting from adding `n * sizeof(pointer-type)` to the address of `p`.</span></span> <span data-ttu-id="7573f-108">Analogamente, `p-n` è il puntatore risultante dalla sottrazione di `n * sizeof(pointer-type)` dall'indirizzo di `p`.</span><span class="sxs-lookup"><span data-stu-id="7573f-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(pointer-type)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="7573f-109">Sottrazione di puntatori</span><span class="sxs-lookup"><span data-stu-id="7573f-109">Subtracting pointers</span></span>  
 <span data-ttu-id="7573f-110">È anche possibile sottrarre puntatori dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="7573f-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="7573f-111">Il risultato è sempre il tipo `long`.</span><span class="sxs-lookup"><span data-stu-id="7573f-111">The result is always of the type `long`.</span></span> <span data-ttu-id="7573f-112">Ad esempio, se `p1` e `p2` sono puntatori di tipo `pointer-type*`, l'espressione `p1-p2` è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="7573f-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 <span data-ttu-id="7573f-113">Non viene generata nessuna eccezione quando l'operazione aritmetica supera il dominio del puntatore e il risultato dipende dall'implementazione.</span><span class="sxs-lookup"><span data-stu-id="7573f-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7573f-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="7573f-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="7573f-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7573f-115">C# language specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7573f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7573f-116">See also</span></span>

- [<span data-ttu-id="7573f-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7573f-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7573f-118">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="7573f-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="7573f-119">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="7573f-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="7573f-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="7573f-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="7573f-121">Modifica dei puntatori</span><span class="sxs-lookup"><span data-stu-id="7573f-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="7573f-122">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="7573f-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="7573f-123">Tipi</span><span class="sxs-lookup"><span data-stu-id="7573f-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="7573f-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="7573f-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="7573f-125">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="7573f-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="7573f-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="7573f-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
