---
title: Sintassi utilizzata dalla proprietà DebugView
description: Descrive la sintassi speciale usata dalla proprietà DebugView per produrre una rappresentazione di stringa degli alberi delle espressioni
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 98ceba37aa226fab68ae1c1028e2a1139b3b8e7e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346874"
---
# <a name="debugview-syntax"></a><span data-ttu-id="e4b35-103">Sintassi `DebugView`</span><span class="sxs-lookup"><span data-stu-id="e4b35-103">`DebugView` syntax</span></span>

<span data-ttu-id="e4b35-104">La proprietà `DebugView` (disponibile solo durante il debug) fornisce un rendering in forma di stringa degli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="e4b35-104">The `DebugView` property (available only when debugging) provides a string rendering of expression trees.</span></span> <span data-ttu-id="e4b35-105">La maggior parte della sintassi è piuttosto semplice da comprendere e i casi speciali vengono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e4b35-105">Most of the syntax is fairly straightforward to understand; the special cases are described in the following sections.</span></span>

<span data-ttu-id="e4b35-106">Ogni esempio è seguito da un blocco di commento che contiene il `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="e4b35-106">Each example is followed by a comment block containing the `DebugView`.</span></span>

## <a name="parameterexpression"></a><span data-ttu-id="e4b35-107">ParameterExpression</span><span class="sxs-lookup"><span data-stu-id="e4b35-107">ParameterExpression</span></span>

<span data-ttu-id="e4b35-108">I nomi delle variabili <xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> vengono visualizzati con un simbolo "$" all'inizio.</span><span class="sxs-lookup"><span data-stu-id="e4b35-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="e4b35-109">Se un parametro non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="e4b35-109">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="e4b35-110">Esempi</span><span class="sxs-lookup"><span data-stu-id="e4b35-110">Examples</span></span>

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

## <a name="constantexpressions"></a><span data-ttu-id="e4b35-111">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="e4b35-111">ConstantExpressions</span></span>

<span data-ttu-id="e4b35-112">Per gli oggetti <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> che rappresentano valori interi, stringhe e `null`, viene visualizzato il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="e4b35-112">For <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

<span data-ttu-id="e4b35-113">Per alcuni tipi numerici, viene aggiunto un suffisso al valore:</span><span class="sxs-lookup"><span data-stu-id="e4b35-113">For some numeric types, a suffix is added to the value:</span></span>

| <span data-ttu-id="e4b35-114">Type</span><span class="sxs-lookup"><span data-stu-id="e4b35-114">Type</span></span> | <span data-ttu-id="e4b35-115">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="e4b35-115">Keyword</span></span> | <span data-ttu-id="e4b35-116">Suffisso</span><span class="sxs-lookup"><span data-stu-id="e4b35-116">Suffix</span></span> |
|--|--|--|
| <xref:System.UInt32> | [<span data-ttu-id="e4b35-117">UInteger</span><span class="sxs-lookup"><span data-stu-id="e4b35-117">UInteger</span></span>](../../../language-reference/data-types/uinteger-data-type.md) | <span data-ttu-id="e4b35-118">U</span><span class="sxs-lookup"><span data-stu-id="e4b35-118">U</span></span> |
| <xref:System.Int64> | [<span data-ttu-id="e4b35-119">Long</span><span class="sxs-lookup"><span data-stu-id="e4b35-119">Long</span></span>](../../../language-reference/data-types/long-data-type.md) | <span data-ttu-id="e4b35-120">L</span><span class="sxs-lookup"><span data-stu-id="e4b35-120">L</span></span> |
| <xref:System.UInt64> | [<span data-ttu-id="e4b35-121">ULong</span><span class="sxs-lookup"><span data-stu-id="e4b35-121">ULong</span></span>](../../../language-reference/data-types/ulong-data-type.md) | <span data-ttu-id="e4b35-122">UL</span><span class="sxs-lookup"><span data-stu-id="e4b35-122">UL</span></span> |
| <xref:System.Double> | [<span data-ttu-id="e4b35-123">Double</span><span class="sxs-lookup"><span data-stu-id="e4b35-123">Double</span></span>](../../../language-reference/data-types/double-data-type.md) | <span data-ttu-id="e4b35-124">D</span><span class="sxs-lookup"><span data-stu-id="e4b35-124">D</span></span> |
| <xref:System.Single> | [<span data-ttu-id="e4b35-125">Single</span><span class="sxs-lookup"><span data-stu-id="e4b35-125">Single</span></span>](../../../language-reference/data-types/single-data-type.md) | <span data-ttu-id="e4b35-126">F</span><span class="sxs-lookup"><span data-stu-id="e4b35-126">F</span></span> |
| <xref:System.Decimal> | [<span data-ttu-id="e4b35-127">Decimal</span><span class="sxs-lookup"><span data-stu-id="e4b35-127">Decimal</span></span>](../../../language-reference/data-types/decimal-data-type.md) | <span data-ttu-id="e4b35-128">M</span><span class="sxs-lookup"><span data-stu-id="e4b35-128">M</span></span> |

### <a name="examples"></a><span data-ttu-id="e4b35-129">Esempi</span><span class="sxs-lookup"><span data-stu-id="e4b35-129">Examples</span></span>

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

## <a name="blockexpression"></a><span data-ttu-id="e4b35-130">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="e4b35-130">BlockExpression</span></span>

<span data-ttu-id="e4b35-131">Se il tipo di un oggetto <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> differisce dal tipo dell'ultima espressione nel blocco, il tipo viene visualizzato all'interno di parentesi angolari (`<` e `>`).</span><span class="sxs-lookup"><span data-stu-id="e4b35-131">If the type of a <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> object differs from the type of the last expression in the block, the type is displayed within angle brackets (`<` and `>`).</span></span> <span data-ttu-id="e4b35-132">In caso contrario, il tipo dell'oggetto <xref:System.Linq.Expressions.BlockExpression> non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="e4b35-132">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="e4b35-133">Esempi</span><span class="sxs-lookup"><span data-stu-id="e4b35-133">Examples</span></span>

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

## <a name="lambdaexpression"></a><span data-ttu-id="e4b35-134">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="e4b35-134">LambdaExpression</span></span>

<span data-ttu-id="e4b35-135">Gli oggetti <xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> vengono visualizzati insieme ai rispettivi tipi delegato.</span><span class="sxs-lookup"><span data-stu-id="e4b35-135"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="e4b35-136">Se un'espressione lamda non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="e4b35-136">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="e4b35-137">Esempi</span><span class="sxs-lookup"><span data-stu-id="e4b35-137">Examples</span></span>

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

## <a name="labelexpression"></a><span data-ttu-id="e4b35-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="e4b35-138">LabelExpression</span></span>

<span data-ttu-id="e4b35-139">Se si specifica un valore predefinito per l'oggetto <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType>, questo valore viene visualizzato prima dell'oggetto <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e4b35-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="e4b35-140">Il token `.Label` indica l'inizio dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="e4b35-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="e4b35-141">Il token `.LabelTarget` indica la destinazione alla quale passare.</span><span class="sxs-lookup"><span data-stu-id="e4b35-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="e4b35-142">Se un'etichetta non presenta un nome, ne viene assegnato uno generato automaticamente, ad esempio `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="e4b35-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="e4b35-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="e4b35-143">Examples</span></span>

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

## <a name="checked-operators"></a><span data-ttu-id="e4b35-144">Operatori checked</span><span class="sxs-lookup"><span data-stu-id="e4b35-144">Checked Operators</span></span>

<span data-ttu-id="e4b35-145">Gli operatori checked vengono visualizzati con il simbolo `#` davanti all'operatore.</span><span class="sxs-lookup"><span data-stu-id="e4b35-145">Checked operators are displayed with the `#` symbol in front of the operator.</span></span> <span data-ttu-id="e4b35-146">Ad esempio, l'operatore di addizione checked viene visualizzato come `#+`.</span><span class="sxs-lookup"><span data-stu-id="e4b35-146">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="e4b35-147">Esempi</span><span class="sxs-lookup"><span data-stu-id="e4b35-147">Examples</span></span>

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
