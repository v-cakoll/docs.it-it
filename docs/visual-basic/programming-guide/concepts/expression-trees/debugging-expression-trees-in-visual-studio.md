---
title: Debug degli alberi delle espressioni in Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 9aead09e0e9469f13e2d6befbad444d3c7fecabd
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196019"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="719cb-102">Debug degli alberi delle espressioni in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="719cb-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="719cb-103">È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="719cb-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="719cb-104">Per ottenere una rapida panoramica della struttura ad albero dell'espressione, è possibile usare la `DebugView` proprietà, che rappresenta gli alberi delle espressioni [usando una sintassi speciale](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="719cb-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="719cb-105">Si noti che `DebugView` è disponibile solo in modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="719cb-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView di un albero delle espressioni all'interno del debugger di Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

<span data-ttu-id="719cb-107">Dato che `DebugView` è una stringa, è possibile usare il [Visualizzatore testo incorporato](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) per visualizzarla su più righe, selezionando **Visualizzatore testo** dall'icona della lente di ingrandimento accanto all'etichetta `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="719cb-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Visualizzatore testo applicato ai risultati di "DebugView"](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

<span data-ttu-id="719cb-109">In alternativa, è possibile installare e usare [un visualizzatore personalizzato](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) degli alberi delle espressioni, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="719cb-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

* <span data-ttu-id="719cb-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licenza MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponibile in [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)) esegue il rendering dell'albero delle espressioni come codice C#:</span><span class="sxs-lookup"><span data-stu-id="719cb-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Visualizzatore Readable Expressions](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="719cb-112">[Visualizzatore di struttura ad albero delle espressioni](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([licenza MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), offre una visualizzazione grafica di albero delle espressioni, relative proprietà e oggetti correlati e può eseguire il rendering dell'albero delle espressioni tramite codice Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="719cb-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![Visualizzatore ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="719cb-114">Per aprire un visualizzatore per un albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="719cb-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="719cb-115">Fare clic sull'icona della lente di ingrandimento visualizzata accanto all'albero delle espressioni in **Suggerimenti dati**, in una finestra **Espressione di controllo**, nella finestra **Automatico** o nella finestra **Variabili locali**.</span><span class="sxs-lookup"><span data-stu-id="719cb-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="719cb-116">Viene visualizzato un elenco dei visualizzatori disponibili:</span><span class="sxs-lookup"><span data-stu-id="719cb-116">A list of available visualizers is displayed.:</span></span> 

      ![Apertura di visualizzatori da Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. <span data-ttu-id="719cb-118">Fare clic sul visualizzatore da usare.</span><span class="sxs-lookup"><span data-stu-id="719cb-118">Click the visualizer you want to use.</span></span>  

## <a name="see-also"></a><span data-ttu-id="719cb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="719cb-119">See also</span></span>

- [<span data-ttu-id="719cb-120">Alberi delle espressioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="719cb-120">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="719cb-121">Debug in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="719cb-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="719cb-122">Creazione di visualizzatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="719cb-122">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
- [<span data-ttu-id="719cb-123">`DebugView` Sintassi</span><span class="sxs-lookup"><span data-stu-id="719cb-123">`DebugView` syntax</span></span>](debugview-syntax.md)
