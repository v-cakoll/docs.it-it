---
title: Debug degli alberi delle espressioni in Visual Studio
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 3811958353d1d55ce74da41c6a45dbe730cc9790
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375434"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Debug degli alberi delle espressioni in Visual Studio (Visual Basic)
È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni. Per una rapida panoramica della struttura dell'albero delle espressioni, è possibile usare la proprietà `DebugView`, che rappresenta gli alberi delle espressioni [usando una sintassi speciale](debugview-syntax.md). Si noti che `DebugView` è disponibile solo in modalità di debug.  

![Screenshot della DebugView dell'albero delle espressioni.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

Dato che `DebugView` è una stringa, è possibile usare il [Visualizzatore testo incorporato](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) per visualizzarla su più righe, selezionando **Visualizzatore testo** dall'icona della lente di ingrandimento accanto all'etichetta `DebugView`.

 ![Screenshot del Visualizzatore di testo applicato ai risultati di DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

In alternativa, è possibile installare e usare [un visualizzatore personalizzato](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) per gli alberi delle espressioni, ad esempio:

- Le [espressioni leggibili](https://github.com/agileobjects/ReadableExpressions) ([licenza mit](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponibili all' [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), eseguono il rendering dell'albero delle espressioni come codice C# con tema, con varie opzioni di rendering:

  ![Screenshot del Visualizzatore espressioni leggibili.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- Il [Visualizzatore dell'albero delle espressioni](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([licenza mit](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) fornisce una visualizzazione albero dell'albero delle espressioni e dei singoli nodi. e possono eseguire il rendering dell'albero delle espressioni usando Visual Basic sintassi:

  ![Screenshot del Visualizzatore dell'albero delle espressioni.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Per aprire un visualizzatore per un albero delle espressioni  
  
1. Fare clic sull'icona della lente di ingrandimento visualizzata accanto all'albero delle espressioni in **Suggerimenti dati**, in una finestra **Espressione di controllo**, nella finestra **Automatico** o nella finestra **Variabili locali**.  
  
    Viene visualizzato un elenco dei visualizzatori disponibili:

    ![Screenshot dell'utente che apre i visualizzatori da Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. Fare clic sul visualizzatore da usare.  

## <a name="see-also"></a>Vedere anche

- [Alberi delle espressioni (Visual Basic)](index.md)
- [Debug in Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Creare visualizzatori personalizzati](/visualstudio/debugger/create-custom-visualizers-of-data)
- [`DebugView`sintassi](debugview-syntax.md)
