---
title: Stringhe
description: Informazioni sul modo F# in cui il tipo ' String ' rappresenta il testo non modificabile come sequenza di caratteri Unicode.
ms.date: 07/05/2019
ms.openlocfilehash: 284de939c90c4d9d4ea064fb4db1fb90a37038e2
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627098"
---
# <a name="strings"></a><span data-ttu-id="f0697-103">Stringhe</span><span class="sxs-lookup"><span data-stu-id="f0697-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="f0697-104">I collegamenti di riferimento all'API in questo articolo portano a MSDN.</span><span class="sxs-lookup"><span data-stu-id="f0697-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="f0697-105">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="f0697-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="f0697-106">Il `string` tipo rappresenta un testo non modificabile sotto forma di sequenza di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="f0697-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="f0697-107">`string` è un alias per `System.String` in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f0697-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0697-108">Note</span><span class="sxs-lookup"><span data-stu-id="f0697-108">Remarks</span></span>

<span data-ttu-id="f0697-109">I valori letterali stringa sono delimitati dal carattere virgolette (").</span><span class="sxs-lookup"><span data-stu-id="f0697-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="f0697-110">Il carattere barra rovesciata ( \\ ) viene usato per codificare alcuni caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="f0697-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="f0697-111">La barra rovesciata e il carattere successivo insieme sono noti come *sequenza di escape*.</span><span class="sxs-lookup"><span data-stu-id="f0697-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="f0697-112">Le sequenze di escape supportate F# nei valori letterali stringa sono illustrate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f0697-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="f0697-113">Carattere</span><span class="sxs-lookup"><span data-stu-id="f0697-113">Character</span></span>|<span data-ttu-id="f0697-114">Sequenza di escape</span><span class="sxs-lookup"><span data-stu-id="f0697-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="f0697-115">Avviso</span><span class="sxs-lookup"><span data-stu-id="f0697-115">Alert</span></span>|`\a`|
|<span data-ttu-id="f0697-116">Backspace</span><span class="sxs-lookup"><span data-stu-id="f0697-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="f0697-117">Avanzamento carta</span><span class="sxs-lookup"><span data-stu-id="f0697-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="f0697-118">Nuova riga</span><span class="sxs-lookup"><span data-stu-id="f0697-118">Newline</span></span>|`\n`|
|<span data-ttu-id="f0697-119">Ritorno a capo</span><span class="sxs-lookup"><span data-stu-id="f0697-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="f0697-120">Scheda</span><span class="sxs-lookup"><span data-stu-id="f0697-120">Tab</span></span>|`\t`|
|<span data-ttu-id="f0697-121">Tabulazione verticale</span><span class="sxs-lookup"><span data-stu-id="f0697-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="f0697-122">Barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="f0697-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="f0697-123">Virgolette</span><span class="sxs-lookup"><span data-stu-id="f0697-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="f0697-124">Apostrofo</span><span class="sxs-lookup"><span data-stu-id="f0697-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="f0697-125">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="f0697-125">Unicode character</span></span>|<span data-ttu-id="f0697-126">`\DDD`(dove `D` indica una cifra decimale, ovvero un intervallo di 000-255 `\231` , ad esempio = "ç")</span><span class="sxs-lookup"><span data-stu-id="f0697-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="f0697-127">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="f0697-127">Unicode character</span></span>|<span data-ttu-id="f0697-128">`\xHH`(dove `H` indica una cifra esadecimale, ovvero un intervallo di 00-FF, `\xE7` ad esempio = "ç")</span><span class="sxs-lookup"><span data-stu-id="f0697-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="f0697-129">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="f0697-129">Unicode character</span></span>|<span data-ttu-id="f0697-130">`\uHHHH`(UTF-16) (dove `H` indica una cifra esadecimale, ovvero un intervallo di 0000-ffff;  ad esempio, `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="f0697-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="f0697-131">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="f0697-131">Unicode character</span></span>|<span data-ttu-id="f0697-132">`\U00HHHHHH`(UTF-32) (dove `H` indica una cifra esadecimale, ovvero un intervallo di 000000-10FFFF;  ad esempio, `\U0001F47D` = "👽")</span><span class="sxs-lookup"><span data-stu-id="f0697-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="f0697-133">La `\DDD` sequenza di escape è la notazione decimale, non la notazione ottale come nella maggior parte degli altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="f0697-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="f0697-134">Pertanto, le `8` cifre `9` e sono valide e una sequenza di `\032` rappresenta uno spazio (U + 0020), mentre lo stesso punto di codice nella notazione ottale `\040`sarà.</span><span class="sxs-lookup"><span data-stu-id="f0697-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="f0697-135">Essendo vincolato a un intervallo di 0-255 (0xFF), le `\DDD` sequenze di escape e `\x` sono in effetti il set di caratteri [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) , perché corrisponde ai primi 256 punti di codice Unicode.</span><span class="sxs-lookup"><span data-stu-id="f0697-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

<span data-ttu-id="f0697-136">Se preceduto dal simbolo @, il valore letterale è una stringa Verbatim.</span><span class="sxs-lookup"><span data-stu-id="f0697-136">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="f0697-137">Ciò significa che tutte le sequenze di escape vengono ignorate, ad eccezione del fatto che due caratteri di virgolette sono interpretati come un carattere di virgolette.</span><span class="sxs-lookup"><span data-stu-id="f0697-137">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="f0697-138">Inoltre, una stringa può essere racchiusa tra virgolette triple.</span><span class="sxs-lookup"><span data-stu-id="f0697-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="f0697-139">In questo caso, tutte le sequenze di escape vengono ignorate, incluse le virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="f0697-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="f0697-140">Per specificare una stringa che contiene una stringa racchiusa tra virgolette, è possibile usare una stringa Verbatim o una stringa racchiusa tra virgolette triple.</span><span class="sxs-lookup"><span data-stu-id="f0697-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="f0697-141">Se si utilizza una stringa Verbatim, è necessario specificare due virgolette per indicare un carattere virgoletta singola.</span><span class="sxs-lookup"><span data-stu-id="f0697-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="f0697-142">Se si usa una stringa racchiusa tra virgolette triple, è possibile usare i caratteri delle virgolette singole senza che vengano analizzati come estremità della stringa.</span><span class="sxs-lookup"><span data-stu-id="f0697-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="f0697-143">Questa tecnica può essere utile quando si lavora con XML o altre strutture che includono virgolette incorporate.</span><span class="sxs-lookup"><span data-stu-id="f0697-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="f0697-144">Nel codice sono accettate stringhe con interruzioni di riga e le interruzioni di riga vengono interpretate letteralmente come nuove righe, a meno che un carattere barra rovesciata non sia l'ultimo carattere prima dell'interruzione di riga.</span><span class="sxs-lookup"><span data-stu-id="f0697-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="f0697-145">Gli spazi vuoti iniziali nella riga successiva vengono ignorati quando si usa il carattere barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="f0697-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="f0697-146">Il codice seguente produce una stringa `str1` con un valore `"abc\ndef"` e una stringa `str2` con valore `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="f0697-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="f0697-147">È possibile accedere ai singoli caratteri di una stringa usando la sintassi di tipo matrice, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f0697-147">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="f0697-148">L'output è `b`.</span><span class="sxs-lookup"><span data-stu-id="f0697-148">The output is `b`.</span></span>

<span data-ttu-id="f0697-149">In alternativa, è possibile estrarre le sottostringhe usando la sintassi della sezione della matrice, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f0697-149">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="f0697-150">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f0697-150">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="f0697-151">È possibile rappresentare stringhe ASCII in base a matrici di byte senza segno, digitare `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="f0697-151">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="f0697-152">Il suffisso `B` viene aggiunto a un valore letterale stringa per indicare che si tratta di una stringa ASCII.</span><span class="sxs-lookup"><span data-stu-id="f0697-152">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="f0697-153">I valori letterali stringa ASCII utilizzati con matrici di byte supportano le stesse sequenze di escape delle stringhe Unicode, ad eccezione delle sequenze di escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="f0697-153">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="f0697-154">Operatori di stringa</span><span class="sxs-lookup"><span data-stu-id="f0697-154">String Operators</span></span>

<span data-ttu-id="f0697-155">Esistono due modi per concatenare le stringhe: usando l' `+` operatore o l' `^` operatore.</span><span class="sxs-lookup"><span data-stu-id="f0697-155">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="f0697-156">L' `+` operatore mantiene la compatibilità con le funzionalità di gestione delle stringhe .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f0697-156">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="f0697-157">Nell'esempio seguente viene illustrata la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="f0697-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="f0697-158">Classe String</span><span class="sxs-lookup"><span data-stu-id="f0697-158">String Class</span></span>

<span data-ttu-id="f0697-159">Poiché il tipo di stringa F# in è effettivamente un `System.String` `System.String` tipo .NET Framework, sono disponibili tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="f0697-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="f0697-160">È incluso l' `+` operatore, usato per concatenare le stringhe, la `Length` proprietà e la `Chars` proprietà, che restituisce la stringa come matrice di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="f0697-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="f0697-161">Per ulteriori informazioni sulle stringhe, vedere `System.String`.</span><span class="sxs-lookup"><span data-stu-id="f0697-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="f0697-162">Utilizzando la `Chars` proprietà di `System.String`è possibile accedere ai singoli caratteri di una stringa specificando un indice, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f0697-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="f0697-163">Modulo stringa</span><span class="sxs-lookup"><span data-stu-id="f0697-163">String Module</span></span>

<span data-ttu-id="f0697-164">Funzionalità aggiuntive per la gestione delle stringhe sono incluse `String` nel modulo `FSharp.Core` nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f0697-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="f0697-165">Per altre informazioni, vedere [modulo core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="f0697-165">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0697-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0697-166">See also</span></span>

- [<span data-ttu-id="f0697-167">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="f0697-167">F# Language Reference</span></span>](index.md)
