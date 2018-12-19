---
title: Operatore &lt; - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
ms.openlocfilehash: 3cc125471eee7bf0002e9844c2a1cdc05e8d4a03
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241227"
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="9be20-102">Operatore &lt; (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="9be20-102">&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="9be20-103">Tutti i tipi numerici e di enumerazione definiscono un operatore relazionale "minore di" (`<`), che restituisce `true` se il primo operando è minore del secondo, in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="9be20-103">All numeric and enumeration types define a "less than" relational operator (`<`) that returns `true` if the first operand is less than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9be20-104">Note</span><span class="sxs-lookup"><span data-stu-id="9be20-104">Remarks</span></span>  
 <span data-ttu-id="9be20-105">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `<` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="9be20-105">User-defined types can overload the `<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="9be20-106">Se `<` è sottoposto a overload, deve esserlo anche [>](../../../csharp/language-reference/operators/greater-than-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9be20-106">If `<` is overloaded, [>](../../../csharp/language-reference/operators/greater-than-operator.md) must also be overloaded.</span></span>
  
## <a name="example"></a><span data-ttu-id="9be20-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="9be20-107">Example</span></span>  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9be20-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9be20-108">See Also</span></span>

- [<span data-ttu-id="9be20-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="9be20-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="9be20-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9be20-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="9be20-111">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="9be20-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
