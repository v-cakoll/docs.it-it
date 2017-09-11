---
title: 'Procedura: utilizzare una classe che definisce gli operatori (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator procedures, calling
- procedures, operator
- procedures, calling
- examples [Visual Basic], CType
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e4d76788346e08123102d56088c0a1e0f5f2238f
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="b4f2d-102">Procedura: utilizzare una classe che definisce gli operatori (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4f2d-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="b4f2d-103">Se si utilizza una classe o struttura che definisce i propri operatori, è possibile accedere a tali operatori da [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4f2d-103">If you are using a class or structure that defines its own operators, you can access those operators from [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="b4f2d-104">Definisce un operatore su una classe o struttura viene anche chiamato *overload* l'operatore.</span><span class="sxs-lookup"><span data-stu-id="b4f2d-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4f2d-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4f2d-105">Example</span></span>  
 <span data-ttu-id="b4f2d-106">Nell'esempio seguente consente di accedere alla struttura SQL <xref:System.Data.SqlTypes.SqlString>, che definisce gli operatori di conversione ([funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md)) in entrambe le direzioni tra una stringa SQL e un [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] stringa.</xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="b4f2d-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string.</span></span> <span data-ttu-id="b4f2d-107">Utilizzare `CType(` *espressione stringa SQL*, `String)` per convertire una stringa SQL a un [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] stringa, e `CType(` *espressione stringa Visual Basic*, <xref:System.Data.SqlTypes.SqlString> `)` da convertire in altra direzione.</xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="b4f2d-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 <span data-ttu-id="b4f2d-108">[!code-vb[&#30; VbVbcnProcedures](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4f2d-108">[!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]</span></span>  
  
 <span data-ttu-id="b4f2d-109">[!code-vb[VbVbcnProcedures&#31;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b4f2d-109">[!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]</span></span>  
  
 <span data-ttu-id="b4f2d-110">Il <xref:System.Data.SqlTypes.SqlString>struttura definisce un operatore di conversione ([CType (funzione)](../../../../visual-basic/language-reference/functions/ctype-function.md)) da `String` a <xref:System.Data.SqlTypes.SqlString>e un altro da <xref:System.Data.SqlTypes.SqlString>a `String`.</xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="b4f2d-110">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="b4f2d-111">L'istruzione che assegna `title` a `jobTitle` utilizza il primo operatore e <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>chiamata di funzione utilizza il secondo.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="b4f2d-111">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b4f2d-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b4f2d-112">Compiling the Code</span></span>  
 <span data-ttu-id="b4f2d-113">Assicurarsi che la classe o struttura in uso definisce l'operatore da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b4f2d-113">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="b4f2d-114">Non presupporre che la classe o struttura è definita tutti gli operatori disponibili per eseguire l'overload.</span><span class="sxs-lookup"><span data-stu-id="b4f2d-114">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="b4f2d-115">Per un elenco di operatori disponibili, vedere [Operator (istruzione)](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b4f2d-115">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="b4f2d-116">Includere l'appropriata `Imports` istruzione per la stringa SQL all'inizio del file di origine (in questo caso <xref:System.Data.SqlTypes>).</xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="b4f2d-116">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="b4f2d-117">Il progetto deve disporre di riferimenti a System. Data e System. Xml.</span><span class="sxs-lookup"><span data-stu-id="b4f2d-117">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f2d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4f2d-118">See Also</span></span>  
 <span data-ttu-id="b4f2d-119">[Routine di operatore](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="b4f2d-119">[Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="b4f2d-120"> [Procedura: definire un operatore](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="b4f2d-120"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="b4f2d-121"> [Procedura: definire un operatore di conversione](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="b4f2d-121"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="b4f2d-122"> [Procedura: chiamare una routine di operatore](./how-to-call-an-operator-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="b4f2d-122"> [How to: Call an Operator Procedure](./how-to-call-an-operator-procedure.md) </span></span>  
<span data-ttu-id="b4f2d-123"> [Ampliamento](../../../../visual-basic/language-reference/modifiers/widening.md) </span><span class="sxs-lookup"><span data-stu-id="b4f2d-123"> [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) </span></span>  
<span data-ttu-id="b4f2d-124"> [Restrizione](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span><span class="sxs-lookup"><span data-stu-id="b4f2d-124"> [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span></span>  
<span data-ttu-id="b4f2d-125"> [Istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b4f2d-125"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="b4f2d-126"> [Procedura: dichiarare una struttura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span><span class="sxs-lookup"><span data-stu-id="b4f2d-126"> [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span></span>  
<span data-ttu-id="b4f2d-127"> [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="b4f2d-127"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="b4f2d-128"> [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="b4f2d-128"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
