---
title: Debug degli alberi delle espressioni in Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 4c522f2c24cff037ff33d400c8bdfa7500fd4c32
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614376"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a>Debug degli alberi delle espressioni in Visual Studio (C#)
È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni. Per una rapida panoramica della struttura dell'albero delle espressioni, è possibile usare la proprietà `DebugView`, che rappresenta gli alberi delle espressioni [usando una sintassi speciale](debugview-syntax.md). Si noti che `DebugView` è disponibile solo in modalità di debug.  

![Screenshot della DebugView di un albero delle espressioni nel debugger di Visual Studio.](media/debugging-expression-trees-in-visual-studio/debugview-expression-tree.png)

Dato che `DebugView` è una stringa, è possibile usare il [Visualizzatore testo incorporato](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) per visualizzarla su più righe, selezionando **Visualizzatore testo** dall'icona della lente di ingrandimento accanto all'etichetta `DebugView`.

 ![Screenshot del Visualizzatore di testo applicato ai risultati di DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-debugview.png)

In alternativa, è possibile installare e usare [un visualizzatore personalizzato](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) per gli alberi delle espressioni, ad esempio:

- Le [espressioni leggibili](https://github.com/agileobjects/ReadableExpressions) ([licenza mit](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponibili all' [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), eseguono il rendering dell'albero delle espressioni come codice C# con tema, con varie opzioni di rendering:

  ![Screenshot del Visualizzatore espressioni leggibili.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- Il [Visualizzatore dell'albero delle espressioni](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([licenza mit](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) fornisce una visualizzazione albero dell'albero delle espressioni e dei singoli nodi:

  ![Screenshot del Visualizzatore dell'albero delle espressioni.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Per aprire un visualizzatore per un albero delle espressioni  
  
1. Fare clic sull'icona della lente di ingrandimento visualizzata accanto all'albero delle espressioni in **Suggerimenti dati**, in una finestra **Espressione di controllo**, nella finestra **Automatico** o nella finestra **Variabili locali**.  

    Viene visualizzato un elenco dei visualizzatori disponibili:

    ![Screenshot che illustra l'apertura dei visualizzatori da Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers.png)

2. Fare clic sul visualizzatore da usare.  
  
## <a name="see-also"></a>Vedere anche

- [Alberi delle espressioni (C#)](./index.md)
- [Debug in Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Creare visualizzatori personalizzati](/visualstudio/debugger/create-custom-visualizers-of-data)
- [`DebugView`sintassi](debugview-syntax.md)
