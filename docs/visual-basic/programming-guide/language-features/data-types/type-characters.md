---
title: Caratteri tipo
ms.date: 01/31/2018
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
ms.openlocfilehash: 628461c8136946dd902c0a52048eee7c516c52cd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352930"
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="84b19-102">Caratteri di tipo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84b19-102">Type characters (Visual Basic)</span></span>

<span data-ttu-id="84b19-103">Oltre a specificare un tipo di dati in un'istruzione di dichiarazione, è possibile forzare il tipo di dati di alcuni elementi di programmazione con un *carattere tipo*.</span><span class="sxs-lookup"><span data-stu-id="84b19-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="84b19-104">Il carattere tipo deve seguire immediatamente l'elemento, senza alcun carattere corrispondente.</span><span class="sxs-lookup"><span data-stu-id="84b19-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="84b19-105">Il tipo di carattere non fa parte del nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="84b19-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="84b19-106">È possibile fare riferimento a un elemento definito con un carattere di tipo senza il carattere tipo.</span><span class="sxs-lookup"><span data-stu-id="84b19-106">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="84b19-107">Caratteri di tipo identificatore</span><span class="sxs-lookup"><span data-stu-id="84b19-107">Identifier type characters</span></span>

<span data-ttu-id="84b19-108">Visual Basic fornisce un set di *caratteri di tipo identificatore* che è possibile utilizzare in una dichiarazione per specificare il tipo di dati di una variabile o di una costante.</span><span class="sxs-lookup"><span data-stu-id="84b19-108">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="84b19-109">Nella tabella seguente sono illustrati i caratteri di tipo identificatore disponibili con esempi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="84b19-109">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="84b19-110">Carattere di tipo identificatore</span><span class="sxs-lookup"><span data-stu-id="84b19-110">Identifier type character</span></span>|<span data-ttu-id="84b19-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="84b19-111">Data type</span></span>|<span data-ttu-id="84b19-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="84b19-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="84b19-113">Nessun carattere di tipo identificatore esistente per i tipi di dati `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`o `UShort` o per qualsiasi tipo di dati composito, ad esempio matrici o strutture.</span><span class="sxs-lookup"><span data-stu-id="84b19-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="84b19-114">In alcuni casi, è possibile aggiungere il carattere `$` a una funzione di Visual Basic, ad esempio `Left$` anziché `Left`, per ottenere un valore restituito di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="84b19-114">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="84b19-115">In tutti i casi, il carattere di tipo identificatore deve seguire immediatamente il nome dell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="84b19-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="84b19-116">Caratteri di tipo letterale</span><span class="sxs-lookup"><span data-stu-id="84b19-116">Literal type characters</span></span>

<span data-ttu-id="84b19-117">Un valore *letterale* è una rappresentazione testuale di un particolare valore di un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="84b19-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="84b19-118">Tipi di valore letterale predefinito</span><span class="sxs-lookup"><span data-stu-id="84b19-118">Default literal types</span></span>

<span data-ttu-id="84b19-119">Il formato di un valore letterale come appare nel codice determina in genere il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="84b19-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="84b19-120">Nella tabella seguente vengono illustrati questi tipi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="84b19-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="84b19-121">Forma testuale di valore letterale</span><span class="sxs-lookup"><span data-stu-id="84b19-121">Textual form of literal</span></span>|<span data-ttu-id="84b19-122">Tipo di dati predefinito</span><span class="sxs-lookup"><span data-stu-id="84b19-122">Default data type</span></span>|<span data-ttu-id="84b19-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="84b19-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="84b19-124">Numeric, nessuna parte frazionaria</span><span class="sxs-lookup"><span data-stu-id="84b19-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="84b19-125">Numerico, nessuna parte frazionaria, troppo grande per `Integer`</span><span class="sxs-lookup"><span data-stu-id="84b19-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="84b19-126">Numerica, parte frazionaria</span><span class="sxs-lookup"><span data-stu-id="84b19-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="84b19-127">Racchiuso tra virgolette doppie</span><span class="sxs-lookup"><span data-stu-id="84b19-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="84b19-128">Racchiuso tra segni di cancelletto</span><span class="sxs-lookup"><span data-stu-id="84b19-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="84b19-129">Tipi di valori letterali forzati</span><span class="sxs-lookup"><span data-stu-id="84b19-129">Forced literal types</span></span>

<span data-ttu-id="84b19-130">Visual Basic fornisce un set di *caratteri di tipo letterale*, che è possibile usare per imporre a un valore letterale di assumere un tipo di dati diverso da quello indicato dal form.</span><span class="sxs-lookup"><span data-stu-id="84b19-130">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="84b19-131">A tale scopo, aggiungere il carattere alla fine del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="84b19-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="84b19-132">Nella tabella seguente vengono illustrati i caratteri di tipo letterale disponibili con esempi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="84b19-132">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="84b19-133">Carattere di tipo letterale</span><span class="sxs-lookup"><span data-stu-id="84b19-133">Literal type character</span></span>|<span data-ttu-id="84b19-134">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="84b19-134">Data type</span></span>|<span data-ttu-id="84b19-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="84b19-135">Example</span></span>|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

