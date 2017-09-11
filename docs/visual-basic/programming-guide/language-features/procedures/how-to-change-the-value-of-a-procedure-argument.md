---
title: 'Procedura: modificare il valore di un argomento di routine (Visual Basic) | Documenti di Microsoft'
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
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
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
ms.openlocfilehash: 3f192d738ca2753cd12b6fffca1f4f94a606a42c
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="22956-102">Procedura: cambiare il valore di un argomento di routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22956-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="22956-103">Quando si chiama una routine, ciascun argomento specificato corrisponde a uno dei parametri definiti nella procedura.</span><span class="sxs-lookup"><span data-stu-id="22956-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="22956-104">In alcuni casi, il codice della routine può modificare il valore sottostante a un argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="22956-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="22956-105">In altri casi, la routine può modificare solo la copia locale di un argomento.</span><span class="sxs-lookup"><span data-stu-id="22956-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="22956-106">Quando si chiama la routine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] crea una copia locale di ogni argomento passato [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="22956-106">When you call the procedure, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="22956-107">Per ogni argomento passato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] fornisce il codice della routine un riferimento diretto all'elemento di programmazione sottostante all'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="22956-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="22956-108">Se l'elemento sottostante nel codice chiamante è modificabile e viene passato l'argomento `ByRef`, il codice della routine può utilizzare il riferimento diretto per modificare il valore dell'elemento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="22956-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="22956-109">La modifica del valore sottostante</span><span class="sxs-lookup"><span data-stu-id="22956-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="22956-110">Per modificare il valore sottostante di un argomento di routine del codice chiamante</span><span class="sxs-lookup"><span data-stu-id="22956-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="22956-111">Nella dichiarazione di routine, specificare [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) per il parametro corrisponde all'argomento.</span><span class="sxs-lookup"><span data-stu-id="22956-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="22956-112">Nel codice chiamante, passare un elemento di programmazione modificabile come argomento.</span><span class="sxs-lookup"><span data-stu-id="22956-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="22956-113">Nel codice chiamante, non racchiudere l'argomento tra parentesi nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="22956-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="22956-114">Nel codice della routine, utilizzare il nome del parametro per assegnare un valore per l'elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="22956-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="22956-115">Vedere l'esempio più in basso per una dimostrazione.</span><span class="sxs-lookup"><span data-stu-id="22956-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="22956-116">Modifica delle copie locali</span><span class="sxs-lookup"><span data-stu-id="22956-116">Changing Local Copies</span></span>  
 <span data-ttu-id="22956-117">Se l'elemento sottostante nel codice chiamante non è modificabile o se viene passato l'argomento `ByVal`, la routine non può modificare il valore del codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="22956-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="22956-118">Tuttavia, la routine può modificare la copia locale di questo tipo di argomento.</span><span class="sxs-lookup"><span data-stu-id="22956-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="22956-119">Per modificare la copia di un argomento di routine nel codice della routine</span><span class="sxs-lookup"><span data-stu-id="22956-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="22956-120">Nella dichiarazione di routine, specificare [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) per il parametro corrisponde all'argomento.</span><span class="sxs-lookup"><span data-stu-id="22956-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="22956-121">-oppure-</span><span class="sxs-lookup"><span data-stu-id="22956-121">-or-</span></span>  
  
     <span data-ttu-id="22956-122">Nel codice chiamante, racchiudere l'argomento tra parentesi nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="22956-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="22956-123">In tal modo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] per passare l'argomento per valore, anche se il parametro corrispondente specifica `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="22956-123">This forces [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="22956-124">Nel codice della routine, utilizzare il nome del parametro per assegnare un valore per la copia locale dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="22956-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="22956-125">Il valore sottostante nel codice chiamante non è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="22956-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22956-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="22956-126">Example</span></span>  
 <span data-ttu-id="22956-127">Nell'esempio seguente illustra due procedure che accettano una variabile di matrice e operano sui relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="22956-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="22956-128">Il `increase` procedura aggiunge semplicemente uno a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="22956-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="22956-129">Il `replace` procedura assegna una nuova matrice al parametro `a()` , quindi aggiunge uno a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="22956-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 <span data-ttu-id="22956-130">[!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="22956-130">[!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]</span></span>  
  
 <span data-ttu-id="22956-131">[!code-vb[VbVbcnProcedures&#36;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="22956-131">[!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]</span></span>  
  
 <span data-ttu-id="22956-132">[!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="22956-132">[!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]</span></span>  
  
 <span data-ttu-id="22956-133">Il primo `MsgBox` chiamata viene visualizzato "dopo Increase (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="22956-133">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="22956-134">Poiché la matrice `n` è un tipo di riferimento, `replace` possibile modificare i relativi membri, anche se è il meccanismo di passaggio `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="22956-134">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="22956-135">Il secondo `MsgBox` chiamata viene visualizzato "dopo Replace (n): 101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="22956-135">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="22956-136">Poiché `n` viene passato `ByRef`, `replace` possibile modificare la variabile `n` nel codice chiamante e assegnare una nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="22956-136">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="22956-137">Poiché `n` è un tipo di riferimento, `replace` inoltre possibile modificare i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="22956-137">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="22956-138">È possibile impedire la procedura di modifica la variabile nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="22956-138">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="22956-139">Vedere [procedura: proteggere un argomento di routine modifica del valore](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="22956-139">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="22956-140">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="22956-140">Compiling the Code</span></span>  
 <span data-ttu-id="22956-141">Quando si passa una variabile per riferimento, è necessario utilizzare il `ByRef` (parola chiave) per specificare tale meccanismo.</span><span class="sxs-lookup"><span data-stu-id="22956-141">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="22956-142">Il valore predefinito in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gli argomenti vengono passati per valore.</span><span class="sxs-lookup"><span data-stu-id="22956-142">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="22956-143">Tuttavia, è buona norma includere una programmazione di [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (parola chiave) con ogni parametro dichiarato.</span><span class="sxs-lookup"><span data-stu-id="22956-143">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="22956-144">In questo modo il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="22956-144">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="22956-145">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="22956-145">.NET Framework Security</span></span>  
 <span data-ttu-id="22956-146">È sempre presente un potenziale rischio per consentire a una procedura per modificare il valore sottostante a un argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="22956-146">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="22956-147">Assicurarsi che si prevede che il valore modificato e in grado di verificare la validità prima di utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="22956-147">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22956-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22956-148">See Also</span></span>  
 <span data-ttu-id="22956-149">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="22956-149">[Procedures](./index.md) </span></span>  
<span data-ttu-id="22956-150"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="22956-150"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="22956-151"> [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="22956-151"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="22956-152"> [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="22956-152"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="22956-153"> [Differenze tra argomenti modificabili e](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="22956-153"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="22956-154"> [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="22956-154"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="22956-155"> [Procedura: proteggere un argomento di routine modifica del valore](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="22956-155"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="22956-156"> [Procedura: forzare un argomento sia passati per valore](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="22956-156"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="22956-157"> [Passaggio di argomenti in base alla posizione e in base al nome](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="22956-157"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="22956-158"> [Tipi valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="22956-158"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
