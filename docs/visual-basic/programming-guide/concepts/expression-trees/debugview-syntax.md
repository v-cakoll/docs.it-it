---
title: Sintassi utilizzata dalla proprietà DebugView (Visual Basic)
description: Viene descritta la sintassi speciale utilizzata dalla proprietà DebugView per produrre una rappresentazione di stringa degli alberi delle espressioni
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 1b2a1164f02208cc7578820d8f8ed3bc145fb5b8
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196531"
---
# <a name="debugview-syntax"></a>Sintassi `DebugView` 

Il `DebugView` proprietà (disponibile solo durante il debug) fornisce un rendering di stringa degli alberi delle espressioni. La maggior parte della sintassi è piuttosto semplice da comprendere; Nelle sezioni seguenti vengono descritti i casi speciali.

Ogni esempio è seguito da un blocco di commento contenente il `DebugView`. 

## <a name="parameterexpression"></a>ParameterExpression

I nomi delle variabili <xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> vengono visualizzati con un simbolo "$" all'inizio.

Se un parametro non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `$var1` o `$var2`.

### <a name="examples"></a>Esempi

```vb
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")
'
'    $num
'

Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer))
'
'    $var1
'
```

## <a name="constantexpressions"></a>ConstantExpressions

Per gli oggetti <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> che rappresentano valori interi, stringhe e `null`, viene visualizzato il valore della costante.

Per alcuni tipi numerici, un suffisso viene aggiunto al valore:

| Tipo | Parola chiave | Suffisso |  
|--|--|--|
| <xref:System.UInt32> | [UInteger](../../../language-reference/data-types/uinteger-data-type.md) | G |
| <xref:System.Int64> | [Long](../../../language-reference/data-types/long-data-type.md) | L |
| <xref:System.UInt64> | [ULong](../../../language-reference/data-types/ulong-data-type.md) | UL |
| <xref:System.Double> | [Double](../../../language-reference/data-types/double-data-type.md) | D |
| <xref:System.Single> | [Single](../../../language-reference/data-types/single-data-type.md) | F | 
| <xref:System.Decimal> | [Decimal](../../../language-reference/data-types/decimal-data-type.md) | M |

### <a name="examples"></a>Esempi

```vb
Dim num as Integer = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10
'

Dim num As Double = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10D
'
```

## <a name="blockexpression"></a>BlockExpression

Se il tipo di un <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> oggetto differisce dal tipo dell'ultima espressione nel blocco, il tipo viene visualizzato tra parentesi angolari (`<` e `>`). In caso contrario, il tipo dell'oggetto <xref:System.Linq.Expressions.BlockExpression> non viene visualizzato.

### <a name="examples"></a>Esempi

```vb
Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
'
'    .Block() {
'        "test"
'    }
'

Dim block As BlockExpression = Expression.Block(
    GetType(Object), 
    Expression.Constant("test")
)
'
'    .Block<System.Object>() {
'        "test"
'    }
'
```

## <a name="lambdaexpression"></a>LambdaExpression

Gli oggetti <xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> vengono visualizzati insieme ai rispettivi tipi delegato.

Se un'espressione lamda non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `#Lambda1` o `#Lambda2`.

### <a name="examples"></a>Esempi

```vb
Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1)
)
'
'    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
'        1
'    }
'

Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1),
    "SampleLambda",
    Nothing
)
'
'    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
'        1
'    }
'
```

## <a name="labelexpression"></a>LabelExpression

Se si specifica un valore predefinito per l'oggetto <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType>, questo valore viene visualizzato prima dell'oggetto <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType>.

Il token `.Label` indica l'inizio dell'etichetta. Il token `.LabelTarget` indica la destinazione alla quale passare.

Se un'etichetta non presenta un nome, ne viene assegnato uno generato automaticamente, ad esempio `#Label1` o `#Label2`.

### <a name="examples"></a>Esempi

```vb
Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
)
'
'    .Block() {
'        .Goto SampleLabel { 0 };
'        .Label
'            -1
'        .LabelTarget SampleLabel:
'    }
'

Dim target As LabelTarget = Expression.Label()
Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), 
    Expression.Label(target)
)
'
'    .Block() {
'        .Goto #Label1 { };
'        .Label
'        .LabelTarget #Label1:
'    }
'
```

## <a name="checked-operators"></a>Operatori checked

Gli operatori vengono visualizzati con il `#` simbolo davanti l'operatore. Ad esempio, l'operatore di addizione checked viene visualizzato come `#+`.

### <a name="examples"></a>Esempi

```vb
Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1),
    Expression.Constant(2)
)
'
'     1 #+ 2
'

Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0),
    GetType(Integer)
)
'
'    #(System.Int32)10D
'
```