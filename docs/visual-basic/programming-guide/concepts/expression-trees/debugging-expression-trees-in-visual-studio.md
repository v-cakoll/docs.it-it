---
title: Debug di alberi delle espressioni in Visual Studio (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 84de749afad6abb748d0622561f8ee7cd399ed54
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="a43e0-102">Alberi delle espressioni di debug in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a43e0-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="a43e0-103">Quando si esegue il debug delle applicazioni, è possibile analizzare la struttura e il contenuto degli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="a43e0-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="a43e0-104">Per ottenere una rapida panoramica della struttura ad albero dell'espressione, è possibile utilizzare il `DebugView` proprietà, che è disponibile solo in modalità debug.</span><span class="sxs-lookup"><span data-stu-id="a43e0-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="a43e0-105">Per ulteriori informazioni sul debug, vedere [debug in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a43e0-105">For more information about debugging, see [Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="a43e0-106">Per rappresentare meglio il contenuto degli alberi delle espressioni, il `DebugView` proprietà utilizza i visualizzatori di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a43e0-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="a43e0-107">Per ulteriori informazioni, vedere [i visualizzatori personalizzati creare](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data).</span><span class="sxs-lookup"><span data-stu-id="a43e0-107">For more information, see [Create Custom Visualizers](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="a43e0-108">Per aprire un visualizzatore per una struttura ad albero dell'espressione</span><span class="sxs-lookup"><span data-stu-id="a43e0-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="a43e0-109">Fare clic sull'icona di lente di ingrandimento visualizzata accanto al `DebugView` proprietà di un albero delle espressioni in **suggerimenti dati**, **espressioni di controllo** finestra, il **Auto** finestra o **variabili locali** finestra.</span><span class="sxs-lookup"><span data-stu-id="a43e0-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="a43e0-110">Verrà visualizzato un elenco di visualizzatori.</span><span class="sxs-lookup"><span data-stu-id="a43e0-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="a43e0-111">Fare clic sul visualizzatore da usare.</span><span class="sxs-lookup"><span data-stu-id="a43e0-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="a43e0-112">Ogni tipo di espressione viene visualizzato nel visualizzatore come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a43e0-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="a43e0-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="a43e0-113">ParameterExpressions</span></span>  
 <span data-ttu-id="a43e0-114"><xref:System.Linq.Expressions.ParameterExpression>vengono visualizzati i nomi delle variabili con un simbolo "$" all'inizio.</xref:System.Linq.Expressions.ParameterExpression></span><span class="sxs-lookup"><span data-stu-id="a43e0-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="a43e0-115">Se un parametro non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="a43e0-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a43e0-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="a43e0-116">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer), "num")  
    ```  
  
     <span data-ttu-id="a43e0-117">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a43e0-117">`DebugView` property</span></span>  
  
     `$num`  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer))  
    ```  
  
     <span data-ttu-id="a43e0-118">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a43e0-118">`DebugView` property</span></span>  
  
     `$var1`  
  
## <a name="constantexpressions"></a><span data-ttu-id="a43e0-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="a43e0-119">ConstantExpressions</span></span>  
 <span data-ttu-id="a43e0-120">Per <xref:System.Linq.Expressions.ConstantExpression>gli oggetti che rappresentano valori integer, stringhe e `null`, viene visualizzato il valore della costante.</xref:System.Linq.Expressions.ConstantExpression></span><span class="sxs-lookup"><span data-stu-id="a43e0-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a43e0-121">Esempi</span><span class="sxs-lookup"><span data-stu-id="a43e0-121">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num as Integer= 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="a43e0-122">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a43e0-122">`DebugView` property</span></span>  
  
     <span data-ttu-id="a43e0-123">10</span><span class="sxs-lookup"><span data-stu-id="a43e0-123">10</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num As Double = 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="a43e0-124">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a43e0-124">`DebugView` property</span></span>  
  
     <span data-ttu-id="a43e0-125">10D</span><span class="sxs-lookup"><span data-stu-id="a43e0-125">10D</span></span>  
  
## <a name="blockexpression"></a><span data-ttu-id="a43e0-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="a43e0-126">BlockExpression</span></span>  
 <span data-ttu-id="a43e0-127">Se il tipo di un <xref:System.Linq.Expressions.BlockExpression>oggetto differisce dal tipo dell'ultima espressione nel blocco, il tipo viene visualizzato nel `DebugInfo` proprietà parentesi angolari (\< e >).</xref:System.Linq.Expressions.BlockExpression></span><span class="sxs-lookup"><span data-stu-id="a43e0-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="a43e0-128">In caso contrario, il tipo di <xref:System.Linq.Expressions.BlockExpression>oggetto non viene visualizzato.</xref:System.Linq.Expressions.BlockExpression></span><span class="sxs-lookup"><span data-stu-id="a43e0-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a43e0-129">Esempi</span><span class="sxs-lookup"><span data-stu-id="a43e0-129">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="a43e0-130">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a43e0-130">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `"test"`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression =   
    Expression.Block(GetType(Object), Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="a43e0-131">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a43e0-131">`DebugView` property</span></span>  
  
     `.Block<System.Object>() {`  
  
     `"test"`  
  
     `}`  
  
## <a name="lambdaexpression"></a><span data-ttu-id="a43e0-132">Oggetto LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="a43e0-132">LambdaExpression</span></span>  
 <span data-ttu-id="a43e0-133"><xref:System.Linq.Expressions.LambdaExpression>gli oggetti vengono visualizzati insieme ai tipi delegati.</xref:System.Linq.Expressions.LambdaExpression></span><span class="sxs-lookup"><span data-stu-id="a43e0-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="a43e0-134">Se un'espressione lambda non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="a43e0-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a43e0-135">Esempi</span><span class="sxs-lookup"><span data-stu-id="a43e0-135">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))  
    ```  
  
     <span data-ttu-id="a43e0-136">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a43e0-136">`DebugView` property</span></span>  
  
     `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLamda", Nothing)  
    ```  
  
     <span data-ttu-id="a43e0-137">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a43e0-137">`DebugView` property</span></span>  
  
     `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
## <a name="labelexpression"></a><span data-ttu-id="a43e0-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="a43e0-138">LabelExpression</span></span>  
 <span data-ttu-id="a43e0-139">Se si specifica un valore predefinito per il <xref:System.Linq.Expressions.LabelExpression>dell'oggetto, questo valore viene visualizzato prima di <xref:System.Linq.Expressions.LabelTarget>oggetto.</xref:System.Linq.Expressions.LabelTarget> </xref:System.Linq.Expressions.LabelExpression></span><span class="sxs-lookup"><span data-stu-id="a43e0-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="a43e0-140">Il `.Label` token indica l'inizio dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="a43e0-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="a43e0-141">Il `.LabelTarget` token indica la destinazione della destinazione a cui passare.</span><span class="sxs-lookup"><span data-stu-id="a43e0-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="a43e0-142">Se un'etichetta non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="a43e0-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a43e0-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="a43e0-143">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")  
    Dim label1 As BlockExpression = Expression.Block(  
    Expression.Goto(target, Expression.Constant(0)),  
    Expression.Label(target, Expression.Constant(-1)))  
    ```  
  
     <span data-ttu-id="a43e0-144">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a43e0-144">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `.Goto SampleLabel { 0 };`  
  
     `.Label`  
  
     `-1`  
  
     `.LabelTarget SampleLabel:`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label()  
    Dim block As BlockExpression = Expression.Block(  
    Expression.Goto(target), Expression.Label(target))  
    ```  
  
     <span data-ttu-id="a43e0-145">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a43e0-145">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `.Goto #Label1 { };`  
  
     `.Label`  
  
     `.LabelTarget #Label1:`  
  
     `}`  
  
## <a name="checked-operators"></a><span data-ttu-id="a43e0-146">Operatori checked</span><span class="sxs-lookup"><span data-stu-id="a43e0-146">Checked Operators</span></span>  
 <span data-ttu-id="a43e0-147">Gli operatori checked vengono visualizzati con il simbolo "#" davanti l'operatore.</span><span class="sxs-lookup"><span data-stu-id="a43e0-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="a43e0-148">Ad esempio, l'operatore di addizione selezionato viene visualizzato come `#+`.</span><span class="sxs-lookup"><span data-stu-id="a43e0-148">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a43e0-149">Esempi</span><span class="sxs-lookup"><span data-stu-id="a43e0-149">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.AddChecked(  
    Expression.Constant(1), Expression.Constant(2))  
    ```  
  
     <span data-ttu-id="a43e0-150">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a43e0-150">`DebugView` property</span></span>  
  
     `1 #+ 2`  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.ConvertChecked(  
    Expression.Constant(10.0), GetType(Integer))  
    ```  
  
     <span data-ttu-id="a43e0-151">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a43e0-151">`DebugView` property</span></span>  
  
     `#(System.Int32)10D`  
  
## <a name="see-also"></a><span data-ttu-id="a43e0-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a43e0-152">See Also</span></span>  
 <span data-ttu-id="a43e0-153">[Alberi delle espressioni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="a43e0-153">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="a43e0-154"> [Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)  (Debug in Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="a43e0-154"> [Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span></span>  
<span data-ttu-id="a43e0-155"> [Creazione di visualizzatori personalizzati](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)</span><span class="sxs-lookup"><span data-stu-id="a43e0-155"> [Create Custom Visualizers](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
