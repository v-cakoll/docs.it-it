---
title: + Operatore (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
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
ms.openlocfilehash: 5455375148f1924c7fe1cdb10e7924abb83a1565
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="05cff-102">Operatore + (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="05cff-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="05cff-103">L'operatore `+` ha la funzione di operatore unario o binario.</span><span class="sxs-lookup"><span data-stu-id="05cff-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05cff-104">Note</span><span class="sxs-lookup"><span data-stu-id="05cff-104">Remarks</span></span>  
 <span data-ttu-id="05cff-105">Gli operatori `+` unari sono predefiniti per tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="05cff-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="05cff-106">Il risultato di un'operazione `+` unaria su un tipo numerico corrisponde al valore dell'operando.</span><span class="sxs-lookup"><span data-stu-id="05cff-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="05cff-107">Gli operatori `+` binari sono predefiniti per i tipi numerici e stringa.</span><span class="sxs-lookup"><span data-stu-id="05cff-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="05cff-108">Per i tipi numerici, + calcola la somma dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="05cff-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="05cff-109">Quando uno o entrambi gli operandi sono di tipo stringa, + concatena le rappresentazioni di stringa degli operandi.</span><span class="sxs-lookup"><span data-stu-id="05cff-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="05cff-110">I tipi delegati offrono anche un operatore `+` binario, che esegue la concatenazione dei delegati.</span><span class="sxs-lookup"><span data-stu-id="05cff-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="05cff-111">I tipi definiti dall'utente possono eseguire l'overload degli operatori `+` unari e `+` binari.</span><span class="sxs-lookup"><span data-stu-id="05cff-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="05cff-112">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="05cff-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="05cff-113">Per altre informazioni, vedere [operatore (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="05cff-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="05cff-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="05cff-114">Example</span></span>  
 <span data-ttu-id="05cff-115">[!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="05cff-115">[!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="05cff-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="05cff-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="05cff-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05cff-117">See Also</span></span>  
 <span data-ttu-id="05cff-118">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="05cff-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="05cff-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="05cff-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="05cff-120">[Operatori di C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="05cff-120">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="05cff-121">operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="05cff-121">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)

