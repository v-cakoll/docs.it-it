---
title: 'Procedura: Definire un operatore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: 14aa25de78eb357f8474d3828aa45e48e7a4f9c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863845"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="0eb97-102">Procedura: Definire un operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eb97-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="0eb97-103">Se è stato definito una classe o struttura, è possibile definire il comportamento di un operatore standard (ad esempio `*`, `<>`, o `And`) quando uno o entrambi gli operandi sono del tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="0eb97-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="0eb97-104">Definire l'operatore standard come una routine di operatore all'interno della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="0eb97-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="0eb97-105">Tutte le routine di operatore devono essere `Public` `Shared`.</span><span class="sxs-lookup"><span data-stu-id="0eb97-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="0eb97-106">La definizione di un operatore in una classe o struttura viene definita anche *overload* l'operatore.</span><span class="sxs-lookup"><span data-stu-id="0eb97-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0eb97-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="0eb97-107">Example</span></span>  
 <span data-ttu-id="0eb97-108">L'esempio seguente definisce la `+` chiamato operatore per una struttura `height`.</span><span class="sxs-lookup"><span data-stu-id="0eb97-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="0eb97-109">La struttura Usa misurata in metri e centimetri di altezza.</span><span class="sxs-lookup"><span data-stu-id="0eb97-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="0eb97-110">Uno *pollice* è 2,54 centimetri e uno *piede* 12 pollici.</span><span class="sxs-lookup"><span data-stu-id="0eb97-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="0eb97-111">Per assicurarsi che i valori normalizzati (pollici < 12.0), esegue il costruttore *modulo* 12 aritmetico.</span><span class="sxs-lookup"><span data-stu-id="0eb97-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="0eb97-112">Il `+` operatore viene utilizzato il costruttore per generare i valori normalizzati.</span><span class="sxs-lookup"><span data-stu-id="0eb97-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 <span data-ttu-id="0eb97-113">È possibile testare la struttura `height` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0eb97-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a><span data-ttu-id="0eb97-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0eb97-114">See also</span></span>

- [<span data-ttu-id="0eb97-115">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="0eb97-115">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="0eb97-116">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="0eb97-116">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="0eb97-117">Procedura: Chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="0eb97-117">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="0eb97-118">Procedura: Usare una classe che definisce gli operatori</span><span class="sxs-lookup"><span data-stu-id="0eb97-118">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="0eb97-119">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="0eb97-119">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="0eb97-120">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="0eb97-120">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="0eb97-121">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="0eb97-121">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="0eb97-122">Operatore Mod</span><span class="sxs-lookup"><span data-stu-id="0eb97-122">Mod Operator</span></span>](../../../../visual-basic/language-reference/operators/mod-operator.md)
