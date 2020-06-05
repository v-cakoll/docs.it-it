---
title: 'Procedura: definire un operatore'
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
ms.openlocfilehash: 49b9c8d1a6db56a56b50c16b4a6bb5b928df6c7d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388037"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="f8d8a-102">Procedura: definire un operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8d8a-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="f8d8a-103">Se è stata definita una classe o una struttura, è possibile definire il comportamento di un operatore standard, ad esempio `*` , `<>` o, `And` quando uno o entrambi gli operandi sono del tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="f8d8a-104">Definire l'operatore standard come routine di operatore all'interno della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="f8d8a-105">Tutte le routine degli operatori devono essere `Public` `Shared` .</span><span class="sxs-lookup"><span data-stu-id="f8d8a-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="f8d8a-106">La definizione di un operatore in una classe o in una struttura è detta anche *Overload* dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8d8a-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8d8a-107">Example</span></span>  
 <span data-ttu-id="f8d8a-108">Nell'esempio seguente viene definito l' `+` operatore per una struttura denominata `height` .</span><span class="sxs-lookup"><span data-stu-id="f8d8a-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="f8d8a-109">La struttura Usa altezze misurate in piedi e pollici.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="f8d8a-110">Un *pollice* è 2,54 centimetri e un *piede* è 12 pollici.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="f8d8a-111">Per garantire la normalizzazione dei valori (pollici < 12,0), il costruttore esegue l'aritmetica *modulo* 12.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="f8d8a-112">L' `+` operatore utilizza il costruttore per generare valori normalizzati.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 <span data-ttu-id="f8d8a-113">È possibile testare la struttura `height` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a><span data-ttu-id="f8d8a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8d8a-114">See also</span></span>

- [<span data-ttu-id="f8d8a-115">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="f8d8a-115">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="f8d8a-116">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="f8d8a-116">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="f8d8a-117">Procedura: chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="f8d8a-117">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="f8d8a-118">Procedura: utilizzare una classe che definisce gli operatori</span><span class="sxs-lookup"><span data-stu-id="f8d8a-118">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="f8d8a-119">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="f8d8a-119">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="f8d8a-120">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="f8d8a-120">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="f8d8a-121">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="f8d8a-121">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="f8d8a-122">Operatore Mod</span><span class="sxs-lookup"><span data-stu-id="f8d8a-122">Mod Operator</span></span>](../../../language-reference/operators/mod-operator.md)
