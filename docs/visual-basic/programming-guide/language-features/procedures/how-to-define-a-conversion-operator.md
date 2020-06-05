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
ms.openlocfilehash: 53b0211c6304625edd7ac24fa52ff0c051d8f0a0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388089"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="14b28-102">Procedura: definire un operatore di conversione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14b28-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="14b28-103">Se è stata definita una classe o una struttura, è possibile definire un operatore di conversione dei tipi tra il tipo della classe o della struttura e un altro tipo di dati, ad esempio `Integer` , `Double` o `String` .</span><span class="sxs-lookup"><span data-stu-id="14b28-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="14b28-104">Definire la conversione del tipo come routine della [funzione CType](../../../language-reference/functions/ctype-function.md) all'interno della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="14b28-104">Define the type conversion as a [CType Function](../../../language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="14b28-105">Tutte le procedure di conversione devono essere `Public Shared` e ognuna di esse deve specificare un valore [crescente](../../../language-reference/modifiers/widening.md) o più [piccolo](../../../language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="14b28-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../language-reference/modifiers/widening.md) or [Narrowing](../../../language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="14b28-106">La definizione di un operatore in una classe o in una struttura è detta anche *Overload* dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="14b28-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14b28-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="14b28-107">Example</span></span>  
 <span data-ttu-id="14b28-108">Nell'esempio seguente vengono definiti gli operatori di conversione tra una struttura denominata `digit` e un oggetto `Byte` .</span><span class="sxs-lookup"><span data-stu-id="14b28-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="14b28-109">È possibile testare la struttura `digit` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="14b28-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="14b28-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14b28-110">See also</span></span>

- [<span data-ttu-id="14b28-111">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="14b28-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="14b28-112">Procedura: definire un operatore</span><span class="sxs-lookup"><span data-stu-id="14b28-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="14b28-113">Procedura: chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="14b28-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="14b28-114">Procedura: utilizzare una classe che definisce gli operatori</span><span class="sxs-lookup"><span data-stu-id="14b28-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="14b28-115">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="14b28-115">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="14b28-116">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="14b28-116">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="14b28-117">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="14b28-117">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="14b28-118">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="14b28-118">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="14b28-119">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="14b28-119">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
