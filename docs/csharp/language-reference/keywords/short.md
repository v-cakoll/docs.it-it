---
title: short (Riferimenti per C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- short
- short_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
caps.latest.revision: 17
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
ms.openlocfilehash: ab3ccfdeb8d8a67b5fcd60b1ad6eee4dcafc9691
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="short-c-reference"></a><span data-ttu-id="c21ba-102">short (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c21ba-102">short (C# Reference)</span></span>

<span data-ttu-id="c21ba-103">`short` denota un tipo di dati integrale che archivia valori in base alla dimensione e all'intervallo illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c21ba-103">`short` denotes an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="c21ba-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="c21ba-104">Type</span></span>|<span data-ttu-id="c21ba-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="c21ba-105">Range</span></span>|<span data-ttu-id="c21ba-106">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="c21ba-106">Size</span></span>|<span data-ttu-id="c21ba-107">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c21ba-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`short`|<span data-ttu-id="c21ba-108">Da –32,768 a 32,767</span><span class="sxs-lookup"><span data-stu-id="c21ba-108">-32,768 to 32,767</span></span>|<span data-ttu-id="c21ba-109">Valore intero a 16 bit con segno</span><span class="sxs-lookup"><span data-stu-id="c21ba-109">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="c21ba-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="c21ba-110">Literals</span></span>  

<span data-ttu-id="c21ba-111">È possibile dichiarare e inizializzare una variabile `short` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="c21ba-111">You can declare and initialize a `short` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="c21ba-112">Se il valore letterale integer è esterno all'intervallo di `short`, vale a dire se è minore di <xref:System.Int16.MinValue?displayProperty=fullName> o maggiore di <xref:System.Int16.MaxValue?displayProperty=fullName>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c21ba-112">If the integer literal is outside the range of `short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=fullName> or greater than <xref:System.Int16.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="c21ba-113">Nell'esempio seguente, i valori interi uguali a 1,034 rappresentati come valori letterali decimali, esadecimali o binari vengono convertiti in modo implicito da valori [int](../../../csharp/language-reference/keywords/int.md) a valori `short`.</span><span class="sxs-lookup"><span data-stu-id="c21ba-113">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `short` values.</span></span>  
  
<span data-ttu-id="c21ba-114">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]</span><span class="sxs-lookup"><span data-stu-id="c21ba-114">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="c21ba-115">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="c21ba-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="c21ba-116">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="c21ba-116">Decimal literals have no prefix.</span></span>

<span data-ttu-id="c21ba-117">A partire da C# 7, è anche possibile usare il carattere di sottolineatura, `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c21ba-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="c21ba-118">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]</span><span class="sxs-lookup"><span data-stu-id="c21ba-118">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]</span></span>  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="c21ba-119">Risoluzione dell'overload del compilatore</span><span class="sxs-lookup"><span data-stu-id="c21ba-119">Compiler overload resolution</span></span>

 <span data-ttu-id="c21ba-120">È necessario usare un cast quando si chiamano metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="c21ba-120">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="c21ba-121">Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `short` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="c21ba-121">Consider, for example, the following overloaded methods that use `short` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 <span data-ttu-id="c21ba-122">L'uso del cast `short` garantisce che venga chiamato il tipo corretto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c21ba-122">Using the `short` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="c21ba-123">Conversioni</span><span class="sxs-lookup"><span data-stu-id="c21ba-123">Conversions</span></span>  

 <span data-ttu-id="c21ba-124">Si verifica una conversione implicita predefinita da `short` a [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="c21ba-124">There is a predefined implicit conversion from `short` to [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="c21ba-125">Non è possibile convertire in modo implicito tipi numerici non letterali che necessitano di maggiore spazio in memoria in `short`. Per informazioni sullo spazio necessario per l'archiviazione dei tipi integrali, vedere [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="c21ba-125">You cannot implicitly convert nonliteral numeric types of larger storage size to `short` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="c21ba-126">Considerare, ad esempio, le due variabili `short` seguenti, `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="c21ba-126">Consider, for example, the following two `short` variables `x` and `y`:</span></span>  
  
```csharp  
short x = 5, y = 12;  
```  
  
 <span data-ttu-id="c21ba-127">L'istruzione di assegnazione seguente genera un errore di compilazione, poiché l'espressione aritmetica a destra dell'operatore di assegnazione restituisce [int](../../../csharp/language-reference/keywords/int.md) per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c21ba-127">The following assignment statement produces a compilation error because the arithmetic expression on the right-hand side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

 <span data-ttu-id="c21ba-128">Per risolvere il problema, usare un cast:</span><span class="sxs-lookup"><span data-stu-id="c21ba-128">To fix this problem, use a cast:</span></span>  
  
```csharp
short z  = (short)(x + y);   // Explicit conversion
```
  
 <span data-ttu-id="c21ba-129">È anche possibile usare le istruzioni seguenti dove la variabile di destinazione ha la stessa dimensione di archiviazione o una dimensione maggiore:</span><span class="sxs-lookup"><span data-stu-id="c21ba-129">It is also possible to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="c21ba-130">Non è disponibile nessuna conversione implicita dai tipi a virgola mobile a `short`.</span><span class="sxs-lookup"><span data-stu-id="c21ba-130">There is no implicit conversion from floating-point types to `short`.</span></span> <span data-ttu-id="c21ba-131">Ad esempio, l'istruzione seguente genera un errore del compilatore, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="c21ba-131">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 <span data-ttu-id="c21ba-132">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="c21ba-132">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="c21ba-133">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="c21ba-133">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c21ba-134">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c21ba-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c21ba-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c21ba-135">See Also</span></span>  
 <span data-ttu-id="c21ba-136"><xref:System.Int16></span><span class="sxs-lookup"><span data-stu-id="c21ba-136"><xref:System.Int16></span></span>   
 <span data-ttu-id="c21ba-137">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c21ba-137">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c21ba-138">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c21ba-138">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c21ba-139">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c21ba-139">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c21ba-140">[Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="c21ba-140">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="c21ba-141">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="c21ba-141">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="c21ba-142">[Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="c21ba-142">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="c21ba-143">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="c21ba-143">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

