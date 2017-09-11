---
title: 'Procedura: proteggere un argomento di routine modifica del valore (Visual Basic) | Documenti di Microsoft'
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
- procedures, calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
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
ms.openlocfilehash: db40b3426256e7789a5273ab4d0afc8d5b47c8a7
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="8e388-102">Procedura: impedire la modifica del valore di un argomento di una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e388-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="8e388-103">Se una routine dichiara un parametro come [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] fornisce il codice della routine un riferimento diretto all'elemento di programmazione sottostante all'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8e388-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="8e388-104">In questo modo la procedura per modificare il valore sottostante all'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8e388-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="8e388-105">In alcuni casi potrebbe essere necessario il codice chiamante per proteggersi da tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="8e388-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="8e388-106">È possibile proteggere sempre un argomento da modifica dichiarando il parametro corrispondente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) nella procedura.</span><span class="sxs-lookup"><span data-stu-id="8e388-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="8e388-107">Se si desidera essere in grado di modificare un determinato argomento in alcuni casi, ma non altri, è possibile dichiarare `ByRef` e consentire al codice chiamante di determinare il meccanismo di passaggio in ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="8e388-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="8e388-108">Questo avviene racchiudere l'argomento corrispondente tra parentesi per passarlo come valore, viene racchiuso o meno tra parentesi essere passato per riferimento.</span><span class="sxs-lookup"><span data-stu-id="8e388-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="8e388-109">Per ulteriori informazioni, vedere [procedura: forzare un argomento sia passati per valore](./how-to-force-an-argument-to-be-passed-by-value.md).</span><span class="sxs-lookup"><span data-stu-id="8e388-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e388-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="8e388-110">Example</span></span>  
 <span data-ttu-id="8e388-111">Nell'esempio seguente illustra due procedure che accettano una variabile di matrice e operano sui relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="8e388-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="8e388-112">Il `increase` procedura aggiunge semplicemente uno a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="8e388-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="8e388-113">Il `replace` procedura assegna una nuova matrice al parametro `a()` , quindi aggiunge uno a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="8e388-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="8e388-114">Tuttavia, la riassegnazione non influiscono sulla variabile di matrice sottostante il codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8e388-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 <span data-ttu-id="8e388-115">[!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8e388-115">[!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]</span></span>  
  
 <span data-ttu-id="8e388-116">[!code-vb[VbVbcnProcedures&#38;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8e388-116">[!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]</span></span>  
  
 <span data-ttu-id="8e388-117">[!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8e388-117">[!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]</span></span>  
  
 <span data-ttu-id="8e388-118">Il primo `MsgBox` chiamata viene visualizzato "dopo Increase (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="8e388-118">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="8e388-119">Poiché la matrice `n` è un tipo di riferimento, `replace` possibile modificare i relativi membri, anche se è il meccanismo di passaggio `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="8e388-119">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="8e388-120">Il secondo `MsgBox` chiamata viene visualizzato "dopo Replace (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="8e388-120">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="8e388-121">Poiché `n` viene passato `ByVal`, `replace` non può modificare la variabile `n` nel codice chiamante assegnandole una nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="8e388-121">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="8e388-122">Quando `replace` crea una nuova istanza di matrice `k` e lo assegna alla variabile locale `a`, perde il riferimento a `n` passato al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8e388-122">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="8e388-123">Quando si trasforma i membri di `a`, solo la matrice locale `k` è interessato.</span><span class="sxs-lookup"><span data-stu-id="8e388-123">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="8e388-124">Di conseguenza, `replace` incrementa i valori della matrice `n` nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="8e388-124">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e388-125">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8e388-125">Compiling the Code</span></span>  
 <span data-ttu-id="8e388-126">Il valore predefinito in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gli argomenti vengono passati per valore.</span><span class="sxs-lookup"><span data-stu-id="8e388-126">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="8e388-127">Tuttavia, è buona norma includere una programmazione di [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (parola chiave) con ogni parametro dichiarato.</span><span class="sxs-lookup"><span data-stu-id="8e388-127">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="8e388-128">In questo modo il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="8e388-128">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e388-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e388-129">See Also</span></span>  
 <span data-ttu-id="8e388-130">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-130">[Procedures](./index.md) </span></span>  
<span data-ttu-id="8e388-131"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-131"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="8e388-132"> [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-132"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="8e388-133"> [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-133"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="8e388-134"> [Differenze tra argomenti modificabili e](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-134"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="8e388-135"> [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-135"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="8e388-136"> [Procedura: modificare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-136"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="8e388-137"> [Procedura: forzare un argomento sia passati per valore](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-137"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="8e388-138"> [Passaggio di argomenti in base alla posizione e in base al nome](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="8e388-138"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="8e388-139"> [Tipi valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="8e388-139"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
