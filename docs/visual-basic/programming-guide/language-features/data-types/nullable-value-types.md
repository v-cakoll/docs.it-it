---
title: Tipi di valore nullable - Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: d17d2ad3fd99c6d563c21ddd646396ccb1c1ca48
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008228"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="705f7-102">Tipi di valori nullable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="705f7-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="705f7-103">In alcuni casi si lavora con un tipo di valore che non hanno un valore definito in determinate circostanze.</span><span class="sxs-lookup"><span data-stu-id="705f7-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="705f7-104">Ad esempio, un campo in un database potrebbe essere necessario distinguere tra l'assegnazione di un valore significativo e che non presentano un valore assegnato.</span><span class="sxs-lookup"><span data-stu-id="705f7-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="705f7-105">I tipi di valore possono essere esteso per sfruttare i relativi valori normale o un valore null.</span><span class="sxs-lookup"><span data-stu-id="705f7-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="705f7-106">Tale estensione viene chiamato un *tipo nullable*.</span><span class="sxs-lookup"><span data-stu-id="705f7-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="705f7-107">Ogni tipo che ammette valori null viene costruito dal modello generico <xref:System.Nullable%601> struttura.</span><span class="sxs-lookup"><span data-stu-id="705f7-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="705f7-108">Si consideri un database che tiene traccia delle attività correlate al lavoro.</span><span class="sxs-lookup"><span data-stu-id="705f7-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="705f7-109">L'esempio seguente crea un valore nullable `Boolean` digitare e viene dichiarata una variabile di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="705f7-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="705f7-110">È possibile scrivere la dichiarazione in tre modi:</span><span class="sxs-lookup"><span data-stu-id="705f7-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="705f7-111">La variabile `ridesBusToWork` può contenere un valore di `True`, un valore di `False`, o nessun valore.</span><span class="sxs-lookup"><span data-stu-id="705f7-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="705f7-112">Il valore predefinito iniziale non è alcun valore, che in questo caso potrebbe significare che le informazioni non ha ancora ottenute per tale persona.</span><span class="sxs-lookup"><span data-stu-id="705f7-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="705f7-113">Al contrario, `False` potrebbe significare che sono state ottenute le informazioni e la persona non recarsi il bus di funzionamento.</span><span class="sxs-lookup"><span data-stu-id="705f7-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="705f7-114">È possibile dichiarare le variabili e le proprietà con tipi nullable, ed è possibile dichiarare una matrice con elementi di un tipo nullable.</span><span class="sxs-lookup"><span data-stu-id="705f7-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="705f7-115">È possibile dichiarare le procedure con tipi nullable come parametri, e si può restituire un tipo nullable da un `Function` procedure.</span><span class="sxs-lookup"><span data-stu-id="705f7-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>

<span data-ttu-id="705f7-116">Impossibile costruire un tipo nullable in un tipo riferimento, ad esempio una matrice, un `String`, o una classe.</span><span class="sxs-lookup"><span data-stu-id="705f7-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="705f7-117">Il tipo sottostante deve essere un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="705f7-117">The underlying type must be a value type.</span></span> <span data-ttu-id="705f7-118">Per altre informazioni, vedere [Value Types and Reference Types](value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="705f7-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="705f7-119">Utilizzo di una variabile di tipo Nullable</span><span class="sxs-lookup"><span data-stu-id="705f7-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="705f7-120">I membri più importanti di un tipo che ammette valori null sono relativi <xref:System.Nullable%601.HasValue%2A> e <xref:System.Nullable%601.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="705f7-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="705f7-121">Per una variabile di un tipo nullable, <xref:System.Nullable%601.HasValue%2A> indica se la variabile contiene un valore definito.</span><span class="sxs-lookup"><span data-stu-id="705f7-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="705f7-122">Se <xref:System.Nullable%601.HasValue%2A> viene `True`, è possibile leggere il valore da <xref:System.Nullable%601.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="705f7-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="705f7-123">Si noti che entrambe <xref:System.Nullable%601.HasValue%2A> e <xref:System.Nullable%601.Value%2A> sono `ReadOnly` proprietà.</span><span class="sxs-lookup"><span data-stu-id="705f7-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="705f7-124">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="705f7-124">Default Values</span></span>

