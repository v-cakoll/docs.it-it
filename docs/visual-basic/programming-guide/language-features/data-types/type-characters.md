---
title: Digitare i caratteri (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals
- F literal type character
- '& identifier type character'
- type characters
- octal literals
- literals, hexadecimal
- '&O prefix for octal values'
- literals, default types
- defaults, literal types
- C literal type character
- type characters, literal
- $ identifier type character
- L literal type character
- UI literal type characters
- default literal types
- D literal type character
- literals, octal
- S literal type character
- '! identifier type character'
- US literal type characters
- '% identifier type character'
- data types [Visual Basic], type characters
- characters, identifier type
- type characters, identifier
- '# identifier type character'
- identifier type characters
- literal type characters
- I literal type character
- R literal type character
- '@ identifier type character'
- UL literal type characters
- literal types, default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 335306eca12070de456a72e918bcbba1e22ab55b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="28fdb-102">Caratteri tipo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28fdb-102">Type Characters (Visual Basic)</span></span>
<span data-ttu-id="28fdb-103">Oltre a specificare un tipo di dati in un'istruzione di dichiarazione, è possibile forzare il tipo di dati di alcuni elementi di programmazione con un *tipo di carattere*.</span><span class="sxs-lookup"><span data-stu-id="28fdb-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="28fdb-104">Il tipo di carattere deve seguire immediatamente l'elemento, senza i caratteri di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="28fdb-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>  
  
 <span data-ttu-id="28fdb-105">Il tipo di carattere non è parte del nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="28fdb-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="28fdb-106">Un elemento definito con un carattere di tipo può fare riferimento senza il carattere di tipo.</span><span class="sxs-lookup"><span data-stu-id="28fdb-106">An element defined with a type character can be referenced without the type character.</span></span>  
  
## <a name="identifier-type-characters"></a><span data-ttu-id="28fdb-107">Caratteri di tipo identificatore</span><span class="sxs-lookup"><span data-stu-id="28fdb-107">Identifier Type Characters</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="28fdb-108">fornisce un set di *caratteri identificatori di tipo*, che è possibile utilizzare in una dichiarazione per specificare il tipo di dati di una variabile o costante.</span><span class="sxs-lookup"><span data-stu-id="28fdb-108"> supplies a set of *identifier type characters*, which you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="28fdb-109">Nella tabella seguente mostra i caratteri di tipo identificatore disponibile con esempi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="28fdb-109">The following table shows the available identifier type characters with examples of usage.</span></span>  
  
|<span data-ttu-id="28fdb-110">Carattere di tipo identificatore</span><span class="sxs-lookup"><span data-stu-id="28fdb-110">Identifier type character</span></span>|<span data-ttu-id="28fdb-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28fdb-111">Data type</span></span>|<span data-ttu-id="28fdb-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="28fdb-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="28fdb-113">Non esiste alcun carattere di tipo identificatore per il `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, o `UShort` tipi di dati, o per qualsiasi tipo di dati compositi, ad esempio matrici o strutture.</span><span class="sxs-lookup"><span data-stu-id="28fdb-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>  
  
 <span data-ttu-id="28fdb-114">In alcuni casi, è possibile aggiungere il `$` carattere per un [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] funzione, ad esempio `Left$` anziché `Left`, per ottenere un valore restituito di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="28fdb-114">In some cases, you can append the `$` character to a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>  
  
 <span data-ttu-id="28fdb-115">In tutti i casi, il carattere di tipo identificatore deve seguire immediatamente il nome dell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="28fdb-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>  
  
## <a name="literal-type-characters"></a><span data-ttu-id="28fdb-116">Caratteri di tipo effettivo</span><span class="sxs-lookup"><span data-stu-id="28fdb-116">Literal Type Characters</span></span>  
 <span data-ttu-id="28fdb-117">Oggetto *letterale* è una rappresentazione testuale di un determinato valore di un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="28fdb-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  
  
### <a name="default-literal-types"></a><span data-ttu-id="28fdb-118">Tipi di valore letterale predefinito</span><span class="sxs-lookup"><span data-stu-id="28fdb-118">Default Literal Types</span></span>  
 <span data-ttu-id="28fdb-119">Il modulo di un valore letterale come appare nel codice in genere determina il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="28fdb-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="28fdb-120">Nella tabella seguente vengono illustrati questi tipi di valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="28fdb-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="28fdb-121">Formato testuale del valore letterale</span><span class="sxs-lookup"><span data-stu-id="28fdb-121">Textual form of literal</span></span>|<span data-ttu-id="28fdb-122">Tipo di dati predefinito</span><span class="sxs-lookup"><span data-stu-id="28fdb-122">Default data type</span></span>|<span data-ttu-id="28fdb-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="28fdb-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="28fdb-124">Numerico, senza parte frazionaria</span><span class="sxs-lookup"><span data-stu-id="28fdb-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="28fdb-125">Numerico, senza parte frazionaria, troppo grande per`Integer`</span><span class="sxs-lookup"><span data-stu-id="28fdb-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="28fdb-126">Numerico, parte frazionaria</span><span class="sxs-lookup"><span data-stu-id="28fdb-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="28fdb-127">Racchiuso tra virgolette doppie</span><span class="sxs-lookup"><span data-stu-id="28fdb-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="28fdb-128">Racchiuso tra simboli di cancelletto</span><span class="sxs-lookup"><span data-stu-id="28fdb-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  
  
### <a name="forced-literal-types"></a><span data-ttu-id="28fdb-129">Tipi letterali forzati</span><span class="sxs-lookup"><span data-stu-id="28fdb-129">Forced Literal Types</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="28fdb-130">fornisce un set di *caratteri di tipo letterale*, indica che è possibile utilizzare per imporre un valore letterale può assumere un tipo di dati diverso da quello dal form.</span><span class="sxs-lookup"><span data-stu-id="28fdb-130"> supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="28fdb-131">Fatto questo, aggiungendo il carattere alla fine del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="28fdb-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="28fdb-132">Nella tabella seguente mostra i caratteri di tipo letterale disponibili con esempi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="28fdb-132">The following table shows the available literal type characters with examples of usage.</span></span>  
  
|<span data-ttu-id="28fdb-133">Carattere di tipo letterale</span><span class="sxs-lookup"><span data-stu-id="28fdb-133">Literal type character</span></span>|<span data-ttu-id="28fdb-134">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="28fdb-134">Data type</span></span>|<span data-ttu-id="28fdb-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="28fdb-135">Example</span></span>|  
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
  
 <span data-ttu-id="28fdb-136">Non esiste alcun carattere di tipo letterale per il `Boolean`, `Byte`, `Date`, `Object`, `SByte`, o `String` tipi di dati, o per qualsiasi tipo di dati compositi, ad esempio matrici o strutture.</span><span class="sxs-lookup"><span data-stu-id="28fdb-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>  
  
 <span data-ttu-id="28fdb-137">Valori letterali possono inoltre utilizzare i caratteri identificatori di tipo (`%`, `&`, `@`, `!`, `#`, `$`), analogamente a variabili, costanti ed espressioni.</span><span class="sxs-lookup"><span data-stu-id="28fdb-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="28fdb-138">Tuttavia, caratteri di tipo letterale (`S`, `I`, `L`, `D`, `F`, `R`, `C`) può essere utilizzato solo con i valori letterali.</span><span class="sxs-lookup"><span data-stu-id="28fdb-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>  
  
 <span data-ttu-id="28fdb-139">In tutti i casi, il carattere di tipo letterale deve seguire immediatamente il valore letterale.</span><span class="sxs-lookup"><span data-stu-id="28fdb-139">In all cases, the literal type character must immediately follow the literal value.</span></span>  
  
## <a name="hexadecimal-and-octal-literals"></a><span data-ttu-id="28fdb-140">Valori letterali esadecimali e ottali</span><span class="sxs-lookup"><span data-stu-id="28fdb-140">Hexadecimal and Octal Literals</span></span>  
 <span data-ttu-id="28fdb-141">Generalmente, il compilatore interpreta un valore letterale integer per il sistema di numero decimale (base 10).</span><span class="sxs-lookup"><span data-stu-id="28fdb-141">The compiler normally construes an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="28fdb-142">È possibile forzare letterale sia un valore integer esadecimale (base 16) con il `&H` prefisso ed è possibile imporle ottale (base 8) con il `&O` prefisso.</span><span class="sxs-lookup"><span data-stu-id="28fdb-142">You can force an integer literal to be hexadecimal (base 16) with the `&H` prefix, and you can force it to be octal (base 8) with the `&O` prefix.</span></span> <span data-ttu-id="28fdb-143">Le cifre che seguono il prefisso devono essere appropriate per il sistema numerico.</span><span class="sxs-lookup"><span data-stu-id="28fdb-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="28fdb-144">Questa condizione è illustrata nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="28fdb-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="28fdb-145">Numero di base</span><span class="sxs-lookup"><span data-stu-id="28fdb-145">Number base</span></span>|<span data-ttu-id="28fdb-146">Prefisso</span><span class="sxs-lookup"><span data-stu-id="28fdb-146">Prefix</span></span>|<span data-ttu-id="28fdb-147">Cifre valide</span><span class="sxs-lookup"><span data-stu-id="28fdb-147">Valid digit values</span></span>|<span data-ttu-id="28fdb-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="28fdb-148">Example</span></span>|  
|-----------------|------------|------------------------|-------------|  
|<span data-ttu-id="28fdb-149">Esadecimale (base 16)</span><span class="sxs-lookup"><span data-stu-id="28fdb-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="28fdb-150">0-9 e a-F</span><span class="sxs-lookup"><span data-stu-id="28fdb-150">0-9 and A-F</span></span>|`&HFFFF`|  
|<span data-ttu-id="28fdb-151">Ottale (base 8)</span><span class="sxs-lookup"><span data-stu-id="28fdb-151">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="28fdb-152">0-7</span><span class="sxs-lookup"><span data-stu-id="28fdb-152">0-7</span></span>|`&O77`|  
  
 <span data-ttu-id="28fdb-153">È possibile seguire un valore letterale con prefisso con un carattere di tipo letterale.</span><span class="sxs-lookup"><span data-stu-id="28fdb-153">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="28fdb-154">Nell'esempio seguente viene illustrata questa operazione.</span><span class="sxs-lookup"><span data-stu-id="28fdb-154">The following example shows this.</span></span>  
  
```  
Dim counter As Short = &H8000S  
Dim flags As UShort = &H8000US  
```  
  
 <span data-ttu-id="28fdb-155">Nell'esempio precedente, `counter` ha il valore decimale compreso tra -32768, e `flags` ha il valore decimale-32768.</span><span class="sxs-lookup"><span data-stu-id="28fdb-155">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28fdb-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28fdb-156">See Also</span></span>  
 <span data-ttu-id="28fdb-157">[Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="28fdb-157">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="28fdb-158"> [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="28fdb-158"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="28fdb-159"> [Tipi di valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="28fdb-159"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="28fdb-160"> [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="28fdb-160"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="28fdb-161"> [Risoluzione dei tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="28fdb-161"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="28fdb-162"> [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="28fdb-162"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="28fdb-163"> [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md)</span><span class="sxs-lookup"><span data-stu-id="28fdb-163"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)</span></span>
