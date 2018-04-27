---
title: 'Procedura: utilizzare una classe che definisce gli operatori (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e0bcfaeca638dfabb841a9e935b872f76fdf957
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="7c7cb-102">Procedura: utilizzare una classe che definisce gli operatori (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c7cb-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="7c7cb-103">Se si utilizza una classe o struttura che definisce i propri operatori, è possibile accedere a tali operatori da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7c7cb-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="7c7cb-104">La definizione di un operatore in una classe o struttura viene definita anche *overload* l'operatore.</span><span class="sxs-lookup"><span data-stu-id="7c7cb-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c7cb-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c7cb-105">Example</span></span>  
 <span data-ttu-id="7c7cb-106">Nell'esempio seguente consente di accedere alla struttura SQL <xref:System.Data.SqlTypes.SqlString>, che definisce gli operatori di conversione ([CType (funzione)](../../../../visual-basic/language-reference/functions/ctype-function.md)) in entrambe le direzioni tra una stringa SQL e una stringa di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7c7cb-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="7c7cb-107">Uso `CType(` *espressione stringa SQL*, `String)` per convertire una stringa SQL in una stringa in Visual Basic, e `CType(` *espressione stringa Visual Basic*, <xref:System.Data.SqlTypes.SqlString> `)` da convertire in altra direzione.</span><span class="sxs-lookup"><span data-stu-id="7c7cb-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 <span data-ttu-id="7c7cb-108">Il <xref:System.Data.SqlTypes.SqlString> struttura definisce un operatore di conversione ([CType (funzione)](../../../../visual-basic/language-reference/functions/ctype-function.md)) da `String` a <xref:System.Data.SqlTypes.SqlString> e un altro da <xref:System.Data.SqlTypes.SqlString> a `String`.</span><span class="sxs-lookup"><span data-stu-id="7c7cb-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="7c7cb-109">L'istruzione che assegna `title` a `jobTitle` utilizza il primo operatore e <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> chiamata di funzione utilizza il secondo.</span><span class="sxs-lookup"><span data-stu-id="7c7cb-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7c7cb-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7c7cb-110">Compiling the Code</span></span>  
 <span data-ttu-id="7c7cb-111">Assicurarsi che la classe o struttura in uso definisce l'operatore a cui che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="7c7cb-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="7c7cb-112">Non presupporre che la classe o struttura sia definito tutti gli operatori disponibili per l'overload.</span><span class="sxs-lookup"><span data-stu-id="7c7cb-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="7c7cb-113">Per un elenco di operatori disponibili, vedere [Operator (istruzione)](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7c7cb-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="7c7cb-114">Includere appropriata `Imports` istruzione per la stringa SQL all'inizio del file di origine (in questo caso <xref:System.Data.SqlTypes>).</span><span class="sxs-lookup"><span data-stu-id="7c7cb-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="7c7cb-115">Il progetto deve includere riferimenti a System. Data e System. Xml.</span><span class="sxs-lookup"><span data-stu-id="7c7cb-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c7cb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c7cb-116">See Also</span></span>  
 [<span data-ttu-id="7c7cb-117">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="7c7cb-117">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="7c7cb-118">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="7c7cb-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="7c7cb-119">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="7c7cb-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="7c7cb-120">Procedura: Chiamare una routine di operatore</span><span class="sxs-lookup"><span data-stu-id="7c7cb-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="7c7cb-121">Widening</span><span class="sxs-lookup"><span data-stu-id="7c7cb-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="7c7cb-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="7c7cb-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="7c7cb-123">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="7c7cb-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="7c7cb-124">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="7c7cb-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="7c7cb-125">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="7c7cb-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="7c7cb-126">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="7c7cb-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
