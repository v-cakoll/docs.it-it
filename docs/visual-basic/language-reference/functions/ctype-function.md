---
title: Funzione CType (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6118ca5f73a0d446842c33859e0623032082bcd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ctype-function-visual-basic"></a><span data-ttu-id="edc19-102">Funzione CType (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edc19-102">CType Function (Visual Basic)</span></span>
<span data-ttu-id="edc19-103">Restituisce il risultato della conversione esplicita di un'espressione in un tipo di dati specificato, oggetto, struttura, classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="edc19-103">Returns the result of explicitly converting an expression to a specified data type, object, structure, class, or interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edc19-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="edc19-104">Syntax</span></span>  
  
```  
CType(expression, typename)  
```  
  
## <a name="parts"></a><span data-ttu-id="edc19-105">Parti</span><span class="sxs-lookup"><span data-stu-id="edc19-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="edc19-106">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="edc19-106">Any valid expression.</span></span> <span data-ttu-id="edc19-107">Se il valore di `expression` non è compreso nell'intervallo consentito da `typename`, Visual Basic genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="edc19-107">If the value of `expression` is outside the range allowed by `typename`, Visual Basic throws an exception.</span></span>  
  
 `typename`  
 <span data-ttu-id="edc19-108">Qualsiasi espressione valida in un `As` clausola in un `Dim` istruzione, vale a dire il nome di qualsiasi tipo di dati, oggetto, struttura, classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="edc19-108">Any expression that is legal within an `As` clause in a `Dim` statement, that is, the name of any data type, object, structure, class, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edc19-109">Note</span><span class="sxs-lookup"><span data-stu-id="edc19-109">Remarks</span></span>  
  
> [!TIP]
>  <span data-ttu-id="edc19-110">È inoltre possibile utilizzare le funzioni seguenti per eseguire una conversione del tipo:</span><span class="sxs-lookup"><span data-stu-id="edc19-110">You can also use the following functions to perform a type conversion:</span></span>  
>   
>  -   <span data-ttu-id="edc19-111">Digitare ad esempio le funzioni di conversione `CByte`, `CDbl`, e `CInt` che eseguono una conversione in un tipo di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="edc19-111">Type conversion functions such as `CByte`, `CDbl`, and `CInt` that perform a conversion to a specific data type.</span></span> <span data-ttu-id="edc19-112">Per ulteriori informazioni, vedere [funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="edc19-112">For more information, see [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
> -   <span data-ttu-id="edc19-113">[Operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) o [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="edc19-113">[DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span> <span data-ttu-id="edc19-114">Questi operatori richiedono che un tipo di ereditare da o implementare l'altro tipo.</span><span class="sxs-lookup"><span data-stu-id="edc19-114">These operators require that one type inherit from or implement the other type.</span></span> <span data-ttu-id="edc19-115">Possono fornire prestazioni migliori rispetto a `CType` durante la conversione da e verso il `Object` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="edc19-115">They can provide somewhat better performance than `CType` when converting to and from the `Object` data type.</span></span>  
  
 <span data-ttu-id="edc19-116">`CType`viene compilata inline, il che significa che il codice di conversione fa parte del codice che valuta l'espressione.</span><span class="sxs-lookup"><span data-stu-id="edc19-116">`CType` is compiled inline, which means that the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="edc19-117">In alcuni casi, il codice viene eseguito più velocemente poiché nessuna procedure vengono chiamata per eseguire la conversione.</span><span class="sxs-lookup"><span data-stu-id="edc19-117">In some cases, the code runs faster because no procedures are called to perform the conversion.</span></span>  
  
 <span data-ttu-id="edc19-118">Se è definita alcuna conversione da `expression` a `typename` (ad esempio, da `Integer` a `Date`), Visual Basic viene visualizzato un messaggio di errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="edc19-118">If no conversion is defined from `expression` to `typename` (for example, from `Integer` to `Date`), Visual Basic displays a compile-time error message.</span></span>  
  
 <span data-ttu-id="edc19-119">Se una conversione non riesce in fase di esecuzione, viene generata l'eccezione appropriata.</span><span class="sxs-lookup"><span data-stu-id="edc19-119">If a conversion fails at run time, the appropriate exception is thrown.</span></span> <span data-ttu-id="edc19-120">Se una conversione non riesce, un <xref:System.OverflowException> è il risultato più comune.</span><span class="sxs-lookup"><span data-stu-id="edc19-120">If a narrowing conversion fails, an <xref:System.OverflowException> is the most common result.</span></span> <span data-ttu-id="edc19-121">Se la conversione non è definita, un <xref:System.InvalidCastException> in generata.</span><span class="sxs-lookup"><span data-stu-id="edc19-121">If the conversion is undefined, an <xref:System.InvalidCastException> in thrown.</span></span> <span data-ttu-id="edc19-122">Ad esempio, questa situazione può verificarsi se `expression` è di tipo `Object` e il relativo tipo in fase di esecuzione non viene convertito in `typename`.</span><span class="sxs-lookup"><span data-stu-id="edc19-122">For example, this can happen  if `expression` is of type `Object` and its run-time type has no conversion to `typename`.</span></span>  
  
 <span data-ttu-id="edc19-123">Se il tipo di dati `expression` o `typename` è una classe o struttura è stato definito, è possibile definire `CType` in quella classe o struttura come operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="edc19-123">If the data type of `expression` or `typename` is a class or structure you've defined, you can define `CType` on that class or structure as a conversion operator.</span></span> <span data-ttu-id="edc19-124">In questo modo `CType` agire come un *operatore di overload*.</span><span class="sxs-lookup"><span data-stu-id="edc19-124">This makes `CType` act as an *overloaded operator*.</span></span> <span data-ttu-id="edc19-125">In questo caso, è possibile controllare il comportamento delle conversioni da e dalla classe o struttura, incluse le eccezioni che possono essere generate.</span><span class="sxs-lookup"><span data-stu-id="edc19-125">If you do this, you can control the behavior of conversions to and from your class or structure, including the exceptions that can be thrown.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="edc19-126">Overload</span><span class="sxs-lookup"><span data-stu-id="edc19-126">Overloading</span></span>  
 <span data-ttu-id="edc19-127">Il `CType` operatore possa essere sottoposti a overload anche in una classe o struttura definita all'esterno del codice.</span><span class="sxs-lookup"><span data-stu-id="edc19-127">The `CType` operator can also be overloaded on a class or structure defined outside your code.</span></span> <span data-ttu-id="edc19-128">Se il codice viene convertito in o da una classe o una struttura, assicurarsi di comprendere il comportamento del relativo `CType` operatore.</span><span class="sxs-lookup"><span data-stu-id="edc19-128">If your code converts to or from such a class or structure, be sure you understand the behavior of its `CType` operator.</span></span> <span data-ttu-id="edc19-129">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="edc19-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="converting-dynamic-objects"></a><span data-ttu-id="edc19-130">Conversione di oggetti dinamici</span><span class="sxs-lookup"><span data-stu-id="edc19-130">Converting Dynamic Objects</span></span>  
 <span data-ttu-id="edc19-131">Conversioni di tipo degli oggetti dinamici vengono eseguite da conversioni dinamiche definite dall'utente che utilizzano il <xref:System.Dynamic.DynamicObject.TryConvert%2A> o <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="edc19-131">Type conversions of dynamic objects are performed by user-defined dynamic conversions that use the <xref:System.Dynamic.DynamicObject.TryConvert%2A> or <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> methods.</span></span> <span data-ttu-id="edc19-132">Se si lavora con gli oggetti dinamici, utilizzare il <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> metodo per convertire l'oggetto dinamico.</span><span class="sxs-lookup"><span data-stu-id="edc19-132">If you're working with dynamic objects, use the <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> method to convert the dynamic object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edc19-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="edc19-133">Example</span></span>  
 <span data-ttu-id="edc19-134">L'esempio seguente usa il `CType` funzione per convertire un'espressione per il `Single` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="edc19-134">The following example uses the `CType` function to convert an expression to the `Single` data type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/ctype-function_1.vb)]  
  
 <span data-ttu-id="edc19-135">Per ulteriori esempi, vedere [conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="edc19-135">For additional examples, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edc19-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edc19-136">See Also</span></span>  
 <xref:System.OverflowException>  
 <xref:System.InvalidCastException>  
 [<span data-ttu-id="edc19-137">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="edc19-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="edc19-138">Funzioni di conversione</span><span class="sxs-lookup"><span data-stu-id="edc19-138">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [<span data-ttu-id="edc19-139">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="edc19-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="edc19-140">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="edc19-140">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="edc19-141">Conversione di tipi in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="edc19-141">Type Conversion in the .NET Framework</span></span>](http://msdn.microsoft.com/library/ba36154f-064c-47d3-9f05-72f93a7ca96d)
