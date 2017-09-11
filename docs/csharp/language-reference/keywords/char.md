---
title: char (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- char
- char_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c6601a58804d6ecfcbedbc19da09560884e54e7f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="char-c-reference"></a><span data-ttu-id="91c87-102">char (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="91c87-102">char (C# Reference)</span></span>
<span data-ttu-id="91c87-103">La parola chiave `char` è usata per dichiarare un'istanza della struttura <xref:System.Char?displayProperty=fullName> usata da .NET Framework per rappresentare un carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="91c87-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=fullName> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="91c87-104">Il valore di un oggetto `Char` è un valore numerico (ordinale) a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="91c87-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>  
  
 <span data-ttu-id="91c87-105">I caratteri Unicode vengono usati per rappresentare la maggior parte delle lingue scritte di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="91c87-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>  
  
|<span data-ttu-id="91c87-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="91c87-106">Type</span></span>|<span data-ttu-id="91c87-107">Intervallo</span><span class="sxs-lookup"><span data-stu-id="91c87-107">Range</span></span>|<span data-ttu-id="91c87-108">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="91c87-108">Size</span></span>|<span data-ttu-id="91c87-109">Tipo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="91c87-109">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`char`|<span data-ttu-id="91c87-110">U+0000 a U+FFFF</span><span class="sxs-lookup"><span data-stu-id="91c87-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="91c87-111">Carattere Unicode a 16 bit</span><span class="sxs-lookup"><span data-stu-id="91c87-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="91c87-112">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="91c87-112">Literals</span></span>  
 <span data-ttu-id="91c87-113">Le costanti di tipo `char` possono essere scritte come valori letterali carattere, sequenze di escape esadecimali o rappresentazioni Unicode.</span><span class="sxs-lookup"><span data-stu-id="91c87-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="91c87-114">È anche possibile eseguire il cast dei codici a caratteri integrali.</span><span class="sxs-lookup"><span data-stu-id="91c87-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="91c87-115">Nell'esempio seguente vengono inizializzate quattro variabili `char` con lo stesso carattere `X`:</span><span class="sxs-lookup"><span data-stu-id="91c87-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>  
  
 <span data-ttu-id="91c87-116">[!code-cs[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="91c87-116">[!code-cs[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="91c87-117">Conversioni</span><span class="sxs-lookup"><span data-stu-id="91c87-117">Conversions</span></span>  
 <span data-ttu-id="91c87-118">`char` può essere convertito in modo implicito in [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="91c87-118">A `char` can be implicitly converted to [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="91c87-119">Non è tuttavia disponibile nessuna conversione implicita da altri tipi nel tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="91c87-119">However, there are no implicit conversions from other types to the `char` type.</span></span>  
  
 <span data-ttu-id="91c87-120">Il tipo <xref:System.Char?displayProperty=fullName> offre diversi metodi statici per usare i valori `char`.</span><span class="sxs-lookup"><span data-stu-id="91c87-120">The <xref:System.Char?displayProperty=fullName> type provides several static methods for working with `char` values.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="91c87-121">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="91c87-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="91c87-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91c87-122">See Also</span></span>  
 <span data-ttu-id="91c87-123"><xref:System.Char></span><span class="sxs-lookup"><span data-stu-id="91c87-123"><xref:System.Char></span></span>   
 <span data-ttu-id="91c87-124">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="91c87-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="91c87-125">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="91c87-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="91c87-126">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="91c87-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="91c87-127">[Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="91c87-127">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="91c87-128">[Tabella dei tipi predefiniti](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="91c87-128">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="91c87-129">[Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="91c87-129">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="91c87-130">[Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="91c87-130">[Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="91c87-131">[Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="91c87-131">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="91c87-132">Stringhe</span><span class="sxs-lookup"><span data-stu-id="91c87-132">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

