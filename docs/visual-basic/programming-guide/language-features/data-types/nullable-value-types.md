---
title: Tipi di valori nullable
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
ms.openlocfilehash: beed8262c50dc68330b8f03aa3d864ed2f8df0d5
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249682"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="2cb57-102">Tipi di valori nullable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2cb57-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="2cb57-103">A volte si lavora con un tipo di valore che non ha un valore definito in determinate circostanze.</span><span class="sxs-lookup"><span data-stu-id="2cb57-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="2cb57-104">Ad esempio, un campo in un database potrebbe essere necessario distinguere tra avere un valore assegnato che è significativo e non avere un valore assegnato.</span><span class="sxs-lookup"><span data-stu-id="2cb57-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="2cb57-105">I tipi di valore possono essere estesi per accettare i valori normali o un valore null.</span><span class="sxs-lookup"><span data-stu-id="2cb57-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="2cb57-106">Tale estensione viene definita *tipo nullable*.</span><span class="sxs-lookup"><span data-stu-id="2cb57-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="2cb57-107">Ogni tipo di valore nullable <xref:System.Nullable%601> viene costruito dalla struttura generica.</span><span class="sxs-lookup"><span data-stu-id="2cb57-107">Each nullable value type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="2cb57-108">Si consideri un database che tiene traccia delle attività correlate al lavoro.</span><span class="sxs-lookup"><span data-stu-id="2cb57-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="2cb57-109">Nell'esempio seguente viene `Boolean` creato un tipo nullable e viene dichiarata una variabile di tale tipo.</span><span class="sxs-lookup"><span data-stu-id="2cb57-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="2cb57-110">È possibile scrivere la dichiarazione in tre modi:You can write the declaration in three ways:</span><span class="sxs-lookup"><span data-stu-id="2cb57-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="2cb57-111">La `ridesBusToWork` variabile può contenere un valore pari `True`a , un valore pari `False`a o nessun valore.</span><span class="sxs-lookup"><span data-stu-id="2cb57-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="2cb57-112">Il suo valore predefinito iniziale non è affatto un valore, il che in questo caso potrebbe significare che le informazioni non sono ancora state ottenute per questa persona.</span><span class="sxs-lookup"><span data-stu-id="2cb57-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="2cb57-113">Al contrario, `False` potrebbe significare che le informazioni sono state ottenute e la persona non guida l'autobus per andare al lavoro.</span><span class="sxs-lookup"><span data-stu-id="2cb57-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="2cb57-114">È possibile dichiarare variabili e proprietà con tipi di valore nullable ed è possibile dichiarare una matrice con elementi di un tipo di valore nullable.</span><span class="sxs-lookup"><span data-stu-id="2cb57-114">You can declare variables and properties with nullable value types, and you can declare an array with elements of a nullable value type.</span></span> <span data-ttu-id="2cb57-115">È possibile dichiarare routine con tipi di valore nullable come parametri `Function` ed è possibile restituire un tipo di valore nullable da una routine.</span><span class="sxs-lookup"><span data-stu-id="2cb57-115">You can declare procedures with nullable value types as parameters, and you can return a nullable value type from a `Function` procedure.</span></span>

<span data-ttu-id="2cb57-116">Non è possibile costruire un tipo nullable su `String`un tipo di riferimento, ad esempio una matrice, un oggetto o una classe.</span><span class="sxs-lookup"><span data-stu-id="2cb57-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="2cb57-117">Il tipo sottostante deve essere un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="2cb57-117">The underlying type must be a value type.</span></span> <span data-ttu-id="2cb57-118">Per altre informazioni, vedere [Value Types and Reference Types](value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="2cb57-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="2cb57-119">Utilizzo di una variabile di tipo nullableUsing a Nullable Type Variable</span><span class="sxs-lookup"><span data-stu-id="2cb57-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="2cb57-120">I membri più importanti di un <xref:System.Nullable%601.HasValue%2A> tipo <xref:System.Nullable%601.Value%2A> di valore nullable sono le relative proprietà e .</span><span class="sxs-lookup"><span data-stu-id="2cb57-120">The most important members of a nullable value type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="2cb57-121">Per una variabile di un <xref:System.Nullable%601.HasValue%2A> tipo di valore nullable, indica se la variabile contiene un valore definito.</span><span class="sxs-lookup"><span data-stu-id="2cb57-121">For a variable of a nullable value type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="2cb57-122">Se <xref:System.Nullable%601.HasValue%2A> `True`è , è possibile <xref:System.Nullable%601.Value%2A>leggere il valore da .</span><span class="sxs-lookup"><span data-stu-id="2cb57-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="2cb57-123">Si noti <xref:System.Nullable%601.Value%2A> `ReadOnly` che entrambe <xref:System.Nullable%601.HasValue%2A> e sono proprietà.</span><span class="sxs-lookup"><span data-stu-id="2cb57-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="2cb57-124">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="2cb57-124">Default Values</span></span>

