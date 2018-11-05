---
title: Stringhe (F#)
description: Informazioni su come il tipo 'string' F# rappresenta il testo non modificabile come una sequenza di caratteri Unicode.
ms.date: 05/16/2016
ms.openlocfilehash: 21971602093bc84b0df47d4ae46a14fb936c28bb
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43799343"
---
# <a name="strings"></a><span data-ttu-id="8a7e9-103">Stringhe</span><span class="sxs-lookup"><span data-stu-id="8a7e9-103">Strings</span></span>

> [!NOTE]
<span data-ttu-id="8a7e9-104">I collegamenti di riferimento all'API in questo articolo portano a MSDN.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="8a7e9-105">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="8a7e9-106">Il `string` tipo rappresenta il testo non modificabile come sequenza di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="8a7e9-107">`string` è un alias per `System.String` in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a7e9-108">Note</span><span class="sxs-lookup"><span data-stu-id="8a7e9-108">Remarks</span></span>

<span data-ttu-id="8a7e9-109">Valori letterali stringa sono delimitati dal carattere di virgolette doppie (").</span><span class="sxs-lookup"><span data-stu-id="8a7e9-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="8a7e9-110">Il carattere barra rovesciata ( \\ ) viene usato per codificare alcuni caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="8a7e9-111">La barra rovesciata e il carattere successivo insieme sono note come un *sequenza di escape*.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="8a7e9-112">Supportato in F# stringa nella tabella seguente vengono visualizzati i valori letterali di sequenze di escape.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="8a7e9-113">Carattere</span><span class="sxs-lookup"><span data-stu-id="8a7e9-113">Character</span></span>|<span data-ttu-id="8a7e9-114">Sequenza di escape</span><span class="sxs-lookup"><span data-stu-id="8a7e9-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="8a7e9-115">Backspace</span><span class="sxs-lookup"><span data-stu-id="8a7e9-115">Backspace</span></span>|`\b`|
|<span data-ttu-id="8a7e9-116">Nuova riga</span><span class="sxs-lookup"><span data-stu-id="8a7e9-116">Newline</span></span>|`\n`|
|<span data-ttu-id="8a7e9-117">Ritorno a capo</span><span class="sxs-lookup"><span data-stu-id="8a7e9-117">Carriage return</span></span>|`\r`|
|<span data-ttu-id="8a7e9-118">Scheda</span><span class="sxs-lookup"><span data-stu-id="8a7e9-118">Tab</span></span>|`\t`|
|<span data-ttu-id="8a7e9-119">Barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="8a7e9-119">Backslash</span></span>|`\\`|
|<span data-ttu-id="8a7e9-120">Virgoletta</span><span class="sxs-lookup"><span data-stu-id="8a7e9-120">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="8a7e9-121">Apostrofo</span><span class="sxs-lookup"><span data-stu-id="8a7e9-121">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="8a7e9-122">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="8a7e9-122">Unicode character</span></span>|<span data-ttu-id="8a7e9-123">`\uXXXX` oppure `\UXXXX` (dove `X` indica una cifra esadecimale)</span><span class="sxs-lookup"><span data-stu-id="8a7e9-123">`\uXXXX` or `\UXXXX` (where `X` indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="8a7e9-124">Se è preceduto dal simbolo @, il valore letterale è una stringa verbatim.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-124">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="8a7e9-125">Ciò significa che tutte le sequenze di escape vengono ignorate, ad eccezione del fatto che i due caratteri segno di virgolette doppie vengono interpretate come carattere un segno di virgolette.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-125">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="8a7e9-126">Inoltre, una stringa può essere racchiusi tra virgolette triple.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-126">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="8a7e9-127">In questo caso, vengono ignorate tutte le sequenze di escape, inclusi i caratteri di virgoletta doppia.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-127">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="8a7e9-128">Per specificare una stringa che contiene un embedded stringa tra virgolette, è possibile utilizzare una stringa verbatim o una stringa racchiusa tra virgolette triple.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-128">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="8a7e9-129">Se si usa una stringa verbatim, è necessario specificare due caratteri segno di virgolette per indicare un carattere di virgoletta singola.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-129">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="8a7e9-130">Se si usa una stringa racchiusa tra virgolette triple, è possibile utilizzare i caratteri di virgoletta singola senza di essi in fase di analisi come la fine della stringa.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-130">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="8a7e9-131">Questa tecnica può essere utile quando si lavora con XML o altre strutture contenenti virgolette incorporate.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-131">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="8a7e9-132">Nel codice, vengono accettate le stringhe con interruzioni di riga e le interruzioni di riga vengono interpretate letteralmente come caratteri di nuova riga, a meno che un carattere di barra rovesciata è l'ultimo carattere prima dell'interruzione di riga.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-132">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="8a7e9-133">Lo spazio vuoto iniziale nella riga successiva viene ignorato quando viene utilizzato il carattere barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-133">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="8a7e9-134">Il codice seguente produce una stringa `str1` con valore `"abc\ndef"` e una stringa `str2` con valore `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-134">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="8a7e9-135">È possibile accedere a singoli caratteri in una stringa usando la sintassi di tipo matrice, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-135">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="8a7e9-136">L'output è `b`.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-136">The output is `b`.</span></span>

<span data-ttu-id="8a7e9-137">Oppure è possibile estrarre le sottostringhe utilizzando la sintassi di sezione di matrice, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-137">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="8a7e9-138">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-138">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="8a7e9-139">È possibile rappresentare le stringhe ASCII da matrici di byte senza segno, tipo `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-139">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="8a7e9-140">Si aggiunge il suffisso `B` a una valore letterale stringa per indicare che si tratta di una stringa ASCII.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-140">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="8a7e9-141">Valori letterali di stringa ASCII usati con le matrici di byte supportano le sequenze di escape stessa sotto forma di stringhe Unicode, fatta eccezione per le sequenze di escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-141">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="8a7e9-142">Operatori di stringa</span><span class="sxs-lookup"><span data-stu-id="8a7e9-142">String Operators</span></span>

<span data-ttu-id="8a7e9-143">Esistono due modi per concatenare le stringhe: usando il `+` operatore o utilizzando il `^` operatore.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-143">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="8a7e9-144">Il `+` operatore mantiene la compatibilità con le funzionalità di gestione delle stringhe di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-144">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="8a7e9-145">L'esempio seguente illustra la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-145">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="8a7e9-146">Classe di stringa</span><span class="sxs-lookup"><span data-stu-id="8a7e9-146">String Class</span></span>

<span data-ttu-id="8a7e9-147">Poiché il tipo di stringa in F# è effettivamente un .NET Framework `System.String` digita, tutti i `System.String` membri sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-147">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="8a7e9-148">Ciò include la `+` operatore, che viene usato per concatenare le stringhe, il `Length` proprietà e il `Chars` proprietà, che restituisce la stringa come una matrice di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-148">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="8a7e9-149">Per altre informazioni sulle stringhe, vedere `System.String`.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-149">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="8a7e9-150">Tramite il `Chars` proprietà di `System.String`, è possibile accedere ai singoli caratteri in una stringa specificando un indice, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-150">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="8a7e9-151">Modulo della stringa</span><span class="sxs-lookup"><span data-stu-id="8a7e9-151">String Module</span></span>

<span data-ttu-id="8a7e9-152">Funzionalità aggiuntive per la gestione delle stringhe è incluso nel `String` modulo nel `FSharp.Core` dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8a7e9-152">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="8a7e9-153">Per altre informazioni, vedere [modulo Core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="8a7e9-153">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="8a7e9-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a7e9-154">See also</span></span>

- [<span data-ttu-id="8a7e9-155">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="8a7e9-155">F# Language Reference</span></span>](index.md)
