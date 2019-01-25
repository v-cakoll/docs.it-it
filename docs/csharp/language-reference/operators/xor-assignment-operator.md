---
title: Operatore ^= - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: 12189d6469a9716d3b7ebcffef23423a75692d1a
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333551"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="89013-102">Operatore ^= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="89013-102">^= operator (C# Reference)</span></span>

<span data-ttu-id="89013-103">Operatore di assegnazione OR esclusivo.</span><span class="sxs-lookup"><span data-stu-id="89013-103">The exclusive-OR assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="89013-104">Note</span><span class="sxs-lookup"><span data-stu-id="89013-104">Remarks</span></span>

<span data-ttu-id="89013-105">Un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="89013-105">An expression of the form</span></span>

```csharp
x ^= y
```

<span data-ttu-id="89013-106">viene valutata come</span><span class="sxs-lookup"><span data-stu-id="89013-106">is evaluated as</span></span>

```csharp
x = x ^ y
```

<span data-ttu-id="89013-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="89013-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="89013-108">L'[operatore ^](xor-operator.md) esegue un'operazione con OR esclusivo bit per bit sugli operandi integrali e un'operazione con OR esclusivo logico sugli operandi [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="89013-108">The [^ operator](xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../keywords/bool.md) operands.</span></span>

<span data-ttu-id="89013-109">L'operatore ^= non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore ^](xor-operator.md) (vedere [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="89013-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](xor-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="89013-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="89013-110">Example</span></span>

[!code-csharp[csRefOperators#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#23)]

## <a name="see-also"></a><span data-ttu-id="89013-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89013-111">See also</span></span>

- [<span data-ttu-id="89013-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="89013-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="89013-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="89013-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="89013-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="89013-114">C# operators</span></span>](index.md)