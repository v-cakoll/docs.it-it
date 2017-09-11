---
title: Passaggio di argomenti per valore e per riferimento (Visual Basic) | Documenti di Microsoft
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
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- passing arguments, by value or by reference
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing, by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
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
ms.openlocfilehash: 44107171d6f24e22614788470c65cf7ad8d28640
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="321d0-102">Passaggio di argomenti per valore e per riferimento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="321d0-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="321d0-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], è possibile passare un argomento a una routine *dal valore* o *per riferimento*.</span><span class="sxs-lookup"><span data-stu-id="321d0-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="321d0-104">Ciò è noto come il *meccanismo di trasferimento*, e determina se la routine può modificare l'elemento di programmazione sottostante all'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="321d0-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="321d0-105">La dichiarazione della routine determina il meccanismo di passaggio per ogni parametro, specificando il [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="321d0-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="321d0-106">Differenze</span><span class="sxs-lookup"><span data-stu-id="321d0-106">Distinctions</span></span>  
 <span data-ttu-id="321d0-107">Quando si passa un argomento a una routine, occorre considerare diverse distinzioni diverse che interagiscono tra loro:</span><span class="sxs-lookup"><span data-stu-id="321d0-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
-   <span data-ttu-id="321d0-108">Se l'elemento di programmazione sottostante è modificabile o meno</span><span class="sxs-lookup"><span data-stu-id="321d0-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="321d0-109">Se l'argomento stesso sia modificabile o meno</span><span class="sxs-lookup"><span data-stu-id="321d0-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="321d0-110">Se l'argomento sia passato per valore o riferimento</span><span class="sxs-lookup"><span data-stu-id="321d0-110">Whether the argument is being passed by value or by reference</span></span>  
  
-   <span data-ttu-id="321d0-111">Se il tipo di dati dell'argomento è un tipo di valore o un tipo di riferimento</span><span class="sxs-lookup"><span data-stu-id="321d0-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="321d0-112">Per ulteriori informazioni, vedere [le differenze tra modificabile e non modificabili argomenti](./differences-between-modifiable-and-nonmodifiable-arguments.md) e [le differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="321d0-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="321d0-113">Meccanismo di passaggio</span><span class="sxs-lookup"><span data-stu-id="321d0-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="321d0-114">È consigliabile scegliere il meccanismo di passaggio attentamente per ogni argomento.</span><span class="sxs-lookup"><span data-stu-id="321d0-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
-   <span data-ttu-id="321d0-115">**Protezione**.</span><span class="sxs-lookup"><span data-stu-id="321d0-115">**Protection**.</span></span> <span data-ttu-id="321d0-116">Nella scelta tra i due meccanismi di passaggio, il criterio più importante è l'esposizione delle variabili chiamanti da modificare.</span><span class="sxs-lookup"><span data-stu-id="321d0-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="321d0-117">Il vantaggio di passare un argomento `ByRef` è che la procedura può restituire un valore per il codice chiamante tramite l'argomento.</span><span class="sxs-lookup"><span data-stu-id="321d0-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="321d0-118">Il vantaggio di passare un argomento `ByVal` è che esso impedisce che la variabile viene modificato dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="321d0-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
-   <span data-ttu-id="321d0-119">**Prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="321d0-119">**Performance**.</span></span> <span data-ttu-id="321d0-120">Sebbene il meccanismo di passaggio può influire sulle prestazioni del codice, la differenza è in genere irrilevante.</span><span class="sxs-lookup"><span data-stu-id="321d0-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="321d0-121">Unica eccezione è un tipo di valore passato `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="321d0-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="321d0-122">In questo caso, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] copia il contenuto di tutti i dati dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="321d0-122">In this case, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] copies the entire data contents of the argument.</span></span> <span data-ttu-id="321d0-123">Pertanto, per un tipo di valore di grandi dimensioni, ad esempio una struttura, può essere più efficiente passare `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="321d0-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="321d0-124">Per i tipi di riferimento, solo il puntatore ai dati viene copiate (quattro byte in piattaforme a 32 bit, otto byte su piattaforme a 64 bit).</span><span class="sxs-lookup"><span data-stu-id="321d0-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="321d0-125">Pertanto, è possibile passare gli argomenti di tipo `String` o `Object` dal valore senza compromettere le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="321d0-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="321d0-126">Determinazione del meccanismo di passaggio</span><span class="sxs-lookup"><span data-stu-id="321d0-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="321d0-127">La dichiarazione della routine specifica il meccanismo di passaggio per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="321d0-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="321d0-128">Il codice chiamante non possono ignorare un `ByVal` meccanismo.</span><span class="sxs-lookup"><span data-stu-id="321d0-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="321d0-129">Se un parametro viene dichiarato con `ByRef`, il codice chiamante può forzare il meccanismo `ByVal` racchiudendo il nome dell'argomento tra parentesi nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="321d0-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="321d0-130">Per ulteriori informazioni, vedere [procedura: forzare un argomento sia passati per valore](./how-to-force-an-argument-to-be-passed-by-value.md).</span><span class="sxs-lookup"><span data-stu-id="321d0-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="321d0-131">Il valore predefinito in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gli argomenti vengono passati per valore.</span><span class="sxs-lookup"><span data-stu-id="321d0-131">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="321d0-132">Quando passare un argomento per valore</span><span class="sxs-lookup"><span data-stu-id="321d0-132">When to Pass an Argument by Value</span></span>  
  
-   <span data-ttu-id="321d0-133">Se l'elemento di codice chiamante sottostante all'argomento non è modificabile, dichiarare il parametro corrispondente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="321d0-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="321d0-134">Codice non è possibile modificare il valore di un elemento non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="321d0-134">No code can change the value of a nonmodifiable element.</span></span>  
  
-   <span data-ttu-id="321d0-135">Se l'elemento sottostante è modificabile, ma non si desidera la procedura per essere in grado di modificare il relativo valore, dichiarare il parametro `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="321d0-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="321d0-136">Solo il codice chiamante può modificare il valore di un elemento modificabile passato per valore.</span><span class="sxs-lookup"><span data-stu-id="321d0-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="321d0-137">Quando un argomento venga passato per riferimento</span><span class="sxs-lookup"><span data-stu-id="321d0-137">When to Pass an Argument by Reference</span></span>  
  
