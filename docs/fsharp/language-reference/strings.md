---
title: Stringhe
description: Informazioni su come il tipo 'string' di F' rappresenta il testo non modificabile come una sequenza di caratteri Unicode.
ms.date: 07/05/2019
ms.openlocfilehash: 242a2cefa1cce8995090dddd1d1fd7181e0f5e0c
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739566"
---
# <a name="strings"></a><span data-ttu-id="a432f-103">Stringhe</span><span class="sxs-lookup"><span data-stu-id="a432f-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="a432f-104">I collegamenti di riferimento all'API in questo articolo portano a MSDN.</span><span class="sxs-lookup"><span data-stu-id="a432f-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="a432f-105">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="a432f-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="a432f-106">Il `string` tipo rappresenta il testo non modificabile come una sequenza di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="a432f-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="a432f-107">`string` è un alias per `System.String` in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a432f-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="a432f-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a432f-108">Remarks</span></span>

<span data-ttu-id="a432f-109">I valori letterali stringa sono delimitati dal carattere virgolette (").</span><span class="sxs-lookup"><span data-stu-id="a432f-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="a432f-110">Il carattere \\ barra rovesciata ( ) viene utilizzato per codificare determinati caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="a432f-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="a432f-111">La barra rovesciata e il carattere successivo insieme sono noti come sequenza di *escape.*</span><span class="sxs-lookup"><span data-stu-id="a432f-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="a432f-112">Le sequenze di escape supportate nei valori letterali stringa F sono illustrate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a432f-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="a432f-113">Carattere</span><span class="sxs-lookup"><span data-stu-id="a432f-113">Character</span></span>|<span data-ttu-id="a432f-114">Sequenza di escape</span><span class="sxs-lookup"><span data-stu-id="a432f-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="a432f-115">Avviso</span><span class="sxs-lookup"><span data-stu-id="a432f-115">Alert</span></span>|`\a`|
|<span data-ttu-id="a432f-116">Backspace</span><span class="sxs-lookup"><span data-stu-id="a432f-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="a432f-117">Avanzamento carta</span><span class="sxs-lookup"><span data-stu-id="a432f-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="a432f-118">Nuova riga</span><span class="sxs-lookup"><span data-stu-id="a432f-118">Newline</span></span>|`\n`|
|<span data-ttu-id="a432f-119">Ritorno a capo</span><span class="sxs-lookup"><span data-stu-id="a432f-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="a432f-120">Scheda</span><span class="sxs-lookup"><span data-stu-id="a432f-120">Tab</span></span>|`\t`|
|<span data-ttu-id="a432f-121">Tabulazione verticale</span><span class="sxs-lookup"><span data-stu-id="a432f-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="a432f-122">Barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="a432f-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="a432f-123">Virgoletta</span><span class="sxs-lookup"><span data-stu-id="a432f-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="a432f-124">Apostrofo</span><span class="sxs-lookup"><span data-stu-id="a432f-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="a432f-125">carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="a432f-125">Unicode character</span></span>|<span data-ttu-id="a432f-126">`\DDD`(dove `D` indica una cifra decimale; intervallo di 000 `\231` - 255; ad esempio,</span><span class="sxs-lookup"><span data-stu-id="a432f-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="a432f-127">carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="a432f-127">Unicode character</span></span>|<span data-ttu-id="a432f-128">`\xHH`(dove `H` indica una cifra esadecimale; intervallo di 00 `\xE7` - FF; ad esempio,</span><span class="sxs-lookup"><span data-stu-id="a432f-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="a432f-129">carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="a432f-129">Unicode character</span></span>|<span data-ttu-id="a432f-130">`\uHHHH`(UTF-16) (dove `H` indica una cifra esadecimale; intervallo di 0000 - FFFF;  ad esempio, `\u00E7` "z")</span><span class="sxs-lookup"><span data-stu-id="a432f-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="a432f-131">carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="a432f-131">Unicode character</span></span>|<span data-ttu-id="a432f-132">`\U00HHHHHH`(UTF-32) (dove `H` indica una cifra esadecimale; intervallo di 000000 - 10FFFF;  ad esempio, `\U0001F47D` 👽" ")</span><span class="sxs-lookup"><span data-stu-id="a432f-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="a432f-133">La `\DDD` sequenza di escape è la notazione decimale, non la notazione ottale come nella maggior parte delle altre lingue.</span><span class="sxs-lookup"><span data-stu-id="a432f-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="a432f-134">Di conseguenza, le `8` cifre e `9` sono valide e una sequenza di `\032` rappresenta uno spazio (U-0020), mentre lo stesso punto di codice in notazione ottale sarebbe `\040`.</span><span class="sxs-lookup"><span data-stu-id="a432f-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="a432f-135">Essendo vincolato a un intervallo compreso tra `\DDD` 0 `\x` e 255 (0xFF), le sequenze di escape e sono effettivamente il set di caratteri [ISO-8859-1,](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) poiché corrisponde ai primi 256 punti di codice Unicode.</span><span class="sxs-lookup"><span data-stu-id="a432f-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="a432f-136">Stringhe Verbatim</span><span class="sxs-lookup"><span data-stu-id="a432f-136">Verbatim Strings</span></span>

<span data-ttu-id="a432f-137">Se preceduto dal simbolo , il valore letterale è una stringa verbatim.</span><span class="sxs-lookup"><span data-stu-id="a432f-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="a432f-138">Ciò significa che tutte le sequenze di escape vengono ignorate, ad eccezione del fatto che due caratteri di virgolette vengono interpretati come un carattere di virgoletta.</span><span class="sxs-lookup"><span data-stu-id="a432f-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="a432f-139">Stringhe triple quotate</span><span class="sxs-lookup"><span data-stu-id="a432f-139">Triple Quoted Strings</span></span>

<span data-ttu-id="a432f-140">Inoltre, una stringa può essere racchiusa tra virgolette triple.</span><span class="sxs-lookup"><span data-stu-id="a432f-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="a432f-141">In questo caso, tutte le sequenze di escape vengono ignorate, inclusi i caratteri virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="a432f-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="a432f-142">Per specificare una stringa che contiene una stringa tra virgolette incorporata, è possibile utilizzare una stringa verbatim o una stringa tra virgolette triple.</span><span class="sxs-lookup"><span data-stu-id="a432f-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="a432f-143">Se si utilizza una stringa verbatim, è necessario specificare due caratteri di virgolette per indicare un carattere di virgoletta singola.</span><span class="sxs-lookup"><span data-stu-id="a432f-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="a432f-144">Se si utilizza una stringa tra virgolette triple, è possibile utilizzare i caratteri virgolette singole senza che vengano analizzati come fine della stringa.</span><span class="sxs-lookup"><span data-stu-id="a432f-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="a432f-145">Questa tecnica può essere utile quando si lavora con XML o altre strutture che includono virgolette incorporate.</span><span class="sxs-lookup"><span data-stu-id="a432f-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="a432f-146">Nel codice, le stringhe con interruzioni di riga vengono accettate e le interruzioni di riga vengono interpretate letteralmente come nuove righe, a meno che un carattere barra rovesciata non sia l'ultimo carattere prima dell'interruzione di riga.</span><span class="sxs-lookup"><span data-stu-id="a432f-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="a432f-147">Lo spazio vuoto iniziale nella riga successiva viene ignorato quando viene utilizzato il carattere barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="a432f-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="a432f-148">Il codice seguente `str1` produce una `"abc\ndef"` stringa `str2` con valore `"abcdef"`e una stringa con valore .</span><span class="sxs-lookup"><span data-stu-id="a432f-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="a432f-149">Indicizzazione e sezionamento delle stringheString Indexing and Slicing</span><span class="sxs-lookup"><span data-stu-id="a432f-149">String Indexing and Slicing</span></span>

<span data-ttu-id="a432f-150">È possibile accedere ai singoli caratteri in una stringa utilizzando una sintassi di tipo matrice, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a432f-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="a432f-151">L'output è `b`.</span><span class="sxs-lookup"><span data-stu-id="a432f-151">The output is `b`.</span></span>

<span data-ttu-id="a432f-152">In alternativa, è possibile estrarre le sottostringhe usando la sintassi della sezione di matrice, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a432f-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="a432f-153">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a432f-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="a432f-154">È possibile rappresentare stringhe ASCII in base `byte[]`a matrici di byte senza segno, digitare .</span><span class="sxs-lookup"><span data-stu-id="a432f-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="a432f-155">Aggiungere il `B` suffisso a un valore letterale stringa per indicare che si tratta di una stringa ASCII.</span><span class="sxs-lookup"><span data-stu-id="a432f-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="a432f-156">I valori letterali stringa ASCII utilizzati con le matrici di byte supportano le stesse sequenze di escape delle stringhe Unicode, ad eccezione delle sequenze di escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="a432f-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="a432f-157">Operatori stringa</span><span class="sxs-lookup"><span data-stu-id="a432f-157">String Operators</span></span>

<span data-ttu-id="a432f-158">L'operatore `+` può essere utilizzato per concatenare stringhe, mantenendo la compatibilità con le funzionalità di gestione delle stringhe di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a432f-158">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="a432f-159">Nell'esempio seguente viene illustrata la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="a432f-159">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="a432f-160">Classe String</span><span class="sxs-lookup"><span data-stu-id="a432f-160">String Class</span></span>

<span data-ttu-id="a432f-161">Poiché il tipo di stringa in `System.String` F è `System.String` in realtà un tipo .NET Framework, tutti i membri sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="a432f-161">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="a432f-162">Ciò `+` include l'operatore , che viene `Length` utilizzato per `Chars` concatenare le stringhe, la proprietà e la proprietà , che restituisce la stringa come matrice di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="a432f-162">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="a432f-163">Per ulteriori informazioni sulle `System.String`stringhe, vedere .</span><span class="sxs-lookup"><span data-stu-id="a432f-163">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="a432f-164">Utilizzando la `Chars` proprietà `System.String`di , è possibile accedere ai singoli caratteri di una stringa specificando un indice, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a432f-164">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="a432f-165">Modulo stringa</span><span class="sxs-lookup"><span data-stu-id="a432f-165">String Module</span></span>

<span data-ttu-id="a432f-166">Funzionalità aggiuntive per la gestione `String` delle `FSharp.Core` stringhe è inclusa nel modulo nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a432f-166">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="a432f-167">Per ulteriori informazioni, vedere [Modulo Core.String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="a432f-167">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="a432f-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a432f-168">See also</span></span>

- [<span data-ttu-id="a432f-169">Guida di riferimento al linguaggio F</span><span class="sxs-lookup"><span data-stu-id="a432f-169">F# Language Reference</span></span>](index.md)
