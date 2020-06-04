---
title: 'Procedura: utilizzare una classe che definisce gli operatori'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: fe15e976e6a5469f2a9d1b3521a70a3e1860fdd3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414350"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="11e3e-102">Procedura: utilizzare una classe che definisce gli operatori (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11e3e-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="11e3e-103">Se si usa una classe o una struttura che definisce operatori propri, è possibile accedere a tali operatori da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="11e3e-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="11e3e-104">La definizione di un operatore in una classe o in una struttura è detta anche *Overload* dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="11e3e-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11e3e-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="11e3e-105">Example</span></span>  
 <span data-ttu-id="11e3e-106">Nell'esempio seguente viene eseguita la connessione alla struttura SQL <xref:System.Data.SqlTypes.SqlString> , che definisce gli operatori di conversione ([funzione CType](../../../language-reference/functions/ctype-function.md)) in entrambe le direzioni tra una stringa SQL e una stringa di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="11e3e-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="11e3e-107">Usare `CType(` l' *espressione stringa SQL*, `String)` per convertire una stringa SQL in una stringa di Visual Basic e `CType(` *Visual Basic espressione stringa*, <xref:System.Data.SqlTypes.SqlString> `)` per eseguire la conversione nell'altra direzione.</span><span class="sxs-lookup"><span data-stu-id="11e3e-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="11e3e-108">La <xref:System.Data.SqlTypes.SqlString> struttura definisce un operatore di conversione ([funzione CType](../../../language-reference/functions/ctype-function.md)) da `String` a <xref:System.Data.SqlTypes.SqlString> e un altro da <xref:System.Data.SqlTypes.SqlString> a `String` .</span><span class="sxs-lookup"><span data-stu-id="11e3e-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="11e3e-109">L'istruzione che assegna `title` a `jobTitle` utilizza il primo operatore e la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> chiamata di funzione utilizza la seconda.</span><span class="sxs-lookup"><span data-stu-id="11e3e-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="11e3e-110">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="11e3e-110">Compile the code</span></span>  
 <span data-ttu-id="11e3e-111">Assicurarsi che la classe o la struttura utilizzata definisca l'operatore che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="11e3e-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="11e3e-112">Non presupporre che la classe o la struttura abbia definito ogni operatore disponibile per l'overload.</span><span class="sxs-lookup"><span data-stu-id="11e3e-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="11e3e-113">Per un elenco degli operatori disponibili, vedere [istruzione Operator](../../../language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="11e3e-113">For a list of available operators, see [Operator Statement](../../../language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="11e3e-114">Includere l' `Imports` istruzione appropriata per la stringa SQL all'inizio del file di origine (in questo caso <xref:System.Data.SqlTypes> ).</span><span class="sxs-lookup"><span data-stu-id="11e3e-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="11e3e-115">Il progetto deve avere riferimenti a System. Data e System. XML.</span><span class="sxs-lookup"><span data-stu-id="11e3e-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e3e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11e3e-116">See also</span></span>

- [<span data-ttu-id="11e3e-117">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="11e3e-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="11e3e-118">Procedura: definire un operatore</span><span class="sxs-lookup"><span data-stu-id="11e3e-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="11e3e-119">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="11e3e-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="11e3e-120">Procedura: chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="11e3e-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="11e3e-121">Widening</span><span class="sxs-lookup"><span data-stu-id="11e3e-121">Widening</span></span>](../../../language-reference/modifiers/widening.md)
- [<span data-ttu-id="11e3e-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="11e3e-122">Narrowing</span></span>](../../../language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="11e3e-123">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="11e3e-123">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="11e3e-124">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="11e3e-124">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="11e3e-125">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="11e3e-125">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="11e3e-126">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="11e3e-126">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
