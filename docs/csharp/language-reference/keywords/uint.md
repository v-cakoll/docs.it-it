---
title: uint (Riferimenti per C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- uint
- uint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
caps.latest.revision: 18
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
ms.openlocfilehash: 4342c08ab536f45a2e3b5fa6fe94839436600a4a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="uint-c-reference"></a><span data-ttu-id="45bbd-102">uint (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="45bbd-102">uint (C# Reference)</span></span>

<span data-ttu-id="45bbd-103">La parola chiave `uint` rappresenta un tipo integrale che archivia valori in base alla dimensione e all'intervallo mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="45bbd-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="45bbd-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="45bbd-104">Type</span></span>|<span data-ttu-id="45bbd-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="45bbd-105">Range</span></span>|<span data-ttu-id="45bbd-106">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="45bbd-106">Size</span></span>|<span data-ttu-id="45bbd-107">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="45bbd-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`uint`|<span data-ttu-id="45bbd-108">Da 0 a 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="45bbd-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="45bbd-109">Intero senza segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="45bbd-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=fullName>|  
  
 <span data-ttu-id="45bbd-110">**Nota** Il tipo `uint` non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="45bbd-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="45bbd-111">Usare `int`, laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="45bbd-111">Use `int` whenever possible.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="45bbd-112">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="45bbd-112">Literals</span></span>  

<span data-ttu-id="45bbd-113">È possibile dichiarare e inizializzare una variabile `uint` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="45bbd-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="45bbd-114">Se il valore letterale integer è esterno all'intervallo di `uint`, vale a dire se è minore di <xref:System.UInt32.MinValue?displayProperty=fullName> o maggiore di <xref:System.UInt32.MaxValue?displayProperty=fullName>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="45bbd-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=fullName> or greater than <xref:System.UInt32.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="45bbd-115">Nell'esempio seguente, i valori interi uguali a 3.000.000.000 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `uint`.</span><span class="sxs-lookup"><span data-stu-id="45bbd-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>  
  
<span data-ttu-id="45bbd-116">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]</span><span class="sxs-lookup"><span data-stu-id="45bbd-116">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="45bbd-117">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="45bbd-117">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="45bbd-118">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="45bbd-118">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="45bbd-119">A partire da C# 7, è anche possibile usare il carattere di sottolineatura, `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="45bbd-119">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="45bbd-120">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]</span><span class="sxs-lookup"><span data-stu-id="45bbd-120">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]</span></span>  
 
 <span data-ttu-id="45bbd-121">Valori letterali integer possono anche includere un suffisso che denota il tipo.</span><span class="sxs-lookup"><span data-stu-id="45bbd-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="45bbd-122">Il suffisso `U` o 'u' denota un valore `uint` o `ulong`, a seconda del valore numerico del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="45bbd-122">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="45bbd-123">L'esempio seguente usa il suffisso `u` per indicare un intero senza segno di entrambi i tipi.</span><span class="sxs-lookup"><span data-stu-id="45bbd-123">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="45bbd-124">Si noti che il primo valore letterale è `uint` perché il relativo valore è minore di <xref:System.UInt32.MaxValue?displayProperty=fullName>, mentre il secondo è `ulong` perché il relativo valore è maggiore di <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="45bbd-124">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=fullName>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span></span>

<span data-ttu-id="45bbd-125">[!code-cs[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="45bbd-125">[!code-cs[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]</span></span>  
 
<span data-ttu-id="45bbd-126">Se un valore letterale integer non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:</span><span class="sxs-lookup"><span data-stu-id="45bbd-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="45bbd-127">int</span><span class="sxs-lookup"><span data-stu-id="45bbd-127">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="45bbd-128">long</span><span class="sxs-lookup"><span data-stu-id="45bbd-128">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="45bbd-129">ulong</span><span class="sxs-lookup"><span data-stu-id="45bbd-129">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
  
## <a name="conversions"></a><span data-ttu-id="45bbd-130">Conversioni</span><span class="sxs-lookup"><span data-stu-id="45bbd-130">Conversions</span></span>  
 <span data-ttu-id="45bbd-131">Si verifica una conversione implicita predefinita da `uint` a [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="45bbd-131">There is a predefined implicit conversion from `uint` to [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="45bbd-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="45bbd-132">For example:</span></span>  
  
```csharp  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 <span data-ttu-id="45bbd-133">Viene eseguita una conversione implicita predefinita da [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) o [char](../../../csharp/language-reference/keywords/char.md) a `uint`.</span><span class="sxs-lookup"><span data-stu-id="45bbd-133">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `uint`.</span></span> <span data-ttu-id="45bbd-134">In tutti gli altri casi è necessario ricorrere a un cast.</span><span class="sxs-lookup"><span data-stu-id="45bbd-134">Otherwise you must use a cast.</span></span> <span data-ttu-id="45bbd-135">Nella seguente istruzione di assegnazione, ad esempio, verrà generato un errore di compilazione senza un cast:</span><span class="sxs-lookup"><span data-stu-id="45bbd-135">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 <span data-ttu-id="45bbd-136">Si noti inoltre che non avviene alcuna conversione implicita dai tipi a virgola mobile in `uint`.</span><span class="sxs-lookup"><span data-stu-id="45bbd-136">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="45bbd-137">Ad esempio, l'istruzione seguente genera un errore del compilatore, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="45bbd-137">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 <span data-ttu-id="45bbd-138">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="45bbd-138">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="45bbd-139">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="45bbd-139">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="45bbd-140">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="45bbd-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="45bbd-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45bbd-141">See Also</span></span>  
 <span data-ttu-id="45bbd-142"><xref:System.UInt32></span><span class="sxs-lookup"><span data-stu-id="45bbd-142"><xref:System.UInt32></span></span>   
 <span data-ttu-id="45bbd-143">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="45bbd-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="45bbd-144">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="45bbd-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="45bbd-145">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="45bbd-145">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="45bbd-146">[Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="45bbd-146">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="45bbd-147">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="45bbd-147">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="45bbd-148">[Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="45bbd-148">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="45bbd-149">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="45bbd-149">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

