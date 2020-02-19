---
title: Stringhe
description: Informazioni sul modo F# in cui il tipo ' String ' rappresenta il testo non modificabile come sequenza di caratteri Unicode.
ms.date: 07/05/2019
ms.openlocfilehash: 002de464d09a49b6161608db6e46c619369f5ceb
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452818"
---
# <a name="strings"></a><span data-ttu-id="2a7a5-103">Stringhe</span><span class="sxs-lookup"><span data-stu-id="2a7a5-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="2a7a5-104">I collegamenti di riferimento all'API in questo articolo portano a MSDN.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="2a7a5-105">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="2a7a5-106">Il tipo di `string` rappresenta il testo non modificabile sotto forma di sequenza di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="2a7a5-107">`string` è un alias per `System.String` in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a7a5-108">Note</span><span class="sxs-lookup"><span data-stu-id="2a7a5-108">Remarks</span></span>

<span data-ttu-id="2a7a5-109">I valori letterali stringa sono delimitati dal carattere virgolette (").</span><span class="sxs-lookup"><span data-stu-id="2a7a5-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="2a7a5-110">Il carattere barra rovesciata (\\) viene usato per codificare alcuni caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="2a7a5-111">La barra rovesciata e il carattere successivo insieme sono noti come *sequenza di escape*.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="2a7a5-112">Le sequenze di escape supportate F# nei valori letterali stringa sono illustrate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="2a7a5-113">Carattere</span><span class="sxs-lookup"><span data-stu-id="2a7a5-113">Character</span></span>|<span data-ttu-id="2a7a5-114">Sequenza di escape</span><span class="sxs-lookup"><span data-stu-id="2a7a5-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="2a7a5-115">Avviso</span><span class="sxs-lookup"><span data-stu-id="2a7a5-115">Alert</span></span>|`\a`|
|<span data-ttu-id="2a7a5-116">Backspace</span><span class="sxs-lookup"><span data-stu-id="2a7a5-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="2a7a5-117">Avanzamento carta</span><span class="sxs-lookup"><span data-stu-id="2a7a5-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="2a7a5-118">Nuova riga</span><span class="sxs-lookup"><span data-stu-id="2a7a5-118">Newline</span></span>|`\n`|
|<span data-ttu-id="2a7a5-119">Ritorno a capo</span><span class="sxs-lookup"><span data-stu-id="2a7a5-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="2a7a5-120">Scheda</span><span class="sxs-lookup"><span data-stu-id="2a7a5-120">Tab</span></span>|`\t`|
|<span data-ttu-id="2a7a5-121">Tabulazione verticale</span><span class="sxs-lookup"><span data-stu-id="2a7a5-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="2a7a5-122">Barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="2a7a5-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="2a7a5-123">Virgoletta</span><span class="sxs-lookup"><span data-stu-id="2a7a5-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="2a7a5-124">Apostrofo</span><span class="sxs-lookup"><span data-stu-id="2a7a5-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="2a7a5-125">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="2a7a5-125">Unicode character</span></span>|<span data-ttu-id="2a7a5-126">`\DDD` (dove `D` indica una cifra decimale, ovvero un intervallo di 000-255, ad esempio `\231` = "ç")</span><span class="sxs-lookup"><span data-stu-id="2a7a5-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="2a7a5-127">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="2a7a5-127">Unicode character</span></span>|<span data-ttu-id="2a7a5-128">`\xHH` (dove `H` indica una cifra esadecimale, ovvero un intervallo di 00-FF, ad esempio `\xE7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="2a7a5-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="2a7a5-129">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="2a7a5-129">Unicode character</span></span>|<span data-ttu-id="2a7a5-130">`\uHHHH` (UTF-16) (dove `H` indica una cifra esadecimale, ovvero un intervallo di 0000-FFFF;  ad esempio, `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="2a7a5-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="2a7a5-131">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="2a7a5-131">Unicode character</span></span>|<span data-ttu-id="2a7a5-132">`\U00HHHHHH` (UTF-32) (dove `H` indica una cifra esadecimale, ovvero un intervallo di 000000-10FFFF;  ad esempio, `\U0001F47D` = "👽")</span><span class="sxs-lookup"><span data-stu-id="2a7a5-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="2a7a5-133">La sequenza di escape `\DDD` è la notazione decimale, non la notazione ottale come nella maggior parte degli altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="2a7a5-134">Pertanto, le cifre `8` e `9` sono valide e una sequenza di `\032` rappresenta uno spazio (U + 0020), mentre lo stesso punto di codice nella notazione ottale verrebbe `\040`.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="2a7a5-135">Essendo vincolato a un intervallo di 0-255 (0xFF), le sequenze di escape `\DDD` e `\x` sono in effetti il set di caratteri [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) , dal momento che corrisponde ai primi 256 punti di codice Unicode.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="2a7a5-136">Stringhe verbatim</span><span class="sxs-lookup"><span data-stu-id="2a7a5-136">Verbatim Strings</span></span>

<span data-ttu-id="2a7a5-137">Se preceduto dal simbolo @, il valore letterale è una stringa Verbatim.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="2a7a5-138">Ciò significa che tutte le sequenze di escape vengono ignorate, ad eccezione del fatto che due caratteri di virgolette sono interpretati come un carattere di virgolette.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="2a7a5-139">Stringhe tra virgolette triple</span><span class="sxs-lookup"><span data-stu-id="2a7a5-139">Triple Quoted Strings</span></span>

<span data-ttu-id="2a7a5-140">Inoltre, una stringa può essere racchiusa tra virgolette triple.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="2a7a5-141">In questo caso, tutte le sequenze di escape vengono ignorate, incluse le virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="2a7a5-142">Per specificare una stringa che contiene una stringa racchiusa tra virgolette, è possibile usare una stringa Verbatim o una stringa racchiusa tra virgolette triple.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="2a7a5-143">Se si utilizza una stringa Verbatim, è necessario specificare due virgolette per indicare un carattere virgoletta singola.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="2a7a5-144">Se si usa una stringa racchiusa tra virgolette triple, è possibile usare i caratteri delle virgolette singole senza che vengano analizzati come estremità della stringa.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="2a7a5-145">Questa tecnica può essere utile quando si lavora con XML o altre strutture che includono virgolette incorporate.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="2a7a5-146">Nel codice sono accettate stringhe con interruzioni di riga e le interruzioni di riga vengono interpretate letteralmente come nuove righe, a meno che un carattere barra rovesciata non sia l'ultimo carattere prima dell'interruzione di riga.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="2a7a5-147">Gli spazi vuoti iniziali nella riga successiva vengono ignorati quando si usa il carattere barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="2a7a5-148">Il codice seguente produce un `str1` di stringa con valore `"abc\ndef"` e una stringa `str2` con valore `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="2a7a5-149">Indicizzazione e sezionamento di stringhe</span><span class="sxs-lookup"><span data-stu-id="2a7a5-149">String Indexing and Slicing</span></span>

<span data-ttu-id="2a7a5-150">È possibile accedere ai singoli caratteri di una stringa usando la sintassi di tipo matrice, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="2a7a5-151">L'output è `b`.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-151">The output is `b`.</span></span>

<span data-ttu-id="2a7a5-152">In alternativa, è possibile estrarre le sottostringhe usando la sintassi della sezione della matrice, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="2a7a5-153">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="2a7a5-154">È possibile rappresentare stringhe ASCII in base a matrici di byte senza segno, digitare `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="2a7a5-155">Aggiungere il suffisso `B` a un valore letterale stringa per indicare che si tratta di una stringa ASCII.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="2a7a5-156">I valori letterali stringa ASCII utilizzati con matrici di byte supportano le stesse sequenze di escape delle stringhe Unicode, ad eccezione delle sequenze di escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="2a7a5-157">Operatori di stringa</span><span class="sxs-lookup"><span data-stu-id="2a7a5-157">String Operators</span></span>

<span data-ttu-id="2a7a5-158">Esistono due modi per concatenare le stringhe: usando l'operatore `+` o l'operatore `^`.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-158">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="2a7a5-159">L'operatore `+` mantiene la compatibilità con le funzionalità di gestione delle stringhe .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-159">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="2a7a5-160">Nell'esempio seguente viene illustrata la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-160">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="2a7a5-161">Classe String</span><span class="sxs-lookup"><span data-stu-id="2a7a5-161">String Class</span></span>

<span data-ttu-id="2a7a5-162">Poiché il tipo di stringa F# in è in realtà un .NET Framework tipo di `System.String`, sono disponibili tutti i membri di `System.String`.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-162">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="2a7a5-163">Questo include l'operatore `+`, che viene usato per concatenare le stringhe, la proprietà `Length` e la proprietà `Chars`, che restituisce la stringa come matrice di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-163">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="2a7a5-164">Per ulteriori informazioni sulle stringhe, vedere `System.String`.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-164">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="2a7a5-165">Utilizzando la proprietà `Chars` di `System.String`, è possibile accedere ai singoli caratteri di una stringa specificando un indice, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-165">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="2a7a5-166">Modulo stringa</span><span class="sxs-lookup"><span data-stu-id="2a7a5-166">String Module</span></span>

<span data-ttu-id="2a7a5-167">Funzionalità aggiuntive per la gestione delle stringhe sono incluse nel modulo `String` nello spazio dei nomi `FSharp.Core`.</span><span class="sxs-lookup"><span data-stu-id="2a7a5-167">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="2a7a5-168">Per altre informazioni, vedere [modulo core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="2a7a5-168">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="2a7a5-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a7a5-169">See also</span></span>

- [<span data-ttu-id="2a7a5-170">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="2a7a5-170">F# Language Reference</span></span>](index.md)
