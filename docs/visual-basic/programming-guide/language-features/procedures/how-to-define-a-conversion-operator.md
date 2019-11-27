---
title: 'Procedura: definire un operatore di conversione'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344891"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="5ec44-102">Procedura: definire un operatore di conversione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ec44-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="5ec44-103">Se è stata definita una classe o una struttura, è possibile definire un operatore di conversione dei tipi tra il tipo della classe o della struttura e un altro tipo di dati (ad esempio `Integer`, `Double`o `String`).</span><span class="sxs-lookup"><span data-stu-id="5ec44-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="5ec44-104">Definire la conversione del tipo come routine della [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) all'interno della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="5ec44-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="5ec44-105">Tutte le procedure di conversione devono essere `Public Shared`te, ognuna delle quali deve specificare un valore [crescente](../../../../visual-basic/language-reference/modifiers/widening.md) o più [piccolo](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="5ec44-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="5ec44-106">La definizione di un operatore in una classe o in una struttura è detta anche *Overload* dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="5ec44-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ec44-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="5ec44-107">Example</span></span>  
 <span data-ttu-id="5ec44-108">Nell'esempio seguente vengono definiti gli operatori di conversione tra una struttura denominata `digit` e una `Byte`.</span><span class="sxs-lookup"><span data-stu-id="5ec44-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="5ec44-109">È possibile testare la struttura `digit` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="5ec44-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="5ec44-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ec44-110">See also</span></span>

- [<span data-ttu-id="5ec44-111">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="5ec44-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="5ec44-112">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="5ec44-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="5ec44-113">Procedura: Chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="5ec44-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="5ec44-114">Procedura: Usare una classe che definisce gli operatori</span><span class="sxs-lookup"><span data-stu-id="5ec44-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="5ec44-115">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="5ec44-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="5ec44-116">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="5ec44-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="5ec44-117">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="5ec44-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="5ec44-118">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="5ec44-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="5ec44-119">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="5ec44-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
