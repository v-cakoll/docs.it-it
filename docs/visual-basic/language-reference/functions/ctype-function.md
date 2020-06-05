---
title: CType Function
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 88d609146648fe1b0c3124b99a65e85293fc0707
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406430"
---
# <a name="ctype-function-visual-basic"></a><span data-ttu-id="2422e-102">Funzione CType (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2422e-102">CType Function (Visual Basic)</span></span>

<span data-ttu-id="2422e-103">Restituisce il risultato della conversione esplicita di un'espressione in un tipo di dati, oggetto, struttura, classe o interfaccia specificati.</span><span class="sxs-lookup"><span data-stu-id="2422e-103">Returns the result of explicitly converting an expression to a specified data type, object, structure, class, or interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="2422e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2422e-104">Syntax</span></span>

```vb
CType(expression, typename)
```

## <a name="parts"></a><span data-ttu-id="2422e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="2422e-105">Parts</span></span>

<span data-ttu-id="2422e-106">`expression`Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="2422e-106">`expression` Any valid expression.</span></span> <span data-ttu-id="2422e-107">Se il valore di non `expression` è compreso nell'intervallo consentito da `typename` , Visual Basic genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2422e-107">If the value of `expression` is outside the range allowed by `typename`, Visual Basic throws an exception.</span></span>

<span data-ttu-id="2422e-108">`typename`Qualsiasi espressione valida all'interno di una `As` clausola in un' `Dim` istruzione, ovvero il nome di qualsiasi tipo di dati, oggetto, struttura, classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2422e-108">`typename` Any expression that is legal within an `As` clause in a `Dim` statement, that is, the name of any data type, object, structure, class, or interface.</span></span>

## <a name="remarks"></a><span data-ttu-id="2422e-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="2422e-109">Remarks</span></span>