<span data-ttu-id="705f7-125">Quando si dichiara una variabile con un tipo che ammette valori null, relative <xref:System.Nullable%601.HasValue%2A> proprietà ha un valore predefinito di `False`.</span><span class="sxs-lookup"><span data-stu-id="705f7-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="705f7-126">Ciò significa che per impostazione predefinita la variabile non ha valore definito, anziché il valore predefinito del relativo tipo di valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="705f7-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="705f7-127">Nell'esempio seguente, la variabile `numberOfChildren` inizialmente non ha valore definito, anche se il valore predefinito di `Integer` tipo è 0.</span><span class="sxs-lookup"><span data-stu-id="705f7-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="705f7-128">Un valore null è utile per indicare un valore sconosciuto o non definito.</span><span class="sxs-lookup"><span data-stu-id="705f7-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="705f7-129">Se `numberOfChildren` fosse stato dichiarato come `Integer`, non vi sarà alcun valore che potrebbe indicare che le informazioni non sono attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="705f7-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="705f7-130">L'archiviazione dei valori</span><span class="sxs-lookup"><span data-stu-id="705f7-130">Storing Values</span></span>

<span data-ttu-id="705f7-131">Archiviare un valore in una variabile o proprietà di un tipo che ammette valori null nel modo usuale.</span><span class="sxs-lookup"><span data-stu-id="705f7-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="705f7-132">L'esempio seguente assegna un valore alla variabile `numberOfChildren` dichiarato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="705f7-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="705f7-133">Se una variabile o una proprietà di un tipo nullable contiene un valore definito, è possibile che vengano tornerà allo stato iniziale di non avere un valore assegnato.</span><span class="sxs-lookup"><span data-stu-id="705f7-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="705f7-134">Eseguire questa operazione impostando la variabile o proprietà `Nothing`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="705f7-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="705f7-135">Sebbene sia possibile assegnare `Nothing` a una variabile di un tipo nullable, è possibile testarlo per `Nothing` con il segno di uguale.</span><span class="sxs-lookup"><span data-stu-id="705f7-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="705f7-136">Confronto che usa il segno di uguale `someVar = Nothing`, restituisce sempre `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="705f7-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="705f7-137">È possibile testare la variabile <xref:System.Nullable%601.HasValue%2A> proprietà per `False`, o di test usando la `Is` o `IsNot` operatore.</span><span class="sxs-lookup"><span data-stu-id="705f7-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="705f7-138">Recupero di valori</span><span class="sxs-lookup"><span data-stu-id="705f7-138">Retrieving Values</span></span>

<span data-ttu-id="705f7-139">Per recuperare il valore di una variabile di un tipo nullable, è necessario innanzitutto testare relativo <xref:System.Nullable%601.HasValue%2A> proprietà per confermare che ha un valore.</span><span class="sxs-lookup"><span data-stu-id="705f7-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="705f7-140">Se si prova a leggere il valore quando <xref:System.Nullable%601.HasValue%2A> viene `False`, Visual Basic genera un <xref:System.InvalidOperationException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="705f7-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="705f7-141">Nell'esempio seguente viene illustrato il modo consigliato per la lettura della variabile `numberOfChildren` degli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="705f7-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="705f7-142">Confronto tra i tipi Nullable</span><span class="sxs-lookup"><span data-stu-id="705f7-142">Comparing Nullable Types</span></span>