<span data-ttu-id="2cb57-125">Quando si dichiara una variabile con un <xref:System.Nullable%601.HasValue%2A> tipo di valore `False`nullable, la relativa proprietà ha un valore predefinito di .</span><span class="sxs-lookup"><span data-stu-id="2cb57-125">When you declare a variable with a nullable value type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="2cb57-126">Ciò significa che per impostazione predefinita la variabile non ha alcun valore definito, anziché il valore predefinito del relativo tipo di valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="2cb57-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="2cb57-127">Nell'esempio seguente, `numberOfChildren` la variabile inizialmente non ha alcun valore `Integer` definito, anche se il valore predefinito del tipo è 0.</span><span class="sxs-lookup"><span data-stu-id="2cb57-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="2cb57-128">Un valore null è utile per indicare un valore non definito o sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2cb57-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="2cb57-129">Se `numberOfChildren` fosse stato `Integer`dichiarato come , non vi sarebbe alcun valore che possa indicare che le informazioni non sono attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="2cb57-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="2cb57-130">Memorizzazione dei valori</span><span class="sxs-lookup"><span data-stu-id="2cb57-130">Storing Values</span></span>

<span data-ttu-id="2cb57-131">Archiviare un valore in una variabile o proprietà di un tipo di valore nullable nel modo tipico.</span><span class="sxs-lookup"><span data-stu-id="2cb57-131">You store a value in a variable or property of a nullable value type in the typical way.</span></span> <span data-ttu-id="2cb57-132">Nell'esempio seguente viene assegnato `numberOfChildren` un valore alla variabile dichiarata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="2cb57-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="2cb57-133">Se una variabile o una proprietà di un tipo di valore nullable contiene un valore definito, è possibile fare in modo che venga ripristinato allo stato iniziale di non avere un valore assegnato.</span><span class="sxs-lookup"><span data-stu-id="2cb57-133">If a variable or property of a nullable value type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="2cb57-134">A tale scopo, impostare `Nothing`la variabile o la proprietà su , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2cb57-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="2cb57-135">Sebbene sia `Nothing` possibile assegnare a una variabile di un `Nothing` tipo di valore nullable, non è possibile testarla utilizzando il segno di uguale.</span><span class="sxs-lookup"><span data-stu-id="2cb57-135">Although you can assign `Nothing` to a variable of a nullable value type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="2cb57-136">Confronto che utilizza il `someVar = Nothing`segno di `Nothing`uguale, , restituisce sempre .</span><span class="sxs-lookup"><span data-stu-id="2cb57-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="2cb57-137">È possibile verificare <xref:System.Nullable%601.HasValue%2A> la `False`proprietà della variabile `Is` per `IsNot` o test utilizzando l'operatore or .</span><span class="sxs-lookup"><span data-stu-id="2cb57-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="2cb57-138">Recupero di valoriRetrieving Values</span><span class="sxs-lookup"><span data-stu-id="2cb57-138">Retrieving Values</span></span>

<span data-ttu-id="2cb57-139">Per recuperare il valore di una variabile di un tipo <xref:System.Nullable%601.HasValue%2A> di valore nullable, è innanzitutto necessario testare la relativa proprietà per verificare che abbia un valore.</span><span class="sxs-lookup"><span data-stu-id="2cb57-139">To retrieve the value of a variable of a nullable value type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="2cb57-140">Se si tenta di <xref:System.Nullable%601.HasValue%2A> leggere `False`il valore quando <xref:System.InvalidOperationException> è , Visual Basic genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2cb57-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="2cb57-141">Nell'esempio seguente viene illustrato il `numberOfChildren` modo consigliato per leggere la variabile degli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="2cb57-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="2cb57-142">Confronto di tipi nullableComparing Nullable Types</span><span class="sxs-lookup"><span data-stu-id="2cb57-142">Comparing Nullable Types</span></span>

