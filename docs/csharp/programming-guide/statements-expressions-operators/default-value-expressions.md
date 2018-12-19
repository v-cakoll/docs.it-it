---
title: Espressioni con valore predefinito - Guida per programmatori C#
ms.custom: seodec18
description: Le espressioni con valore predefinito producono il valore predefinito per qualsiasi tipo riferimento o tipo valore
ms.date: 04/25/2018
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.openlocfilehash: 4b14714a55f77763425299ffc13ba579ead57810
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237285"
---
# <a name="default-value-expressions-c-programming-guide"></a><span data-ttu-id="00877-103">espressioni con valore predefinito (guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="00877-103">default value expressions (C# programming guide)</span></span>

<span data-ttu-id="00877-104">Un'espressione con valore predefinito `default(T)` produce il valore predefinito per un tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="00877-104">A default value expression `default(T)` produces the default value of a type `T`.</span></span> <span data-ttu-id="00877-105">La tabella seguente mostra i valori generati per vari tipi:</span><span class="sxs-lookup"><span data-stu-id="00877-105">The following table shows which values are produced for various types:</span></span>

|<span data-ttu-id="00877-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="00877-106">Type</span></span>|<span data-ttu-id="00877-107">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="00877-107">Default value</span></span>|
|---------|---------|
|<span data-ttu-id="00877-108">Qualsiasi tipo riferimento</span><span class="sxs-lookup"><span data-stu-id="00877-108">Any reference type</span></span>|`null`|
|<span data-ttu-id="00877-109">Tipo di valore numerico</span><span class="sxs-lookup"><span data-stu-id="00877-109">Numeric value type</span></span>|<span data-ttu-id="00877-110">Zero</span><span class="sxs-lookup"><span data-stu-id="00877-110">Zero</span></span>|
|[<span data-ttu-id="00877-111">bool</span><span class="sxs-lookup"><span data-stu-id="00877-111">bool</span></span>](../../language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="00877-112">char</span><span class="sxs-lookup"><span data-stu-id="00877-112">char</span></span>](../../language-reference/keywords/char.md)|`'\0'`|
|[<span data-ttu-id="00877-113">enum</span><span class="sxs-lookup"><span data-stu-id="00877-113">enum</span></span>](../../language-reference/keywords/enum.md)|<span data-ttu-id="00877-114">Valore prodotto dall'espressione `(E)0`, dove `E` è l'identificatore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="00877-114">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="00877-115">struct</span><span class="sxs-lookup"><span data-stu-id="00877-115">struct</span></span>](../../language-reference/keywords/struct.md)|<span data-ttu-id="00877-116">Valore generato impostando tutti i campi dei tipi valore sui rispettivi valori predefiniti e tutti i campi dei tipi riferimento su `null`.</span><span class="sxs-lookup"><span data-stu-id="00877-116">The value produced by setting all value type fields to their default value and all reference type fields to `null`.</span></span>|
|<span data-ttu-id="00877-117">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="00877-117">Nullable type</span></span>|<span data-ttu-id="00877-118">Un'istanza per la quale la proprietà <xref:System.Nullable%601.HasValue%2A> è `false` e la proprietà <xref:System.Nullable%601.Value%2A> non è definita.</span><span class="sxs-lookup"><span data-stu-id="00877-118">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>|

<span data-ttu-id="00877-119">Le espressioni con valore predefinito risultano particolarmente utili nelle classi e nei metodi generici.</span><span class="sxs-lookup"><span data-stu-id="00877-119">Default value expressions are particularly useful in generic classes and methods.</span></span> <span data-ttu-id="00877-120">Un problema relativo all'uso dei metodi generici riguarda l'assegnazione di un valore predefinito a un tipo con parametri `T` quando non è noto quanto segue:</span><span class="sxs-lookup"><span data-stu-id="00877-120">One issue that arises using generics is how to assign a default value of a parameterized type `T` when you don't know the following in advance:</span></span>

- <span data-ttu-id="00877-121">Se `T` è un tipo riferimento o un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="00877-121">Whether `T` is a reference type or a value type.</span></span>
- <span data-ttu-id="00877-122">Se `T` è un tipo valore, se sarà un valore numerico o struct.</span><span class="sxs-lookup"><span data-stu-id="00877-122">If `T` is a value type, whether it's a numeric value or a struct.</span></span>

 <span data-ttu-id="00877-123">Data una variabile `t` di un tipo con parametri `T`, l'istruzione `t = null` è valida solo se `T` è un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="00877-123">Given a variable `t` of a parameterized type `T`, the statement `t = null` is only valid if `T` is a reference type.</span></span> <span data-ttu-id="00877-124">L'assegnazione `t = 0` funziona solo per i tipi di valore numerico ma non per gli struct.</span><span class="sxs-lookup"><span data-stu-id="00877-124">The assignment `t = 0` only works for numeric value types but not for structs.</span></span> <span data-ttu-id="00877-125">Per risolvere questo problema, usare un valore predefinito:</span><span class="sxs-lookup"><span data-stu-id="00877-125">To solve that, use a default value expression:</span></span>

