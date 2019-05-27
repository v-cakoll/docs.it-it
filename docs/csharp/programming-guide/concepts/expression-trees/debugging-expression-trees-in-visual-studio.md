---
title: Debug degli alberi delle espressioni in Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 4017e2c2592dc1d6067b428fc1d47f37775abf85
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877179"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="4f662-102">Debug degli alberi delle espressioni in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="4f662-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="4f662-103">È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4f662-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="4f662-104">Per una panoramica rapida della struttura dell'albero delle espressioni è possibile usare la proprietà `DebugView`, che rappresenta gli alberi delle espressioni usando una sintassi speciale descritta [di seguito](#debugview-syntax).</span><span class="sxs-lookup"><span data-stu-id="4f662-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="4f662-105">Si noti che `DebugView` è disponibile solo in modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="4f662-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView di un albero delle espressioni all'interno del debugger di Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview.png)

<span data-ttu-id="4f662-107">Dato che `DebugView` è una stringa, è possibile usare il [Visualizzatore testo incorporato](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) per visualizzarla su più righe, selezionando **Visualizzatore testo** dall'icona della lente di ingrandimento accanto all'etichetta `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="4f662-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Visualizzatore testo applicato ai risultati di "DebugView"](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

<span data-ttu-id="4f662-109">In alternativa è possibile installare e usare [un visualizzatore personalizzato](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) per gli alberi delle espressioni:</span><span class="sxs-lookup"><span data-stu-id="4f662-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="4f662-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licenza MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponibile in [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)) esegue il rendering dell'albero delle espressioni come codice C#:</span><span class="sxs-lookup"><span data-stu-id="4f662-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Visualizzatore Readable Expressions](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="4f662-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([licenza MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)) offre una visualizzazione grafica dell'albero delle espressioni, delle relative proprietà e degli oggetti correlati:</span><span class="sxs-lookup"><span data-stu-id="4f662-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects:</span></span>

  ![Visualizzatore ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="4f662-114">Per aprire un visualizzatore per un albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="4f662-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="4f662-115">Fare clic sull'icona della lente di ingrandimento visualizzata accanto all'albero delle espressioni in **Suggerimenti dati**, in una finestra **Espressione di controllo**, nella finestra **Automatico** o nella finestra **Variabili locali**.</span><span class="sxs-lookup"><span data-stu-id="4f662-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="4f662-116">Viene visualizzato un elenco dei visualizzatori disponibili:</span><span class="sxs-lookup"><span data-stu-id="4f662-116">A list of available visualizers is displayed.:</span></span> 

      ![Apertura di visualizzatori da Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. <span data-ttu-id="4f662-118">Fare clic sul visualizzatore da usare.</span><span class="sxs-lookup"><span data-stu-id="4f662-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="4f662-119">Sintassi `DebugView`</span><span class="sxs-lookup"><span data-stu-id="4f662-119">`DebugView` syntax</span></span> 

<span data-ttu-id="4f662-120">Ogni tipo di espressione viene visualizzato dalla proprietà `DebugView` come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4f662-120">Each expression type is displayed by the `DebugView` property as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="4f662-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="4f662-121">ParameterExpressions</span></span>  
 <span data-ttu-id="4f662-122">I nomi delle variabili <xref:System.Linq.Expressions.ParameterExpression> vengono visualizzati con un simbolo "$" all'inizio.</span><span class="sxs-lookup"><span data-stu-id="4f662-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="4f662-123">Se un parametro non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="4f662-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="4f662-124">Esempi</span><span class="sxs-lookup"><span data-stu-id="4f662-124">Examples</span></span>  
  
|<span data-ttu-id="4f662-125">Espressione</span><span class="sxs-lookup"><span data-stu-id="4f662-125">Expression</span></span>|<span data-ttu-id="4f662-126">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4f662-126">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="4f662-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="4f662-127">ConstantExpressions</span></span>  
 <span data-ttu-id="4f662-128">Per gli oggetti <xref:System.Linq.Expressions.ConstantExpression> che rappresentano valori interi, stringhe e `null`, viene visualizzato il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="4f662-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="4f662-129">Per i tipi numerici che usano suffissi standard come valori letterali in C#, il suffisso viene aggiunto al valore.</span><span class="sxs-lookup"><span data-stu-id="4f662-129">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="4f662-130">La tabella seguente mostra i suffissi associati ai vari tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="4f662-130">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="4f662-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="4f662-131">Type</span></span>|<span data-ttu-id="4f662-132">Suffisso</span><span class="sxs-lookup"><span data-stu-id="4f662-132">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="4f662-133">G</span><span class="sxs-lookup"><span data-stu-id="4f662-133">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="4f662-134">L</span><span class="sxs-lookup"><span data-stu-id="4f662-134">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="4f662-135">UL</span><span class="sxs-lookup"><span data-stu-id="4f662-135">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="4f662-136">D</span><span class="sxs-lookup"><span data-stu-id="4f662-136">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="4f662-137">F</span><span class="sxs-lookup"><span data-stu-id="4f662-137">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="4f662-138">M</span><span class="sxs-lookup"><span data-stu-id="4f662-138">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="4f662-139">Esempi</span><span class="sxs-lookup"><span data-stu-id="4f662-139">Examples</span></span>  
  
|<span data-ttu-id="4f662-140">Espressione</span><span class="sxs-lookup"><span data-stu-id="4f662-140">Expression</span></span>|<span data-ttu-id="4f662-141">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4f662-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="4f662-142">10</span><span class="sxs-lookup"><span data-stu-id="4f662-142">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="4f662-143">10D</span><span class="sxs-lookup"><span data-stu-id="4f662-143">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="4f662-144">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="4f662-144">BlockExpression</span></span>  
 <span data-ttu-id="4f662-145">Se il tipo di un oggetto <xref:System.Linq.Expressions.BlockExpression> differisce dal tipo dell'ultima espressione nel blocco, il tipo viene visualizzato nella proprietà `DebugInfo` tra parentesi angolari (\< e >).</span><span class="sxs-lookup"><span data-stu-id="4f662-145">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="4f662-146">In caso contrario, il tipo dell'oggetto <xref:System.Linq.Expressions.BlockExpression> non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="4f662-146">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="4f662-147">Esempi</span><span class="sxs-lookup"><span data-stu-id="4f662-147">Examples</span></span>  
  
|<span data-ttu-id="4f662-148">Espressione</span><span class="sxs-lookup"><span data-stu-id="4f662-148">Expression</span></span>|<span data-ttu-id="4f662-149">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4f662-149">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="4f662-150">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="4f662-150">LambdaExpression</span></span>  
 <span data-ttu-id="4f662-151">Gli oggetti <xref:System.Linq.Expressions.LambdaExpression> vengono visualizzati insieme ai rispettivi tipi delegato.</span><span class="sxs-lookup"><span data-stu-id="4f662-151"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="4f662-152">Se un'espressione lamda non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="4f662-152">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="4f662-153">Esempi</span><span class="sxs-lookup"><span data-stu-id="4f662-153">Examples</span></span>  
  
|<span data-ttu-id="4f662-154">Espressione</span><span class="sxs-lookup"><span data-stu-id="4f662-154">Expression</span></span>|<span data-ttu-id="4f662-155">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4f662-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="4f662-156">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="4f662-156">LabelExpression</span></span>  
 <span data-ttu-id="4f662-157">Se si specifica un valore predefinito per l'oggetto <xref:System.Linq.Expressions.LabelExpression>, questo valore viene visualizzato prima dell'oggetto <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="4f662-157">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="4f662-158">Il token `.Label` indica l'inizio dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="4f662-158">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="4f662-159">Il token `.LabelTarget` indica la destinazione alla quale passare.</span><span class="sxs-lookup"><span data-stu-id="4f662-159">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="4f662-160">Se un'etichetta non presenta un nome, ne viene assegnato uno generato automaticamente, ad esempio `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="4f662-160">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="4f662-161">Esempi</span><span class="sxs-lookup"><span data-stu-id="4f662-161">Examples</span></span>  
  
