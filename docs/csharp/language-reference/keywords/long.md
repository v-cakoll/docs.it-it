---
title: long (Riferimenti per C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- long_CSharpKeyword
- long
dev_langs:
- CSharp
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
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
ms.openlocfilehash: 5f7d2d6a3d5781b4e120b8399c7206d4429dd98e
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="long-c-reference"></a><span data-ttu-id="39a22-102">long (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="39a22-102">long (C# Reference)</span></span>

<span data-ttu-id="39a22-103">`long` denota un tipo integrale che archivia valori in base alla dimensione e all'intervallo visualizzato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="39a22-103">`long` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="39a22-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="39a22-104">Type</span></span>|<span data-ttu-id="39a22-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="39a22-105">Range</span></span>|<span data-ttu-id="39a22-106">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="39a22-106">Size</span></span>|<span data-ttu-id="39a22-107">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="39a22-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`long`|<span data-ttu-id="39a22-108">Da -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="39a22-108">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="39a22-109">Numero intero con segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="39a22-109">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="39a22-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="39a22-110">Literals</span></span> 

<span data-ttu-id="39a22-111">È possibile dichiarare e inizializzare una variabile `long` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="39a22-111">You can declare and initialize a `long` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> 

<span data-ttu-id="39a22-112">Nell'esempio seguente, i valori interi uguali a 4.294.967.296 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `long`.</span><span class="sxs-lookup"><span data-stu-id="39a22-112">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `long` values.</span></span>  
  
<span data-ttu-id="39a22-113">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]</span><span class="sxs-lookup"><span data-stu-id="39a22-113">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="39a22-114">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="39a22-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="39a22-115">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="39a22-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="39a22-116">A partire da C# 7, è anche possibile usare il carattere di sottolineatura, `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="39a22-116">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="39a22-117">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span><span class="sxs-lookup"><span data-stu-id="39a22-117">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span></span>  
 
 <span data-ttu-id="39a22-118">Valori letterali integer possono anche includere un suffisso che denota il tipo.</span><span class="sxs-lookup"><span data-stu-id="39a22-118">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="39a22-119">Il suffisso `L` denota un `long`.</span><span class="sxs-lookup"><span data-stu-id="39a22-119">The suffix `L` denotes a `long`.</span></span> <span data-ttu-id="39a22-120">L'esempio seguente usa il suffisso `L` per indicare un valore long integer:</span><span class="sxs-lookup"><span data-stu-id="39a22-120">The following example uses the `L` suffix to denote a long integer:</span></span>
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  <span data-ttu-id="39a22-121">È anche possibile usare la lettera minuscola "l" come suffisso.</span><span class="sxs-lookup"><span data-stu-id="39a22-121">You can also use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="39a22-122">In questo caso, viene tuttavia generato un avviso del compilatore perché la lettera "l" viene facilmente confusa con la cifra "1".</span><span class="sxs-lookup"><span data-stu-id="39a22-122">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="39a22-123">Per maggiore chiarezza, usare la lettera "L".</span><span class="sxs-lookup"><span data-stu-id="39a22-123">Use "L" for clarity.</span></span>  
  
 <span data-ttu-id="39a22-124">Quando si usa il suffisso `L`, il tipo del valore letterale integer viene impostato su `long` o [ulong](../../../csharp/language-reference/keywords/ulong.md) a seconda delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="39a22-124">When you use the suffix `L`, the type of the literal integer is determined to be either `long` or [ulong](../../../csharp/language-reference/keywords/ulong.md), depending on its size.</span></span> <span data-ttu-id="39a22-125">In questo caso è di tipo `long` perché è minore dell'intervallo di [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="39a22-125">In this case, it is `long` because it less than the range of [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="39a22-126">Un uso comune del suffisso è la chiamata di metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="39a22-126">A common use of the suffix is to call overloaded methods.</span></span> <span data-ttu-id="39a22-127">I metodi di overload seguenti, ad esempio, hanno parametri di tipo `long` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="39a22-127">For example, the following overloaded methods have parameters of type `long` and [int](../../../csharp/language-reference/keywords/int.md):</span></span>  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 <span data-ttu-id="39a22-128">Il suffisso `L` garantisce che venga chiamato l'overload corretto:</span><span class="sxs-lookup"><span data-stu-id="39a22-128">The `L` suffix guarantees that the correct overload is called:</span></span>  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
<span data-ttu-id="39a22-129">Se un valore letterale integer non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:</span><span class="sxs-lookup"><span data-stu-id="39a22-129">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="39a22-130">int</span><span class="sxs-lookup"><span data-stu-id="39a22-130">int</span></span>](int.md)
2. [<span data-ttu-id="39a22-131">uint</span><span class="sxs-lookup"><span data-stu-id="39a22-131">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [<span data-ttu-id="39a22-132">ulong</span><span class="sxs-lookup"><span data-stu-id="39a22-132">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 

<span data-ttu-id="39a22-133">Il valore letterale 4294967296 nell'esempio precedente è di tipo `long` perché è esterno all'intervallo di [uint](../../../csharp/language-reference/keywords/uint.md). Per informazioni sullo spazio necessario per l'archiviazione dei tipi integrali, vedere [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="39a22-133">The literal 4294967296 in the previous examples is of type `long`, because it exceeds the range of [uint](../../../csharp/language-reference/keywords/uint.md) (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span>  
  
 <span data-ttu-id="39a22-134">Se si usa il tipo `long` con altri tipi integrali nella stessa espressione, l'espressione darà un risultato di tipo `long` (o [bool](../../../csharp/language-reference/keywords/bool.md) nel caso di espressioni relazionali o booleane).</span><span class="sxs-lookup"><span data-stu-id="39a22-134">If you use the `long` type with other integral types in the same expression, the expression is evaluated as `long` (or [bool](../../../csharp/language-reference/keywords/bool.md) in the case of relational or Boolean expressions).</span></span> <span data-ttu-id="39a22-135">Ad esempio, l'espressione riportata di seguito restituisce `long`:</span><span class="sxs-lookup"><span data-stu-id="39a22-135">For example, the following expression evaluates as `long`:</span></span>  
  
```csharp  
898L + 88  
```  
  
 <span data-ttu-id="39a22-136">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="39a22-136">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="39a22-137">Conversioni</span><span class="sxs-lookup"><span data-stu-id="39a22-137">Conversions</span></span>  
 <span data-ttu-id="39a22-138">Si verifica una conversione implicita predefinita da `long` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="39a22-138">There is a predefined implicit conversion from `long` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="39a22-139">In tutti gli altri casi è necessario usare un cast.</span><span class="sxs-lookup"><span data-stu-id="39a22-139">Otherwise a cast must be used.</span></span> <span data-ttu-id="39a22-140">L'istruzione seguente, ad esempio, genera un errore di compilazione se non viene usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="39a22-140">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 <span data-ttu-id="39a22-141">Si verifica una conversione implicita predefinita da [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) in `long`.</span><span class="sxs-lookup"><span data-stu-id="39a22-141">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `long`.</span></span>  
  
 <span data-ttu-id="39a22-142">Si noti anche che non esiste alcuna conversione implicita dai tipi a virgola mobile a `long`.</span><span class="sxs-lookup"><span data-stu-id="39a22-142">Notice also that there is no implicit conversion from floating-point types to `long`.</span></span> <span data-ttu-id="39a22-143">L'istruzione seguente, ad esempio, genera un errore di compilazione a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="39a22-143">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="39a22-144">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="39a22-144">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="39a22-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39a22-145">See Also</span></span>  
 <span data-ttu-id="39a22-146"><xref:System.Int64></span><span class="sxs-lookup"><span data-stu-id="39a22-146"><xref:System.Int64></span></span>   
 <span data-ttu-id="39a22-147">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="39a22-147">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="39a22-148">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="39a22-148">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="39a22-149">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="39a22-149">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="39a22-150">[Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="39a22-150">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="39a22-151">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="39a22-151">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="39a22-152">[Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="39a22-152">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="39a22-153">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="39a22-153">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

