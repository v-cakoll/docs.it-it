---
title: Stringhe (F#)
description: "Informazioni su come il tipo 'string' F # rappresenta il testo non modificabile come una sequenza di caratteri Unicode."
ms.date: 05/16/2016
ms.openlocfilehash: bdd1d1a542e70bcd95fce51e75d0c1ddffceb008
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564859"
---
# <a name="strings"></a><span data-ttu-id="f09c5-103">Stringhe</span><span class="sxs-lookup"><span data-stu-id="f09c5-103">Strings</span></span>

> [!NOTE]
<span data-ttu-id="f09c5-104">I collegamenti di riferimento all'API in questo articolo portano a MSDN.</span><span class="sxs-lookup"><span data-stu-id="f09c5-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="f09c5-105">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="f09c5-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="f09c5-106">Il `string` tipo rappresenta il testo non modificabile come una sequenza di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="f09c5-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="f09c5-107">`string` è un alias per `System.String` in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f09c5-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="f09c5-108">Note</span><span class="sxs-lookup"><span data-stu-id="f09c5-108">Remarks</span></span>
<span data-ttu-id="f09c5-109">Valori letterali stringa sono delimitati dal carattere di virgolette doppie (").</span><span class="sxs-lookup"><span data-stu-id="f09c5-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="f09c5-110">Il carattere barra rovesciata (\) viene utilizzato per codificare alcuni caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="f09c5-110">The backslash character (\) is used to encode certain special characters.</span></span> <span data-ttu-id="f09c5-111">La barra rovesciata e il carattere successivo insieme sono note come un *sequenza di escape*.</span><span class="sxs-lookup"><span data-stu-id="f09c5-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="f09c5-112">Supportato in F # stringa i valori letterali vengono visualizzati nella tabella seguente sequenze di escape.</span><span class="sxs-lookup"><span data-stu-id="f09c5-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="f09c5-113">Carattere</span><span class="sxs-lookup"><span data-stu-id="f09c5-113">Character</span></span>|<span data-ttu-id="f09c5-114">Sequenza di escape</span><span class="sxs-lookup"><span data-stu-id="f09c5-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="f09c5-115">Backspace</span><span class="sxs-lookup"><span data-stu-id="f09c5-115">Backspace</span></span>|<span data-ttu-id="f09c5-116">\b</span><span class="sxs-lookup"><span data-stu-id="f09c5-116">\b</span></span>|
|<span data-ttu-id="f09c5-117">Nuova riga</span><span class="sxs-lookup"><span data-stu-id="f09c5-117">Newline</span></span>|<span data-ttu-id="f09c5-118">\n</span><span class="sxs-lookup"><span data-stu-id="f09c5-118">\n</span></span>|
|<span data-ttu-id="f09c5-119">Ritorno a capo</span><span class="sxs-lookup"><span data-stu-id="f09c5-119">Carriage return</span></span>|<span data-ttu-id="f09c5-120">\r</span><span class="sxs-lookup"><span data-stu-id="f09c5-120">\r</span></span>|
|<span data-ttu-id="f09c5-121">Scheda</span><span class="sxs-lookup"><span data-stu-id="f09c5-121">Tab</span></span>|<span data-ttu-id="f09c5-122">\t</span><span class="sxs-lookup"><span data-stu-id="f09c5-122">\t</span></span>|
|<span data-ttu-id="f09c5-123">Barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="f09c5-123">Backslash</span></span>|\\|
|<span data-ttu-id="f09c5-124">Virgolette</span><span class="sxs-lookup"><span data-stu-id="f09c5-124">Quotation mark</span></span>|\"|
|<span data-ttu-id="f09c5-125">Apostrofo</span><span class="sxs-lookup"><span data-stu-id="f09c5-125">Apostrophe</span></span>|\'|
|<span data-ttu-id="f09c5-126">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="f09c5-126">Unicode character</span></span>|<span data-ttu-id="f09c5-127">\u*XXXX* o \U*XXXXXXXX* (dove *X* indica una cifra esadecimale)</span><span class="sxs-lookup"><span data-stu-id="f09c5-127">\u*XXXX* or \U*XXXXXXXX* (where *X* indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="f09c5-128">Se è preceduto dal simbolo @, il valore letterale è una stringa verbatim.</span><span class="sxs-lookup"><span data-stu-id="f09c5-128">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="f09c5-129">Ciò significa che le sequenze di escape vengono ignorate, ad eccezione del fatto che i due caratteri segno di virgolette doppie vengono interpretate come carattere un segno di virgolette.</span><span class="sxs-lookup"><span data-stu-id="f09c5-129">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="f09c5-130">Inoltre, una stringa può essere racchiusi tra virgolette triple.</span><span class="sxs-lookup"><span data-stu-id="f09c5-130">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="f09c5-131">In questo caso, vengono ignorate tutte le sequenze di escape, inclusi i caratteri di virgoletta doppia.</span><span class="sxs-lookup"><span data-stu-id="f09c5-131">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="f09c5-132">Per specificare una stringa che contiene un elemento incorporato stringa tra virgolette, è possibile utilizzare una stringa lettera o una stringa tra virgolette triple.</span><span class="sxs-lookup"><span data-stu-id="f09c5-132">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="f09c5-133">Se si utilizza una stringa lettera, è necessario specificare due caratteri di virgoletta per indicare un carattere di virgoletta singola.</span><span class="sxs-lookup"><span data-stu-id="f09c5-133">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="f09c5-134">Se si utilizza una stringa con virgolette triple, è possibile utilizzare i caratteri di virgoletta singola senza di essi viene analizzato come la fine della stringa.</span><span class="sxs-lookup"><span data-stu-id="f09c5-134">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="f09c5-135">Questa tecnica può rivelarsi utile quando lavora con XML o altre strutture contenenti virgolette incorporate.</span><span class="sxs-lookup"><span data-stu-id="f09c5-135">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="f09c5-136">Nel codice vengono accettate le stringhe che presentano le interruzioni di riga e le interruzioni di riga vengono interpretate letteralmente come caratteri di nuova riga, a meno che un carattere barra rovesciata è l'ultimo carattere prima dell'interruzione di riga.</span><span class="sxs-lookup"><span data-stu-id="f09c5-136">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="f09c5-137">Gli spazi iniziali nella riga successiva viene ignorato quando viene utilizzato il carattere barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="f09c5-137">Leading whitespace on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="f09c5-138">Il codice seguente produce una stringa `str1` con valore `"abc\n     def"` e una stringa `str2` con valore `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="f09c5-138">The following code produces a string `str1` that has value `"abc\n     def"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="f09c5-139">È possibile accedere a singoli caratteri in una stringa utilizzando la sintassi di tipo matrice, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f09c5-139">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="f09c5-140">L'output è `b`.</span><span class="sxs-lookup"><span data-stu-id="f09c5-140">The output is `b`.</span></span>

<span data-ttu-id="f09c5-141">Oppure è possibile estrarre sottostringhe utilizzando la sintassi di sezione di matrice, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f09c5-141">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="f09c5-142">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f09c5-142">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="f09c5-143">È possibile rappresentare le stringhe ASCII matrici di byte senza segno, tipo `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="f09c5-143">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="f09c5-144">Aggiungere il suffisso `B` a una stringa letterale per indicare che è una stringa ASCII.</span><span class="sxs-lookup"><span data-stu-id="f09c5-144">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="f09c5-145">Valori letterali di stringa ASCII utilizzati con le matrici di byte supportano le sequenze di escape stesso come stringhe Unicode, ad eccezione di sequenze di escape Unicode.</span><span class="sxs-lookup"><span data-stu-id="f09c5-145">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]
    
## <a name="string-operators"></a><span data-ttu-id="f09c5-146">Operatori di stringa</span><span class="sxs-lookup"><span data-stu-id="f09c5-146">String Operators</span></span>
<span data-ttu-id="f09c5-147">Esistono due modi per concatenare stringhe: tramite il `+` operatore o utilizzando il `^` operatore.</span><span class="sxs-lookup"><span data-stu-id="f09c5-147">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="f09c5-148">Il `+` operatore mantiene la compatibilità con la stringa di .NET Framework di gestione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f09c5-148">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="f09c5-149">L'esempio seguente illustra la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="f09c5-149">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]
    
## <a name="string-class"></a><span data-ttu-id="f09c5-150">Classe di stringa</span><span class="sxs-lookup"><span data-stu-id="f09c5-150">String Class</span></span>
<span data-ttu-id="f09c5-151">Poiché il tipo di stringa in F # è effettivamente un .NET Framework `System.String` digitare tutti i `System.String` membri sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="f09c5-151">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="f09c5-152">Sono inclusi il `+` operatore, che viene utilizzato per concatenare stringhe, il `Length` , proprietà e `Chars` proprietà, che restituisce la stringa come matrice di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="f09c5-152">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="f09c5-153">Per ulteriori informazioni sulle stringhe, vedere `System.String`.</span><span class="sxs-lookup"><span data-stu-id="f09c5-153">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="f09c5-154">Tramite il `Chars` proprietà `System.String`, è possibile accedere a singoli caratteri in una stringa, specificando un indice, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f09c5-154">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]
    
## <a name="string-module"></a><span data-ttu-id="f09c5-155">Modulo di stringa</span><span class="sxs-lookup"><span data-stu-id="f09c5-155">String Module</span></span>
<span data-ttu-id="f09c5-156">Funzionalità aggiuntive per la gestione delle stringhe è incluso nel `String` modulo il `FSharp.Core` dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f09c5-156">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="f09c5-157">Per ulteriori informazioni, vedere [modulo Core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="f09c5-157">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="f09c5-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f09c5-158">See Also</span></span>
[<span data-ttu-id="f09c5-159">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="f09c5-159">F# Language Reference</span></span>](index.md)
