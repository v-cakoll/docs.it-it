---
title: operator (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: d633a46e21f913aa8c05289dccfb63e71efd697e
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2018
ms.locfileid: "37959546"
---
# <a name="operator-c-reference"></a><span data-ttu-id="fd4bd-102">operator (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="fd4bd-102">operator (C# Reference)</span></span>
<span data-ttu-id="fd4bd-103">Usare la parola chiave `operator` per eseguire l'overload di un operatore predefinito o specificare una conversione definita dall'utente in una classe o una dichiarazione di struttura.</span><span class="sxs-lookup"><span data-stu-id="fd4bd-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd4bd-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd4bd-104">Example</span></span>  
 <span data-ttu-id="fd4bd-105">La classe riportata di seguito è una classe estremamente semplificata per numeri frazionari.</span><span class="sxs-lookup"><span data-stu-id="fd4bd-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="fd4bd-106">La classe esegue l'overload degli operatori `+` e `*` per eseguire addizioni e moltiplicazioni frazionarie e specifica un operatore di conversione che converte un tipo `Fraction` in un tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="fd4bd-106">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="fd4bd-107">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="fd4bd-107">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fd4bd-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd4bd-108">See Also</span></span>  
 [<span data-ttu-id="fd4bd-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="fd4bd-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fd4bd-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="fd4bd-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fd4bd-111">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="fd4bd-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="fd4bd-112">implicit</span><span class="sxs-lookup"><span data-stu-id="fd4bd-112">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="fd4bd-113">explicit</span><span class="sxs-lookup"><span data-stu-id="fd4bd-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="fd4bd-114">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="fd4bd-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