<span data-ttu-id="84b19-136">Nessun carattere di tipo letterale esistente per i tipi di dati `Boolean`, `Byte`, `Date`, `Object`, `SByte`o `String` oppure per qualsiasi tipo di dati composito, ad esempio matrici o strutture.</span><span class="sxs-lookup"><span data-stu-id="84b19-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="84b19-137">I valori letterali possono anche usare i caratteri di tipo identificatore (`%`, `&`, `@`, `!`, `#`, `$`), così come possono variabili, costanti ed espressioni.</span><span class="sxs-lookup"><span data-stu-id="84b19-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="84b19-138">Tuttavia, i caratteri di tipo letterale (`S`, `I`, `L`, `D`, `F`, `R`, `C`) possono essere utilizzati solo con valori letterali.</span><span class="sxs-lookup"><span data-stu-id="84b19-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="84b19-139">In tutti i casi, il carattere di tipo letterale deve seguire immediatamente il valore letterale.</span><span class="sxs-lookup"><span data-stu-id="84b19-139">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="84b19-140">Valori letterali esadecimali, binari e ottali</span><span class="sxs-lookup"><span data-stu-id="84b19-140">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="84b19-141">Il compilatore interpreta in genere un valore letterale integer che si trova nel sistema numerico Decimal (base 10).</span><span class="sxs-lookup"><span data-stu-id="84b19-141">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="84b19-142">È anche possibile definire un valore letterale integer come numero esadecimale (base 16) con il prefisso `&H`, come numero binario (base 2) con il prefisso di `&B` e come numero ottale (base 8) con il prefisso `&O`.</span><span class="sxs-lookup"><span data-stu-id="84b19-142">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="84b19-143">Le cifre che seguono il prefisso devono essere appropriate per il sistema di numeri.</span><span class="sxs-lookup"><span data-stu-id="84b19-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="84b19-144">Questa operazione è illustrata nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="84b19-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="84b19-145">Base numero</span><span class="sxs-lookup"><span data-stu-id="84b19-145">Number base</span></span>|<span data-ttu-id="84b19-146">Prefisso</span><span class="sxs-lookup"><span data-stu-id="84b19-146">Prefix</span></span>|<span data-ttu-id="84b19-147">Valori numerici validi</span><span class="sxs-lookup"><span data-stu-id="84b19-147">Valid digit values</span></span>|<span data-ttu-id="84b19-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="84b19-148">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="84b19-149">Esadecimale (base 16)</span><span class="sxs-lookup"><span data-stu-id="84b19-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="84b19-150">0-9 e A-F</span><span class="sxs-lookup"><span data-stu-id="84b19-150">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="84b19-151">Binary (base 2)</span><span class="sxs-lookup"><span data-stu-id="84b19-151">Binary (base 2)</span></span>|`&B`|<span data-ttu-id="84b19-152">0-1</span><span class="sxs-lookup"><span data-stu-id="84b19-152">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="84b19-153">Ottale (base 8)</span><span class="sxs-lookup"><span data-stu-id="84b19-153">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="84b19-154">0-7</span><span class="sxs-lookup"><span data-stu-id="84b19-154">0-7</span></span>|`&O77`|

<span data-ttu-id="84b19-155">A partire da Visual Basic 2017, è possibile usare il carattere di sottolineatura (`_`) come separatore di gruppo per migliorare la leggibilità di un valore letterale integrale.</span><span class="sxs-lookup"><span data-stu-id="84b19-155">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="84b19-156">Nell'esempio seguente viene usato il carattere `_` per raggruppare un valore letterale binario in gruppi a 8 bit:</span><span class="sxs-lookup"><span data-stu-id="84b19-156">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="84b19-157">È possibile seguire un valore letterale con prefisso con un carattere di tipo letterale.</span><span class="sxs-lookup"><span data-stu-id="84b19-157">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="84b19-158">Nell'esempio seguente viene illustrato questo.</span><span class="sxs-lookup"><span data-stu-id="84b19-158">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="84b19-159">Nell'esempio precedente `counter` ha il valore decimale di-32768 e il valore decimale di `flags` è + 32768.</span><span class="sxs-lookup"><span data-stu-id="84b19-159">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

<span data-ttu-id="84b19-160">A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali.</span><span class="sxs-lookup"><span data-stu-id="84b19-160">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="84b19-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="84b19-161">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a><span data-ttu-id="84b19-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84b19-162">See also</span></span>

- [<span data-ttu-id="84b19-163">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="84b19-163">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="84b19-164">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="84b19-164">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="84b19-165">Tipi valore e tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="84b19-165">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="84b19-166">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84b19-166">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="84b19-167">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="84b19-167">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="84b19-168">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="84b19-168">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="84b19-169">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="84b19-169">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
