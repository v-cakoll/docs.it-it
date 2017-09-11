---
title: decimal (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- decimal_CSharpKeyword
- decimal
dev_langs:
- CSharp
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
caps.latest.revision: 32
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
ms.openlocfilehash: 4c06d14f01302a21427845d0269fc8181a380914
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="decimal-c-reference"></a><span data-ttu-id="f5cdd-102">decimal (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f5cdd-102">decimal (C# Reference)</span></span>
<span data-ttu-id="f5cdd-103">La parola chiave `decimal` indica un tipo di dati a 128 bit.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-103">The `decimal` keyword indicates a 128-bit data type.</span></span> <span data-ttu-id="f5cdd-104">Rispetto ad altri tipi a virgola mobile, il tipo `decimal` è caratterizzato da una maggiore precisione e da un intervallo minore, che lo rendono appropriato per calcoli finanziari e monetari.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-104">Compared to other floating-point types, the `decimal` type has more precision and a smaller range, which makes it appropriate for financial and monetary calculations.</span></span> <span data-ttu-id="f5cdd-105">Nella tabella riportata di seguito vengono indicati l'intervallo approssimativo e il grado di precisione del tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-105">The approximate range and precision for the `decimal` type are shown in the following table.</span></span>  
  
|<span data-ttu-id="f5cdd-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="f5cdd-106">Type</span></span>|<span data-ttu-id="f5cdd-107">Intervallo approssimativo</span><span class="sxs-lookup"><span data-stu-id="f5cdd-107">Approximate Range</span></span>|<span data-ttu-id="f5cdd-108">Precisione</span><span class="sxs-lookup"><span data-stu-id="f5cdd-108">Precision</span></span>|<span data-ttu-id="f5cdd-109">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f5cdd-109">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`decimal`|<span data-ttu-id="f5cdd-110">(Da -7,9 x 10<sup>28</sup> a 7,9 x 10<sup>28</sup>) / (da 10<sup>0</sup> a 10<sup>28</sup>)</span><span class="sxs-lookup"><span data-stu-id="f5cdd-110">(-7.9 x 10<sup>28</sup> to 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> to 10<sup>28</sup>)</span></span>|<span data-ttu-id="f5cdd-111">28-29 cifre significative</span><span class="sxs-lookup"><span data-stu-id="f5cdd-111">28-29 significant digits</span></span>|<xref:System.Decimal?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="f5cdd-112">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="f5cdd-112">Literals</span></span>  
 <span data-ttu-id="f5cdd-113">Se si desidera che un valore letterale numerico reale venga gestito come `decimal`, utilizzare il suffisso m o M, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f5cdd-113">If you want a numeric real literal to be treated as `decimal`, use the suffix m or M, for example:</span></span>  
  
```csharp
decimal myMoney = 300.5m;  
```  
  
 <span data-ttu-id="f5cdd-114">Senza il suffisso m, il numero viene gestito come valore [double](../../../csharp/language-reference/keywords/double.md) e genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-114">Without the suffix m, the number is treated as a [double](../../../csharp/language-reference/keywords/double.md) and generates a compiler error.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="f5cdd-115">Conversioni</span><span class="sxs-lookup"><span data-stu-id="f5cdd-115">Conversions</span></span>  
 <span data-ttu-id="f5cdd-116">I tipi integrali vengono convertiti in modo implicito in `decimal` e il risultato restituisce `decimal`.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-116">The integral types are implicitly converted to `decimal` and the result evaluates to `decimal`.</span></span> <span data-ttu-id="f5cdd-117">È pertanto possibile inizializzare una variabile decimale mediante un valore letterale Integer, senza il suffisso, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f5cdd-117">Therefore you can initialize a decimal variable using an integer literal, without the suffix, as follows:</span></span>  
  
```csharp
decimal myMoney = 300;  
```  
  
 <span data-ttu-id="f5cdd-118">Poiché non esiste alcuna conversione implicita tra altri tipi a virgola mobile e il tipo `decimal`, è necessario usare un cast per eseguire una conversione tra questi due tipi.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-118">There is no implicit conversion between other floating-point types and the `decimal` type; therefore, a cast must be used to convert between these two types.</span></span> <span data-ttu-id="f5cdd-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f5cdd-119">For example:</span></span>  
  
```csharp
decimal myMoney = 99.9m;  
double x = (double)myMoney;  
myMoney = (decimal)x;  
```  
  
 <span data-ttu-id="f5cdd-120">È inoltre possibile combinare tipi `decimal` e tipi integrali numerici nella stessa espressione.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-120">You can also mix `decimal` and numeric integral types in the same expression.</span></span> <span data-ttu-id="f5cdd-121">Tuttavia, la combinazione di `decimal` e altri tipi a virgola mobile senza un cast genera un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-121">However, mixing `decimal` and other floating-point types without a cast causes a compilation error.</span></span>  
  
 <span data-ttu-id="f5cdd-122">Per altre informazioni sulle conversioni numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="f5cdd-122">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="f5cdd-123">Per altre informazioni sulle conversioni numeriche esplicite, vedere [Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="f5cdd-123">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
## <a name="formatting-decimal-output"></a><span data-ttu-id="f5cdd-124">Formattazione dell'output di tipo decimal</span><span class="sxs-lookup"><span data-stu-id="f5cdd-124">Formatting Decimal Output</span></span>  
 <span data-ttu-id="f5cdd-125">È possibile applicare il formato desiderato ai risultati utilizzando il metodo `String.Format` o mediante il metodo <xref:System.Console.Write%2A?displayProperty=fullName> che chiama `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-125">You can format the results by using the `String.Format` method, or through the <xref:System.Console.Write%2A?displayProperty=fullName> method, which calls `String.Format()`.</span></span> <span data-ttu-id="f5cdd-126">Il formato valuta viene specificato tramite la stringa di formato valuta standard "C" o "c", come illustrato nel secondo esempio riportato più avanti.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-126">The currency format is specified by using the standard currency format string "C" or "c," as shown in the second example later in this article.</span></span> <span data-ttu-id="f5cdd-127">Per ulteriori informazioni sul metodo `String.Format`, vedere <xref:System.String.Format%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-127">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=fullName>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5cdd-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5cdd-128">Example</span></span>  
 <span data-ttu-id="f5cdd-129">L'esempio seguente causa un errore del compilatore tentando di aggiungere le variabili [double](../../../csharp/language-reference/keywords/double.md) e `decimal`.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-129">The following example causes a compiler error by trying to add [double](../../../csharp/language-reference/keywords/double.md) and `decimal` variables.</span></span>  
  
```csharp  
double dub = 9;  
// The following line causes an error that reads "Operator '+' cannot be applied to   
// operands of type 'double' and 'decimal'"  
Console.WriteLine(dec + dub);   
  
// You can fix the error by using explicit casting of either operand.  
Console.WriteLine(dec + (decimal)dub);  
Console.WriteLine((double)dec + dub);  
```  
  
 <span data-ttu-id="f5cdd-130">Viene restituito l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="f5cdd-130">The result is the following error:</span></span>  
  
 `Operator '+' cannot be applied to operands of type 'double' and 'decimal'`  
  
 <span data-ttu-id="f5cdd-131">In questo esempio `decimal` e [int](../../../csharp/language-reference/keywords/int.md) sono combinate nella stessa espressione.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-131">In this example, a `decimal` and an [int](../../../csharp/language-reference/keywords/int.md) are mixed in the same expression.</span></span> <span data-ttu-id="f5cdd-132">Il risultato restituisce il tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-132">The result evaluates to the `decimal` type.</span></span>  
  
 <span data-ttu-id="f5cdd-133">[!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f5cdd-133">[!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5cdd-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5cdd-134">Example</span></span>  
 <span data-ttu-id="f5cdd-135">In questo esempio l'output viene formattato mediante la stringa del formato valuta (in dollari).</span><span class="sxs-lookup"><span data-stu-id="f5cdd-135">In this example, the output is formatted by using the currency format string.</span></span> <span data-ttu-id="f5cdd-136">Si noti che `x` viene arrotondato perché le cifre decimali sono superiori a $ 0,99.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-136">Notice that `x` is rounded because the decimal places exceed $0.99.</span></span> <span data-ttu-id="f5cdd-137">La variabile `y`, che rappresenta le cifre a precisione massima, viene invece visualizzata nel formato esatto.</span><span class="sxs-lookup"><span data-stu-id="f5cdd-137">The variable `y`, which represents the maximum exact digits, is displayed exactly in the correct format.</span></span>  
  
 <span data-ttu-id="f5cdd-138">[!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f5cdd-138">[!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f5cdd-139">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f5cdd-139">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5cdd-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5cdd-140">See Also</span></span>  
 <span data-ttu-id="f5cdd-141"><xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="f5cdd-141"><xref:System.Decimal></span></span>   
 <span data-ttu-id="f5cdd-142">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f5cdd-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f5cdd-143">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f5cdd-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f5cdd-144">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f5cdd-144">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f5cdd-145">[Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="f5cdd-145">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="f5cdd-146">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="f5cdd-146">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="f5cdd-147">[Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="f5cdd-147">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="f5cdd-148">[Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="f5cdd-148">[Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="f5cdd-149">Stringhe di formato numerico standard</span><span class="sxs-lookup"><span data-stu-id="f5cdd-149">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)

