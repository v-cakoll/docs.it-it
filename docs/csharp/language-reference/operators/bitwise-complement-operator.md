---
title: Operatore ~ (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 8af25217f9e7e66796192783a0b8e3415604dc90
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510111"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="49d8e-102">Operatore ~ (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="49d8e-102">~ Operator (C# Reference)</span></span>
<span data-ttu-id="49d8e-103">L'operatore `~` esegue un'operazione di complemento bit per bit sul relativo operando, che ha l'effetto di invertire ogni bit.</span><span class="sxs-lookup"><span data-stu-id="49d8e-103">The `~` operator performs a bitwise complement operation on its operand, which has the effect of reversing each bit.</span></span> <span data-ttu-id="49d8e-104">Gli operatori di complemento bit per bit sono predefiniti per [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) e [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="49d8e-104">Bitwise complement operators are predefined for [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), and [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49d8e-105">È possibile anche usare il simbolo `~` per dichiarare i finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="49d8e-105">The `~` symbol also is used to declare finalizers.</span></span> <span data-ttu-id="49d8e-106">Per altre informazioni, vedere [Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="49d8e-106">For more information, see [Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49d8e-107">Note</span><span class="sxs-lookup"><span data-stu-id="49d8e-107">Remarks</span></span>  
 <span data-ttu-id="49d8e-108">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `~`.</span><span class="sxs-lookup"><span data-stu-id="49d8e-108">User-defined types can overload the `~` operator.</span></span> <span data-ttu-id="49d8e-109">Per altre informazioni, vedere l'argomento relativo all'[operatore](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="49d8e-109">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="49d8e-110">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="49d8e-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49d8e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="49d8e-111">Example</span></span>  
 [!code-csharp[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="49d8e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49d8e-112">See Also</span></span>

- [<span data-ttu-id="49d8e-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="49d8e-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="49d8e-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="49d8e-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="49d8e-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="49d8e-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="49d8e-116">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="49d8e-116">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