<span data-ttu-id="2cb57-143">Quando le `Boolean` variabili nullable vengono utilizzate nelle `True` `False`espressioni `Nothing`booleane, il risultato può essere , , o .</span><span class="sxs-lookup"><span data-stu-id="2cb57-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="2cb57-144">Di seguito è riportata la tabella della verità per `And` e `Or`.</span><span class="sxs-lookup"><span data-stu-id="2cb57-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="2cb57-145">Perché `b1` `b2` e ora hanno tre valori possibili, ci sono nove combinazioni da valutare.</span><span class="sxs-lookup"><span data-stu-id="2cb57-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="2cb57-146">b1</span><span class="sxs-lookup"><span data-stu-id="2cb57-146">b1</span></span>|<span data-ttu-id="2cb57-147">B2</span><span class="sxs-lookup"><span data-stu-id="2cb57-147">b2</span></span>|<span data-ttu-id="2cb57-148">b1 E b2</span><span class="sxs-lookup"><span data-stu-id="2cb57-148">b1 And b2</span></span>|<span data-ttu-id="2cb57-149">b1 O b2</span><span class="sxs-lookup"><span data-stu-id="2cb57-149">b1 Or b2</span></span>|
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

<span data-ttu-id="2cb57-150">Quando il valore di una `Nothing`variabile booleana `true` `false`o di un'espressione è , non è né né .</span><span class="sxs-lookup"><span data-stu-id="2cb57-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="2cb57-151">Si consideri l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2cb57-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="2cb57-152">In questo `b1 And b2` esempio vengono `Nothing`valutati .</span><span class="sxs-lookup"><span data-stu-id="2cb57-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="2cb57-153">Di conseguenza, `Else` la clausola `If` viene eseguita in ogni istruzione e l'output è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2cb57-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="2cb57-154">`AndAlso`e `OrElse`, che utilizzano la valutazione del corto circuito, devono valutare `Nothing`il secondo operandi quando il primo restituisce .</span><span class="sxs-lookup"><span data-stu-id="2cb57-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="2cb57-155">Propagazione</span><span class="sxs-lookup"><span data-stu-id="2cb57-155">Propagation</span></span>

<span data-ttu-id="2cb57-156">Se uno o entrambi gli operandi di un'operazione aritmetica, di confronto, di spostamento o di tipo è un tipo di valore nullable, il risultato dell'operazione è anche un tipo di valore nullable.</span><span class="sxs-lookup"><span data-stu-id="2cb57-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is a nullable value type, the result of the operation is also a nullable value type.</span></span> <span data-ttu-id="2cb57-157">Se entrambi gli operandi `Nothing`hanno valori che non lo sono , l'operazione viene eseguita sui valori sottostanti degli operandi, come se nessuno dei due fosse un tipo di valore nullable.</span><span class="sxs-lookup"><span data-stu-id="2cb57-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable value type.</span></span> <span data-ttu-id="2cb57-158">Nell'esempio seguente, `compare1` `sum1` le variabili e sono tipizzate in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="2cb57-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="2cb57-159">Se si posiziona il puntatore del mouse su di essi, si noterà che il compilatore deduce i tipi di valore nullable per entrambi.</span><span class="sxs-lookup"><span data-stu-id="2cb57-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable value types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="2cb57-160">Se uno o entrambi gli operandi hanno un valore pari `Nothing`a , il risultato sarà `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="2cb57-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="2cb57-161">Utilizzo di tipi nullable con i datiUsing Nullable Types with Data</span><span class="sxs-lookup"><span data-stu-id="2cb57-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="2cb57-162">Un database è una delle posizioni più importanti in cui utilizzare i tipi di valore nullable.</span><span class="sxs-lookup"><span data-stu-id="2cb57-162">A database is one of the most important places to use nullable value types.</span></span> <span data-ttu-id="2cb57-163">Non tutti gli oggetti di database supportano attualmente i tipi di valore nullable, ma gli adattatori di tabella generati dalla finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="2cb57-163">Not all database objects currently support nullable value types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="2cb57-164">Vedere [Supporto TableAdapter per i tipi nullable](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span><span class="sxs-lookup"><span data-stu-id="2cb57-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="2cb57-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cb57-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="2cb57-166">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="2cb57-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="2cb57-167">Tipi valore e tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="2cb57-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="2cb57-168">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="2cb57-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="2cb57-169">Compilare i set di dati usando oggetti TableAdapter</span><span class="sxs-lookup"><span data-stu-id="2cb57-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="2cb57-170">Operatore If</span><span class="sxs-lookup"><span data-stu-id="2cb57-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="2cb57-171">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="2cb57-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="2cb57-172">Operatore Is</span><span class="sxs-lookup"><span data-stu-id="2cb57-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="2cb57-173">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="2cb57-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="2cb57-174">Tipi di valore nullable (c ')</span><span class="sxs-lookup"><span data-stu-id="2cb57-174">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
