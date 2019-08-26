---
title: Debug degli alberi delle espressioni in Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 19d00aaa99c7ef08e291337f38bf74a3beac12b0
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595233"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="c092c-102">Debug degli alberi delle espressioni in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="c092c-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="c092c-103">È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c092c-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="c092c-104">Per una rapida panoramica della struttura dell'albero delle espressioni, è possibile usare la proprietà `DebugView`, che rappresenta gli alberi delle espressioni [usando una sintassi speciale](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="c092c-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="c092c-105">Si noti che `DebugView` è disponibile solo in modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="c092c-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView di un albero delle espressioni all'interno del debugger di Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview.png)

<span data-ttu-id="c092c-107">Dato che `DebugView` è una stringa, è possibile usare il [Visualizzatore testo incorporato](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) per visualizzarla su più righe, selezionando **Visualizzatore testo** dall'icona della lente di ingrandimento accanto all'etichetta `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="c092c-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Visualizzatore testo applicato ai risultati di "DebugView"](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

<span data-ttu-id="c092c-109">In alternativa, è possibile installare e usare [un visualizzatore personalizzato](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) per gli alberi delle espressioni, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c092c-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

* <span data-ttu-id="c092c-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licenza MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponibile in [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)) esegue il rendering dell'albero delle espressioni come codice C#:</span><span class="sxs-lookup"><span data-stu-id="c092c-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Visualizzatore Readable Expressions](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="c092c-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([licenza MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)) offre una visualizzazione grafica dell'albero delle espressioni, delle relative proprietà e degli oggetti correlati:</span><span class="sxs-lookup"><span data-stu-id="c092c-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects:</span></span>

  ![Visualizzatore ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="c092c-114">Per aprire un visualizzatore per un albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="c092c-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="c092c-115">Fare clic sull'icona della lente di ingrandimento visualizzata accanto all'albero delle espressioni in **Suggerimenti dati**, in una finestra **Espressione di controllo**, nella finestra **Automatico** o nella finestra **Variabili locali**.</span><span class="sxs-lookup"><span data-stu-id="c092c-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="c092c-116">Viene visualizzato un elenco dei visualizzatori disponibili:</span><span class="sxs-lookup"><span data-stu-id="c092c-116">A list of available visualizers is displayed.:</span></span> 

      ![Apertura di visualizzatori da Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. <span data-ttu-id="c092c-118">Fare clic sul visualizzatore da usare.</span><span class="sxs-lookup"><span data-stu-id="c092c-118">Click the visualizer you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c092c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c092c-119">See also</span></span>

- [<span data-ttu-id="c092c-120">Alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="c092c-120">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="c092c-121">Debug in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c092c-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="c092c-122">Creazione di visualizzatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="c092c-122">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- <span data-ttu-id="c092c-123">Sintassi di [`DebugView`](debugview-syntax.md)</span><span class="sxs-lookup"><span data-stu-id="c092c-123">[`DebugView` syntax](debugview-syntax.md)</span></span>
