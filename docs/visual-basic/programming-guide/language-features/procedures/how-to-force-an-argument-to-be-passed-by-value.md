---
title: 'Procedura: forzare un argomento sia passati per valore (Visual Basic) | Documenti di Microsoft'
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
- procedures, arguments
- procedures, parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], in parentheses
- procedure arguments, in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: 16
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
ms.openlocfilehash: b151c319489ccda357faa082ce0b3c1addad0458
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="66e4f-102">Procedura: forzare il passaggio di un argomento per valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66e4f-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="66e4f-103">La dichiarazione della routine determina il meccanismo di passaggio.</span><span class="sxs-lookup"><span data-stu-id="66e4f-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="66e4f-104">Se un parametro dichiarato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] prevede di passare all'argomento corrispondente per riferimento.</span><span class="sxs-lookup"><span data-stu-id="66e4f-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="66e4f-105">In questo modo la procedura modificare il valore dell'elemento di programmazione sottostante all'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="66e4f-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="66e4f-106">Se si desidera proteggere l'elemento sottostante da tale modifica, è possibile eseguire l'override di `ByRef` meccanismo di passaggio della procedura chiamata racchiudendo il nome dell'argomento tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="66e4f-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="66e4f-107">Tali parentesi vengono aggiunte le parentesi che racchiudono l'elenco di argomenti nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="66e4f-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="66e4f-108">Il codice chiamante non può ignorare un [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) meccanismo.</span><span class="sxs-lookup"><span data-stu-id="66e4f-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="66e4f-109">Per forzare un argomento sia passati per valore</span><span class="sxs-lookup"><span data-stu-id="66e4f-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="66e4f-110">Se viene dichiarato il parametro corrispondente `ByVal` nella procedura, non è necessario eseguire passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="66e4f-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="66e4f-111">già prevede di passare l'argomento per valore.</span><span class="sxs-lookup"><span data-stu-id="66e4f-111"> already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="66e4f-112">Se viene dichiarato il parametro corrispondente `ByRef` nella routine, racchiudere l'argomento tra parentesi nella chiamata di procedura.</span><span class="sxs-lookup"><span data-stu-id="66e4f-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66e4f-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="66e4f-113">Example</span></span>  
 <span data-ttu-id="66e4f-114">Nell'esempio seguente esegue l'override di un `ByRef` dichiarazione del parametro.</span><span class="sxs-lookup"><span data-stu-id="66e4f-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="66e4f-115">Nella chiamata che forza `ByVal`, notare i due livelli di parentesi.</span><span class="sxs-lookup"><span data-stu-id="66e4f-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 <span data-ttu-id="66e4f-116">[!code-vb[VbVbcnProcedures&#39;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="66e4f-116">[!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]</span></span>  
  
 <span data-ttu-id="66e4f-117">[!code-vb[&#40; VbVbcnProcedures](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="66e4f-117">[!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]</span></span>  
  
 <span data-ttu-id="66e4f-118">Quando `str` è racchiuso tra parentesi aggiuntive nell'elenco degli argomenti, il `setNewString` routine non può modificare il valore del codice chiamante e `MsgBox` Visualizza "Non può essere sostituito se passato ByVal".</span><span class="sxs-lookup"><span data-stu-id="66e4f-118">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="66e4f-119">Quando `str` non viene racchiusa tra parentesi aggiuntive, la routine può modificare, e `MsgBox` Visualizza "È un nuovo valore per l'argomento inString".</span><span class="sxs-lookup"><span data-stu-id="66e4f-119">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="66e4f-120">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="66e4f-120">Compiling the Code</span></span>  
 <span data-ttu-id="66e4f-121">Quando si passa una variabile per riferimento, è necessario utilizzare il `ByRef` (parola chiave) per specificare tale meccanismo.</span><span class="sxs-lookup"><span data-stu-id="66e4f-121">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="66e4f-122">Il valore predefinito in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gli argomenti vengono passati per valore.</span><span class="sxs-lookup"><span data-stu-id="66e4f-122">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="66e4f-123">Tuttavia, è buona norma includere una programmazione di [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (parola chiave) con ogni parametro dichiarato.</span><span class="sxs-lookup"><span data-stu-id="66e4f-123">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="66e4f-124">In questo modo il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="66e4f-124">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="66e4f-125">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="66e4f-125">Robust Programming</span></span>  
 <span data-ttu-id="66e4f-126">Se una routine dichiara un parametro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), la corretta esecuzione del codice potrebbe dipendere la possibilità di modificare l'elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="66e4f-126">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="66e4f-127">Se il codice chiamante esegue l'override di questo meccanismo di chiamata racchiudendo l'argomento tra parentesi, o se viene passato un argomento non modificabile, la routine non può modificare l'elemento sottostante.</span><span class="sxs-lookup"><span data-stu-id="66e4f-127">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="66e4f-128">Ciò potrebbe produrre risultati imprevisti nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="66e4f-128">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="66e4f-129">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="66e4f-129">.NET Framework Security</span></span>  
 <span data-ttu-id="66e4f-130">È sempre presente un potenziale rischio per consentire a una procedura per modificare il valore sottostante a un argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="66e4f-130">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="66e4f-131">Assicurarsi che si prevede che il valore modificato e in grado di verificare la validità prima di utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="66e4f-131">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66e4f-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66e4f-132">See Also</span></span>  
 <span data-ttu-id="66e4f-133">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="66e4f-133">[Procedures](./index.md) </span></span>  
<span data-ttu-id="66e4f-134"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="66e4f-134"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="66e4f-135"> [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="66e4f-135"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="66e4f-136"> [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="66e4f-136"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="66e4f-137"> [Differenze tra argomenti modificabili e](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="66e4f-137"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="66e4f-138"> [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="66e4f-138"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="66e4f-139"> [Procedura: modificare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="66e4f-139"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="66e4f-140"> [Procedura: proteggere un argomento di routine modifica del valore](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="66e4f-140"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="66e4f-141"> [Passaggio di argomenti in base alla posizione e in base al nome](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="66e4f-141"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="66e4f-142"> [Tipi valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="66e4f-142"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
