---
title: Differenze tra il passaggio di un argomento per valore e per riferimento (Visual Basic) | Documenti di Microsoft
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
- procedures, passing arguments
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
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
ms.openlocfilehash: 706c64cd316791a748e2b68fe406e34084b04d5a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="16071-102">Differenze tra il passaggio di un argomento per valore e per riferimento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16071-102">Differences Between Passing an Argument By Value and By Reference (Visual Basic)</span></span>
<span data-ttu-id="16071-103">Quando si passano uno o più argomenti a una routine, ciascun argomento corrisponde a un elemento di programmazione sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="16071-103">When you pass one or more arguments to a procedure, each argument corresponds to an underlying programming element in the calling code.</span></span> <span data-ttu-id="16071-104">È possibile passare il valore di questo elemento sottostante oppure un riferimento a esso.</span><span class="sxs-lookup"><span data-stu-id="16071-104">You can pass either the value of this underlying element, or a reference to it.</span></span> <span data-ttu-id="16071-105">Ciò è noto come il *meccanismo di trasferimento*.</span><span class="sxs-lookup"><span data-stu-id="16071-105">This is known as the *passing mechanism*.</span></span>  
  
## <a name="passing-by-value"></a><span data-ttu-id="16071-106">passaggio per valore</span><span class="sxs-lookup"><span data-stu-id="16071-106">Passing by Value</span></span>  
 <span data-ttu-id="16071-107">Si passa un argomento *dal valore* specificando il [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) (parola chiave) per il parametro corrispondente nella definizione della routine.</span><span class="sxs-lookup"><span data-stu-id="16071-107">You pass an argument *by value* by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="16071-108">Quando si utilizza questo meccanismo di passaggio, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] copia il valore dell'elemento di programmazione sottostante in una variabile locale nella procedura.</span><span class="sxs-lookup"><span data-stu-id="16071-108">When you use this passing mechanism, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] copies the value of the underlying programming element into a local variable in the procedure.</span></span> <span data-ttu-id="16071-109">Il codice della routine non dispone di accesso per l'elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="16071-109">The procedure code does not have any access to the underlying element in the calling code.</span></span>  
  
