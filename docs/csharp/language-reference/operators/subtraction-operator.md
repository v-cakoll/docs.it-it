---
title: '- Operatore - - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 8cf6e8871a88e2b37b9531ecbd616289523473c7
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333759"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="4f00c-102">Operatore - (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4f00c-102">- operator (C# Reference)</span></span>

<span data-ttu-id="4f00c-103">L'operatore `-` ha la funzione di operatore unario o binario.</span><span class="sxs-lookup"><span data-stu-id="4f00c-103">The `-` operator can function as either a unary or a binary operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f00c-104">Note</span><span class="sxs-lookup"><span data-stu-id="4f00c-104">Remarks</span></span>

<span data-ttu-id="4f00c-105">Gli operatori `-` unari sono predefiniti per tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="4f00c-105">Unary `-` operators are predefined for all numeric types.</span></span> <span data-ttu-id="4f00c-106">Il risultato di un'operazione `-` unaria su un tipo numerico corrisponde alla negazione numerica dell'operando.</span><span class="sxs-lookup"><span data-stu-id="4f00c-106">The result of a unary `-` operation on a numeric type is the numeric negation of the operand.</span></span>

<span data-ttu-id="4f00c-107">Gli operatori `-` binari sono predefiniti per tutti i tipi numerici e di enumerazione per sottrarre il secondo operando dal primo.</span><span class="sxs-lookup"><span data-stu-id="4f00c-107">Binary `-` operators are predefined for all numeric and enumeration types to subtract the second operand from the first.</span></span>

<span data-ttu-id="4f00c-108">I tipi delegati offrono anche un operatore `-` binario, che esegue la rimozione dei delegati.</span><span class="sxs-lookup"><span data-stu-id="4f00c-108">Delegate types also provide a binary `-` operator, which performs delegate removal.</span></span>

<span data-ttu-id="4f00c-109">I tipi definiti dall'utente possono eseguire l'overload degli operatori `-` unari e `-` binari.</span><span class="sxs-lookup"><span data-stu-id="4f00c-109">User-defined types can overload the unary `-` and binary `-` operators.</span></span> <span data-ttu-id="4f00c-110">Per altre informazioni, vedere [Parola chiave operator](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="4f00c-110">For more information, see [operator keyword](../keywords/operator.md).</span></span>

## <a name="example"></a><span data-ttu-id="4f00c-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f00c-111">Example</span></span>

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a><span data-ttu-id="4f00c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f00c-112">See also</span></span>

- [<span data-ttu-id="4f00c-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4f00c-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4f00c-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4f00c-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4f00c-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="4f00c-115">C# operators</span></span>](index.md)