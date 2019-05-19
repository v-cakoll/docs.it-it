---
title: Debug degli alberi delle espressioni in Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 7fc97d898c5956b5a569036e6e0fe1174714576d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65879876"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Debug degli alberi delle espressioni in Visual Studio (Visual Basic)
È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni. Per ottenere una rapida panoramica della struttura ad albero dell'espressione, è possibile usare la `DebugView` proprietà, che rappresenta gli alberi delle espressioni usando una sintassi speciale descritta [seguito](#debugview-syntax). (Si noti che `DebugView` è disponibile solo in modalità di debug.)  

![DebugView di albero delle espressioni all'interno del debugger di Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

Poiché `DebugView` è una stringa, è possibile usare il [Visualizzatore testo incorporato](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) per visualizzarlo su più righe, selezionando **Visualizzatore di testo** dall'icona della lente di ingrandimento accanto al `DebugView` etichetta.

 ![Visualizzatore testo applicato ai risultati di 'DebugView'](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

In alternativa, è possibile installare e usare [un visualizzatore personalizzato](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) degli alberi delle espressioni:

* [Le espressioni leggibile](https://github.com/agileobjects/ReadableExpressions) ([licenza MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponibile all'indirizzo il [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), viene eseguito il rendering dell'albero delle espressioni come C# codice:

  ![Visualizzatore espressioni leggibile](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* [Visualizzatore di struttura ad albero delle espressioni](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([licenza MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), offre una visualizzazione grafica di albero delle espressioni, relative proprietà e oggetti correlati e può eseguire il rendering dell'albero delle espressioni tramite codice Visual Basic:

  ![Visualizzatore ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Per aprire un visualizzatore per un albero delle espressioni  
  
1. Fai clic sull'icona della lente di ingrandimento visualizzata accanto l'albero delle espressioni in **suggerimenti dati**, un **Watch** finestra, il **Auto** finestra o il **variabililocali** finestra.  
  
     Viene visualizzato un elenco di visualizzatori disponibili.: 

      ![Visualizzatori di apertura da Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. Fare clic sul visualizzatore da usare.  

## <a name="debugview-syntax"></a>`DebugView` Sintassi 

Ogni tipo di espressione viene visualizzato nel visualizzatore come descritto nelle sezioni seguenti.

## <a name="parameterexpressions"></a>ParameterExpressions

I nomi delle variabili <xref:System.Linq.Expressions.ParameterExpression> vengono visualizzati con un simbolo "$" all'inizio.

Se un parametro non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `$var1` o `$var2`.

### <a name="examples"></a>Esempi

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    Proprietà`DebugView` 

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    Proprietà`DebugView` 

    `$var1`

## <a name="constantexpressions"></a>ConstantExpressions
 Per gli oggetti <xref:System.Linq.Expressions.ConstantExpression> che rappresentano valori interi, stringhe e `null`, viene visualizzato il valore della costante.

### <a name="examples"></a>Esempi

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    Proprietà`DebugView` 

    10

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    Proprietà`DebugView` 

    10D

## <a name="blockexpression"></a>BlockExpression

Se il tipo di un oggetto <xref:System.Linq.Expressions.BlockExpression> differisce dal tipo dell'ultima espressione nel blocco, il tipo viene visualizzato nella proprietà `DebugInfo` tra parentesi angolari (\< e >). In caso contrario, il tipo dell'oggetto <xref:System.Linq.Expressions.BlockExpression> non viene visualizzato.

### <a name="examples"></a>Esempi

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    Proprietà`DebugView` 

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    Proprietà`DebugView` 

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a>LambdaExpression

Gli oggetti <xref:System.Linq.Expressions.LambdaExpression> vengono visualizzati insieme ai rispettivi tipi delegato.

Se un'espressione lamda non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `#Lambda1` o `#Lambda2`.

### <a name="examples"></a>Esempi

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    Proprietà`DebugView` 

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    Proprietà`DebugView` 

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a>LabelExpression

Se si specifica un valore predefinito per l'oggetto <xref:System.Linq.Expressions.LabelExpression>, questo valore viene visualizzato prima dell'oggetto <xref:System.Linq.Expressions.LabelTarget>.

Il token `.Label` indica l'inizio dell'etichetta. Il token `.LabelTarget` indica la destinazione alla quale passare.

Se un'etichetta non presenta un nome, ne viene assegnato uno generato automaticamente, ad esempio `#Label1` o `#Label2`.

### <a name="examples"></a>Esempi

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    Proprietà`DebugView` 

    `.Block() {`

    `.Goto SampleLabel { 0 };`

    `.Label`

    `-1`

    `.LabelTarget SampleLabel:`

    `}`

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label()
    Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), Expression.Label(target))
    ```

    Proprietà`DebugView` 

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a>Operatori checked

Gli operatori di questo tipo vengono visualizzati con il simbolo "#" davanti l'operatore. Ad esempio, l'operatore di addizione checked viene visualizzato come `#+`.

### <a name="examples"></a>Esempi

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    Proprietà`DebugView` 

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    Proprietà`DebugView` 

    `#(System.Int32)10D`

## <a name="see-also"></a>Vedere anche

- [Alberi delle espressioni (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [Debug in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Creazione di visualizzatori personalizzati](/visualstudio/debugger/create-custom-visualizers-of-data)
