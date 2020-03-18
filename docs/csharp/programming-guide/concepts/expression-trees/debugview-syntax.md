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
# <a name="debugview-syntax"></a><span data-ttu-id="41a35-103">Sintassi `DebugView`</span><span class="sxs-lookup"><span data-stu-id="41a35-103">`DebugView` syntax</span></span>

<span data-ttu-id="41a35-104">La proprietà `DebugView` (disponibile solo durante il debug) fornisce un rendering in forma di stringa degli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="41a35-104">The `DebugView` property (available only when debugging) provides a string rendering of expression trees.</span></span> <span data-ttu-id="41a35-105">La maggior parte della sintassi è piuttosto semplice da comprendere e i casi speciali vengono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="41a35-105">Most of the syntax is fairly straightforward to understand; the special cases are described in the following sections.</span></span>

<span data-ttu-id="41a35-106">Ogni esempio è seguito da un commento del blocco, che contiene `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="41a35-106">Each example is followed by a block comment, containing the `DebugView`.</span></span>

## <a name="parameterexpression"></a><span data-ttu-id="41a35-107">ParameterExpression</span><span class="sxs-lookup"><span data-stu-id="41a35-107">ParameterExpression</span></span>

<span data-ttu-id="41a35-108">I nomi delle variabili <xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> vengono visualizzati con un simbolo `$` all'inizio.</span><span class="sxs-lookup"><span data-stu-id="41a35-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> variable names are displayed with a `$` symbol at the beginning.</span></span>

<span data-ttu-id="41a35-109">Se un parametro non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="41a35-109">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="41a35-110">Esempi</span><span class="sxs-lookup"><span data-stu-id="41a35-110">Examples</span></span>

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

## <a name="constantexpression"></a><span data-ttu-id="41a35-111">ConstantExpression</span><span class="sxs-lookup"><span data-stu-id="41a35-111">ConstantExpression</span></span>

<span data-ttu-id="41a35-112">Per gli oggetti <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> che rappresentano valori interi, stringhe e `null`, viene visualizzato il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="41a35-112">For <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

<span data-ttu-id="41a35-113">Per i tipi numerici che usano suffissi standard come valori letterali in C#, il suffisso viene aggiunto al valore.</span><span class="sxs-lookup"><span data-stu-id="41a35-113">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="41a35-114">La tabella seguente mostra i suffissi associati ai vari tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="41a35-114">The following table shows the suffixes associated with various numeric types.</span></span>

| <span data-ttu-id="41a35-115">Type</span><span class="sxs-lookup"><span data-stu-id="41a35-115">Type</span></span> | <span data-ttu-id="41a35-116">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="41a35-116">Keyword</span></span> | <span data-ttu-id="41a35-117">Suffisso</span><span class="sxs-lookup"><span data-stu-id="41a35-117">Suffix</span></span> |
|--|--|--|
| <xref:System.UInt32?displayProperty=nameWithType> | [<span data-ttu-id="41a35-118">uint</span><span class="sxs-lookup"><span data-stu-id="41a35-118">uint</span></span>](../../../language-reference/builtin-types/integral-numeric-types.md) | <span data-ttu-id="41a35-119">U</span><span class="sxs-lookup"><span data-stu-id="41a35-119">U</span></span> |
| <xref:System.Int64?displayProperty=nameWithType> | [<span data-ttu-id="41a35-120">Lungo</span><span class="sxs-lookup"><span data-stu-id="41a35-120">long</span></span>](../../../language-reference/builtin-types/integral-numeric-types.md) | <span data-ttu-id="41a35-121">L</span><span class="sxs-lookup"><span data-stu-id="41a35-121">L</span></span> |
| <xref:System.UInt64?displayProperty=nameWithType> | [<span data-ttu-id="41a35-122">Ulong</span><span class="sxs-lookup"><span data-stu-id="41a35-122">ulong</span></span>](../../../language-reference/builtin-types/integral-numeric-types.md) | <span data-ttu-id="41a35-123">UL</span><span class="sxs-lookup"><span data-stu-id="41a35-123">UL</span></span> |
| <xref:System.Double?displayProperty=nameWithType> | [<span data-ttu-id="41a35-124">Doppia</span><span class="sxs-lookup"><span data-stu-id="41a35-124">double</span></span>](../../../language-reference/builtin-types/floating-point-numeric-types.md) | <span data-ttu-id="41a35-125">D</span><span class="sxs-lookup"><span data-stu-id="41a35-125">D</span></span> |
| <xref:System.Single?displayProperty=nameWithType> | [<span data-ttu-id="41a35-126">Galleggiante</span><span class="sxs-lookup"><span data-stu-id="41a35-126">float</span></span>](../../../language-reference/builtin-types/floating-point-numeric-types.md) | <span data-ttu-id="41a35-127">F</span><span class="sxs-lookup"><span data-stu-id="41a35-127">F</span></span> |
| <xref:System.Decimal?displayProperty=nameWithType> | [<span data-ttu-id="41a35-128">Decimale</span><span class="sxs-lookup"><span data-stu-id="41a35-128">decimal</span></span>](../../../language-reference/builtin-types/floating-point-numeric-types.md) | <span data-ttu-id="41a35-129">M</span><span class="sxs-lookup"><span data-stu-id="41a35-129">M</span></span> |

### <a name="examples"></a><span data-ttu-id="41a35-130">Esempi</span><span class="sxs-lookup"><span data-stu-id="41a35-130">Examples</span></span>

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

## <a name="blockexpression"></a><span data-ttu-id="41a35-131">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="41a35-131">BlockExpression</span></span>

<span data-ttu-id="41a35-132">Se il tipo di un oggetto <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> differisce dal tipo dell'ultima espressione nel blocco, il tipo viene visualizzato all'interno di parentesi angolari (`<` e `>`).</span><span class="sxs-lookup"><span data-stu-id="41a35-132">If the type of a <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> object differs from the type of the last expression in the block, the type is displayed within angle brackets (`<` and `>`).</span></span> <span data-ttu-id="41a35-133">In caso contrario, il tipo dell'oggetto <xref:System.Linq.Expressions.BlockExpression> non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="41a35-133">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="41a35-134">Esempi</span><span class="sxs-lookup"><span data-stu-id="41a35-134">Examples</span></span>

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

## <a name="lambdaexpression"></a><span data-ttu-id="41a35-135">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="41a35-135">LambdaExpression</span></span>

<span data-ttu-id="41a35-136">Gli oggetti <xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> vengono visualizzati insieme ai rispettivi tipi delegato.</span><span class="sxs-lookup"><span data-stu-id="41a35-136"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="41a35-137">Se un'espressione lamda non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="41a35-137">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="41a35-138">Esempi</span><span class="sxs-lookup"><span data-stu-id="41a35-138">Examples</span></span>

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

## <a name="labelexpression"></a><span data-ttu-id="41a35-139">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="41a35-139">LabelExpression</span></span>

<span data-ttu-id="41a35-140">Se si specifica un valore predefinito per l'oggetto <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType>, questo valore viene visualizzato prima dell'oggetto <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="41a35-140">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="41a35-141">Il token `.Label` indica l'inizio dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="41a35-141">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="41a35-142">Il token `.LabelTarget` indica la destinazione alla quale passare.</span><span class="sxs-lookup"><span data-stu-id="41a35-142">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="41a35-143">Se un'etichetta non presenta un nome, ne viene assegnato uno generato automaticamente, ad esempio `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="41a35-143">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="41a35-144">Esempi</span><span class="sxs-lookup"><span data-stu-id="41a35-144">Examples</span></span>

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

## <a name="checked-operators"></a><span data-ttu-id="41a35-145">Operatori checked</span><span class="sxs-lookup"><span data-stu-id="41a35-145">Checked Operators</span></span>

<span data-ttu-id="41a35-146">Gli operatori checked vengono visualizzati con il simbolo `#` davanti all'operatore.</span><span class="sxs-lookup"><span data-stu-id="41a35-146">Checked operators are displayed with the `#` symbol in front of the operator.</span></span> <span data-ttu-id="41a35-147">Ad esempio, l'operatore di addizione checked viene visualizzato come `#+`.</span><span class="sxs-lookup"><span data-stu-id="41a35-147">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="41a35-148">Esempi</span><span class="sxs-lookup"><span data-stu-id="41a35-148">Examples</span></span>

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
