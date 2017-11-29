---
title: 'Procedura: definire un operatore di conversione (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b0f9e63ba039a48226186fa4ce118d3e47b5673e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="0961c-102">Procedura: definire un operatore di conversione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0961c-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="0961c-103">Se è stato definito una classe o struttura, è possibile definire un operatore di conversione di tipi tra il tipo di classe o struttura e un altro tipo di dati (ad esempio `Integer`, `Double`, o `String`).</span><span class="sxs-lookup"><span data-stu-id="0961c-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="0961c-104">Definire la conversione del tipo come un [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) routine all'interno della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="0961c-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="0961c-105">Tutte le routine di conversione devono essere `Public Shared`, e ognuno di essi è necessario specificare [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) o [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="0961c-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="0961c-106">La definizione di un operatore in una classe o struttura viene definita anche *overload* l'operatore.</span><span class="sxs-lookup"><span data-stu-id="0961c-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0961c-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="0961c-107">Example</span></span>  
 <span data-ttu-id="0961c-108">L'esempio seguente definisce gli operatori di conversione tra una struttura denominata `digit` e `Byte`.</span><span class="sxs-lookup"><span data-stu-id="0961c-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_1.vb)]  
  
 <span data-ttu-id="0961c-109">È possibile testare la struttura `digit` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0961c-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0961c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0961c-110">See Also</span></span>  
 [<span data-ttu-id="0961c-111">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="0961c-111">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="0961c-112">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="0961c-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="0961c-113">Procedura: Chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="0961c-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="0961c-114">Procedura: Usare una classe che definisce gli operatori</span><span class="sxs-lookup"><span data-stu-id="0961c-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)  
 [<span data-ttu-id="0961c-115">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="0961c-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="0961c-116">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="0961c-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="0961c-117">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="0961c-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="0961c-118">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="0961c-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="0961c-119">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="0961c-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
