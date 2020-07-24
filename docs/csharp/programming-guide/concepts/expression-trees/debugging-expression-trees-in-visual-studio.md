---
title: Debug degli alberi delle espressioni in Visual Studio (C#)
description: Informazioni sulla proprietà DebugView in Visual Studio. Vedere come usare questa proprietà per analizzare la struttura e il contenuto degli alberi delle espressioni.
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 5d62a5e6fa5ce537a1ea8b316e7322eb976200c0
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105650"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="ffd0c-104">Debug degli alberi delle espressioni in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="ffd0c-104">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="ffd0c-105">È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ffd0c-105">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="ffd0c-106">Per una rapida panoramica della struttura dell'albero delle espressioni, è possibile usare la proprietà `DebugView`, che rappresenta gli alberi delle espressioni [usando una sintassi speciale](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="ffd0c-106">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="ffd0c-107">Si noti che `DebugView` è disponibile solo in modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="ffd0c-107">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Screenshot della DebugView di un albero delle espressioni nel debugger di Visual Studio.](media/debugging-expression-trees-in-visual-studio/debugview-expression-tree.png)

<span data-ttu-id="ffd0c-109">Dato che `DebugView` è una stringa, è possibile usare il [Visualizzatore testo incorporato](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) per visualizzarla su più righe, selezionando **Visualizzatore testo** dall'icona della lente di ingrandimento accanto all'etichetta `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="ffd0c-109">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Screenshot del Visualizzatore di testo applicato ai risultati di DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-debugview.png)

<span data-ttu-id="ffd0c-111">In alternativa, è possibile installare e usare [un visualizzatore personalizzato](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) per gli alberi delle espressioni, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ffd0c-111">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="ffd0c-112">Le [espressioni leggibili](https://github.com/agileobjects/ReadableExpressions) ([licenza mit](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponibili all' [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), eseguono il rendering dell'albero delle espressioni come codice C# con tema, con varie opzioni di rendering:</span><span class="sxs-lookup"><span data-stu-id="ffd0c-112">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as themeable C# code, with various rendering options:</span></span>

  ![Screenshot del Visualizzatore espressioni leggibili.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- <span data-ttu-id="ffd0c-114">Il [Visualizzatore dell'albero delle espressioni](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([licenza mit](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) fornisce una visualizzazione albero dell'albero delle espressioni e dei singoli nodi:</span><span class="sxs-lookup"><span data-stu-id="ffd0c-114">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([MIT license](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) provides a tree view of the expression tree and its individual nodes:</span></span>

  ![Screenshot del Visualizzatore dell'albero delle espressioni.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="ffd0c-116">Per aprire un visualizzatore per un albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="ffd0c-116">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="ffd0c-117">Fare clic sull'icona della lente di ingrandimento visualizzata accanto all'albero delle espressioni in **Suggerimenti dati**, in una finestra **Espressione di controllo**, nella finestra **Automatico** o nella finestra **Variabili locali**.</span><span class="sxs-lookup"><span data-stu-id="ffd0c-117">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  

    <span data-ttu-id="ffd0c-118">Viene visualizzato un elenco dei visualizzatori disponibili:</span><span class="sxs-lookup"><span data-stu-id="ffd0c-118">A list of available visualizers is displayed.:</span></span>

    ![Screenshot che illustra l'apertura dei visualizzatori da Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers.png)

2. <span data-ttu-id="ffd0c-120">Fare clic sul visualizzatore da usare.</span><span class="sxs-lookup"><span data-stu-id="ffd0c-120">Click the visualizer you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffd0c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffd0c-121">See also</span></span>

- [<span data-ttu-id="ffd0c-122">Alberi delle espressioni (C#)</span><span class="sxs-lookup"><span data-stu-id="ffd0c-122">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="ffd0c-123">Debug in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ffd0c-123">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="ffd0c-124">Creare visualizzatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="ffd0c-124">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="ffd0c-125">`DebugView`sintassi</span><span class="sxs-lookup"><span data-stu-id="ffd0c-125">`DebugView` syntax</span></span>](debugview-syntax.md)