> [!TIP]
> <span data-ttu-id="2422e-110">Per eseguire una conversione del tipo è inoltre possibile utilizzare le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2422e-110">You can also use the following functions to perform a type conversion:</span></span>
>
> - <span data-ttu-id="2422e-111">Funzioni di conversione dei tipi `CByte` , ad esempio, `CDbl` e `CInt` che eseguono una conversione in un tipo di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="2422e-111">Type conversion functions such as `CByte`, `CDbl`, and `CInt` that perform a conversion to a specific data type.</span></span> <span data-ttu-id="2422e-112">Per altre informazioni, vedere [Funzioni di conversione del tipo](type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="2422e-112">For more information, see [Type Conversion Functions](type-conversion-functions.md).</span></span>
> - <span data-ttu-id="2422e-113">Operatore [DirectCast](../operators/directcast-operator.md) o [operatore TryCast](../operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="2422e-113">[DirectCast Operator](../operators/directcast-operator.md) or [TryCast Operator](../operators/trycast-operator.md).</span></span> <span data-ttu-id="2422e-114">Questi operatori richiedono che un tipo erediti da o implementi l'altro tipo.</span><span class="sxs-lookup"><span data-stu-id="2422e-114">These operators require that one type inherit from or implement the other type.</span></span> <span data-ttu-id="2422e-115">Possono fornire prestazioni leggermente migliori rispetto `CType` a quando si esegue la conversione da e verso il `Object` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="2422e-115">They can provide somewhat better performance than `CType` when converting to and from the `Object` data type.</span></span>

<span data-ttu-id="2422e-116">`CType`viene compilato inline, il che significa che il codice di conversione fa parte del codice che valuta l'espressione.</span><span class="sxs-lookup"><span data-stu-id="2422e-116">`CType` is compiled inline, which means that the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="2422e-117">In alcuni casi, il codice viene eseguito più velocemente perché non viene chiamata alcuna routine per eseguire la conversione.</span><span class="sxs-lookup"><span data-stu-id="2422e-117">In some cases, the code runs faster because no procedures are called to perform the conversion.</span></span>

<span data-ttu-id="2422e-118">Se non viene definita alcuna conversione da `expression` a `typename` (ad esempio, da `Integer` a `Date` ), Visual Basic Visualizza un messaggio di errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="2422e-118">If no conversion is defined from `expression` to `typename` (for example, from `Integer` to `Date`), Visual Basic displays a compile-time error message.</span></span>

<span data-ttu-id="2422e-119">Se una conversione non riesce in fase di esecuzione, viene generata l'eccezione appropriata.</span><span class="sxs-lookup"><span data-stu-id="2422e-119">If a conversion fails at run time, the appropriate exception is thrown.</span></span> <span data-ttu-id="2422e-120">Se una conversione verso un tipo di caratteri più piccolo non riesce, <xref:System.OverflowException> è il risultato più comune.</span><span class="sxs-lookup"><span data-stu-id="2422e-120">If a narrowing conversion fails, an <xref:System.OverflowException> is the most common result.</span></span> <span data-ttu-id="2422e-121">Se la conversione non è definita, viene <xref:System.InvalidCastException> generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2422e-121">If the conversion is undefined, an <xref:System.InvalidCastException> in thrown.</span></span> <span data-ttu-id="2422e-122">Questo può verificarsi, ad esempio, se `expression` è di tipo `Object` e il tipo in fase di esecuzione non dispone di conversione in `typename` .</span><span class="sxs-lookup"><span data-stu-id="2422e-122">For example, this can happen  if `expression` is of type `Object` and its run-time type has no conversion to `typename`.</span></span>

<span data-ttu-id="2422e-123">Se il tipo di dati di `expression` o `typename` è una classe o una struttura definita, è possibile definire `CType` su tale classe o struttura come operatore di conversione.</span><span class="sxs-lookup"><span data-stu-id="2422e-123">If the data type of `expression` or `typename` is a class or structure you've defined, you can define `CType` on that class or structure as a conversion operator.</span></span> <span data-ttu-id="2422e-124">In questo `CType` modo, funge da *operatore di overload*.</span><span class="sxs-lookup"><span data-stu-id="2422e-124">This makes `CType` act as an *overloaded operator*.</span></span> <span data-ttu-id="2422e-125">In tal caso, è possibile controllare il comportamento delle conversioni da e verso la classe o la struttura, incluse le eccezioni che possono essere generate.</span><span class="sxs-lookup"><span data-stu-id="2422e-125">If you do this, you can control the behavior of conversions to and from your class or structure, including the exceptions that can be thrown.</span></span>

## <a name="overloading"></a><span data-ttu-id="2422e-126">Overload</span><span class="sxs-lookup"><span data-stu-id="2422e-126">Overloading</span></span>

<span data-ttu-id="2422e-127">`CType`È inoltre possibile eseguire l'overload dell'operatore in una classe o in una struttura definita all'esterno del codice.</span><span class="sxs-lookup"><span data-stu-id="2422e-127">The `CType` operator can also be overloaded on a class or structure defined outside your code.</span></span> <span data-ttu-id="2422e-128">Se il codice viene convertito in o da tale classe o struttura, assicurarsi di comprendere il comportamento dell' `CType` operatore.</span><span class="sxs-lookup"><span data-stu-id="2422e-128">If your code converts to or from such a class or structure, be sure you understand the behavior of its `CType` operator.</span></span> <span data-ttu-id="2422e-129">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2422e-129">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="converting-dynamic-objects"></a><span data-ttu-id="2422e-130">Conversione di oggetti dinamici</span><span class="sxs-lookup"><span data-stu-id="2422e-130">Converting Dynamic Objects</span></span>

<span data-ttu-id="2422e-131">Le conversioni di tipi di oggetti dinamici vengono eseguite da conversioni dinamiche definite dall'utente che utilizzano i <xref:System.Dynamic.DynamicObject.TryConvert%2A> <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> metodi o.</span><span class="sxs-lookup"><span data-stu-id="2422e-131">Type conversions of dynamic objects are performed by user-defined dynamic conversions that use the <xref:System.Dynamic.DynamicObject.TryConvert%2A> or <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> methods.</span></span> <span data-ttu-id="2422e-132">Se si utilizzano oggetti dinamici, utilizzare il <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> metodo per convertire l'oggetto dinamico.</span><span class="sxs-lookup"><span data-stu-id="2422e-132">If you're working with dynamic objects, use the <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> method to convert the dynamic object.</span></span>

## <a name="example"></a><span data-ttu-id="2422e-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="2422e-133">Example</span></span>

<span data-ttu-id="2422e-134">Nell'esempio seguente viene utilizzata la `CType` funzione per convertire un'espressione nel `Single` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="2422e-134">The following example uses the `CType` function to convert an expression to the `Single` data type.</span></span>

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

<span data-ttu-id="2422e-135">Per altri esempi, vedere [conversioni implicite ed esplicite](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="2422e-135">For additional examples, see [Implicit and Explicit Conversions](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2422e-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2422e-136">See also</span></span>

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [<span data-ttu-id="2422e-137">CString</span><span class="sxs-lookup"><span data-stu-id="2422e-137">Type Conversion Functions</span></span>](type-conversion-functions.md)
- [<span data-ttu-id="2422e-138">Funzioni di conversione</span><span class="sxs-lookup"><span data-stu-id="2422e-138">Conversion Functions</span></span>](conversion-functions.md)
- [<span data-ttu-id="2422e-139">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="2422e-139">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="2422e-140">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="2422e-140">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="2422e-141">Conversione dei tipi nel .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2422e-141">Type Conversion in the .NET Framework</span></span>](../../../standard/base-types/type-conversion.md)
