---
title: 'Procedura: forzare il passaggio di un argomento per valore (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 30f5e5fe7b9c92f90673dc99a0e299136a38305b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="e79b9-102">Procedura: forzare il passaggio di un argomento per valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e79b9-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="e79b9-103">La dichiarazione di routine determina il meccanismo di passaggio.</span><span class="sxs-lookup"><span data-stu-id="e79b9-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="e79b9-104">Se un parametro è dichiarato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic è previsto passare all'argomento corrispondente per riferimento.</span><span class="sxs-lookup"><span data-stu-id="e79b9-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="e79b9-105">In questo modo la procedura modificare il valore dell'elemento di programmazione sottostante all'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="e79b9-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="e79b9-106">Se si desidera proteggere l'elemento sottostante da tale modifica, è possibile eseguire l'override di `ByRef` meccanismo di passaggio della procedura chiamata racchiudendo il nome dell'argomento tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="e79b9-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="e79b9-107">Tali parentesi vengono aggiunte le parentesi che racchiude l'elenco di argomenti nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="e79b9-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="e79b9-108">Il codice chiamante non è possibile sostituire un [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) meccanismo.</span><span class="sxs-lookup"><span data-stu-id="e79b9-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="e79b9-109">Per forzare un argomento sia passati per valore</span><span class="sxs-lookup"><span data-stu-id="e79b9-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="e79b9-110">Se il parametro corrispondente viene dichiarato `ByVal` nella procedura, non è necessario eseguire passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e79b9-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="e79b9-111">Visual Basic già prevede di passare l'argomento per valore.</span><span class="sxs-lookup"><span data-stu-id="e79b9-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="e79b9-112">Se il parametro corrispondente viene dichiarato `ByRef` nella procedura, racchiudere l'argomento tra parentesi nella chiamata di procedura.</span><span class="sxs-lookup"><span data-stu-id="e79b9-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e79b9-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="e79b9-113">Example</span></span>  
 <span data-ttu-id="e79b9-114">Nell'esempio seguente esegue l'override di un `ByRef` dichiarazione di parametro.</span><span class="sxs-lookup"><span data-stu-id="e79b9-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="e79b9-115">Nella chiamata che forza `ByVal`, tenere presente i due livelli di parentesi.</span><span class="sxs-lookup"><span data-stu-id="e79b9-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 <span data-ttu-id="e79b9-116">Quando `str` è racchiuso tra parentesi aggiuntive nell'elenco degli argomenti, il `setNewString` routine non può modificare il valore nel codice chiamante, e `MsgBox` Visualizza "Non può essere sostituito se passato ByVal".</span><span class="sxs-lookup"><span data-stu-id="e79b9-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="e79b9-117">Quando `str` non viene racchiusa tra parentesi aggiuntive, la routine può modificarlo, e `MsgBox` Visualizza "This is a un nuovo valore per l'argomento inString".</span><span class="sxs-lookup"><span data-stu-id="e79b9-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e79b9-118">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e79b9-118">Compiling the Code</span></span>  
 <span data-ttu-id="e79b9-119">Quando si passa una variabile per riferimento, è necessario utilizzare il `ByRef` (parola chiave) per specificare tale meccanismo.</span><span class="sxs-lookup"><span data-stu-id="e79b9-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="e79b9-120">Il valore predefinito in Visual Basic consiste nel passare gli argomenti per valore.</span><span class="sxs-lookup"><span data-stu-id="e79b9-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="e79b9-121">Tuttavia, è buona norma includere una programmazione di [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (parola chiave) con ogni parametro dichiarato.</span><span class="sxs-lookup"><span data-stu-id="e79b9-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="e79b9-122">Questo rende il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="e79b9-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e79b9-123">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="e79b9-123">Robust Programming</span></span>  
 <span data-ttu-id="e79b9-124">Se una routine dichiara un parametro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), la corretta esecuzione del codice potrebbe dipendere in grado di modificare l'elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="e79b9-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="e79b9-125">Se il codice chiamante esegue l'override di questo meccanismo di chiamata racchiudendo l'argomento tra parentesi, o se passa un argomento non modificabile, la procedura non è possibile modificare l'elemento sottostante.</span><span class="sxs-lookup"><span data-stu-id="e79b9-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="e79b9-126">Ciò potrebbe produrre risultati imprevisti nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="e79b9-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e79b9-127">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e79b9-127">.NET Framework Security</span></span>  
 <span data-ttu-id="e79b9-128">È sempre un potenziale rischio per consentire a una stored procedure per modificare il valore sottostante a un argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="e79b9-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="e79b9-129">Verificare che si prevede che questo valore da modificare e prepararsi a verificare la validità prima di utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="e79b9-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e79b9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e79b9-130">See Also</span></span>  
 [<span data-ttu-id="e79b9-131">Routine</span><span class="sxs-lookup"><span data-stu-id="e79b9-131">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="e79b9-132">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="e79b9-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="e79b9-133">Procedura: Passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="e79b9-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="e79b9-134">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="e79b9-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="e79b9-135">Differenze tra argomenti modificabili e non modificabili</span><span class="sxs-lookup"><span data-stu-id="e79b9-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="e79b9-136">Differenze tra il passaggio di un argomento per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="e79b9-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="e79b9-137">Procedura: cambiare il valore di un argomento di routine</span><span class="sxs-lookup"><span data-stu-id="e79b9-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="e79b9-138">Procedura: impedire la modifica del valore di un argomento di una routine</span><span class="sxs-lookup"><span data-stu-id="e79b9-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="e79b9-139">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="e79b9-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="e79b9-140">Tipi valore e tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="e79b9-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
