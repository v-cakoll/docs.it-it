---
title: Tabella delle conversioni numeriche esplicite (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0315810522be319a6bb565c99e1c8f7d1ba4701b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="64eaa-102">Tabella delle conversioni numeriche esplicite (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="64eaa-102">Explicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="64eaa-103">La conversione numerica esplicita viene usata per convertire qualsiasi tipo numerico in qualsiasi altro tipo numerico, per il quale non c'è alcuna conversione implicita, usando un'espressione cast.</span><span class="sxs-lookup"><span data-stu-id="64eaa-103">Explicit numeric conversion is used to convert any numeric type to any other numeric type, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="64eaa-104">La tabella seguente illustra queste conversioni.</span><span class="sxs-lookup"><span data-stu-id="64eaa-104">The following table shows these conversions.</span></span>  
  
 <span data-ttu-id="64eaa-105">Per altre informazioni sulle conversioni, vedere [Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="64eaa-105">For more information about conversions, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
|<span data-ttu-id="64eaa-106">Da</span><span class="sxs-lookup"><span data-stu-id="64eaa-106">From</span></span>|<span data-ttu-id="64eaa-107">A</span><span class="sxs-lookup"><span data-stu-id="64eaa-107">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="64eaa-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="64eaa-108">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="64eaa-109">`byte`, `ushort`, `uint`, `ulong` o `char`</span><span class="sxs-lookup"><span data-stu-id="64eaa-109">`byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="64eaa-110">byte</span><span class="sxs-lookup"><span data-stu-id="64eaa-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="64eaa-111">`Sbyte` o `char`</span><span class="sxs-lookup"><span data-stu-id="64eaa-111">`Sbyte` or `char`</span></span>|  
|[<span data-ttu-id="64eaa-112">short</span><span class="sxs-lookup"><span data-stu-id="64eaa-112">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="64eaa-113">`sbyte`, `byte`, `ushort`, `uint`, `ulong` o `char`</span><span class="sxs-lookup"><span data-stu-id="64eaa-113">`sbyte`, `byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="64eaa-114">ushort</span><span class="sxs-lookup"><span data-stu-id="64eaa-114">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="64eaa-115">`sbyte`, `byte`, `short` o `char`</span><span class="sxs-lookup"><span data-stu-id="64eaa-115">`sbyte`, `byte`, `short`, or `char`</span></span>|  
|[<span data-ttu-id="64eaa-116">int</span><span class="sxs-lookup"><span data-stu-id="64eaa-116">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="64eaa-117">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` o `char`</span><span class="sxs-lookup"><span data-stu-id="64eaa-117">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`,or `char`</span></span>|  
|[<span data-ttu-id="64eaa-118">uint</span><span class="sxs-lookup"><span data-stu-id="64eaa-118">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="64eaa-119">`sbyte`, `byte`, `short`, `ushort`, `int` o `char`</span><span class="sxs-lookup"><span data-stu-id="64eaa-119">`sbyte`, `byte`, `short`, `ushort`, `int`, or `char`</span></span>|  
|[<span data-ttu-id="64eaa-120">long</span><span class="sxs-lookup"><span data-stu-id="64eaa-120">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="64eaa-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` o `char`</span><span class="sxs-lookup"><span data-stu-id="64eaa-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="64eaa-122">ulong</span><span class="sxs-lookup"><span data-stu-id="64eaa-122">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="64eaa-123">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` o `char`</span><span class="sxs-lookup"><span data-stu-id="64eaa-123">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, or `char`</span></span>|  
|[<span data-ttu-id="64eaa-124">char</span><span class="sxs-lookup"><span data-stu-id="64eaa-124">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="64eaa-125">`sbyte`, `byte`o `short`</span><span class="sxs-lookup"><span data-stu-id="64eaa-125">`sbyte`, `byte`, or `short`</span></span>|  
|[<span data-ttu-id="64eaa-126">float</span><span class="sxs-lookup"><span data-stu-id="64eaa-126">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="64eaa-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="64eaa-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`,or `decimal`</span></span>|  
|[<span data-ttu-id="64eaa-128">double</span><span class="sxs-lookup"><span data-stu-id="64eaa-128">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="64eaa-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="64eaa-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`,or `decimal`</span></span>|  
|[<span data-ttu-id="64eaa-130">decimal</span><span class="sxs-lookup"><span data-stu-id="64eaa-130">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="64eaa-131">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `double`</span><span class="sxs-lookup"><span data-stu-id="64eaa-131">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, or `double`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64eaa-132">Note</span><span class="sxs-lookup"><span data-stu-id="64eaa-132">Remarks</span></span>  
  
-   <span data-ttu-id="64eaa-133">La conversione numerica esplicita può causare una perdita nella precisione o comportare la generazione di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="64eaa-133">The explicit numeric conversion may cause loss of precision or result in throwing exceptions.</span></span>  
  
-   <span data-ttu-id="64eaa-134">Quando si esegue una conversione da un valore `decimal` a un tipo integrale, il valore viene arrotondato per difetto al valore integrale più vicino.</span><span class="sxs-lookup"><span data-stu-id="64eaa-134">When you convert a `decimal` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="64eaa-135">Se il valore integrale risultante non rientra nell'intervallo del tipo di destinazione, viene generata un'eccezione <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="64eaa-135">If the resulting integral value is outside the range of the destination type, an <xref:System.OverflowException> is thrown.</span></span>  
  
-   <span data-ttu-id="64eaa-136">Quando si esegue una conversione da un valore `double` o `float` a un tipo integrale, il valore viene troncato.</span><span class="sxs-lookup"><span data-stu-id="64eaa-136">When you convert from a `double` or `float` value to an integral type, the value is truncated.</span></span> <span data-ttu-id="64eaa-137">Se il valore integrale risultante non rientra nell'intervallo del valore di destinazione, il risultato dipende dal contesto di controllo dell'overflow.</span><span class="sxs-lookup"><span data-stu-id="64eaa-137">If the resulting integral value is outside the range of the destination value, the result depends on the overflow checking context.</span></span> <span data-ttu-id="64eaa-138">In un contesto controllato (checked) viene generata un'eccezione `OverflowException`, mentre in un contesto non controllato (unckecked) il risultato è un valore non specificato del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="64eaa-138">In a checked context, an `OverflowException` is thrown, while in an unchecked context, the result is an unspecified value of the destination type.</span></span>  
  
-   <span data-ttu-id="64eaa-139">Per una conversione da `double` a `float`, il valore `double` viene arrotondato al valore `float` più vicino.</span><span class="sxs-lookup"><span data-stu-id="64eaa-139">When you convert `double` to `float`, the `double` value is rounded to the nearest `float` value.</span></span> <span data-ttu-id="64eaa-140">Se il valore `double` è troppo piccolo o troppo grande per essere contenuto nel tipo di destinazione, il risultato sarà zero o infinito.</span><span class="sxs-lookup"><span data-stu-id="64eaa-140">If the `double` value is too small or too large to fit into the destination type, the result will be zero or infinity.</span></span>  
  
-   <span data-ttu-id="64eaa-141">Quando si esegue una conversione da `float` o `double` a `decimal`, il valore di origine viene convertito nella rappresentazione `decimal` e arrotondato al numero più vicino successivo alla ventottesima posizione decimale, se necessario.</span><span class="sxs-lookup"><span data-stu-id="64eaa-141">When you convert `float` or `double` to `decimal`, the source value is converted to `decimal` representation and rounded to the nearest number after the 28th decimal place if required.</span></span> <span data-ttu-id="64eaa-142">A seconda dell'entità del valore di origine, è possibile che si verifichi uno dei risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="64eaa-142">Depending on the value of the source value, one of the following results may occur:</span></span>  
  
    -   <span data-ttu-id="64eaa-143">Se il valore di origine è troppo piccolo per essere rappresentato come `decimal`, il risultato diventa zero.</span><span class="sxs-lookup"><span data-stu-id="64eaa-143">If the source value is too small to be represented as a `decimal`, the result becomes zero.</span></span>  
  
    -   <span data-ttu-id="64eaa-144">Se il valore di origine è NaN (non un numero), infinito o troppo grande per essere rappresentato come `decimal`, viene generata un'eccezione `OverflowException`.</span><span class="sxs-lookup"><span data-stu-id="64eaa-144">If the source value is NaN (not a number), infinity, or too large to be represented as a `decimal`, an `OverflowException` is thrown.</span></span>  
  
-   <span data-ttu-id="64eaa-145">Quando si esegue una conversione da `decimal` a `float` o `double`, il valore `decimal` viene arrotondato al valore `double` o `float` più vicino.</span><span class="sxs-lookup"><span data-stu-id="64eaa-145">When you convert `decimal` to `float` or `double`, the `decimal` value is rounded to the nearest `double` or `float` value.</span></span>  
  
 <span data-ttu-id="64eaa-146">Per altre informazioni sulla conversione esplicita, vedere Explicit nella specifica del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="64eaa-146">For more information on explicit conversion, see Explicit in the C# Language Specification.</span></span> <span data-ttu-id="64eaa-147">Per altre informazioni su come accedere alla specifica, vedere [Specifica del linguaggio C#](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="64eaa-147">For more information on how to access the spec, see [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64eaa-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64eaa-148">See Also</span></span>  
 <span data-ttu-id="64eaa-149">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="64eaa-149">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="64eaa-150">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="64eaa-150">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="64eaa-151">[Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="64eaa-151">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 <span data-ttu-id="64eaa-152">[Operatore ()](../../../csharp/language-reference/operators/invocation-operator.md) </span><span class="sxs-lookup"><span data-stu-id="64eaa-152">[() Operator](../../../csharp/language-reference/operators/invocation-operator.md) </span></span>  
 <span data-ttu-id="64eaa-153">[Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="64eaa-153">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="64eaa-154">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="64eaa-154">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 [<span data-ttu-id="64eaa-155">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="64eaa-155">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)

