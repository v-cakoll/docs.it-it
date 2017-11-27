---
title: 'Procedura: impedire la modifica del valore di un argomento di una routine (Visual Basic)'
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
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7975cbbc38c39223a4af5c87ac6bb090be548f2d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="dde59-102">Procedura: impedire la modifica del valore di un argomento di una routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dde59-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="dde59-103">Se una routine dichiara un parametro come [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] fornisce il codice della routine un riferimento diretto all'elemento di programmazione sottostante all'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="dde59-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="dde59-104">In tal modo la procedura per modificare il valore sottostante all'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="dde59-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="dde59-105">In alcuni casi il codice chiamante può essere per proteggersi da tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="dde59-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="dde59-106">È possibile proteggere sempre un argomento da modifica dichiarando il parametro corrispondente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) nella procedura.</span><span class="sxs-lookup"><span data-stu-id="dde59-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="dde59-107">Se si desidera essere in grado di modificare un determinato argomento in alcuni casi, ma non altri, è possibile dichiararla `ByRef` e consentire al codice chiamante di determinare il meccanismo di passaggio in ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="dde59-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="dde59-108">Questo scopo, racchiudere l'argomento corrispondente tra parentesi per passarlo come valore o non racchiudendolo tra parentesi per passarlo come riferimento.</span><span class="sxs-lookup"><span data-stu-id="dde59-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="dde59-109">Per ulteriori informazioni, vedere [procedura: forzare un argomento sia passati per valore](./how-to-force-an-argument-to-be-passed-by-value.md).</span><span class="sxs-lookup"><span data-stu-id="dde59-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dde59-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="dde59-110">Example</span></span>  
 <span data-ttu-id="dde59-111">Nell'esempio seguente mostra due procedure che accettano una variabile di matrice e operano sui relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="dde59-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="dde59-112">Il `increase` procedura aggiunge semplicemente uno per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="dde59-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="dde59-113">Il `replace` procedure assegna una nuova matrice al parametro `a()` , quindi aggiunge uno per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="dde59-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="dde59-114">Tuttavia, la riassegnazione inalterata la variabile di matrice sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="dde59-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 <span data-ttu-id="dde59-115">Il primo `MsgBox` chiamata viene visualizzato "dopo Increase (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="dde59-115">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="dde59-116">Poiché la matrice `n` è un tipo riferimento, `replace` possibile modificare i relativi membri, anche se è il meccanismo di passaggio `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="dde59-116">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="dde59-117">Il secondo `MsgBox` chiamata viene visualizzato "dopo Replace (n): 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="dde59-117">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="dde59-118">Poiché `n` viene passato `ByVal`, `replace` non è possibile modificare la variabile `n` nel codice chiamante assegnandole una nuova matrice.</span><span class="sxs-lookup"><span data-stu-id="dde59-118">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="dde59-119">Quando `replace` crea una nuova istanza di matrice `k` e assegnarlo alla variabile locale `a`, perde il riferimento a `n` passato al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="dde59-119">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="dde59-120">Quando si trasforma i membri di `a`, solo la matrice locale `k` è interessato.</span><span class="sxs-lookup"><span data-stu-id="dde59-120">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="dde59-121">Pertanto, `replace` incrementa i valori della matrice `n` nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="dde59-121">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dde59-122">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="dde59-122">Compiling the Code</span></span>  
 <span data-ttu-id="dde59-123">Il valore predefinito in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] gli argomenti vengono passati per valore.</span><span class="sxs-lookup"><span data-stu-id="dde59-123">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="dde59-124">Tuttavia, è buona norma includere una programmazione di [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (parola chiave) con ogni parametro dichiarato.</span><span class="sxs-lookup"><span data-stu-id="dde59-124">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="dde59-125">Questo rende il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="dde59-125">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde59-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dde59-126">See Also</span></span>  
 [<span data-ttu-id="dde59-127">Routine</span><span class="sxs-lookup"><span data-stu-id="dde59-127">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="dde59-128">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="dde59-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="dde59-129">Procedura: Passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="dde59-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="dde59-130">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="dde59-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="dde59-131">Differenze tra argomenti modificabili e non modificabili</span><span class="sxs-lookup"><span data-stu-id="dde59-131">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="dde59-132">Differenze tra il passaggio di un argomento per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="dde59-132">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="dde59-133">Procedura: cambiare il valore di un argomento di routine</span><span class="sxs-lookup"><span data-stu-id="dde59-133">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="dde59-134">Procedura: forzare il passaggio di un argomento per valore</span><span class="sxs-lookup"><span data-stu-id="dde59-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="dde59-135">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="dde59-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="dde59-136">Tipi valore e tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="dde59-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
