---
title: Debug degli alberi delle espressioni in Visual Studio
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: c6c44d079ab0854b2325b82d3569280752da32fb
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266833"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Debug di strutture ad albero dell'espressione in Visual Studio (Visual Basic)Debugging Expression Trees in Visual Studio (Visual Basic)
È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni. Per una rapida panoramica della struttura dell'albero delle espressioni, è possibile usare la proprietà `DebugView`, che rappresenta gli alberi delle espressioni [usando una sintassi speciale](debugview-syntax.md). Si noti che `DebugView` è disponibile solo in modalità di debug.  

![Screenshot della visualizzazione Debug della struttura ad albero dell'espressione.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

Dato che `DebugView` è una stringa, è possibile usare il [Visualizzatore testo incorporato](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) per visualizzarla su più righe, selezionando **Visualizzatore testo** dall'icona della lente di ingrandimento accanto all'etichetta `DebugView`.

 ![Screenshot del visualizzatore di testo applicato ai risultati di DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

In alternativa, è possibile installare e usare [un visualizzatore personalizzato](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) per gli alberi delle espressioni, ad esempio:

- [Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licenza MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponibile in [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)) esegue il rendering dell'albero delle espressioni come codice C#:

  ![Screenshot del visualizzatore Espressioni leggibili.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- [Visualizzatore albero delle](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) espressioni ([licenza MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), fornisce una visualizzazione grafica della struttura ad albero delle espressioni, delle relative proprietà e degli oggetti correlati. e può eseguire il rendering della struttura ad albero dell'espressione utilizzando il codice Visual Basic:

  ![Screenshot del visualizzatore ExpressionToString.](media/debugging-expression-trees-in-visual-studio/expression-to-string-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Per aprire un visualizzatore per un albero delle espressioni  
  
1. Fare clic sull'icona della lente di ingrandimento visualizzata accanto all'albero delle espressioni in **Suggerimenti dati**, in una finestra **Espressione di controllo**, nella finestra **Automatico** o nella finestra **Variabili locali**.  
  
    Viene visualizzato un elenco dei visualizzatori disponibili:

    ![Screenshot dell'utente che apre i visualizzatori da Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. Fare clic sul visualizzatore da usare.  

## <a name="see-also"></a>Vedere anche

- [Alberi delle espressioni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [Debug in Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Creare visualizzatori personalizzati](/visualstudio/debugger/create-custom-visualizers-of-data)
- [`DebugView`Sintassi](debugview-syntax.md)
