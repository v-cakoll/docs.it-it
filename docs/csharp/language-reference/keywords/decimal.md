---
title: Parola chiave decimal (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
ms.openlocfilehash: 18924abefb85012fc6c61073603c594de906b58d
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2018
ms.locfileid: "37961196"
---
# <a name="decimal-c-reference"></a><span data-ttu-id="a5b92-102">decimal (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a5b92-102">decimal (C# Reference)</span></span>

<span data-ttu-id="a5b92-103">La parola chiave `decimal` indica un tipo di dati a 128 bit.</span><span class="sxs-lookup"><span data-stu-id="a5b92-103">The `decimal` keyword indicates a 128-bit data type.</span></span> <span data-ttu-id="a5b92-104">Rispetto ad altri tipi a virgola mobile, il tipo `decimal` è caratterizzato da una maggiore precisione e da un intervallo minore, che lo rendono appropriato per calcoli finanziari e monetari.</span><span class="sxs-lookup"><span data-stu-id="a5b92-104">Compared to other floating-point types, the `decimal` type has more precision and a smaller range, which makes it appropriate for financial and monetary calculations.</span></span> <span data-ttu-id="a5b92-105">Nella tabella riportata di seguito vengono indicati l'intervallo approssimativo e il grado di precisione del tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="a5b92-105">The approximate range and precision for the `decimal` type are shown in the following table.</span></span>

|<span data-ttu-id="a5b92-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="a5b92-106">Type</span></span>|<span data-ttu-id="a5b92-107">Intervallo approssimativo</span><span class="sxs-lookup"><span data-stu-id="a5b92-107">Approximate Range</span></span>|<span data-ttu-id="a5b92-108">Precisione</span><span class="sxs-lookup"><span data-stu-id="a5b92-108">Precision</span></span>|<span data-ttu-id="a5b92-109">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="a5b92-109">.NET type</span></span>|
|----------|-----------------------|---------------|-------------------------|
|`decimal`|<span data-ttu-id="a5b92-110">(Da -7,9 x 10<sup>28</sup> a 7,9 x 10<sup>28</sup>) / (da 10<sup>0</sup> a 10<sup>28</sup>)</span><span class="sxs-lookup"><span data-stu-id="a5b92-110">(-7.9 x 10<sup>28</sup> to 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> to 10<sup>28</sup>)</span></span>|<span data-ttu-id="a5b92-111">28-29 cifre significative</span><span class="sxs-lookup"><span data-stu-id="a5b92-111">28-29 significant digits</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="a5b92-112">Il valore predefinito di un `decimal` è 0m.</span><span class="sxs-lookup"><span data-stu-id="a5b92-112">The default value of a `decimal` is 0m.</span></span>

## <a name="literals"></a><span data-ttu-id="a5b92-113">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="a5b92-113">Literals</span></span>

<span data-ttu-id="a5b92-114">Se si desidera che un valore letterale numerico reale venga gestito come `decimal`, utilizzare il suffisso m o M, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a5b92-114">If you want a numeric real literal to be treated as `decimal`, use the suffix m or M, for example:</span></span>

```csharp
decimal myMoney = 300.5m;
```

<span data-ttu-id="a5b92-115">Senza il suffisso m, il numero viene gestito come valore [double](../../../csharp/language-reference/keywords/double.md) e genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="a5b92-115">Without the suffix m, the number is treated as a [double](../../../csharp/language-reference/keywords/double.md) and generates a compiler error.</span></span>

## <a name="conversions"></a><span data-ttu-id="a5b92-116">Conversioni</span><span class="sxs-lookup"><span data-stu-id="a5b92-116">Conversions</span></span>

<span data-ttu-id="a5b92-117">I tipi integrali vengono convertiti in modo implicito in `decimal` e il risultato restituisce `decimal`.</span><span class="sxs-lookup"><span data-stu-id="a5b92-117">The integral types are implicitly converted to `decimal` and the result evaluates to `decimal`.</span></span> <span data-ttu-id="a5b92-118">È pertanto possibile inizializzare una variabile decimale mediante un valore letterale Integer, senza il suffisso, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a5b92-118">Therefore you can initialize a decimal variable using an integer literal, without the suffix, as follows:</span></span>

```csharp
decimal myMoney = 300;
```

<span data-ttu-id="a5b92-119">Poiché non esiste alcuna conversione implicita tra altri tipi a virgola mobile e il tipo `decimal`, è necessario usare un cast per eseguire una conversione tra questi due tipi.</span><span class="sxs-lookup"><span data-stu-id="a5b92-119">There is no implicit conversion between other floating-point types and the `decimal` type; therefore, a cast must be used to convert between these two types.</span></span> <span data-ttu-id="a5b92-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a5b92-120">For example:</span></span>

```csharp
decimal myMoney = 99.9m;
double x = (double)myMoney;
myMoney = (decimal)x;
```

<span data-ttu-id="a5b92-121">È inoltre possibile combinare tipi `decimal` e tipi integrali numerici nella stessa espressione.</span><span class="sxs-lookup"><span data-stu-id="a5b92-121">You can also mix `decimal` and numeric integral types in the same expression.</span></span> <span data-ttu-id="a5b92-122">Tuttavia, la combinazione di `decimal` e altri tipi a virgola mobile senza un cast genera un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a5b92-122">However, mixing `decimal` and other floating-point types without a cast causes a compilation error.</span></span>

<span data-ttu-id="a5b92-123">Per altre informazioni sulle conversioni numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="a5b92-123">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="a5b92-124">Per altre informazioni sulle conversioni numeriche esplicite, vedere [Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="a5b92-124">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="formatting-decimal-output"></a><span data-ttu-id="a5b92-125">Formattazione dell'output di tipo decimal</span><span class="sxs-lookup"><span data-stu-id="a5b92-125">Formatting decimal output</span></span>

<span data-ttu-id="a5b92-126">È possibile applicare il formato desiderato ai risultati utilizzando il metodo `String.Format` o mediante il metodo <xref:System.Console.Write%2A?displayProperty=nameWithType> che chiama `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="a5b92-126">You can format the results by using the `String.Format` method, or through the <xref:System.Console.Write%2A?displayProperty=nameWithType> method, which calls `String.Format()`.</span></span> <span data-ttu-id="a5b92-127">Il formato valuta viene specificato tramite la stringa di formato valuta standard "C" o "c", come illustrato nel secondo esempio riportato più avanti.</span><span class="sxs-lookup"><span data-stu-id="a5b92-127">The currency format is specified by using the standard currency format string "C" or "c," as shown in the second example later in this article.</span></span> <span data-ttu-id="a5b92-128">Per ulteriori informazioni sul metodo `String.Format`, vedere <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a5b92-128">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="a5b92-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5b92-129">Example</span></span>

<span data-ttu-id="a5b92-130">L'esempio seguente causa un errore del compilatore tentando di aggiungere le variabili [double](../../../csharp/language-reference/keywords/double.md) e `decimal`.</span><span class="sxs-lookup"><span data-stu-id="a5b92-130">The following example causes a compiler error by trying to add [double](../../../csharp/language-reference/keywords/double.md) and `decimal` variables.</span></span>

```csharp
decimal dec = 0m;
double dub = 9;
// The following line causes an error that reads "Operator '+' cannot be applied to
// operands of type 'double' and 'decimal'"
Console.WriteLine(dec + dub);

// You can fix the error by using explicit casting of either operand.
Console.WriteLine(dec + (decimal)dub);
Console.WriteLine((double)dec + dub);
```

<span data-ttu-id="a5b92-131">Viene restituito l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="a5b92-131">The result is the following error:</span></span>

`Operator '+' cannot be applied to operands of type 'double' and 'decimal'`

<span data-ttu-id="a5b92-132">In questo esempio `decimal` e [int](../../../csharp/language-reference/keywords/int.md) sono combinate nella stessa espressione.</span><span class="sxs-lookup"><span data-stu-id="a5b92-132">In this example, a `decimal` and an [int](../../../csharp/language-reference/keywords/int.md) are mixed in the same expression.</span></span> <span data-ttu-id="a5b92-133">Il risultato restituisce il tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="a5b92-133">The result evaluates to the `decimal` type.</span></span>

[!code-csharp[csrefKeywordsTypes#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#6)]

## <a name="example"></a><span data-ttu-id="a5b92-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5b92-134">Example</span></span>

<span data-ttu-id="a5b92-135">In questo esempio l'output viene formattato mediante la stringa del formato valuta (in dollari).</span><span class="sxs-lookup"><span data-stu-id="a5b92-135">In this example, the output is formatted by using the currency format string.</span></span> <span data-ttu-id="a5b92-136">Si noti che `x` viene arrotondato perché le cifre decimali sono superiori a $ 0,99.</span><span class="sxs-lookup"><span data-stu-id="a5b92-136">Notice that `x` is rounded because the decimal places exceed $0.99.</span></span> <span data-ttu-id="a5b92-137">La variabile `y`, che rappresenta le cifre a precisione massima, viene invece visualizzata nel formato esatto.</span><span class="sxs-lookup"><span data-stu-id="a5b92-137">The variable `y`, which represents the maximum exact digits, is displayed exactly in the correct format.</span></span>

[!code-csharp[csrefKeywordsTypes#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#7)]

## <a name="c-language-specification"></a><span data-ttu-id="a5b92-138">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a5b92-138">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a5b92-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5b92-139">See also</span></span>

<xref:System.Decimal>  
[<span data-ttu-id="a5b92-140">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a5b92-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
[<span data-ttu-id="a5b92-141">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a5b92-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="a5b92-142">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="a5b92-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
[<span data-ttu-id="a5b92-143">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="a5b92-143">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
[<span data-ttu-id="a5b92-144">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="a5b92-144">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
[<span data-ttu-id="a5b92-145">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="a5b92-145">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
[<span data-ttu-id="a5b92-146">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="a5b92-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
[<span data-ttu-id="a5b92-147">Stringhe di formato numerico standard</span><span class="sxs-lookup"><span data-stu-id="a5b92-147">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)