## <a name="passing-by-reference"></a><span data-ttu-id="16071-110">Il passaggio per riferimento</span><span class="sxs-lookup"><span data-stu-id="16071-110">Passing by Reference</span></span>  
 <span data-ttu-id="16071-111">Si passa un argomento *per riferimento* specificando il [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (parola chiave) per il parametro corrispondente nella definizione della routine.</span><span class="sxs-lookup"><span data-stu-id="16071-111">You pass an argument *by reference* by specifying the [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="16071-112">Quando si utilizza questo meccanismo di passaggio, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] assegna alla routine un riferimento diretto all'elemento di programmazione sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="16071-112">When you use this passing mechanism, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gives the procedure a direct reference to the underlying programming element in the calling code.</span></span>  
  
## <a name="passing-mechanism-and-element-type"></a><span data-ttu-id="16071-113">Meccanismo di passaggio e il tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="16071-113">Passing Mechanism and Element Type</span></span>  
 <span data-ttu-id="16071-114">La scelta del meccanismo di trasferimento non è quello utilizzato per la classificazione del tipo dell'elemento sottostante.</span><span class="sxs-lookup"><span data-stu-id="16071-114">The choice of passing mechanism is not the same as the classification of the underlying element type.</span></span> <span data-ttu-id="16071-115">Il passaggio per valore o per riferimento si riferisce a quanto [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] fornisce al codice della routine.</span><span class="sxs-lookup"><span data-stu-id="16071-115">Passing by value or by reference refers to what [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] supplies to the procedure code.</span></span> <span data-ttu-id="16071-116">Tipo di valore o tipo di riferimento fa riferimento a come un elemento di programmazione viene archiviato in memoria.</span><span class="sxs-lookup"><span data-stu-id="16071-116">A value type or reference type refers to how a programming element is stored in memory.</span></span>  
  
 <span data-ttu-id="16071-117">Tuttavia, il meccanismo di passaggio e il tipo di elemento sono correlati.</span><span class="sxs-lookup"><span data-stu-id="16071-117">However, the passing mechanism and element type are interrelated.</span></span> <span data-ttu-id="16071-118">Il valore di un tipo di riferimento è un puntatore ai dati in un' posizione in memoria.</span><span class="sxs-lookup"><span data-stu-id="16071-118">The value of a reference type is a pointer to the data elsewhere in memory.</span></span> <span data-ttu-id="16071-119">Ciò significa che quando si passa un tipo di riferimento per valore, il codice della routine è un puntatore ai dati dell'elemento sottostante, anche se non può accedere l'elemento sottostante.</span><span class="sxs-lookup"><span data-stu-id="16071-119">This means that when you pass a reference type by value, the procedure code has a pointer to the underlying element's data, even though it cannot access the underlying element itself.</span></span> <span data-ttu-id="16071-120">Ad esempio, se l'elemento è una variabile di matrice, il codice della routine non dispone dell'accesso alla variabile stessa, ma può accedere i membri della matrice.</span><span class="sxs-lookup"><span data-stu-id="16071-120">For example, if the element is an array variable, the procedure code does not have access to the variable itself, but it can access the array members.</span></span>  
  
## <a name="ability-to-modify"></a><span data-ttu-id="16071-121">Possibilità di modificare</span><span class="sxs-lookup"><span data-stu-id="16071-121">Ability to Modify</span></span>  
 <span data-ttu-id="16071-122">Quando si passa un elemento non è modificabile come argomento, la procedura mai modificarlo nel codice chiamante, se viene passato `ByVal` o `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="16071-122">When you pass a nonmodifiable element as an argument, the procedure can never modify it in the calling code, whether it is passed `ByVal` or `ByRef`.</span></span>  
  
 <span data-ttu-id="16071-123">Per un elemento modificabile, nella tabella seguente viene riepilogata l'interazione tra il tipo di elemento e il meccanismo di passaggio.</span><span class="sxs-lookup"><span data-stu-id="16071-123">For a modifiable element, the following table summarizes the interaction between the element type and the passing mechanism.</span></span>  
  
|<span data-ttu-id="16071-124">Tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="16071-124">Element type</span></span>|<span data-ttu-id="16071-125">Passato`ByVal`</span><span class="sxs-lookup"><span data-stu-id="16071-125">Passed `ByVal`</span></span>|<span data-ttu-id="16071-126">Passato`ByRef`</span><span class="sxs-lookup"><span data-stu-id="16071-126">Passed `ByRef`</span></span>|  
|------------------|--------------------|--------------------|  
|<span data-ttu-id="16071-127">Tipo di valore (contiene un solo valore)</span><span class="sxs-lookup"><span data-stu-id="16071-127">Value type (contains only a value)</span></span>|<span data-ttu-id="16071-128">La routine non può modificare la variabile o i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="16071-128">The procedure cannot change the variable or any of its members.</span></span>|<span data-ttu-id="16071-129">La procedura è possibile modificare la variabile e i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="16071-129">The procedure can change the variable and its members.</span></span>|  
|<span data-ttu-id="16071-130">Tipo di riferimento (contiene un puntatore a un'istanza di classe o struttura)</span><span class="sxs-lookup"><span data-stu-id="16071-130">Reference type (contains a pointer to a class or structure instance)</span></span>|<span data-ttu-id="16071-131">La routine non può modificare la variabile ma può modificare i membri dell'istanza a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="16071-131">The procedure cannot change the variable but can change members of the instance to which it points.</span></span>|<span data-ttu-id="16071-132">La procedura è possibile modificare la variabile e i membri dell'istanza a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="16071-132">The procedure can change the variable and members of the instance to which it points.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16071-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16071-133">See Also</span></span>  
 <span data-ttu-id="16071-134">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="16071-134">[Procedures](./index.md) </span></span>  
<span data-ttu-id="16071-135"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="16071-135"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="16071-136"> [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="16071-136"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="16071-137"> [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="16071-137"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="16071-138"> [Differenze tra argomenti modificabili e](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="16071-138"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="16071-139"> [Procedura: modificare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="16071-139"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="16071-140"> [Procedura: proteggere un argomento di routine modifica del valore](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="16071-140"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="16071-141"> [Procedura: forzare un argomento sia passati per valore](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="16071-141"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="16071-142"> [Passaggio di argomenti in base alla posizione e in base al nome](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="16071-142"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="16071-143"> [Tipi valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="16071-143"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
