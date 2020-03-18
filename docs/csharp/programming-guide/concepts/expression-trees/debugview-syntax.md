---
title: Sintassi usata dalla proprietà DebugView (C#)
description: Descrive la sintassi speciale usata dalla proprietà DebugView per produrre una rappresentazione di stringa degli alberi delle espressioni
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: ba695fc808108c49a4eee3c70a305b24c91769d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "67661721"
---
# <a name="debugview-syntax"></a>Sintassi `DebugView`

La proprietà `DebugView` (disponibile solo durante il debug) fornisce un rendering in forma di stringa degli alberi delle espressioni. La maggior parte della sintassi è piuttosto semplice da comprendere e i casi speciali vengono descritti nelle sezioni seguenti.

Ogni esempio è seguito da un commento del blocco, che contiene `DebugView`.

## <a name="parameterexpression"></a>ParameterExpression

I nomi delle variabili <xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> vengono visualizzati con un simbolo `$` all'inizio.

Se un parametro non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `$var1` o `$var2`.

### <a name="examples"></a>Esempi

```csharp
ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");
/*
    $num
*/

ParameterExpression numParam =  Expression.Parameter(typeof(int));
/*
    $var1
*/
```

## <a name="constantexpression"></a>ConstantExpression

Per gli oggetti <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> che rappresentano valori interi, stringhe e `null`, viene visualizzato il valore della costante.

Per i tipi numerici che usano suffissi standard come valori letterali in C#, il suffisso viene aggiunto al valore. La tabella seguente mostra i suffissi associati ai vari tipi numerici.

| Type | Parola chiave | Suffisso |
|--|--|--|
| <xref:System.UInt32?displayProperty=nameWithType> | [uint](../../../language-reference/builtin-types/integral-numeric-types.md) | U |
| <xref:System.Int64?displayProperty=nameWithType> | [Lungo](../../../language-reference/builtin-types/integral-numeric-types.md) | L |
| <xref:System.UInt64?displayProperty=nameWithType> | [Ulong](../../../language-reference/builtin-types/integral-numeric-types.md) | UL |
| <xref:System.Double?displayProperty=nameWithType> | [Doppia](../../../language-reference/builtin-types/floating-point-numeric-types.md) | D |
| <xref:System.Single?displayProperty=nameWithType> | [Galleggiante](../../../language-reference/builtin-types/floating-point-numeric-types.md) | F |
| <xref:System.Decimal?displayProperty=nameWithType> | [Decimale](../../../language-reference/builtin-types/floating-point-numeric-types.md) | M |

### <a name="examples"></a>Esempi

```csharp
int num = 10;
ConstantExpression expr = Expression.Constant(num);
/*
    10
*/

double num = 10;
ConstantExpression expr = Expression.Constant(num);
/*
    10D
*/
```

## <a name="blockexpression"></a>BlockExpression

Se il tipo di un oggetto <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> differisce dal tipo dell'ultima espressione nel blocco, il tipo viene visualizzato all'interno di parentesi angolari (`<` e `>`). In caso contrario, il tipo dell'oggetto <xref:System.Linq.Expressions.BlockExpression> non viene visualizzato.

### <a name="examples"></a>Esempi

```csharp
BlockExpression block = Expression.Block(Expression.Constant("test"));
/*
    .Block() {
        "test"
    }
*/

BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));
/*
    .Block<System.Object>() {
        "test"
    }
*/
```

## <a name="lambdaexpression"></a>LambdaExpression

Gli oggetti <xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> vengono visualizzati insieme ai rispettivi tipi delegato.

Se un'espressione lamda non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `#Lambda1` o `#Lambda2`.

### <a name="examples"></a>Esempi

```csharp
LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));
/*
    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
        1
    }
*/

LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);
/*
    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
        1
    }
*/
```

## <a name="labelexpression"></a>LabelExpression

Se si specifica un valore predefinito per l'oggetto <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType>, questo valore viene visualizzato prima dell'oggetto <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType>.

Il token `.Label` indica l'inizio dell'etichetta. Il token `.LabelTarget` indica la destinazione alla quale passare.

Se un'etichetta non presenta un nome, ne viene assegnato uno generato automaticamente, ad esempio `#Label1` o `#Label2`.

### <a name="examples"></a>Esempi

```csharp
LabelTarget target = Expression.Label(typeof(int), "SampleLabel");
BlockExpression block = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
);
/*
    .Block() {
        .Goto SampleLabel { 0 };
        .Label
            -1
        .LabelTarget SampleLabel:
    }
*/

LabelTarget target = Expression.Label();
BlockExpression block = Expression.Block(
    Expression.Goto(target),
    Expression.Label(target)
);
/*
    .Block() {
        .Goto #Label1 { };
        .Label
        .LabelTarget #Label1:
    }
*/
```

## <a name="checked-operators"></a>Operatori checked

Gli operatori checked vengono visualizzati con il simbolo `#` davanti all'operatore. Ad esempio, l'operatore di addizione checked viene visualizzato come `#+`.

### <a name="examples"></a>Esempi

```csharp
Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));
/*
    1 #+ 2
*/

Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));
/*
    #(System.Int32)10D
*/
```
