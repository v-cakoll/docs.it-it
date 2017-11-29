---
title: + Operatore (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b15d5d1a304569b92b2f811a9ea714e4b30d60d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f5622-102">Operatore + (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f5622-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="f5622-103">L'operatore `+` ha la funzione di operatore unario o binario.</span><span class="sxs-lookup"><span data-stu-id="f5622-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5622-104">Note</span><span class="sxs-lookup"><span data-stu-id="f5622-104">Remarks</span></span>  
 <span data-ttu-id="f5622-105">Gli operatori `+` unari sono predefiniti per tutti i tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="f5622-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="f5622-106">Il risultato di un'operazione `+` unaria su un tipo numerico corrisponde al valore dell'operando.</span><span class="sxs-lookup"><span data-stu-id="f5622-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="f5622-107">Gli operatori `+` binari sono predefiniti per i tipi numerici e stringa.</span><span class="sxs-lookup"><span data-stu-id="f5622-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="f5622-108">Per i tipi numerici, + calcola la somma dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="f5622-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="f5622-109">Quando uno o entrambi gli operandi sono di tipo stringa, + concatena le rappresentazioni di stringa degli operandi.</span><span class="sxs-lookup"><span data-stu-id="f5622-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="f5622-110">I tipi delegati offrono anche un operatore `+` binario, che esegue la concatenazione dei delegati.</span><span class="sxs-lookup"><span data-stu-id="f5622-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="f5622-111">I tipi definiti dall'utente possono eseguire l'overload degli operatori `+` unari e `+` binari.</span><span class="sxs-lookup"><span data-stu-id="f5622-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="f5622-112">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f5622-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="f5622-113">Per altre informazioni, vedere [operatore (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="f5622-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5622-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5622-114">Example</span></span>  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f5622-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f5622-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5622-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5622-116">See Also</span></span>  
 [<span data-ttu-id="f5622-117">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f5622-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f5622-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f5622-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f5622-119">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="f5622-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="f5622-120">operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f5622-120">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)
