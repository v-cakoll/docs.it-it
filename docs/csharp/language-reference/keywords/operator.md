---
title: operator (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- operator_CSharpKeyword
- operator
dev_langs:
- CSharp
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 76d403493861e9c587672412cd2989c419b8717a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="operator-c-reference"></a><span data-ttu-id="eed62-102">operator (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="eed62-102">operator (C# Reference)</span></span>
<span data-ttu-id="eed62-103">Usare la parola chiave `operator` per eseguire l'overload di un operatore predefinito o specificare una conversione definita dall'utente in una classe o una dichiarazione di struttura.</span><span class="sxs-lookup"><span data-stu-id="eed62-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eed62-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="eed62-104">Example</span></span>  
 <span data-ttu-id="eed62-105">La classe riportata di seguito è una classe estremamente semplificata per numeri frazionari.</span><span class="sxs-lookup"><span data-stu-id="eed62-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="eed62-106">La classe esegue l'overload degli operatori + e * per eseguire addizioni e moltiplicazioni frazionarie e specifica un operatore di conversione che converte un tipo Fraction in un tipo double.</span><span class="sxs-lookup"><span data-stu-id="eed62-106">It overloads the + and * operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a Fraction type to a double type.</span></span>  
  
 <span data-ttu-id="eed62-107">[!code-cs[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="eed62-107">[!code-cs[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="eed62-108">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="eed62-108">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eed62-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eed62-109">See Also</span></span>  
 <span data-ttu-id="eed62-110">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="eed62-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="eed62-111">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="eed62-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="eed62-112">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="eed62-112">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="eed62-113">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span><span class="sxs-lookup"><span data-stu-id="eed62-113">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span></span>  
 <span data-ttu-id="eed62-114">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span><span class="sxs-lookup"><span data-stu-id="eed62-114">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span></span>  
 [<span data-ttu-id="eed62-115">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="eed62-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

