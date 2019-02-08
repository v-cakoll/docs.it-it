---
title: Operatore << - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: 0271c97bc624a8946b90508e9ce39d217a128c05
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261750"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="7e96d-102">Operatore \<\< (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7e96d-102">\<\< operator (C# Reference)</span></span>

<span data-ttu-id="7e96d-103">L'operatore di spostamento a sinistra (`<<`) sposta verso sinistra il primo operando del numero di bit specificato dal secondo operando.</span><span class="sxs-lookup"><span data-stu-id="7e96d-103">The left-shift operator (`<<`) shifts its first operand left by the number of bits specified by its second operand.</span></span> <span data-ttu-id="7e96d-104">Il tipo del secondo operando deve essere un [int](../keywords/int.md) o un tipo con una conversione numerica implicita predefinita in `int`.</span><span class="sxs-lookup"><span data-stu-id="7e96d-104">The type of the second operand must be an [int](../keywords/int.md) or a type that has a predefined implicit numeric conversion to `int`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e96d-105">Note</span><span class="sxs-lookup"><span data-stu-id="7e96d-105">Remarks</span></span>

<span data-ttu-id="7e96d-106">Se il primo operando è di tipo [int](../keywords/int.md) o [uint](../keywords/uint.md) (quantità a 32 bit), il conteggio dello spostamento è dato dai cinque bit meno significativi del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="7e96d-106">If the first operand is an [int](../keywords/int.md) or [uint](../keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand.</span></span> <span data-ttu-id="7e96d-107">Il conteggio dello spostamento effettivo, quindi, è compreso tra 0 e 31 bit.</span><span class="sxs-lookup"><span data-stu-id="7e96d-107">That is, the actual shift count is 0 to 31 bits.</span></span>

<span data-ttu-id="7e96d-108">Se il primo operando è di tipo [long](../keywords/long.md) o [ulong](../keywords/ulong.md) (quantità a 64 bit), il conteggio dello spostamento è dato dai sei bit meno significativi del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="7e96d-108">If the first operand is a [long](../keywords/long.md) or [ulong](../keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand.</span></span> <span data-ttu-id="7e96d-109">Il conteggio dello spostamento effettivo, quindi, è compreso tra 0 e 63 bit.</span><span class="sxs-lookup"><span data-stu-id="7e96d-109">That is, the actual shift count is 0 to 63 bits.</span></span>

<span data-ttu-id="7e96d-110">Tutti i bit più significativi che non rientrano nell'intervallo del tipo del primo operando dopo lo spostamento vengono scartati, mentre i bit vuoti meno significativi vengono riempiti con zero.</span><span class="sxs-lookup"><span data-stu-id="7e96d-110">Any high-order bits that are not within the range of the type of the first operand after the shift are discarded, and the low-order empty bits are zero-filled.</span></span> <span data-ttu-id="7e96d-111">Le operazioni di spostamento non provocano mai overflow.</span><span class="sxs-lookup"><span data-stu-id="7e96d-111">Shift operations never cause overflows.</span></span>

<span data-ttu-id="7e96d-112">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `<<` (vedere [operator](../keywords/operator.md)): il tipo del primo operando deve essere il tipo definito dall'utente e il tipo del secondo operando deve essere `int`.</span><span class="sxs-lookup"><span data-stu-id="7e96d-112">User-defined types can overload the `<<` operator (see [operator](../keywords/operator.md)); the type of the first operand must be the user-defined type, and the type of the second operand must be `int`.</span></span> <span data-ttu-id="7e96d-113">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="7e96d-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="7e96d-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="7e96d-114">Example</span></span>

[!code-csharp[csRefOperators#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#14)]

## <a name="comments"></a><span data-ttu-id="7e96d-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="7e96d-115">Comments</span></span>

<span data-ttu-id="7e96d-116">Osservare come `i<<1` e `i<<33` generino lo stesso risultato, poiché 1 e 33 hanno gli stessi cinque bit meno significativi.</span><span class="sxs-lookup"><span data-stu-id="7e96d-116">Note that `i<<1` and `i<<33` give the same result, because 1 and 33 have the same low-order five bits.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e96d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e96d-117">See also</span></span>

- [<span data-ttu-id="7e96d-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="7e96d-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7e96d-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7e96d-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7e96d-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="7e96d-120">C# Operators</span></span>](index.md)
