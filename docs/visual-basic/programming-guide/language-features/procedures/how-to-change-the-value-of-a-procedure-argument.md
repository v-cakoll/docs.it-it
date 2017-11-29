---
title: 'Procedura: cambiare il valore di un argomento di routine (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ba23c8f0b4b0b6e751546019af902a6305b9ef53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="fd146-102">Procedura: cambiare il valore di un argomento di routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd146-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="fd146-103">Quando si chiama una routine, ogni argomento che è fornire corrisponde a uno dei parametri definiti nella procedura.</span><span class="sxs-lookup"><span data-stu-id="fd146-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="fd146-104">In alcuni casi, il codice della stored procedure può modificare il valore sottostante a un argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="fd146-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="fd146-105">In altri casi, la routine può modificare solo la copia locale di un argomento.</span><span class="sxs-lookup"><span data-stu-id="fd146-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="fd146-106">Quando si chiama la routine, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] crea una copia locale di ogni argomento passato [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="fd146-106">When you call the procedure, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="fd146-107">Per ogni argomento passato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] fornisce il codice della routine un riferimento diretto all'elemento di programmazione sottostante all'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="fd146-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="fd146-108">Se l'elemento sottostante nel codice chiamante è modificabile e viene passato l'argomento `ByRef`, il codice della stored procedure è possibile utilizzare il riferimento diretto per modificare il valore dell'elemento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="fd146-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="fd146-109">La modifica del valore sottostante</span><span class="sxs-lookup"><span data-stu-id="fd146-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="fd146-110">Per modificare il valore sottostante di un argomento di routine nel codice chiamante</span><span class="sxs-lookup"><span data-stu-id="fd146-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="fd146-111">Nella dichiarazione di routine, specificare [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) per il parametro corrisponde all'argomento.</span><span class="sxs-lookup"><span data-stu-id="fd146-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="fd146-112">Nel codice chiamante, passare un elemento di programmazione modificabile come argomento.</span><span class="sxs-lookup"><span data-stu-id="fd146-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="fd146-113">Nel codice chiamante, non racchiudere l'argomento tra parentesi nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="fd146-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="fd146-114">Nel codice della procedura, utilizzare il nome del parametro per assegnare un valore per l'elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="fd146-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="fd146-115">Vedere l'esempio più in basso per una dimostrazione.</span><span class="sxs-lookup"><span data-stu-id="fd146-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="fd146-116">Modifica delle copie locali</span><span class="sxs-lookup"><span data-stu-id="fd146-116">Changing Local Copies</span></span>  
 <span data-ttu-id="fd146-117">Se l'elemento sottostante nel codice chiamante non è modificabile, o se l'argomento viene passato `ByVal`, la procedura non è possibile modificarne il valore nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="fd146-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="fd146-118">Tuttavia, la procedura è possibile modificare la copia locale di questo tipo di argomento.</span><span class="sxs-lookup"><span data-stu-id="fd146-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="fd146-119">Per modificare la copia di un argomento di routine nel codice della procedura</span><span class="sxs-lookup"><span data-stu-id="fd146-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="fd146-120">Nella dichiarazione di routine, specificare [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) per il parametro corrisponde all'argomento.</span><span class="sxs-lookup"><span data-stu-id="fd146-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="fd146-121">-oppure-</span><span class="sxs-lookup"><span data-stu-id="fd146-121">-or-</span></span>  
  
     <span data-ttu-id="fd146-122">Nel codice chiamante, racchiudere l'argomento tra parentesi nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="fd146-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="fd146-123">In questo modo [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] per passare l'argomento per valore, anche se il parametro corrispondente specifica `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="fd146-123">This forces [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="fd146-124">Nel codice della procedura, utilizzare il nome del parametro per assegnare un valore per la copia locale dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="fd146-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="fd146-125">Il valore sottostante nel codice chiamante non è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="fd146-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd146-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd146-126">Example</span></span>  
 <span data-ttu-id="fd146-127">Nell'esempio seguente mostra due procedure che accettano una variabile di matrice e operano sui relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="fd146-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="fd146-128">Il `increase` procedura aggiunge semplicemente uno per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="fd146-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="fd146-129">Il `replace` procedure assegna una nuova matrice al parametro `a()` , quindi aggiunge uno per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="fd146-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 <span data-ttu-id="fd146-130">Il primo `MsgBox` chiamata viene visualizzato "dopo Increase (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="fd146-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="fd146-131">Poiché la matrice `n` è un tipo riferimento, `replace` possibile modificare i relativi membri, anche se è il meccanismo di passaggio `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="fd146-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="fd146-132">Il secondo `MsgBox` chiamata viene visualizzato "dopo Replace (n): 101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="fd146-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="fd146-133">Poiché `n` viene passato `ByRef`, `replace` possibile modificare la variabile `n` nel codice chiamante e assegnare una nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="fd146-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="fd146-134">Poiché `n` è un tipo riferimento, `replace` inoltre possibile modificare i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="fd146-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="fd146-135">È possibile impedire la procedura di modifica la variabile nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="fd146-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="fd146-136">Vedere [procedura: proteggere un argomento di routine modifica del valore](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="fd146-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fd146-137">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="fd146-137">Compiling the Code</span></span>  
 <span data-ttu-id="fd146-138">Quando si passa una variabile per riferimento, è necessario utilizzare il `ByRef` (parola chiave) per specificare tale meccanismo.</span><span class="sxs-lookup"><span data-stu-id="fd146-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="fd146-139">Il valore predefinito in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] gli argomenti vengono passati per valore.</span><span class="sxs-lookup"><span data-stu-id="fd146-139">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="fd146-140">Tuttavia, è buona norma includere una programmazione di [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (parola chiave) con ogni parametro dichiarato.</span><span class="sxs-lookup"><span data-stu-id="fd146-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="fd146-141">Questo rende il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="fd146-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="fd146-142">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fd146-142">.NET Framework Security</span></span>  
 <span data-ttu-id="fd146-143">È sempre un potenziale rischio per consentire a una stored procedure per modificare il valore sottostante a un argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="fd146-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="fd146-144">Verificare che si prevede che questo valore da modificare e prepararsi a verificare la validità prima di utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="fd146-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd146-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd146-145">See Also</span></span>  
 [<span data-ttu-id="fd146-146">Routine</span><span class="sxs-lookup"><span data-stu-id="fd146-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="fd146-147">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="fd146-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="fd146-148">Procedura: Passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="fd146-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="fd146-149">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="fd146-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="fd146-150">Differenze tra argomenti modificabili e non modificabili</span><span class="sxs-lookup"><span data-stu-id="fd146-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="fd146-151">Differenze tra il passaggio di un argomento per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="fd146-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="fd146-152">Procedura: impedire la modifica del valore di un argomento di una routine</span><span class="sxs-lookup"><span data-stu-id="fd146-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="fd146-153">Procedura: forzare il passaggio di un argomento per valore</span><span class="sxs-lookup"><span data-stu-id="fd146-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="fd146-154">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="fd146-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="fd146-155">Tipi valore e tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="fd146-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