```csharp
T t = default(T);
```

<span data-ttu-id="00877-126">L'espressione `default(T)` non è limitata a classi e metodi generici.</span><span class="sxs-lookup"><span data-stu-id="00877-126">The `default(T)` expression is not limited to generic classes and methods.</span></span> <span data-ttu-id="00877-127">Le espressioni con valore predefinito possono essere usate con qualsiasi tipo gestito.</span><span class="sxs-lookup"><span data-stu-id="00877-127">Default value expressions can be used with any managed type.</span></span> <span data-ttu-id="00877-128">Tutte le espressioni seguenti sono valide:</span><span class="sxs-lookup"><span data-stu-id="00877-128">Any of these expressions are valid:</span></span>

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 <span data-ttu-id="00877-129">L'esempio seguente dalla classe `GenericList<T>` mostra come usare l'operatore `default(T)` in una classe generica.</span><span class="sxs-lookup"><span data-stu-id="00877-129">The following example from the `GenericList<T>` class shows how to use the `default(T)` operator in a generic class.</span></span> <span data-ttu-id="00877-130">Per altre informazioni, vedere [Introduzione ai generics](../generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="00877-130">For more information, see [Introduction to Generics](../generics/introduction-to-generics.md).</span></span>

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a><span data-ttu-id="00877-131">Valore letterale e inferenza del tipo</span><span class="sxs-lookup"><span data-stu-id="00877-131">default literal and type inference</span></span>

<span data-ttu-id="00877-132">A partire dalla versione C# 7.1, il valore letterale `default` può essere usato per le espressioni con valore predefinito quando il compilatore è in grado di eseguire l'inferenza del tipo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="00877-132">Beginning with C# 7.1, the `default` literal can be used for default value expressions when the compiler can infer the type of the expression.</span></span> <span data-ttu-id="00877-133">Il valore letterale `default` produce lo stesso valore dell'equivalente `default(T)` dove `T` è il tipo dedotto.</span><span class="sxs-lookup"><span data-stu-id="00877-133">The `default` literal produces the same value as the equivalent `default(T)` where `T` is the inferred type.</span></span> <span data-ttu-id="00877-134">Questo approccio può consentire di rendere più conciso il codice, riducendo la ridondanza dovuta alla dichiarazione ripetuta di un tipo.</span><span class="sxs-lookup"><span data-stu-id="00877-134">This can make code more concise by reducing the redundancy of declaring a type more than once.</span></span> <span data-ttu-id="00877-135">Il valore letterale `default` può essere usato in una qualsiasi delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="00877-135">The `default` literal can be used in any of the following locations:</span></span>

- <span data-ttu-id="00877-136">Inizializzatore di variabile</span><span class="sxs-lookup"><span data-stu-id="00877-136">variable initializer</span></span>
- <span data-ttu-id="00877-137">assegnazione di variabili</span><span class="sxs-lookup"><span data-stu-id="00877-137">variable assignment</span></span>
- <span data-ttu-id="00877-138">Dichiarazione del valore predefinito per un parametro facoltativo</span><span class="sxs-lookup"><span data-stu-id="00877-138">declaring the default value for an optional parameter</span></span>
- <span data-ttu-id="00877-139">Specifica del valore per l'argomento della chiamata di un metodo</span><span class="sxs-lookup"><span data-stu-id="00877-139">providing the value for a method call argument</span></span>
- <span data-ttu-id="00877-140">Istruzione return (o espressione in un membro con corpo di espressione)</span><span class="sxs-lookup"><span data-stu-id="00877-140">return statement (or expression in an expression bodied member)</span></span>

<span data-ttu-id="00877-141">L'esempio seguente mostra molti utilizzi del valore letterale `default` in un'espressione con valore predefinito:</span><span class="sxs-lookup"><span data-stu-id="00877-141">The following example shows many usages of the `default` literal in a default value expression:</span></span>

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a><span data-ttu-id="00877-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00877-142">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="00877-143">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="00877-143">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="00877-144">Generics (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="00877-144">Generics (C# Programming Guide)</span></span>](../generics/index.md)  
- [<span data-ttu-id="00877-145">Metodi generici</span><span class="sxs-lookup"><span data-stu-id="00877-145">Generic Methods</span></span>](../generics/generic-methods.md)  
- [<span data-ttu-id="00877-146">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="00877-146">Generics in .NET</span></span>](~/docs/standard/generics/index.md)  
- [<span data-ttu-id="00877-147">Tabella dei valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="00877-147">Default values table</span></span>](../../language-reference/keywords/default-values-table.md)