<span data-ttu-id="705f7-143">Quando nullable `Boolean` variabili vengono usate in espressioni booleane, possono verificarsi `True`, `False`, o `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="705f7-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="705f7-144">Di seguito è riportato nella tabella di verità per `And` e `Or`.</span><span class="sxs-lookup"><span data-stu-id="705f7-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="705f7-145">In quanto `b1` e `b2` disporrà di tre valori possibili, sono presenti nove combinazioni da valutare.</span><span class="sxs-lookup"><span data-stu-id="705f7-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="705f7-146">b1</span><span class="sxs-lookup"><span data-stu-id="705f7-146">b1</span></span>|<span data-ttu-id="705f7-147">b2</span><span class="sxs-lookup"><span data-stu-id="705f7-147">b2</span></span>|<span data-ttu-id="705f7-148">B1 e b2</span><span class="sxs-lookup"><span data-stu-id="705f7-148">b1 And b2</span></span>|<span data-ttu-id="705f7-149">B1 o b2</span><span class="sxs-lookup"><span data-stu-id="705f7-149">b1 Or b2</span></span>|
|--------|--------|---------------|--------------|
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|
|`Nothing`|`True`|`Nothing`|`True`|
|`Nothing`|`False`|`False`|`Nothing`|
|`True`|`Nothing`|`Nothing`|`True`|
|`True`|`True`|`True`|`True`|
|`True`|`False`|`False`|`True`|
|`False`|`Nothing`|`False`|`Nothing`|
|`False`|`True`|`False`|`True`|
|`False`|`False`|`False`|`False`|

<span data-ttu-id="705f7-150">Quando è il valore di una variabile booleana o espressione `Nothing`, non è né `true` né `false`.</span><span class="sxs-lookup"><span data-stu-id="705f7-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="705f7-151">Si osservi l'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="705f7-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="705f7-152">In questo esempio `b1 And b2` restituisca `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="705f7-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="705f7-153">Di conseguenza, il `Else` clausola viene eseguita in ogni `If` istruzione e l'output è come segue:</span><span class="sxs-lookup"><span data-stu-id="705f7-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="705f7-154">`AndAlso` e `OrElse`, che usano la valutazione, short circuit deve restituire i relativi operandi secondo quando restituisce il primo `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="705f7-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="705f7-155">Propagazione</span><span class="sxs-lookup"><span data-stu-id="705f7-155">Propagation</span></span>

<span data-ttu-id="705f7-156">Se uno o entrambi gli operandi di un aritmetica, di confronto, MAIUSC o operazione di tipo è nullable, anche il risultato dell'operazione è nullable.</span><span class="sxs-lookup"><span data-stu-id="705f7-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="705f7-157">Se entrambi gli operandi hanno valori diversi da quelli `Nothing`, l'operazione viene eseguita sui valori sottostanti degli operandi, come se non fossero un tipo nullable.</span><span class="sxs-lookup"><span data-stu-id="705f7-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="705f7-158">Nell'esempio seguente, le variabili `compare1` e `sum1` sono tipizzate in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="705f7-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="705f7-159">Se si posiziona il puntatore del mouse su di essi, si noterà che il compilatore deduce i tipi nullable per entrambi.</span><span class="sxs-lookup"><span data-stu-id="705f7-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="705f7-160">Se il valore di uno o entrambi gli operandi `Nothing`, il risultato sarà `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="705f7-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="705f7-161">Utilizzo dei tipi Nullable con dati</span><span class="sxs-lookup"><span data-stu-id="705f7-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="705f7-162">Un database è uno dei posti più importanti da usare tipi nullable.</span><span class="sxs-lookup"><span data-stu-id="705f7-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="705f7-163">Non tutti gli oggetti di database attualmente supportano i tipi nullable, mentre gli adattatori di tabella generati dalla finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="705f7-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="705f7-164">Visualizzare [TableAdapter supporto per i tipi nullable](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span><span class="sxs-lookup"><span data-stu-id="705f7-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="705f7-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="705f7-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="705f7-166">Uso dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="705f7-166">Using Nullable Types</span></span>](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="705f7-167">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="705f7-167">Data Types</span></span>](index.md)
- [<span data-ttu-id="705f7-168">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="705f7-168">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="705f7-169">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="705f7-169">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="705f7-170">Compilare i set di dati usando oggetti TableAdapter</span><span class="sxs-lookup"><span data-stu-id="705f7-170">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="705f7-171">Operatore If</span><span class="sxs-lookup"><span data-stu-id="705f7-171">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="705f7-172">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="705f7-172">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="705f7-173">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="705f7-173">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="705f7-174">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="705f7-174">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)