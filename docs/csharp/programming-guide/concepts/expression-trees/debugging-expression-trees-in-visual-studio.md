---
title: Debug degli alberi delle espressioni in Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: dd3008ffd1364eec3938053bd7d37f95b8a1ebc0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509623"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="8d3ee-102">Debug degli alberi delle espressioni in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="8d3ee-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="8d3ee-103">È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="8d3ee-104">Per una breve panoramica della struttura ad albero dell'espressione, è possibile usare la proprietà `DebugView`, disponibile solo nella modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="8d3ee-105">Per altre informazioni sul debug, vedere [Debug in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="8d3ee-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="8d3ee-106">Per rappresentare meglio il contenuto degli alberi delle espressioni, la proprietà `DebugView` usa i visualizzatori di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="8d3ee-107">Per altre informazioni, vedere [Creare visualizzatori personalizzati](/visualstudio/debugger/create-custom-visualizers-of-data).</span><span class="sxs-lookup"><span data-stu-id="8d3ee-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="8d3ee-108">Per aprire un visualizzatore per un albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="8d3ee-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="8d3ee-109">Fare clic sull'icona a forma di lente di ingrandimento visualizzata accanto alla proprietà `DebugView` di una struttura ad albero dell'espressione in **Suggerimenti dati**, in una finestra **Espressioni di controllo**, nella finestra **Auto** o nella finestra **Variabili locali**.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="8d3ee-110">Verrà visualizzato un elenco di visualizzatori.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="8d3ee-111">Fare clic sul visualizzatore da usare.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="8d3ee-112">Ogni tipo di espressione viene visualizzato nel visualizzatore come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="8d3ee-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="8d3ee-113">ParameterExpressions</span></span>  
 <span data-ttu-id="8d3ee-114">I nomi delle variabili <xref:System.Linq.Expressions.ParameterExpression> vengono visualizzati con un simbolo "$" all'inizio.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="8d3ee-115">Se un parametro non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="8d3ee-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="8d3ee-116">Examples</span></span>  
  
|<span data-ttu-id="8d3ee-117">Espressione</span><span class="sxs-lookup"><span data-stu-id="8d3ee-117">Expression</span></span>|<span data-ttu-id="8d3ee-118">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="8d3ee-118">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="8d3ee-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="8d3ee-119">ConstantExpressions</span></span>  
 <span data-ttu-id="8d3ee-120">Per gli oggetti <xref:System.Linq.Expressions.ConstantExpression> che rappresentano valori interi, stringhe e `null`, viene visualizzato il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="8d3ee-121">Per i tipi numerici che usano suffissi standard come valori letterali in C#, il suffisso viene aggiunto al valore.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-121">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="8d3ee-122">La tabella seguente mostra i suffissi associati ai vari tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-122">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="8d3ee-123">Tipo</span><span class="sxs-lookup"><span data-stu-id="8d3ee-123">Type</span></span>|<span data-ttu-id="8d3ee-124">Suffisso</span><span class="sxs-lookup"><span data-stu-id="8d3ee-124">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="8d3ee-125">G</span><span class="sxs-lookup"><span data-stu-id="8d3ee-125">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="8d3ee-126">L</span><span class="sxs-lookup"><span data-stu-id="8d3ee-126">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="8d3ee-127">UL</span><span class="sxs-lookup"><span data-stu-id="8d3ee-127">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="8d3ee-128">D</span><span class="sxs-lookup"><span data-stu-id="8d3ee-128">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="8d3ee-129">F</span><span class="sxs-lookup"><span data-stu-id="8d3ee-129">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="8d3ee-130">M</span><span class="sxs-lookup"><span data-stu-id="8d3ee-130">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="8d3ee-131">Esempi</span><span class="sxs-lookup"><span data-stu-id="8d3ee-131">Examples</span></span>  
  
