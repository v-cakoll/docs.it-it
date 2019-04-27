---
title: 'Procedura: Definire un operatore di conversione (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: cf7bfdd09c7f3429f9c730a7aec34b24af3f2e9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863714"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="33e5e-102">Procedura: Definire un operatore di conversione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33e5e-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="33e5e-103">Se è stato definito una classe o struttura, è possibile definire un operatore di conversione di tipi tra il tipo di classe o struttura e un altro tipo di dati (ad esempio `Integer`, `Double`, o `String`).</span><span class="sxs-lookup"><span data-stu-id="33e5e-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="33e5e-104">Definire la conversione del tipo come un [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure all'interno della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="33e5e-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="33e5e-105">Tutte le routine di conversione devono essere `Public Shared`, e ognuno di essi è necessario specificare [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) oppure [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="33e5e-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="33e5e-106">La definizione di un operatore in una classe o struttura viene definita anche *overload* l'operatore.</span><span class="sxs-lookup"><span data-stu-id="33e5e-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33e5e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="33e5e-107">Example</span></span>  
 <span data-ttu-id="33e5e-108">L'esempio seguente definisce gli operatori di conversione tra una struttura definita `digit` e un `Byte`.</span><span class="sxs-lookup"><span data-stu-id="33e5e-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="33e5e-109">È possibile testare la struttura `digit` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="33e5e-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="33e5e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33e5e-110">See also</span></span>

- [<span data-ttu-id="33e5e-111">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="33e5e-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="33e5e-112">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="33e5e-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="33e5e-113">Procedura: Chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="33e5e-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="33e5e-114">Procedura: Usare una classe che definisce gli operatori</span><span class="sxs-lookup"><span data-stu-id="33e5e-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="33e5e-115">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="33e5e-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="33e5e-116">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="33e5e-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="33e5e-117">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="33e5e-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="33e5e-118">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="33e5e-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="33e5e-119">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="33e5e-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
