---
title: Debug degli alberi delle espressioni in Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 7fc97d898c5956b5a569036e6e0fe1174714576d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65879876"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="4fbb1-102">Debug degli alberi delle espressioni in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fbb1-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="4fbb1-103">È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="4fbb1-104">Per ottenere una rapida panoramica della struttura ad albero dell'espressione, è possibile usare la `DebugView` proprietà, che rappresenta gli alberi delle espressioni usando una sintassi speciale descritta [seguito](#debugview-syntax).</span><span class="sxs-lookup"><span data-stu-id="4fbb1-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="4fbb1-105">(Si noti che `DebugView` è disponibile solo in modalità di debug.)</span><span class="sxs-lookup"><span data-stu-id="4fbb1-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView di albero delle espressioni all'interno del debugger di Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

<span data-ttu-id="4fbb1-107">Poiché `DebugView` è una stringa, è possibile usare il [Visualizzatore testo incorporato](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) per visualizzarlo su più righe, selezionando **Visualizzatore di testo** dall'icona della lente di ingrandimento accanto al `DebugView` etichetta.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Visualizzatore testo applicato ai risultati di 'DebugView'](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

<span data-ttu-id="4fbb1-109">In alternativa, è possibile installare e usare [un visualizzatore personalizzato](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) degli alberi delle espressioni:</span><span class="sxs-lookup"><span data-stu-id="4fbb1-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="4fbb1-110">[Le espressioni leggibile](https://github.com/agileobjects/ReadableExpressions) ([licenza MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponibile all'indirizzo il [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), viene eseguito il rendering dell'albero delle espressioni come C# codice:</span><span class="sxs-lookup"><span data-stu-id="4fbb1-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Visualizzatore espressioni leggibile](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="4fbb1-112">[Visualizzatore di struttura ad albero delle espressioni](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([licenza MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), offre una visualizzazione grafica di albero delle espressioni, relative proprietà e oggetti correlati e può eseguire il rendering dell'albero delle espressioni tramite codice Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="4fbb1-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![Visualizzatore ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="4fbb1-114">Per aprire un visualizzatore per un albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="4fbb1-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="4fbb1-115">Fai clic sull'icona della lente di ingrandimento visualizzata accanto l'albero delle espressioni in **suggerimenti dati**, un **Watch** finestra, il **Auto** finestra o il **variabililocali** finestra.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="4fbb1-116">Viene visualizzato un elenco di visualizzatori disponibili.:</span><span class="sxs-lookup"><span data-stu-id="4fbb1-116">A list of available visualizers is displayed.:</span></span> 

      ![Visualizzatori di apertura da Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. <span data-ttu-id="4fbb1-118">Fare clic sul visualizzatore da usare.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="4fbb1-119">`DebugView` Sintassi</span><span class="sxs-lookup"><span data-stu-id="4fbb1-119">`DebugView` syntax</span></span> 

<span data-ttu-id="4fbb1-120">Ogni tipo di espressione viene visualizzato nel visualizzatore come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-120">Each expression type is displayed in the visualizer as described in the following sections.</span></span>

## <a name="parameterexpressions"></a><span data-ttu-id="4fbb1-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="4fbb1-121">ParameterExpressions</span></span>

<span data-ttu-id="4fbb1-122">I nomi delle variabili <xref:System.Linq.Expressions.ParameterExpression> vengono visualizzati con un simbolo "$" all'inizio.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="4fbb1-123">Se un parametro non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="4fbb1-124">Esempi</span><span class="sxs-lookup"><span data-stu-id="4fbb1-124">Examples</span></span>

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    <span data-ttu-id="4fbb1-125">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4fbb1-125">`DebugView` property</span></span>

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    <span data-ttu-id="4fbb1-126">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4fbb1-126">`DebugView` property</span></span>

    `$var1`

## <a name="constantexpressions"></a><span data-ttu-id="4fbb1-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="4fbb1-127">ConstantExpressions</span></span>
 <span data-ttu-id="4fbb1-128">Per gli oggetti <xref:System.Linq.Expressions.ConstantExpression> che rappresentano valori interi, stringhe e `null`, viene visualizzato il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="4fbb1-129">Esempi</span><span class="sxs-lookup"><span data-stu-id="4fbb1-129">Examples</span></span>

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="4fbb1-130">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4fbb1-130">`DebugView` property</span></span>

    <span data-ttu-id="4fbb1-131">10</span><span class="sxs-lookup"><span data-stu-id="4fbb1-131">10</span></span>

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="4fbb1-132">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4fbb1-132">`DebugView` property</span></span>

    <span data-ttu-id="4fbb1-133">10D</span><span class="sxs-lookup"><span data-stu-id="4fbb1-133">10D</span></span>

## <a name="blockexpression"></a><span data-ttu-id="4fbb1-134">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="4fbb1-134">BlockExpression</span></span>

<span data-ttu-id="4fbb1-135">Se il tipo di un oggetto <xref:System.Linq.Expressions.BlockExpression> differisce dal tipo dell'ultima espressione nel blocco, il tipo viene visualizzato nella proprietà `DebugInfo` tra parentesi angolari (\< e >).</span><span class="sxs-lookup"><span data-stu-id="4fbb1-135">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="4fbb1-136">In caso contrario, il tipo dell'oggetto <xref:System.Linq.Expressions.BlockExpression> non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-136">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="4fbb1-137">Esempi</span><span class="sxs-lookup"><span data-stu-id="4fbb1-137">Examples</span></span>

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    <span data-ttu-id="4fbb1-138">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4fbb1-138">`DebugView` property</span></span>

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    <span data-ttu-id="4fbb1-139">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4fbb1-139">`DebugView` property</span></span>

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a><span data-ttu-id="4fbb1-140">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="4fbb1-140">LambdaExpression</span></span>

<span data-ttu-id="4fbb1-141">Gli oggetti <xref:System.Linq.Expressions.LambdaExpression> vengono visualizzati insieme ai rispettivi tipi delegato.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-141"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="4fbb1-142">Se un'espressione lamda non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-142">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="4fbb1-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="4fbb1-143">Examples</span></span>

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    <span data-ttu-id="4fbb1-144">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4fbb1-144">`DebugView` property</span></span>

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    <span data-ttu-id="4fbb1-145">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4fbb1-145">`DebugView` property</span></span>

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a><span data-ttu-id="4fbb1-146">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="4fbb1-146">LabelExpression</span></span>

<span data-ttu-id="4fbb1-147">Se si specifica un valore predefinito per l'oggetto <xref:System.Linq.Expressions.LabelExpression>, questo valore viene visualizzato prima dell'oggetto <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-147">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="4fbb1-148">Il token `.Label` indica l'inizio dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-148">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="4fbb1-149">Il token `.LabelTarget` indica la destinazione alla quale passare.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-149">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="4fbb1-150">Se un'etichetta non presenta un nome, ne viene assegnato uno generato automaticamente, ad esempio `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-150">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="4fbb1-151">Esempi</span><span class="sxs-lookup"><span data-stu-id="4fbb1-151">Examples</span></span>

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    <span data-ttu-id="4fbb1-152">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4fbb1-152">`DebugView` property</span></span>

    `.Block() {`

    `.Goto SampleLabel { 0 };`

    `.Label`

    `-1`

    `.LabelTarget SampleLabel:`

    `}`

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label()
    Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), Expression.Label(target))
    ```

    <span data-ttu-id="4fbb1-153">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4fbb1-153">`DebugView` property</span></span>

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a><span data-ttu-id="4fbb1-154">Operatori checked</span><span class="sxs-lookup"><span data-stu-id="4fbb1-154">Checked Operators</span></span>

<span data-ttu-id="4fbb1-155">Gli operatori di questo tipo vengono visualizzati con il simbolo "#" davanti l'operatore.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-155">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="4fbb1-156">Ad esempio, l'operatore di addizione checked viene visualizzato come `#+`.</span><span class="sxs-lookup"><span data-stu-id="4fbb1-156">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="4fbb1-157">Esempi</span><span class="sxs-lookup"><span data-stu-id="4fbb1-157">Examples</span></span>

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    <span data-ttu-id="4fbb1-158">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4fbb1-158">`DebugView` property</span></span>

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    <span data-ttu-id="4fbb1-159">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4fbb1-159">`DebugView` property</span></span>

    `#(System.Int32)10D`

## <a name="see-also"></a><span data-ttu-id="4fbb1-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fbb1-160">See also</span></span>

- [<span data-ttu-id="4fbb1-161">Alberi delle espressioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fbb1-161">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="4fbb1-162">Debug in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4fbb1-162">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="4fbb1-163">Creazione di visualizzatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="4fbb1-163">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