-   <span data-ttu-id="321d0-138">Se la procedura richiede la modifica dell'elemento sottostante nel codice chiamante, dichiarare il parametro corrispondente [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span><span class="sxs-lookup"><span data-stu-id="321d0-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
-   <span data-ttu-id="321d0-139">Se la corretta esecuzione del codice si basa sulla procedura di modifica dell'elemento nel codice chiamante, dichiarare il parametro `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="321d0-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="321d0-140">Se viene passato per valore o se il codice chiamante esegue l'override di `ByRef` meccanismo di passaggio racchiudendo l'argomento tra parentesi, la chiamata di procedura potrebbe produrre risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="321d0-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="321d0-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="321d0-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="321d0-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="321d0-142">Description</span></span>  
 <span data-ttu-id="321d0-143">Nell'esempio seguente viene illustrato come passare gli argomenti per valore e quando passarli per riferimento.</span><span class="sxs-lookup"><span data-stu-id="321d0-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="321d0-144">Procedura `Calculate` ha sia un `ByVal` e `ByRef` parametro.</span><span class="sxs-lookup"><span data-stu-id="321d0-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="321d0-145">Dato un tasso di interesse, `rate`e una somma di denaro, `debt`, l'attività della procedura consiste nel calcolare un nuovo valore per `debt` che rappresenta il risultato dell'applicazione il tasso di interesse per il valore originale di `debt`.</span><span class="sxs-lookup"><span data-stu-id="321d0-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="321d0-146">Poiché `debt` è un `ByRef` parametro, il nuovo totale viene riflesso nel valore dell'argomento nel codice chiamante che corrisponde a `debt`.</span><span class="sxs-lookup"><span data-stu-id="321d0-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="321d0-147">Parametro `rate` è un `ByVal` parametro perché `Calculate` non deve modificare il relativo valore.</span><span class="sxs-lookup"><span data-stu-id="321d0-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="321d0-148">Codice</span><span class="sxs-lookup"><span data-stu-id="321d0-148">Code</span></span>  
 <span data-ttu-id="321d0-149">[!code-vb[VbVbcnProcedures&#74;](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="321d0-149">[!code-vb[VbVbcnProcedures#74](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="321d0-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="321d0-150">See Also</span></span>  
 <span data-ttu-id="321d0-151">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="321d0-151">[Procedures](./index.md) </span></span>  
<span data-ttu-id="321d0-152"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="321d0-152"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="321d0-153"> [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="321d0-153"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="321d0-154"> [Procedura: modificare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="321d0-154"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="321d0-155"> [Procedura: proteggere un argomento di routine modifica del valore](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="321d0-155"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="321d0-156"> [Procedura: forzare un argomento sia passati per valore](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="321d0-156"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="321d0-157"> [Passaggio di argomenti in base alla posizione e in base al nome](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="321d0-157"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="321d0-158"> [Tipi valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="321d0-158"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
