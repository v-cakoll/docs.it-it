---
title: Operatore -= - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 3b6890be4460a599a5d2f5f5f6ee1627be933f0b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333330"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="cb6f4-102">Operatore -= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="cb6f4-102">-= operator (C# Reference)</span></span>

<span data-ttu-id="cb6f4-103">Operatore di assegnazione di sottrazione.</span><span class="sxs-lookup"><span data-stu-id="cb6f4-103">The subtraction assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb6f4-104">Note</span><span class="sxs-lookup"><span data-stu-id="cb6f4-104">Remarks</span></span>

<span data-ttu-id="cb6f4-105">Un'espressione che usa l'operatore di assegnazione `-=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="cb6f4-105">An expression using the `-=` assignment operator, such as</span></span>

```csharp
x -= y
```

 <span data-ttu-id="cb6f4-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="cb6f4-106">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="cb6f4-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="cb6f4-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="cb6f4-108">Il significato dell'[operatore -](subtraction-operator.md) dipende dai tipi di `x` e `y` (sottrazione per gli operandi numerici, rimozione del delegato per gli operandi delegati e così via).</span><span class="sxs-lookup"><span data-stu-id="cb6f4-108">The meaning of the [- operator](subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>

<span data-ttu-id="cb6f4-109">L'operatore `-=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore -](subtraction-operator.md) (vedere [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="cb6f4-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](subtraction-operator.md) (see [operator](../keywords/operator.md)).</span></span>

<span data-ttu-id="cb6f4-110">L'operatore -= viene anche usato in C# per annullare la sottoscrizione a un evento.</span><span class="sxs-lookup"><span data-stu-id="cb6f4-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="cb6f4-111">Per altre informazioni, vedere [Procedura: Eseguire e annullare la sottoscrizione a eventi](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="cb6f4-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="example"></a><span data-ttu-id="cb6f4-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="cb6f4-112">Example</span></span>

[!code-csharp[csRefOperators#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#6)]

## <a name="see-also"></a><span data-ttu-id="cb6f4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb6f4-113">See also</span></span>

- [<span data-ttu-id="cb6f4-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="cb6f4-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cb6f4-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cb6f4-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cb6f4-116">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="cb6f4-116">C# operators</span></span>](index.md)
