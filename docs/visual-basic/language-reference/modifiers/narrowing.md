---
title: Narrowing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: eb5f021371291483b8eb2a13727a9fda94540638
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838849"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="2a195-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a195-102">Narrowing (Visual Basic)</span></span>
<span data-ttu-id="2a195-103">Indica che un operatore di conversione (`CType`) converte una classe o struttura in un tipo che potrebbe non essere in grado di contenere alcuni dei possibili valori della classe o struttura originale.</span><span class="sxs-lookup"><span data-stu-id="2a195-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="2a195-104">Conversione di Narrowing (parola chiave)</span><span class="sxs-lookup"><span data-stu-id="2a195-104">Converting with the Narrowing Keyword</span></span>  
 <span data-ttu-id="2a195-105">Routine di conversione deve specificare `Public Shared` oltre a `Narrowing`.</span><span class="sxs-lookup"><span data-stu-id="2a195-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="2a195-106">Conversioni di Narrowing non sempre riuscire in fase di esecuzione e può avere esito negativo o comportano una perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="2a195-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="2a195-107">Sono esempi `Long` al `Integer`, `String` a `Date`e un tipo di base a un tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="2a195-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="2a195-108">Questa conversione ultimo è narrowing perché il tipo di base potrebbe non contenere tutti i membri del tipo derivato e pertanto non è un'istanza del tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="2a195-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="2a195-109">Se `Option Strict` viene `On`, il codice deve usare `CType` per tutte le conversioni di narrowing.</span><span class="sxs-lookup"><span data-stu-id="2a195-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="2a195-110">Il `Narrowing` parola chiave può essere usata in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="2a195-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="2a195-111">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="2a195-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="2a195-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a195-112">See also</span></span>

- [<span data-ttu-id="2a195-113">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="2a195-113">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="2a195-114">Widening</span><span class="sxs-lookup"><span data-stu-id="2a195-114">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="2a195-115">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="2a195-115">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="2a195-116">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="2a195-116">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="2a195-117">Funzione CType</span><span class="sxs-lookup"><span data-stu-id="2a195-117">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="2a195-118">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="2a195-118">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
