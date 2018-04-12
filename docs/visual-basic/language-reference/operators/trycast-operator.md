---
title: Operatore TryCast (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6be11b49eb3b9d98e3bf147e9b1026d4ffc860c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="1bff6-102">Operatore TryCast (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bff6-102">TryCast Operator (Visual Basic)</span></span>
<span data-ttu-id="1bff6-103">Introduce un'operazione di conversione di tipo che non viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1bff6-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bff6-104">Note</span><span class="sxs-lookup"><span data-stu-id="1bff6-104">Remarks</span></span>  
 <span data-ttu-id="1bff6-105">Se un tentativo di conversione non riesce, `CType` e `DirectCast` generano entrambi un <xref:System.InvalidCastException> errore.</span><span class="sxs-lookup"><span data-stu-id="1bff6-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="1bff6-106">Questo può influire negativamente sulle prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1bff6-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="1bff6-107">`TryCast`Restituisce [nulla](../../../visual-basic/language-reference/nothing.md), in modo che, anziché dover gestire una possibile eccezione, è necessario testare solo il risultato restituito contro `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="1bff6-107">`TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="1bff6-108">Utilizzare il `TryCast` parola chiave la stessa modalità di utilizzo il [CType (funzione)](../../../visual-basic/language-reference/functions/ctype-function.md) e [operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="1bff6-108">You use the `TryCast` keyword the same way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) keyword.</span></span> <span data-ttu-id="1bff6-109">Specificare un'espressione come primo argomento e un tipo per convertirlo in come secondo argomento.</span><span class="sxs-lookup"><span data-stu-id="1bff6-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="1bff6-110">`TryCast`opera solo sui tipi di riferimento, ad esempio le classi e interfacce.</span><span class="sxs-lookup"><span data-stu-id="1bff6-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="1bff6-111">Richiede una relazione di ereditarietà o implementazione tra i due tipi.</span><span class="sxs-lookup"><span data-stu-id="1bff6-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="1bff6-112">Ciò significa che un tipo deve ereditare da o implementare l'altro.</span><span class="sxs-lookup"><span data-stu-id="1bff6-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="1bff6-113">Errori e problemi</span><span class="sxs-lookup"><span data-stu-id="1bff6-113">Errors and Failures</span></span>  
 <span data-ttu-id="1bff6-114">`TryCast`Genera un errore del compilatore se rileva che non esiste alcuna relazione di ereditarietà o implementazione.</span><span class="sxs-lookup"><span data-stu-id="1bff6-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="1bff6-115">Tuttavia, la mancanza di un errore del compilatore non garantisce una corretta conversione.</span><span class="sxs-lookup"><span data-stu-id="1bff6-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="1bff6-116">Se la conversione desiderata è più piccolo, potrebbe non riuscire in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1bff6-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="1bff6-117">In questo caso, `TryCast` restituisce [nulla](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="1bff6-117">If this happens, `TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="1bff6-118">Parole chiave di conversione</span><span class="sxs-lookup"><span data-stu-id="1bff6-118">Conversion Keywords</span></span>  
 <span data-ttu-id="1bff6-119">Un confronto delle parole chiave di conversione del tipo è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1bff6-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="1bff6-120">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="1bff6-120">Keyword</span></span>|<span data-ttu-id="1bff6-121">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="1bff6-121">Data types</span></span>|<span data-ttu-id="1bff6-122">Relazione tra gli argomenti</span><span class="sxs-lookup"><span data-stu-id="1bff6-122">Argument relationship</span></span>|<span data-ttu-id="1bff6-123">Errore di run-time</span><span class="sxs-lookup"><span data-stu-id="1bff6-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="1bff6-124">Funzione CType</span><span class="sxs-lookup"><span data-stu-id="1bff6-124">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="1bff6-125">I tipi di dati</span><span class="sxs-lookup"><span data-stu-id="1bff6-125">Any data types</span></span>|<span data-ttu-id="1bff6-126">Widening o narrowing conversione deve essere definito tra i due tipi di dati</span><span class="sxs-lookup"><span data-stu-id="1bff6-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="1bff6-127">Genera un'eccezione<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="1bff6-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="1bff6-128">Operatore DirectCast</span><span class="sxs-lookup"><span data-stu-id="1bff6-128">DirectCast Operator</span></span>](../../../visual-basic/language-reference/operators/directcast-operator.md)|<span data-ttu-id="1bff6-129">I tipi di dati</span><span class="sxs-lookup"><span data-stu-id="1bff6-129">Any data types</span></span>|<span data-ttu-id="1bff6-130">Un tipo deve ereditare da o implementare l'altro tipo</span><span class="sxs-lookup"><span data-stu-id="1bff6-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="1bff6-131">Genera un'eccezione<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="1bff6-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="1bff6-132">Solo i tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="1bff6-132">Reference types only</span></span>|<span data-ttu-id="1bff6-133">Un tipo deve ereditare da o implementare l'altro tipo</span><span class="sxs-lookup"><span data-stu-id="1bff6-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="1bff6-134">Restituisce [Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="1bff6-134">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1bff6-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bff6-135">Example</span></span>  
 <span data-ttu-id="1bff6-136">Nell'esempio riportato di seguito viene illustrato come usare `TryCast`.</span><span class="sxs-lookup"><span data-stu-id="1bff6-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1bff6-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bff6-137">See Also</span></span>  
 [<span data-ttu-id="1bff6-138">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="1bff6-138">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="1bff6-139">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="1bff6-139">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
