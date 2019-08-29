---
title: Debug degli alberi delle espressioni in Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 3334828475ef5d933ea660ea33ae264d4ccce172
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106873"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Debug degli alberi delle espressioni in Visual Studio (Visual Basic)
È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni. Per una rapida panoramica della struttura dell'albero delle espressioni, è possibile usare la proprietà `DebugView`, che rappresenta gli alberi delle espressioni [usando una sintassi speciale](debugview-syntax.md). Si noti che `DebugView` è disponibile solo in modalità di debug.  

![DebugView di un albero delle espressioni all'interno del debugger di Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

Dato che `DebugView` è una stringa, è possibile usare il [Visualizzatore testo incorporato](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) per visualizzarla su più righe, selezionando **Visualizzatore testo** dall'icona della lente di ingrandimento accanto all'etichetta `DebugView`.

 ![Visualizzatore testo applicato ai risultati di "DebugView"](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

In alternativa, è possibile installare e usare [un visualizzatore personalizzato](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) per gli alberi delle espressioni, ad esempio:

- [Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licenza MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponibile in [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)) esegue il rendering dell'albero delle espressioni come codice C#:

  ![Visualizzatore Readable Expressions](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

- [Visualizzatore albero delle espressioni](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([Licenza mit](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), fornisce una visualizzazione grafica dell'albero delle espressioni, delle relative proprietà e degli oggetti correlati. e possono eseguire il rendering dell'albero delle espressioni usando Visual Basic codice:

  ![Visualizzatore ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Per aprire un visualizzatore per un albero delle espressioni  
  
1. Fare clic sull'icona della lente di ingrandimento visualizzata accanto all'albero delle espressioni in **Suggerimenti dati**, in una finestra **Espressione di controllo**, nella finestra **Automatico** o nella finestra **Variabili locali**.  
  
     Viene visualizzato un elenco dei visualizzatori disponibili: 

      ![Apertura di visualizzatori da Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. Fare clic sul visualizzatore da usare.  

## <a name="see-also"></a>Vedere anche

- [Alberi delle espressioni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [Debug in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Creazione di visualizzatori personalizzati](/visualstudio/debugger/create-custom-visualizers-of-data)
- Sintassi di [`DebugView`](debugview-syntax.md)
