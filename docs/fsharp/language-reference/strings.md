---
title: Stringhe
description: Informazioni su come il F# di tipo 'stringa' rappresenta il testo non modificabile come sequenza di caratteri Unicode.
ms.date: 07/05/2019
ms.openlocfilehash: ec895723cc6d21a701a27b5d70d053bb681ce2b3
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "67660604"
---
# <a name="strings"></a><span data-ttu-id="87307-103">Stringhe</span><span class="sxs-lookup"><span data-stu-id="87307-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="87307-104">I collegamenti di riferimento all'API in questo articolo portano a MSDN.</span><span class="sxs-lookup"><span data-stu-id="87307-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="87307-105">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="87307-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="87307-106">Il `string` tipo rappresenta il testo non modificabile come sequenza di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="87307-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="87307-107">`string` è un alias per `System.String` in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="87307-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="87307-108">Note</span><span class="sxs-lookup"><span data-stu-id="87307-108">Remarks</span></span>

<span data-ttu-id="87307-109">Valori letterali stringa sono delimitati dal carattere di virgolette doppie (").</span><span class="sxs-lookup"><span data-stu-id="87307-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="87307-110">Il carattere barra rovesciata ( \\ ) viene usato per codificare alcuni caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="87307-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="87307-111">La barra rovesciata e il carattere successivo insieme sono note come un *sequenza di escape*.</span><span class="sxs-lookup"><span data-stu-id="87307-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="87307-112">Supportato in sequenze di escape F# valori letterali stringa vengono visualizzati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="87307-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="87307-113">Carattere</span><span class="sxs-lookup"><span data-stu-id="87307-113">Character</span></span>|<span data-ttu-id="87307-114">Sequenza di escape</span><span class="sxs-lookup"><span data-stu-id="87307-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="87307-115">Avviso</span><span class="sxs-lookup"><span data-stu-id="87307-115">Alert</span></span>|`\a`|
|<span data-ttu-id="87307-116">Backspace</span><span class="sxs-lookup"><span data-stu-id="87307-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="87307-117">Avanzamento carta</span><span class="sxs-lookup"><span data-stu-id="87307-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="87307-118">Nuova riga</span><span class="sxs-lookup"><span data-stu-id="87307-118">Newline</span></span>|`\n`|
|<span data-ttu-id="87307-119">Ritorno a capo</span><span class="sxs-lookup"><span data-stu-id="87307-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="87307-120">Scheda</span><span class="sxs-lookup"><span data-stu-id="87307-120">Tab</span></span>|`\t`|
|<span data-ttu-id="87307-121">Tabulazione verticale</span><span class="sxs-lookup"><span data-stu-id="87307-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="87307-122">Barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="87307-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="87307-123">Virgoletta</span><span class="sxs-lookup"><span data-stu-id="87307-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="87307-124">Apostrofo</span><span class="sxs-lookup"><span data-stu-id="87307-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="87307-125">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="87307-125">Unicode character</span></span>|<span data-ttu-id="87307-126">`\DDD` (dove `D` indica un valore decimal digit; intervallo di 000 - 255, ad esempio `\231` = "ç")</span><span class="sxs-lookup"><span data-stu-id="87307-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="87307-127">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="87307-127">Unicode character</span></span>|<span data-ttu-id="87307-128">`\xHH` (dove `H` indica una cifra esadecimale; intervallo 00 - FF; ad esempio, `\xE7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="87307-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="87307-129">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="87307-129">Unicode character</span></span>|<span data-ttu-id="87307-130">`\uHHHH` (UTF-16) (in cui `H` indica una cifra esadecimale; intervallo di 0000 - FFFF.  ad esempio, `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="87307-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="87307-131">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="87307-131">Unicode character</span></span>|<span data-ttu-id="87307-132">`\U00HHHHHH` (UTF-32) (in cui `H` indica una cifra esadecimale; intervallo di 000000 - 10FFFF;  ad esempio, `\U0001F47D` = "👽")</span><span class="sxs-lookup"><span data-stu-id="87307-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="87307-133">Il `\DDD` sequenza di escape è la notazione decimale, notazione non ottale, ad esempio la maggior parte degli altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="87307-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="87307-134">Pertanto, cifre `8` e `9` siano valide e una sequenza di `\032` rappresenta uno spazio (u+0020), mentre tale stesso punto di codice in notazione ottale sarebbe `\040`.</span><span class="sxs-lookup"><span data-stu-id="87307-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="87307-135">Che è vincolato a un intervallo pari a 0 - 255 (0xFF), il `\DDD` e `\x` sequenze di escape sono effettivamente il [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) set di caratteri e poiché i primi 256 punti di codice Unicode corrispondente.</span><span class="sxs-lookup"><span data-stu-id="87307-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

<span data-ttu-id="87307-136">Se è preceduto dal simbolo @, il valore letterale è una stringa verbatim.</span><span class="sxs-lookup"><span data-stu-id="87307-136">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="87307-137">Ciò significa che tutte le sequenze di escape vengono ignorate, ad eccezione del fatto che i due caratteri segno di virgolette doppie vengono interpretate come carattere un segno di virgolette.</span><span class="sxs-lookup"><span data-stu-id="87307-137">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="87307-138">Inoltre, una stringa può essere racchiusi tra virgolette triple.</span><span class="sxs-lookup"><span data-stu-id="87307-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="87307-139">In questo caso, vengono ignorate tutte le sequenze di escape, inclusi i caratteri di virgoletta doppia.</span><span class="sxs-lookup"><span data-stu-id="87307-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="87307-140">Per specificare una stringa che contiene un embedded stringa tra virgolette, è possibile utilizzare una stringa verbatim o una stringa racchiusa tra virgolette triple.</span><span class="sxs-lookup"><span data-stu-id="87307-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="87307-141">Se si usa una stringa verbatim, è necessario specificare due caratteri segno di virgolette per indicare un carattere di virgoletta singola.</span><span class="sxs-lookup"><span data-stu-id="87307-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="87307-142">Se si usa una stringa racchiusa tra virgolette triple, è possibile utilizzare i caratteri di virgoletta singola senza di essi in fase di analisi come la fine della stringa.</span><span class="sxs-lookup"><span data-stu-id="87307-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="87307-143">Questa tecnica può essere utile quando si lavora con XML o altre strutture contenenti virgolette incorporate.</span><span class="sxs-lookup"><span data-stu-id="87307-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="87307-144">Nel codice, vengono accettate le stringhe con interruzioni di riga e le interruzioni di riga vengono interpretate letteralmente come caratteri di nuova riga, a meno che un carattere di barra rovesciata è l'ultimo carattere prima dell'interruzione di riga.</span><span class="sxs-lookup"><span data-stu-id="87307-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="87307-145">Lo spazio vuoto iniziale nella riga successiva viene ignorato quando viene utilizzato il carattere barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="87307-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="87307-146">Il codice seguente produce una stringa `str1` con valore `"abc\ndef"` e una stringa `str2` con valore `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="87307-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="87307-147">È possibile accedere a singoli caratteri in una stringa usando la sintassi di tipo matrice, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="87307-147">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="87307-148">L'output è `b`.</span><span class="sxs-lookup"><span data-stu-id="87307-148">The output is `b`.</span></span>

<span data-ttu-id="87307-149">Oppure è possibile estrarre le sottostringhe utilizzando la sintassi di sezione di matrice, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="87307-149">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="87307-150">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="87307-150">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="87307-151">È possibile rappresentare le stringhe ASCII da matrici di byte senza segno, tipo `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="87307-151">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="87307-152">Si aggiunge il suffisso `B` a una valore letterale stringa per indicare che si tratta di una stringa ASCII.</span><span class="sxs-lookup"><span data-stu-id="87307-152">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="87307-153">Valori letterali di stringa ASCII usati con le matrici di byte supportano le sequenze di escape stessa sotto forma di stringhe Unicode, fatta eccezione per le sequenze di escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="87307-153">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="87307-154">Operatori di stringa</span><span class="sxs-lookup"><span data-stu-id="87307-154">String Operators</span></span>

<span data-ttu-id="87307-155">Esistono due modi per concatenare le stringhe: usando il `+` operatore o utilizzando il `^` operatore.</span><span class="sxs-lookup"><span data-stu-id="87307-155">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="87307-156">Il `+` operatore mantiene la compatibilità con le funzionalità di gestione delle stringhe di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="87307-156">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="87307-157">L'esempio seguente illustra la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="87307-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="87307-158">Classe di stringa</span><span class="sxs-lookup"><span data-stu-id="87307-158">String Class</span></span>

<span data-ttu-id="87307-159">Dal momento che la stringa di tipo F# è effettivamente un Framework .NET `System.String` digitare, tutti i `System.String` membri sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="87307-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="87307-160">Ciò include la `+` operatore, che viene usato per concatenare le stringhe, il `Length` proprietà e il `Chars` proprietà, che restituisce la stringa come una matrice di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="87307-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="87307-161">Per altre informazioni sulle stringhe, vedere `System.String`.</span><span class="sxs-lookup"><span data-stu-id="87307-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="87307-162">Tramite il `Chars` proprietà di `System.String`, è possibile accedere ai singoli caratteri in una stringa specificando un indice, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="87307-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="87307-163">Modulo della stringa</span><span class="sxs-lookup"><span data-stu-id="87307-163">String Module</span></span>

<span data-ttu-id="87307-164">Funzionalità aggiuntive per la gestione delle stringhe è incluso nel `String` modulo nel `FSharp.Core` dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="87307-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="87307-165">Per altre informazioni, vedere [modulo Core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="87307-165">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="87307-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87307-166">See also</span></span>

- [<span data-ttu-id="87307-167">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="87307-167">F# Language Reference</span></span>](index.md)