|<span data-ttu-id="8d3ee-132">Espressione</span><span class="sxs-lookup"><span data-stu-id="8d3ee-132">Expression</span></span>|<span data-ttu-id="8d3ee-133">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="8d3ee-133">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="8d3ee-134">10</span><span class="sxs-lookup"><span data-stu-id="8d3ee-134">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="8d3ee-135">10D</span><span class="sxs-lookup"><span data-stu-id="8d3ee-135">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="8d3ee-136">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="8d3ee-136">BlockExpression</span></span>  
 <span data-ttu-id="8d3ee-137">Se il tipo di un oggetto <xref:System.Linq.Expressions.BlockExpression> differisce dal tipo dell'ultima espressione nel blocco, il tipo viene visualizzato nella proprietà `DebugInfo` tra parentesi angolari (\< e >).</span><span class="sxs-lookup"><span data-stu-id="8d3ee-137">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="8d3ee-138">In caso contrario, il tipo dell'oggetto <xref:System.Linq.Expressions.BlockExpression> non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-138">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="8d3ee-139">Esempi</span><span class="sxs-lookup"><span data-stu-id="8d3ee-139">Examples</span></span>  
  
|<span data-ttu-id="8d3ee-140">Espressione</span><span class="sxs-lookup"><span data-stu-id="8d3ee-140">Expression</span></span>|<span data-ttu-id="8d3ee-141">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="8d3ee-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="8d3ee-142">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="8d3ee-142">LambdaExpression</span></span>  
 <span data-ttu-id="8d3ee-143">Gli oggetti <xref:System.Linq.Expressions.LambdaExpression> vengono visualizzati insieme ai rispettivi tipi delegato.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-143"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="8d3ee-144">Se un'espressione lamda non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-144">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="8d3ee-145">Esempi</span><span class="sxs-lookup"><span data-stu-id="8d3ee-145">Examples</span></span>  
  
|<span data-ttu-id="8d3ee-146">Espressione</span><span class="sxs-lookup"><span data-stu-id="8d3ee-146">Expression</span></span>|<span data-ttu-id="8d3ee-147">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="8d3ee-147">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="8d3ee-148">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="8d3ee-148">LabelExpression</span></span>  
 <span data-ttu-id="8d3ee-149">Se si specifica un valore predefinito per l'oggetto <xref:System.Linq.Expressions.LabelExpression>, questo valore viene visualizzato prima dell'oggetto <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-149">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="8d3ee-150">Il token `.Label` indica l'inizio dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-150">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="8d3ee-151">Il token `.LabelTarget` indica la destinazione alla quale passare.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-151">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="8d3ee-152">Se un'etichetta non presenta un nome, ne viene assegnato uno generato automaticamente, ad esempio `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-152">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="8d3ee-153">Esempi</span><span class="sxs-lookup"><span data-stu-id="8d3ee-153">Examples</span></span>  
  
|<span data-ttu-id="8d3ee-154">Espressione</span><span class="sxs-lookup"><span data-stu-id="8d3ee-154">Expression</span></span>|<span data-ttu-id="8d3ee-155">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="8d3ee-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="8d3ee-156">Operatori checked</span><span class="sxs-lookup"><span data-stu-id="8d3ee-156">Checked Operators</span></span>  
 <span data-ttu-id="8d3ee-157">Gli operatori di questo tipo vengono visualizzati con il simbolo "#" davanti l'operatore.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-157">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="8d3ee-158">Ad esempio, l'operatore di addizione checked viene visualizzato come `#+`.</span><span class="sxs-lookup"><span data-stu-id="8d3ee-158">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="8d3ee-159">Esempi</span><span class="sxs-lookup"><span data-stu-id="8d3ee-159">Examples</span></span>  
  
|<span data-ttu-id="8d3ee-160">Espressione</span><span class="sxs-lookup"><span data-stu-id="8d3ee-160">Expression</span></span>|<span data-ttu-id="8d3ee-161">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="8d3ee-161">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="8d3ee-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d3ee-162">See Also</span></span>

- [<span data-ttu-id="8d3ee-163">Alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="8d3ee-163">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
- [<span data-ttu-id="8d3ee-164">Debug in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8d3ee-164">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)  
- [<span data-ttu-id="8d3ee-165">Creazione di visualizzatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="8d3ee-165">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
