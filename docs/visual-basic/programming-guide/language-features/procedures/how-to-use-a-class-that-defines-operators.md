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
ms.openlocfilehash: 455c839702b90738ec5aea37c1b09d72eba42ff4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347884"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="e8d55-102">Procedura: utilizzare una classe che definisce gli operatori (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8d55-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="e8d55-103">Se si usa una classe o una struttura che definisce operatori propri, è possibile accedere a tali operatori da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e8d55-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="e8d55-104">La definizione di un operatore in una classe o in una struttura è detta anche *Overload* dell'operatore.</span><span class="sxs-lookup"><span data-stu-id="e8d55-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8d55-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8d55-105">Example</span></span>  
 <span data-ttu-id="e8d55-106">Nell'esempio seguente viene accesso alla struttura SQL <xref:System.Data.SqlTypes.SqlString>, che definisce gli operatori di conversione ([funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) in entrambe le direzioni tra una stringa SQL e una stringa di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e8d55-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="e8d55-107">Usare `CType(`*espressione stringa sql*`String)` per convertire una stringa SQL in una stringa di Visual Basic e `CType(`*Visual Basic espressione stringa*, <xref:System.Data.SqlTypes.SqlString>`)` da convertire nell'altra direzione.</span><span class="sxs-lookup"><span data-stu-id="e8d55-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="e8d55-108">La struttura <xref:System.Data.SqlTypes.SqlString> definisce un operatore di conversione ([funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) da `String` a <xref:System.Data.SqlTypes.SqlString> e un altro da <xref:System.Data.SqlTypes.SqlString> a `String`.</span><span class="sxs-lookup"><span data-stu-id="e8d55-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="e8d55-109">L'istruzione che assegna `title` a `jobTitle` usa il primo operatore e la chiamata di funzione <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> usa il secondo.</span><span class="sxs-lookup"><span data-stu-id="e8d55-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="e8d55-110">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="e8d55-110">Compile the code</span></span>  
 <span data-ttu-id="e8d55-111">Assicurarsi che la classe o la struttura utilizzata definisca l'operatore che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e8d55-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="e8d55-112">Non presupporre che la classe o la struttura abbia definito ogni operatore disponibile per l'overload.</span><span class="sxs-lookup"><span data-stu-id="e8d55-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="e8d55-113">Per un elenco degli operatori disponibili, vedere [istruzione Operator](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e8d55-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="e8d55-114">Includere l'istruzione `Imports` appropriata per la stringa SQL all'inizio del file di origine (in questo caso <xref:System.Data.SqlTypes>).</span><span class="sxs-lookup"><span data-stu-id="e8d55-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="e8d55-115">Il progetto deve avere riferimenti a System. Data e System. XML.</span><span class="sxs-lookup"><span data-stu-id="e8d55-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d55-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8d55-116">See also</span></span>

- [<span data-ttu-id="e8d55-117">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="e8d55-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="e8d55-118">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="e8d55-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="e8d55-119">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="e8d55-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="e8d55-120">Procedura: Chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="e8d55-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="e8d55-121">Widening</span><span class="sxs-lookup"><span data-stu-id="e8d55-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="e8d55-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="e8d55-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="e8d55-123">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="e8d55-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="e8d55-124">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="e8d55-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="e8d55-125">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="e8d55-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="e8d55-126">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="e8d55-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
