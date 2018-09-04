---
title: Parola chiave operator (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: c3bfada235993670bf158fe9803a09707b2b3251
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929872"
---
# <a name="operator-c-reference"></a><span data-ttu-id="1482d-102">operator (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1482d-102">operator (C# Reference)</span></span>

<span data-ttu-id="1482d-103">Usare la parola chiave `operator` per eseguire l'overload di un operatore predefinito o specificare una conversione definita dall'utente in una classe o una dichiarazione di struttura.</span><span class="sxs-lookup"><span data-stu-id="1482d-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

## <a name="example"></a><span data-ttu-id="1482d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="1482d-104">Example</span></span>

<span data-ttu-id="1482d-105">La classe riportata di seguito è una classe estremamente semplificata per numeri frazionari.</span><span class="sxs-lookup"><span data-stu-id="1482d-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="1482d-106">La classe esegue l'overload degli operatori `+` e `*` per eseguire addizioni e moltiplicazioni frazionarie e specifica un operatore di conversione che converte un tipo `Fraction` in un tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="1482d-106">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="1482d-107">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1482d-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1482d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1482d-108">See also</span></span>

- [<span data-ttu-id="1482d-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1482d-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1482d-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1482d-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1482d-111">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="1482d-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1482d-112">implicit</span><span class="sxs-lookup"><span data-stu-id="1482d-112">implicit</span></span>](implicit.md)
- [<span data-ttu-id="1482d-113">explicit</span><span class="sxs-lookup"><span data-stu-id="1482d-113">explicit</span></span>](explicit.md)
- [<span data-ttu-id="1482d-114">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="1482d-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