|<span data-ttu-id="4f662-162">Espressione</span><span class="sxs-lookup"><span data-stu-id="4f662-162">Expression</span></span>|<span data-ttu-id="4f662-163">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4f662-163">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="4f662-164">Operatori checked</span><span class="sxs-lookup"><span data-stu-id="4f662-164">Checked Operators</span></span>  
 <span data-ttu-id="4f662-165">Gli operatori di questo tipo vengono visualizzati con il simbolo "#" davanti l'operatore.</span><span class="sxs-lookup"><span data-stu-id="4f662-165">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="4f662-166">Ad esempio, l'operatore di addizione checked viene visualizzato come `#+`.</span><span class="sxs-lookup"><span data-stu-id="4f662-166">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="4f662-167">Esempi</span><span class="sxs-lookup"><span data-stu-id="4f662-167">Examples</span></span>  
  
|<span data-ttu-id="4f662-168">Espressione</span><span class="sxs-lookup"><span data-stu-id="4f662-168">Expression</span></span>|<span data-ttu-id="4f662-169">Proprietà`DebugView` </span><span class="sxs-lookup"><span data-stu-id="4f662-169">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="4f662-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f662-170">See also</span></span>

- [<span data-ttu-id="4f662-171">Alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="4f662-171">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="4f662-172">Debug in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4f662-172">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="4f662-173">Creazione di visualizzatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="4f662-173">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
