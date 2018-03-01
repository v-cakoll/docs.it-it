---
title: Operatore DirectCast (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b81abea364e328b831ee98c3b847161c3f7dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="db14d-102">Operatore DirectCast (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db14d-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="db14d-103">Introduce un'operazione di conversione di tipo in base a ereditarietà o implementazione.</span><span class="sxs-lookup"><span data-stu-id="db14d-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db14d-104">Note</span><span class="sxs-lookup"><span data-stu-id="db14d-104">Remarks</span></span>  
 <span data-ttu-id="db14d-105">`DirectCast`non utilizzare Visual Basic le routine di supporto in fase di esecuzione per la conversione, in modo da poter garantire prestazioni migliori rispetto `CType` durante la conversione da e verso il tipo di dati `Object`.</span><span class="sxs-lookup"><span data-stu-id="db14d-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="db14d-106">Utilizzare il `DirectCast` (parola chiave) simile alla modalità di utilizzo di [CType (funzione)](../../../visual-basic/language-reference/functions/ctype-function.md) e [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="db14d-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) keyword.</span></span> <span data-ttu-id="db14d-107">Specificare un'espressione come primo argomento e un tipo per convertirlo in come secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="db14d-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="db14d-108">`DirectCast`richiede una relazione di ereditarietà o implementazione tra i tipi di dati dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="db14d-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="db14d-109">Ciò significa che un tipo deve ereditare da o implementare l'altro.</span><span class="sxs-lookup"><span data-stu-id="db14d-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="db14d-110">Errori e problemi</span><span class="sxs-lookup"><span data-stu-id="db14d-110">Errors and Failures</span></span>  
 <span data-ttu-id="db14d-111">`DirectCast`Genera un errore del compilatore se rileva che non esiste alcuna relazione di ereditarietà o implementazione.</span><span class="sxs-lookup"><span data-stu-id="db14d-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="db14d-112">Tuttavia, la mancanza di un errore del compilatore non garantisce una corretta conversione.</span><span class="sxs-lookup"><span data-stu-id="db14d-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="db14d-113">Se la conversione desiderata è più piccolo, potrebbe non riuscire in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="db14d-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="db14d-114">In questo caso, il runtime genera un <xref:System.InvalidCastException> errore.</span><span class="sxs-lookup"><span data-stu-id="db14d-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="db14d-115">Parole chiave di conversione</span><span class="sxs-lookup"><span data-stu-id="db14d-115">Conversion Keywords</span></span>  
 <span data-ttu-id="db14d-116">Un confronto delle parole chiave di conversione del tipo è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="db14d-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="db14d-117">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="db14d-117">Keyword</span></span>|<span data-ttu-id="db14d-118">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="db14d-118">Data types</span></span>|<span data-ttu-id="db14d-119">Relazione tra gli argomenti</span><span class="sxs-lookup"><span data-stu-id="db14d-119">Argument relationship</span></span>|<span data-ttu-id="db14d-120">Errore di run-time</span><span class="sxs-lookup"><span data-stu-id="db14d-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="db14d-121">Funzione CType</span><span class="sxs-lookup"><span data-stu-id="db14d-121">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="db14d-122">I tipi di dati</span><span class="sxs-lookup"><span data-stu-id="db14d-122">Any data types</span></span>|<span data-ttu-id="db14d-123">Widening o narrowing conversione deve essere definito tra i due tipi di dati</span><span class="sxs-lookup"><span data-stu-id="db14d-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="db14d-124">Genera un'eccezione<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="db14d-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="db14d-125">I tipi di dati</span><span class="sxs-lookup"><span data-stu-id="db14d-125">Any data types</span></span>|<span data-ttu-id="db14d-126">Un tipo deve ereditare da o implementare l'altro tipo</span><span class="sxs-lookup"><span data-stu-id="db14d-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="db14d-127">Genera un'eccezione<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="db14d-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="db14d-128">Operatore TryCast</span><span class="sxs-lookup"><span data-stu-id="db14d-128">TryCast Operator</span></span>](../../../visual-basic/language-reference/operators/trycast-operator.md)|<span data-ttu-id="db14d-129">Solo i tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="db14d-129">Reference types only</span></span>|<span data-ttu-id="db14d-130">Un tipo deve ereditare da o implementare l'altro tipo</span><span class="sxs-lookup"><span data-stu-id="db14d-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="db14d-131">Restituisce [Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="db14d-131">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="db14d-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="db14d-132">Example</span></span>  
 <span data-ttu-id="db14d-133">L'esempio seguente illustra due utilizzi di `DirectCast`, con esito negativo in fase di esecuzione e una che ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="db14d-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 <span data-ttu-id="db14d-134">Nell'esempio precedente, il runtime tipo `q` è `Double`.</span><span class="sxs-lookup"><span data-stu-id="db14d-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="db14d-135">`CType`ha esito positivo perché `Double` può essere convertito in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="db14d-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="db14d-136">Tuttavia, il primo `DirectCast` ha esito negativo in fase di esecuzione perché il tipo di runtime di `Double` non ha alcuna relazione di ereditarietà con `Integer`, anche se esiste una conversione.</span><span class="sxs-lookup"><span data-stu-id="db14d-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="db14d-137">Il secondo `DirectCast` ha esito positivo perché esegue la conversione dal tipo <xref:System.Windows.Forms.Form> al tipo <xref:System.Windows.Forms.Control>, da cui <xref:System.Windows.Forms.Form> eredita.</span><span class="sxs-lookup"><span data-stu-id="db14d-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db14d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db14d-138">See Also</span></span>  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="db14d-139">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="db14d-139">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="db14d-140">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="db14d-140">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
