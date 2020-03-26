---
title: Introduzione alla codifica dei caratteri in .NETIntroduction to character encoding in .NET
description: Informazioni sulla codifica e decodifica dei caratteri in .NET.
ms.date: 03/09/2020
no-loc:
- Rune
- char
- string
dev_langs:
- csharp
helpviewer_keywords:
- encoding, understanding
ms.openlocfilehash: 34b1577f8bcea80c1f41b6f9605bf47d132fdb4f
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134417"
---
# <a name="character-encoding-in-net"></a><span data-ttu-id="b3051-103">Codifica dei caratteri in .NET</span><span class="sxs-lookup"><span data-stu-id="b3051-103">Character encoding in .NET</span></span>

<span data-ttu-id="b3051-104">In questo articolo viene fornita un'introduzione ai sistemi di codifica dei caratteri utilizzati da .NET.</span><span class="sxs-lookup"><span data-stu-id="b3051-104">This article provides an introduction to character encoding systems that are used by .NET.</span></span> <span data-ttu-id="b3051-105">Nell'articolo viene <xref:System.String>illustrato <xref:System.Char> <xref:System.Text.Rune>il <xref:System.Globalization.StringInfo> funzionamento dei tipi , , e con Unicode, UTF-16 e UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b3051-105">The article explains how the <xref:System.String>, <xref:System.Char>, <xref:System.Text.Rune>, and <xref:System.Globalization.StringInfo> types work with Unicode, UTF-16, and UTF-8.</span></span>

<span data-ttu-id="b3051-106">Il termine *carattere* viene utilizzato qui nel senso generale di *ciò che un lettore percepisce come un singolo elemento di visualizzazione*.</span><span class="sxs-lookup"><span data-stu-id="b3051-106">The term *character* is used here in the general sense of *what a reader perceives as a single display element*.</span></span> <span data-ttu-id="b3051-107">Esempi comuni sono la lettera "a", il simbolo🐂"" e l'emoji " ".</span><span class="sxs-lookup"><span data-stu-id="b3051-107">Common examples are the letter "a", the symbol "@", and the emoji "🐂".</span></span> <span data-ttu-id="b3051-108">A volte ciò che sembra un carattere è in realtà composto da più elementi di visualizzazione indipendenti, come spiega la sezione sui [cluster di grafemi.](#grapheme-clusters)</span><span class="sxs-lookup"><span data-stu-id="b3051-108">Sometimes what looks like one character is actually composed of multiple independent display elements, as the section on [grapheme clusters](#grapheme-clusters) explains.</span></span>

## <a name="the-string-and-char-types"></a><span data-ttu-id="b3051-109">I tipi string e char</span><span class="sxs-lookup"><span data-stu-id="b3051-109">The string and char types</span></span>

<span data-ttu-id="b3051-110">Un'istanza della classe [string](xref:System.String) rappresenta del testo.</span><span class="sxs-lookup"><span data-stu-id="b3051-110">An instance of the [string](xref:System.String) class represents some text.</span></span> <span data-ttu-id="b3051-111">A `string` è logicamente una sequenza di valori a 16 bit, ognuno dei quali è un'istanza della struttura [char.](xref:System.Char)</span><span class="sxs-lookup"><span data-stu-id="b3051-111">A `string` is logically a sequence of 16-bit values, each of which is an instance of the [char](xref:System.Char) struct.</span></span> <span data-ttu-id="b3051-112">[Stringa. Proprietà Length](xref:System.String.Length) restituisce `char` il `string` numero di istanze nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="b3051-112">The [string.Length](xref:System.String.Length) property returns the number of `char` instances in the `string` instance.</span></span>

<span data-ttu-id="b3051-113">La seguente funzione di esempio stampa i valori in notazione esadecimale di tutte le `char` istanze in un: `string`</span><span class="sxs-lookup"><span data-stu-id="b3051-113">The following sample function prints out the values in hexadecimal notation of all the `char` instances in a `string`:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::

<span data-ttu-id="b3051-114">Passare la stringa "Hello" a questa funzione e ottenere l'output seguente:Pass the string "Hello" to this function, and you get the following output:</span><span class="sxs-lookup"><span data-stu-id="b3051-114">Pass the string "Hello" to this function, and you get the following output:</span></span>

```csharp
PrintChars("Hello");
```

```output
"Hello".Length = 5
s[0] = 'H' ('\u0048')
s[1] = 'e' ('\u0065')
s[2] = 'l' ('\u006c')
s[3] = 'l' ('\u006c')
s[4] = 'o' ('\u006f')
```

<span data-ttu-id="b3051-115">Ogni carattere è `char` rappresentato da un singolo valore.</span><span class="sxs-lookup"><span data-stu-id="b3051-115">Each character is represented by a single `char` value.</span></span> <span data-ttu-id="b3051-116">Questo schema vale per la maggior parte delle lingue del mondo.</span><span class="sxs-lookup"><span data-stu-id="b3051-116">That pattern holds true for most of the world's languages.</span></span> <span data-ttu-id="b3051-117">Ad esempio, ecco l'output per due caratteri cinesi che suonano come *n ' h 'o* e significa *Ciao*:</span><span class="sxs-lookup"><span data-stu-id="b3051-117">For example, here's the output for two Chinese characters that sound like *nǐ hǎo* and mean *Hello*:</span></span>

```csharp
PrintChars("你好");
```

```output
"你好".Length = 2
s[0] = '你' ('\u4f60')
s[1] = '好' ('\u597d')
```

<span data-ttu-id="b3051-118">Tuttavia, per alcune lingue e per alcuni `char` simboli ed emoji, sono necessarie due istanze per rappresentare un singolo carattere.</span><span class="sxs-lookup"><span data-stu-id="b3051-118">However, for some languages and for some symbols and emoji, it takes two `char` instances to represent a single character.</span></span> <span data-ttu-id="b3051-119">Ad esempio, confrontare `char` i caratteri e le istanze nella parola che indica *Osage* nella lingua di Osage:</span><span class="sxs-lookup"><span data-stu-id="b3051-119">For example, compare the characters and `char` instances in the word that means *Osage* in the Osage language:</span></span>

```csharp
PrintChars("𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟");
```

```output
"𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟".Length = 17
s[0] = '�' ('\ud801')
s[1] = '�' ('\udccf')
s[2] = '�' ('\ud801')
s[3] = '�' ('\udcd8')
s[4] = '�' ('\ud801')
s[5] = '�' ('\udcfb')
s[6] = '�' ('\ud801')
s[7] = '�' ('\udcd8')
s[8] = '�' ('\ud801')
s[9] = '�' ('\udcfb')
s[10] = '�' ('\ud801')
s[11] = '�' ('\udcdf')
s[12] = ' ' ('\u0020')
s[13] = '�' ('\ud801')
s[14] = '�' ('\udcbb')
s[15] = '�' ('\ud801')
s[16] = '�' ('\udcdf')
```

<span data-ttu-id="b3051-120">Nell'esempio precedente, ogni carattere ad eccezione dello spazio è rappresentato da due `char` istanze.</span><span class="sxs-lookup"><span data-stu-id="b3051-120">In the preceding example, each character except the space is represented by two `char` instances.</span></span>

<span data-ttu-id="b3051-121">Una singola emoji Unicode è `char`rappresentata anche da due s, come si vede nell'esempio seguente che mostra un emoji bue:</span><span class="sxs-lookup"><span data-stu-id="b3051-121">A single Unicode emoji is also represented by two `char`s, as seen in the following example showing an ox emoji:</span></span>

```
"🐂".Length = 2
s[0] = '�' ('\ud83d')
s[1] = '�' ('\udc02')
```

<span data-ttu-id="b3051-122">In questi esempi viene `string.Length`mostrato che il `char` valore di , che indica il numero di istanze, non indica necessariamente il numero di caratteri visualizzati.</span><span class="sxs-lookup"><span data-stu-id="b3051-122">These examples show that the value of `string.Length`, which indicates the number of `char` instances, doesn't necessarily indicate the number of displayed characters.</span></span> <span data-ttu-id="b3051-123">Una `char` singola istanza da sola non rappresenta necessariamente un carattere.</span><span class="sxs-lookup"><span data-stu-id="b3051-123">A single `char` instance by itself doesn't necessarily represent a character.</span></span>

<span data-ttu-id="b3051-124">Le `char` coppie che eseguono il mapping a un singolo carattere sono *denominate coppie di surrogati*.</span><span class="sxs-lookup"><span data-stu-id="b3051-124">The `char` pairs that map to a single character are called *surrogate pairs*.</span></span> <span data-ttu-id="b3051-125">Per capire come funzionano, è necessario comprendere la codifica Unicode e UTF-16.</span><span class="sxs-lookup"><span data-stu-id="b3051-125">To understand how they work, you need to understand Unicode and UTF-16 encoding.</span></span>

## <a name="unicode-code-points"></a><span data-ttu-id="b3051-126">Punti di codice Unicode</span><span class="sxs-lookup"><span data-stu-id="b3051-126">Unicode code points</span></span>

<span data-ttu-id="b3051-127">Unicode è uno standard di codifica internazionale per l'uso su varie piattaforme e con varie lingue e script.</span><span class="sxs-lookup"><span data-stu-id="b3051-127">Unicode is an international encoding standard for use on various platforms and with various languages and scripts.</span></span>

<span data-ttu-id="b3051-128">Lo standard Unicode definisce oltre 1,1 milioni di [punti di codice.](https://www.unicode.org/glossary/#code_point)</span><span class="sxs-lookup"><span data-stu-id="b3051-128">The Unicode Standard defines over 1.1 million [code points](https://www.unicode.org/glossary/#code_point).</span></span> <span data-ttu-id="b3051-129">Un punto di codice è un valore `U+10FFFF` intero compreso tra 0 e (decimale 1.114.111).</span><span class="sxs-lookup"><span data-stu-id="b3051-129">A code point is an integer value that can range from 0 to `U+10FFFF` (decimal 1,114,111).</span></span> <span data-ttu-id="b3051-130">Alcuni punti di codice vengono assegnati a lettere, simboli o emoji.</span><span class="sxs-lookup"><span data-stu-id="b3051-130">Some code points are assigned to letters, symbols, or emoji.</span></span> <span data-ttu-id="b3051-131">Altri vengono assegnati ad azioni che controllano la modalità di visualizzazione del testo o dei caratteri, ad esempio l'avanzamento a una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="b3051-131">Others are assigned to actions that control how text or characters are displayed, such as advance to a new line.</span></span> <span data-ttu-id="b3051-132">Molti punti di codice non sono ancora assegnati.</span><span class="sxs-lookup"><span data-stu-id="b3051-132">Many code points are not yet assigned.</span></span>

<span data-ttu-id="b3051-133">Di seguito sono riportati alcuni esempi di assegnazioni di punti di codice, con collegamenti a i grafici Unicode in cui vengono visualizzati:Here are some examples of code point assignments, with links to Unicode charts in which they appear:</span><span class="sxs-lookup"><span data-stu-id="b3051-133">Here are some examples of code point assignments, with links to Unicode charts in which they appear:</span></span>

|<span data-ttu-id="b3051-134">Decimal</span><span class="sxs-lookup"><span data-stu-id="b3051-134">Decimal</span></span>|<span data-ttu-id="b3051-135">Hex</span><span class="sxs-lookup"><span data-stu-id="b3051-135">Hex</span></span>       |<span data-ttu-id="b3051-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3051-136">Example</span></span>|<span data-ttu-id="b3051-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3051-137">Description</span></span>|
|------:|----------|-------|-----------|
|<span data-ttu-id="b3051-138">10</span><span class="sxs-lookup"><span data-stu-id="b3051-138">10</span></span>     | `U+000A` |<span data-ttu-id="b3051-139">N/D</span><span class="sxs-lookup"><span data-stu-id="b3051-139">N/A</span></span>| [<span data-ttu-id="b3051-140">AVANZAMENTO RIGA</span><span class="sxs-lookup"><span data-stu-id="b3051-140">LINE FEED</span></span>](https://www.unicode.org/charts/PDF/U0000.pdf) |
|<span data-ttu-id="b3051-141">65</span><span class="sxs-lookup"><span data-stu-id="b3051-141">65</span></span>     | `U+0061` | <span data-ttu-id="b3051-142">a</span><span class="sxs-lookup"><span data-stu-id="b3051-142">a</span></span> | [<span data-ttu-id="b3051-143">LATIN SMALL LETTER A</span><span class="sxs-lookup"><span data-stu-id="b3051-143">LATIN SMALL LETTER A</span></span>](https://www.unicode.org/charts/PDF/U0000.pdf) |
|<span data-ttu-id="b3051-144">562</span><span class="sxs-lookup"><span data-stu-id="b3051-144">562</span></span>    | `U+0232` | <span data-ttu-id="b3051-145"><a0>T</span><span class="sxs-lookup"><span data-stu-id="b3051-145">Ȳ</span></span> | [<span data-ttu-id="b3051-146">LATIN MAIUSCOL ODMAIUSCOLO Con MACRON</span><span class="sxs-lookup"><span data-stu-id="b3051-146">LATIN CAPITAL LETTER Y WITH MACRON</span></span>](https://www.unicode.org/charts/PDF/U0180.pdf) |
|<span data-ttu-id="b3051-147">68,675</span><span class="sxs-lookup"><span data-stu-id="b3051-147">68,675</span></span> | `U+10C43`| <span data-ttu-id="b3051-148">𐱃</span><span class="sxs-lookup"><span data-stu-id="b3051-148">𐱃</span></span> | [<span data-ttu-id="b3051-149">OLD TURKIC LETTER ORKHON AT</span><span class="sxs-lookup"><span data-stu-id="b3051-149">OLD TURKIC LETTER ORKHON AT</span></span>](https://www.unicode.org/charts/PDF/U10C00.pdf) |
|<span data-ttu-id="b3051-150">127,801</span><span class="sxs-lookup"><span data-stu-id="b3051-150">127,801</span></span>| `U+1F339`| <span data-ttu-id="b3051-151">🌹</span><span class="sxs-lookup"><span data-stu-id="b3051-151">🌹</span></span> | [<span data-ttu-id="b3051-152">EMOJI ROSA</span><span class="sxs-lookup"><span data-stu-id="b3051-152">ROSE emoji</span></span>](https://www.unicode.org/charts/PDF/U1F300.pdf) |

<span data-ttu-id="b3051-153">I punti di codice vengono in genere `U+xxxx`indicati utilizzando la sintassi , dove `xxxx` è il valore intero con codifica esadecimale.</span><span class="sxs-lookup"><span data-stu-id="b3051-153">Code points are customarily referred to by using the syntax `U+xxxx`, where `xxxx` is the hex-encoded integer value.</span></span>

<span data-ttu-id="b3051-154">All'interno dell'intera gamma di punti di codice ci sono due intervalli secondari:</span><span class="sxs-lookup"><span data-stu-id="b3051-154">Within the full range of code points there are two subranges:</span></span>

* <span data-ttu-id="b3051-155">Il **piano multilingue di base (BMP)** nell'intervallo `U+0000..U+FFFF`.</span><span class="sxs-lookup"><span data-stu-id="b3051-155">The **Basic Multilingual Plane (BMP)** in the range `U+0000..U+FFFF`.</span></span> <span data-ttu-id="b3051-156">Questa gamma a 16 bit fornisce 65.536 punti di codice, sufficienti a coprire la maggior parte dei sistemi di scrittura del mondo.</span><span class="sxs-lookup"><span data-stu-id="b3051-156">This 16-bit range provides 65,536 code points, enough to cover the majority of the world's writing systems.</span></span>
* <span data-ttu-id="b3051-157">**Punti di codice supplementari** nell'intervallo `U+10000..U+10FFFF`.</span><span class="sxs-lookup"><span data-stu-id="b3051-157">**Supplementary code points** in the range `U+10000..U+10FFFF`.</span></span> <span data-ttu-id="b3051-158">Questo intervallo a 21 bit fornisce più di un milione di punti di codice aggiuntivi che possono essere utilizzati per lingue meno conosciute e altri scopi come emoji.</span><span class="sxs-lookup"><span data-stu-id="b3051-158">This 21-bit range provides more than a million additional code points that can be used for less well-known languages and other purposes such as emojis.</span></span>

<span data-ttu-id="b3051-159">Il diagramma seguente illustra la relazione tra il BMP e i punti di codice supplementari.</span><span class="sxs-lookup"><span data-stu-id="b3051-159">The following diagram illustrates the relationship between the BMP and the supplementary code points.</span></span>

:::image type="content" source="media/character-encoding-introduction/bmp-and-supplementary.svg" alt-text="Punti BMP e codice supplementare":::

## <a name="utf-16-code-units"></a><span data-ttu-id="b3051-161">Unità di codice UTF-16</span><span class="sxs-lookup"><span data-stu-id="b3051-161">UTF-16 code units</span></span>

<span data-ttu-id="b3051-162">Il formato di trasformazione Unicode a 16 bit ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) è un sistema di codifica dei caratteri che utilizza unità di *codice* a 16 bit per rappresentare i punti di codice Unicode.</span><span class="sxs-lookup"><span data-stu-id="b3051-162">16-bit Unicode Transformation Format ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) is a character encoding system that uses 16-bit *code units* to represent Unicode code points.</span></span> <span data-ttu-id="b3051-163">.NET utilizza UTF-16 per codificare `string`il testo in un oggetto .</span><span class="sxs-lookup"><span data-stu-id="b3051-163">.NET uses UTF-16 to encode the text in a `string`.</span></span> <span data-ttu-id="b3051-164">Un'istanza `char` rappresenta un'unità di codice a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="b3051-164">A `char` instance represents a 16-bit code unit.</span></span>

<span data-ttu-id="b3051-165">Una singola unità di codice a 16 bit può rappresentare qualsiasi punto di codice nell'intervallo a 16 bit del piano multilingue di base.</span><span class="sxs-lookup"><span data-stu-id="b3051-165">A single 16-bit code unit can represent any code point in the 16-bit range of the Basic Multilingual Plane.</span></span> <span data-ttu-id="b3051-166">Ma per un punto di codice `char` nell'intervallo supplementare, sono necessarie due istanze.</span><span class="sxs-lookup"><span data-stu-id="b3051-166">But for a code point in the supplementary range, two `char` instances are needed.</span></span>

## <a name="surrogate-pairs"></a><span data-ttu-id="b3051-167">Coppie di surrogati</span><span class="sxs-lookup"><span data-stu-id="b3051-167">Surrogate pairs</span></span>

<span data-ttu-id="b3051-168">La conversione di due valori a 16 bit in un singolo valore a 21 bit `U+D800` `U+DFFF` è facilitata da un intervallo speciale denominato punti di *codice surrogato,* da (decimale 55.296 a 57.343), inclusivo.</span><span class="sxs-lookup"><span data-stu-id="b3051-168">The translation of two 16-bit values to a single 21-bit value is facilitated by a special range called the *surrogate code points*, from `U+D800` to `U+DFFF` (decimal 55,296 to 57,343), inclusive.</span></span>

<span data-ttu-id="b3051-169">Il diagramma seguente illustra la relazione tra BMP e i punti di codice surrogati.</span><span class="sxs-lookup"><span data-stu-id="b3051-169">The following diagram illustrates the relationship between the BMP and the surrogate code points.</span></span>

:::image type="content" source="media/character-encoding-introduction/bmp-and-surrogate.svg" alt-text="Punti di codice BMP e surrogati":::

<span data-ttu-id="b3051-171">Quando un punto di`U+D800..U+DBFF`codice surrogato alto ( ) viene`U+DC00..U+DFFF`immediatamente seguito da un punto di codice *surrogato basso* ( ), la coppia viene interpretata come un punto di codice *supplementare* utilizzando la formula seguente:</span><span class="sxs-lookup"><span data-stu-id="b3051-171">When a *high surrogate* code point (`U+D800..U+DBFF`) is immediately followed by a *low surrogate* code point (`U+DC00..U+DFFF`), the pair is interpreted as a supplementary code point by using the following formula:</span></span>

```
code point = 0x10000 +
  ((high surrogate code point - 0xD800) * 0x0400) +
  (low surrogate code point - 0xDC00)
```

<span data-ttu-id="b3051-172">Ecco la stessa formula che usa la notazione decimale:</span><span class="sxs-lookup"><span data-stu-id="b3051-172">Here's the same formula using decimal notation:</span></span>

```
code point = 65,536 +
  ((high surrogate code point - 55,296) * 1,024) +
  (low surrogate code point - 56,320)
```

<span data-ttu-id="b3051-173">Un punto di codice surrogato *alto* non ha un valore numerico più alto di un punto di codice surrogato *basso.*</span><span class="sxs-lookup"><span data-stu-id="b3051-173">A *high* surrogate code point doesn't have a higher number value than a *low* surrogate code point.</span></span> <span data-ttu-id="b3051-174">Il punto di codice surrogato alto viene chiamato "alto" perché viene utilizzato per calcolare gli 11 bit di ordine superiore dell'intero intervallo di punti di codice a 21 bit.</span><span class="sxs-lookup"><span data-stu-id="b3051-174">The high surrogate code point is called "high" because it's used to calculate the higher-order 11 bits of the full 21-bit code point range.</span></span> <span data-ttu-id="b3051-175">Il punto di codice surrogato basso viene utilizzato per calcolare i 10 bit di ordine inferiore.</span><span class="sxs-lookup"><span data-stu-id="b3051-175">The low surrogate code point is used to calculate the lower-order 10 bits.</span></span>

<span data-ttu-id="b3051-176">Ad esempio, il punto di codice effettivo `0xD83C` `0xDF39` che corrisponde alla coppia di surrogati e viene calcolato come segue:</span><span class="sxs-lookup"><span data-stu-id="b3051-176">For example, the actual code point that corresponds to the surrogate pair `0xD83C` and `0xDF39`  is computed as follows:</span></span>

```
actual = 0x10000 + ((0xD83C - 0xD800) * 0x0400) + (0xDF39 - 0xDC00)
       = 0x10000 + (          0x003C  * 0x0400) +           0x0339
       = 0x10000 +                      0xF000  +           0x0339
       = 0x1F339
```

<span data-ttu-id="b3051-177">Ecco lo stesso calcolo utilizzando la notazione decimale:</span><span class="sxs-lookup"><span data-stu-id="b3051-177">Here's the same calculation using decimal notation:</span></span>

```
actual =  65,536 + ((55,356 - 55,296) * 1,024) + (57,145 - 56320)
       =  65,536 + (              60  * 1,024) +             825
       =  65,536 +                     61,440  +             825
       = 127,801
```

<span data-ttu-id="b3051-178">Nell'esempio precedente `"\ud83c\udf39"` viene illustrato che è la `U+1F339 ROSE ('🌹')` codifica UTF-16 del punto di codice menzionato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b3051-178">The preceding example demonstrates that `"\ud83c\udf39"` is the UTF-16 encoding of the `U+1F339 ROSE ('🌹')` code point mentioned earlier.</span></span>

## <a name="unicode-scalar-values"></a><span data-ttu-id="b3051-179">Valori scalari Unicode</span><span class="sxs-lookup"><span data-stu-id="b3051-179">Unicode scalar values</span></span>

<span data-ttu-id="b3051-180">Il termine [valore scalare Unicode](https://www.unicode.org/glossary/#unicode_scalar_value) fa riferimento a tutti i punti di codice diversi dai punti di codice surrogati.</span><span class="sxs-lookup"><span data-stu-id="b3051-180">The term [Unicode scalar value](https://www.unicode.org/glossary/#unicode_scalar_value) refers to all code points other than the surrogate code points.</span></span> <span data-ttu-id="b3051-181">In altre parole, un valore scalare è qualsiasi punto di codice a cui viene assegnato un carattere o a cui è possibile assegnare un carattere in futuro.</span><span class="sxs-lookup"><span data-stu-id="b3051-181">In other words, a scalar value is any code point that is assigned a character or can be assigned a character in the future.</span></span> <span data-ttu-id="b3051-182">"Carattere" qui si riferisce a tutto ciò che può essere assegnato a un punto di codice, che include elementi quali azioni che controllano la modalità di visualizzazione del testo o dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="b3051-182">"Character" here refers to anything that can be assigned to a code point, which includes such things as actions that control how text or characters are displayed.</span></span>

<span data-ttu-id="b3051-183">Il diagramma seguente illustra i punti di codice del valore scalare.</span><span class="sxs-lookup"><span data-stu-id="b3051-183">The following diagram illustrates the scalar value code points.</span></span>

:::image type="content" source="media/character-encoding-introduction/scalar-values.svg" alt-text="Valori scalari":::

### <a name="the-opno-locrune-type-as-a-scalar-value"></a><span data-ttu-id="b3051-185">Il Rune tipo come valore scalare</span><span class="sxs-lookup"><span data-stu-id="b3051-185">The Rune type as a scalar value</span></span>

<span data-ttu-id="b3051-186">A partire da .NET Core <xref:System.Text.Rune?displayProperty=fullName> 3.0, il tipo rappresenta un valore scalare Unicode.Beginning with .NET Core 3.0, the type represents a Unicode scalar value.</span><span class="sxs-lookup"><span data-stu-id="b3051-186">Beginning with .NET Core 3.0, the <xref:System.Text.Rune?displayProperty=fullName> type represents a Unicode scalar value.</span></span> <span data-ttu-id="b3051-187">**`Rune`non è disponibile in .NET Core 2.x o .NET Framework 4.x.**</span><span class="sxs-lookup"><span data-stu-id="b3051-187">**`Rune` is not available in .NET Core 2.x or .NET Framework 4.x.**</span></span>

<span data-ttu-id="b3051-188">I `Rune` costruttori convalidano che l'istanza risultante sia un valore scalare Unicode valido, in caso contrario generano un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b3051-188">The `Rune` constructors validate that the resulting instance is a valid Unicode scalar value, otherwise they throw an exception.</span></span> <span data-ttu-id="b3051-189">L'esempio seguente mostra il `Rune` codice che crea correttamente un'istanza delle istanze perché l'input rappresenta valori scalari validi:The following example shows code that successfully instantiates instances because the input represents valid scalar values:</span><span class="sxs-lookup"><span data-stu-id="b3051-189">The following example shows code that successfully instantiates `Rune` instances because the input represents valid scalar values:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetValid":::

<span data-ttu-id="b3051-190">L'esempio seguente genera un'eccezione perché il punto di codice è nell'intervallo di surrogati e non fa parte di una coppia di surrogati:The following example throws an exception because the code point is in the surrogate range and isn't part of a surrogate pair:</span><span class="sxs-lookup"><span data-stu-id="b3051-190">The following example throws an exception because the code point is in the surrogate range and isn't part of a surrogate pair:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidSurrogate":::

<span data-ttu-id="b3051-191">Nell'esempio seguente viene generata un'eccezione perché il punto di codice non rientra nell'intervallo supplementare:The following example throws an exception because the code point is beyond the supplementary range:</span><span class="sxs-lookup"><span data-stu-id="b3051-191">The following example throws an exception because the code point is beyond the supplementary range:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidHigh":::

### <a name="opno-locrune-usage-example-changing-letter-case"></a>Rune<span data-ttu-id="b3051-192">esempio di utilizzo: modifica della custodia per lettere</span><span class="sxs-lookup"><span data-stu-id="b3051-192"> usage example: changing letter case</span></span>

<span data-ttu-id="b3051-193">Un'API che `char` accetta un e presuppone che stia lavorando con un punto di `char` codice che è un valore scalare non funziona correttamente se l'è da una coppia di surrogati.</span><span class="sxs-lookup"><span data-stu-id="b3051-193">An API that takes a `char` and assumes it is working with a code point that is a scalar value doesn't work correctly if the `char` is from a surrogate pair.</span></span> <span data-ttu-id="b3051-194">Si consideri, ad esempio, char il stringmetodo seguente che chiama <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> ciascuno in un:</span><span class="sxs-lookup"><span data-stu-id="b3051-194">For example, consider the following method that calls <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> on each char in a string:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::

<span data-ttu-id="b3051-195">`input` string Se contiene la lettera `er` Deseret`𐑉`minuscola ( ), questo codice`𐐡`non la convertirà in maiuscolo ( ).</span><span class="sxs-lookup"><span data-stu-id="b3051-195">If the `input` string contains the lowercase Deseret letter `er` (`𐑉`), this code won't convert it to uppercase (`𐐡`).</span></span> <span data-ttu-id="b3051-196">Il codice `char.ToUpperInvariant` chiama separatamente su `U+D801` ogni `U+DC49`punto di codice surrogato e .</span><span class="sxs-lookup"><span data-stu-id="b3051-196">The code calls `char.ToUpperInvariant` separately on each surrogate code point, `U+D801` and `U+DC49`.</span></span> <span data-ttu-id="b3051-197">Ma `U+D801` non ha abbastanza informazioni da solo per identificarlo `char.ToUpperInvariant` come una lettera minuscola, quindi lascialo solo.</span><span class="sxs-lookup"><span data-stu-id="b3051-197">But `U+D801` doesn't have enough information by itself to identify it as a lowercase letter, so `char.ToUpperInvariant` leaves it alone.</span></span> <span data-ttu-id="b3051-198">E gestisce `U+DC49` allo stesso modo.</span><span class="sxs-lookup"><span data-stu-id="b3051-198">And it handles `U+DC49` the same way.</span></span> <span data-ttu-id="b3051-199">Il risultato è che il `input` string valore minuscolo ''' nella casella non viene convertito in lettere maiuscole '''.</span><span class="sxs-lookup"><span data-stu-id="b3051-199">The result is that lowercase '𐑉' in the `input` string doesn't get converted to uppercase '𐐡'.</span></span>

<span data-ttu-id="b3051-200">Di seguito sono riportate string due opzioni per convertire correttamente una caratteri maiuscola:</span><span class="sxs-lookup"><span data-stu-id="b3051-200">Here are two options for correctly converting a string to uppercase:</span></span>

* <span data-ttu-id="b3051-201">Chiamata <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> all'input string anziché `char`iterare`char`-by- .</span><span class="sxs-lookup"><span data-stu-id="b3051-201">Call <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> on the input string rather than iterating `char`-by-`char`.</span></span> <span data-ttu-id="b3051-202">Il `string.ToUpperInvariant` metodo ha accesso a entrambe le parti di ogni coppia di surrogati, in modo da poter gestire correttamente tutti i punti di codice Unicode.The method has access to both parts of each surrogate pair, so it can handle all Unicode code points correctly.</span><span class="sxs-lookup"><span data-stu-id="b3051-202">The `string.ToUpperInvariant` method has access to both parts of each surrogate pair, so it can handle all Unicode code points correctly.</span></span>
* <span data-ttu-id="b3051-203">Scorrere i valori scalari `Rune` Unicode `char` come istanze anziché come istanze, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b3051-203">Iterate through the Unicode scalar values as `Rune` instances instead of `char` instances, as shown in the following example.</span></span> <span data-ttu-id="b3051-204">Poiché `Rune` un'istanza è un valore scalare Unicode valido, può essere passata alle API che prevedono di operare su un valore scalare.</span><span class="sxs-lookup"><span data-stu-id="b3051-204">Since a `Rune` instance is a valid Unicode scalar value, it can be passed to APIs that expect to operate on a scalar value.</span></span> <span data-ttu-id="b3051-205">Ad esempio, <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType> la chiamata come illustrato nell'esempio seguente fornisce risultati corretti:For example, calling as shown in the following example gives correct results:</span><span class="sxs-lookup"><span data-stu-id="b3051-205">For example, calling <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType> as shown in the following example gives correct results:</span></span>

  :::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::

### <a name="other-opno-locrune-apis"></a><span data-ttu-id="b3051-206">Altre Rune API</span><span class="sxs-lookup"><span data-stu-id="b3051-206">Other Rune APIs</span></span>

<span data-ttu-id="b3051-207">Il `Rune` tipo espone analoghi di `char` molte delle API.</span><span class="sxs-lookup"><span data-stu-id="b3051-207">The `Rune` type exposes analogs of many of the `char` APIs.</span></span> <span data-ttu-id="b3051-208">Ad esempio, i metodi seguenti rispecchiano le API statiche sul tipo:For example, the following methods mirror static APIs on the `char` type:</span><span class="sxs-lookup"><span data-stu-id="b3051-208">For example, the following methods mirror static APIs on the `char` type:</span></span>

* <xref:System.Text.Rune.IsLetter%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsWhiteSpace%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsLetterOrDigit%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.GetUnicodeCategory%2A?displayProperty=nameWithType>

<span data-ttu-id="b3051-209">Per ottenere il valore scalare non elaborato da un'istanza, `Rune` usare la <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType> proprietà .</span><span class="sxs-lookup"><span data-stu-id="b3051-209">To get the raw scalar value from a `Rune` instance, use the <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="b3051-210">`Rune` Per riconvertire un'istanza `char`in una <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> sequenza di s, utilizzare o il <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType> metodo .</span><span class="sxs-lookup"><span data-stu-id="b3051-210">To convert a `Rune` instance back to a sequence of `char`s, use <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> or the <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="b3051-211">Poiché qualsiasi valore scalare Unicode `char` è rappresentabile da una `Rune` singola o da una `char` coppia di surrogati, qualsiasi istanza può essere rappresentata al massimo da 2 istanze.</span><span class="sxs-lookup"><span data-stu-id="b3051-211">Since any Unicode scalar value is representable by a single `char` or by a surrogate pair, any `Rune` instance can be represented by at most 2 `char` instances.</span></span> <span data-ttu-id="b3051-212">Utilizzare <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType> per vedere `char` quante istanze `Rune` sono necessarie per rappresentare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="b3051-212">Use <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType> to see how many `char` instances are required to represent a `Rune` instance.</span></span>

<span data-ttu-id="b3051-213">Per ulteriori informazioni sul `Rune` tipo .NET, vedere le [ `Rune` informazioni](xref:System.Text.Rune)di riferimento sulle API .</span><span class="sxs-lookup"><span data-stu-id="b3051-213">For more information about the .NET `Rune` type, see the [`Rune` API reference](xref:System.Text.Rune).</span></span>

## <a name="grapheme-clusters"></a><span data-ttu-id="b3051-214">Cluster di grafemi</span><span class="sxs-lookup"><span data-stu-id="b3051-214">Grapheme clusters</span></span>

<span data-ttu-id="b3051-215">L'aspetto di un carattere potrebbe derivare da una combinazione di più punti di codice, pertanto un termine più descrittivo che viene spesso utilizzato al posto di "carattere" è cluster di [grafemi](https://www.unicode.org/glossary/#grapheme_cluster).</span><span class="sxs-lookup"><span data-stu-id="b3051-215">What looks like one character might result from a combination of multiple code points, so a more descriptive term that is often used in place of "character" is [grapheme cluster](https://www.unicode.org/glossary/#grapheme_cluster).</span></span> <span data-ttu-id="b3051-216">Il termine equivalente in .NET è elemento di [testo](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).</span><span class="sxs-lookup"><span data-stu-id="b3051-216">The equivalent term in .NET is [text element](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).</span></span>

<span data-ttu-id="b3051-217">Considerare `string` le istanze "a", "z".</span><span class="sxs-lookup"><span data-stu-id="b3051-217">Consider the `string` instances "a", "á".</span></span> <span data-ttu-id="b3051-218">"" e "`👩🏽‍🚒`".</span><span class="sxs-lookup"><span data-stu-id="b3051-218">"á", and "`👩🏽‍🚒`".</span></span> <span data-ttu-id="b3051-219">Se il sistema operativo li gestisce come specificato `string` dallo standard Unicode, ognuna di queste istanze viene visualizzata come un singolo elemento di testo o cluster di grafemi.</span><span class="sxs-lookup"><span data-stu-id="b3051-219">If your operating system handles them as specified by the Unicode standard, each of these `string` instances appears as a single text element or grapheme cluster.</span></span> <span data-ttu-id="b3051-220">Ma gli ultimi due sono rappresentati da più di un punto di codice di valore scalare.</span><span class="sxs-lookup"><span data-stu-id="b3051-220">But the last two are represented by more than one scalar value code point.</span></span>

* <span data-ttu-id="b3051-221">La string "a" è rappresentata da un `char` valore scalare e contiene un'istanza.</span><span class="sxs-lookup"><span data-stu-id="b3051-221">The string "a" is represented by one scalar value and contains one `char` instance.</span></span>

  * `U+0061 LATIN SMALL LETTER A`

* <span data-ttu-id="b3051-222">La string "z" è rappresentata da un `char` valore scalare e contiene un'istanza.</span><span class="sxs-lookup"><span data-stu-id="b3051-222">The string "á" is represented by one scalar value and contains one `char` instance.</span></span>

  * `U+00E1 LATIN SMALL LETTER E WITH ACUTE`

* <span data-ttu-id="b3051-223">Il string valore di "z" ha lo stesso aspetto di "" `char` ma è rappresentato da due valori scalari e contiene due istanze.</span><span class="sxs-lookup"><span data-stu-id="b3051-223">The string "á" looks the same as "á" but is represented by two scalar values and contains two `char` instances.</span></span>

  * `U+0065 LATIN SMALL LETTER A`
  * `U+0301 COMBINING ACUTE ACCENT`

* <span data-ttu-id="b3051-224">Infine, string il`👩🏽‍🚒`" " è rappresentato da `char` quattro valori scalari e contiene sette istanze.</span><span class="sxs-lookup"><span data-stu-id="b3051-224">Finally, the string "`👩🏽‍🚒`" is represented by four scalar values and contains seven `char` instances.</span></span>

  * <span data-ttu-id="b3051-225">`U+1F469 WOMAN`(intervallo supplementare, richiede una coppia di surrogati)</span><span class="sxs-lookup"><span data-stu-id="b3051-225">`U+1F469 WOMAN` (supplementary range, requires a surrogate pair)</span></span>
  * <span data-ttu-id="b3051-226">`U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4`(intervallo supplementare, richiede una coppia di surrogati)</span><span class="sxs-lookup"><span data-stu-id="b3051-226">`U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4` (supplementary range, requires a surrogate pair)</span></span>
  * `U+200D ZERO WIDTH JOINER`
  * <span data-ttu-id="b3051-227">`U+1F692 FIRE ENGINE`(intervallo supplementare, richiede una coppia di surrogati)</span><span class="sxs-lookup"><span data-stu-id="b3051-227">`U+1F692 FIRE ENGINE` (supplementary range, requires a surrogate pair)</span></span>

<span data-ttu-id="b3051-228">In alcuni degli esempi precedenti, ad esempio il modificatore di accento combinato o il modificatore del tono della pelle, il punto di codice non viene visualizzato come elemento autonomo sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="b3051-228">In some of the preceding examples - such as the combining accent modifier or the skin tone modifier - the code point does not display as a standalone element on the screen.</span></span> <span data-ttu-id="b3051-229">Piuttosto, serve a modificare l'aspetto di un elemento di testo che è venuto prima di esso.</span><span class="sxs-lookup"><span data-stu-id="b3051-229">Rather, it serves to modify the appearance of a text element that came before it.</span></span> <span data-ttu-id="b3051-230">Questi esempi mostrano che potrebbero essere presenti più valori scalari per costituiscono quelli che consideriamo un singolo "carattere" o "cluster di grafici".</span><span class="sxs-lookup"><span data-stu-id="b3051-230">These examples show that it might take multiple scalar values to make up what we think of as a single "character," or "grapheme cluster."</span></span>

<span data-ttu-id="b3051-231">Per enumerare i cluster di `string`grafemi di un oggetto , utilizzare la <xref:System.Globalization.StringInfo> classe come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b3051-231">To enumerate the grapheme clusters of a `string`, use the <xref:System.Globalization.StringInfo> class as shown in the following example.</span></span> <span data-ttu-id="b3051-232">Se si ha familiarità con `StringInfo` Swift, il tipo .NET è concettualmente simile al [tipo `character` di Swift.](https://developer.apple.com/documentation/swift/character)</span><span class="sxs-lookup"><span data-stu-id="b3051-232">If you're familiar with Swift, the .NET `StringInfo` type is conceptually similar to [Swift's `character` type](https://developer.apple.com/documentation/swift/character).</span></span>

### <a name="example-count-opno-locchar-opno-locrune-and-text-element-instances"></a><span data-ttu-id="b3051-233">Esempio: charistanze di elementi count , Runee text</span><span class="sxs-lookup"><span data-stu-id="b3051-233">Example: count char, Rune, and text element instances</span></span>

<span data-ttu-id="b3051-234">Nelle API .NET un cluster di grafemi è denominato elemento di *testo.*</span><span class="sxs-lookup"><span data-stu-id="b3051-234">In .NET APIs, a grapheme cluster is called a *text element*.</span></span> <span data-ttu-id="b3051-235">Nel metodo riportato `char`di `Rune`seguito vengono illustrate `string`le differenze tra istanze di elementi , e text in un oggetto :</span><span class="sxs-lookup"><span data-stu-id="b3051-235">The following method demonstrates the differences between `char`, `Rune`, and text element instances in a `string`:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::

<span data-ttu-id="b3051-236">Se si esegue questo codice in .NET Framework o .NET Core 3.1 `4`o versioni precedenti, il conteggio degli elementi di testo per l'emoji mostra .</span><span class="sxs-lookup"><span data-stu-id="b3051-236">If you run this code in .NET Framework or .NET Core 3.1 or earlier, the text element count for the emoji shows `4`.</span></span> <span data-ttu-id="b3051-237">Ciò è dovuto a `StringInfo` un bug nella classe che viene risolto in .NET 5.</span><span class="sxs-lookup"><span data-stu-id="b3051-237">That is due to a bug in the `StringInfo` class that is fixed in .NET 5.</span></span>

### <a name="example-splitting-opno-locstring-instances"></a><span data-ttu-id="b3051-238">Esempio: divisione delle istanzeExample: splitting string instances</span><span class="sxs-lookup"><span data-stu-id="b3051-238">Example: splitting string instances</span></span>

<span data-ttu-id="b3051-239">Quando si `string` suddividono le istanze, evitare di dividere coppie di surrogati e cluster di grafemi.</span><span class="sxs-lookup"><span data-stu-id="b3051-239">When splitting `string` instances, avoid splitting surrogate pairs and grapheme clusters.</span></span> <span data-ttu-id="b3051-240">Si consideri l'esempio seguente di codice non corretto, che stringintende inserire interruzioni di riga ogni 10 caratteri in un :</span><span class="sxs-lookup"><span data-stu-id="b3051-240">Consider the following example of incorrect code, which intends to insert line breaks every 10 characters in a string:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::

<span data-ttu-id="b3051-241">Poiché questo `char` codice enumera le istanze, una coppia di`char` surrogati che si verifica a cavallo di un limite di 10 verrà divisa e verrà inserita una nuova riga tra di esse.</span><span class="sxs-lookup"><span data-stu-id="b3051-241">Because this code enumerates `char` instances, a surrogate pair that happens to straddle a 10-`char` boundary will be split and a newline injected between them.</span></span> <span data-ttu-id="b3051-242">Questo inserimento introduce il danneggiamento dei dati, perché i punti di codice surrogati sono significativi solo come coppie.</span><span class="sxs-lookup"><span data-stu-id="b3051-242">This insertion introduces data corruption, because surrogate code points are meaningful only as pairs.</span></span>

<span data-ttu-id="b3051-243">Il rischio di danneggiamento dei dati `Rune` non viene eliminato se `char` si enumerano le istanze (valori scalari) anziché le istanze.</span><span class="sxs-lookup"><span data-stu-id="b3051-243">The potential for data corruption isn't eliminated if you enumerate `Rune` instances (scalar values) instead of `char` instances.</span></span> <span data-ttu-id="b3051-244">Un set `Rune` di istanze può creare un cluster di grafemi a cavallo di un`char` limite di 10.</span><span class="sxs-lookup"><span data-stu-id="b3051-244">A set of `Rune` instances might make up a grapheme cluster that straddles a 10-`char` boundary.</span></span> <span data-ttu-id="b3051-245">Se il set di cluster del grafeme è suddiviso, non può essere interpretato correttamente.</span><span class="sxs-lookup"><span data-stu-id="b3051-245">If the grapheme cluster set is split up, it can't be interpreted correctly.</span></span>

<span data-ttu-id="b3051-246">Un approccio migliore string consiste nell'interrompere il con il conteggio cluster di grafemi, o elementi di testo, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b3051-246">A better approach is to break the string by counting grapheme clusters, or text elements, as in the following example:</span></span>

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::

<span data-ttu-id="b3051-247">Come indicato in precedenza, tuttavia, in implementazioni `StringInfo` di .NET diverse da .NET 5, la classe potrebbe gestire alcuni cluster di grafemi in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="b3051-247">As noted earlier, however, in implementations of .NET other than .NET 5, the `StringInfo` class might handle some grapheme clusters incorrectly.</span></span>

## <a name="utf-8-and-utf-32"></a><span data-ttu-id="b3051-248">UTF-8 e UTF-32</span><span class="sxs-lookup"><span data-stu-id="b3051-248">UTF-8 and UTF-32</span></span>

<span data-ttu-id="b3051-249">Le sezioni precedenti si concentravano su UTF-16 perché questo `string` è ciò che .NET utilizza per codificare le istanze.</span><span class="sxs-lookup"><span data-stu-id="b3051-249">The preceding sections focused on UTF-16 because that's what .NET uses to encode `string` instances.</span></span> <span data-ttu-id="b3051-250">Esistono altri sistemi di codifica per Unicode - [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) e [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32).</span><span class="sxs-lookup"><span data-stu-id="b3051-250">There are other encoding systems for Unicode - [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) and [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32).</span></span> <span data-ttu-id="b3051-251">Queste codifiche utilizzano rispettivamente unità di codice a 8 bit e unità di codice a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="b3051-251">These encodings use 8-bit code units and 32-bit code units, respectively.</span></span>

<span data-ttu-id="b3051-252">Come UTF-16, UTF-8 richiede più unità di codice per rappresentare alcuni valori scalari Unicode.</span><span class="sxs-lookup"><span data-stu-id="b3051-252">Like UTF-16, UTF-8 requires multiple code units to represent some Unicode scalar values.</span></span> <span data-ttu-id="b3051-253">UTF-32 può rappresentare qualsiasi valore scalare in una singola unità di codice a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="b3051-253">UTF-32 can represent any scalar value in a single 32-bit code unit.</span></span>

<span data-ttu-id="b3051-254">Di seguito sono riportati alcuni esempi che illustrano come lo stesso punto di codice Unicode viene rappresentato in ognuno di questi tre sistemi di codifica Unicode:Here are some examples showing how the same Unicode code point is represented in each of these three Unicode encoding systems:</span><span class="sxs-lookup"><span data-stu-id="b3051-254">Here are some examples showing how the same Unicode code point is represented in each of these three Unicode encoding systems:</span></span>

```
Scalar: U+0061 LATIN SMALL LETTER A ('a')
UTF-8 : [ 61 ]           (1x  8-bit code unit  = 8 bits total)
UTF-16: [ 0061 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000061 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+0429 CYRILLIC CAPITAL LETTER SHCHA ('Щ')
UTF-8 : [ D0 A9 ]        (2x  8-bit code units = 16 bits total)
UTF-16: [ 0429 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000429 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+A992 JAVANESE LETTER GA ('ꦒ')
UTF-8 : [ EA A6 92 ]     (3x  8-bit code units = 24 bits total)
UTF-16: [ A992 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 0000A992 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+104CC OSAGE CAPITAL LETTER TSHA ('𐓌')
UTF-8 : [ F0 90 93 8C ]  (4x  8-bit code units = 32 bits total)
UTF-16: [ D801 DCCC ]    (2x 16-bit code units = 32 bits total)
UTF-32: [ 000104CC ]     (1x 32-bit code unit  = 32 bits total)
```

<span data-ttu-id="b3051-255">Come indicato in precedenza, una singola unità di codice UTF-16 da una [coppia di surrogati](#surrogate-pairs) è priva di significato.</span><span class="sxs-lookup"><span data-stu-id="b3051-255">As noted earlier, a single UTF-16 code unit from a [surrogate pair](#surrogate-pairs) is meaningless by itself.</span></span> <span data-ttu-id="b3051-256">Allo stesso modo, una singola unità di codice UTF-8 è priva di significato se si trova in una sequenza di due, tre o quattro utilizzati per calcolare un valore scalare.</span><span class="sxs-lookup"><span data-stu-id="b3051-256">In the same way, a single UTF-8 code unit is meaningless by itself if it's in a sequence of two, three, or four used to calculate a scalar value.</span></span>

### <a name="endianness"></a><span data-ttu-id="b3051-257">Ordine dei byte</span><span class="sxs-lookup"><span data-stu-id="b3051-257">Endianness</span></span>

<span data-ttu-id="b3051-258">In .NET, le unità di codice string UTF-16 di un vengono archiviate nella memoria`char` contigua come sequenza di interi a 16 bit (istanze).</span><span class="sxs-lookup"><span data-stu-id="b3051-258">In .NET, the UTF-16 code units of a string are stored in contiguous memory as a sequence of 16-bit integers (`char` instances).</span></span> <span data-ttu-id="b3051-259">I bit delle singole unità di codice vengono disposti in base [all'endianness](https://en.wikipedia.org/wiki/Endianness) dell'architettura corrente.</span><span class="sxs-lookup"><span data-stu-id="b3051-259">The bits of individual code units are laid out according to the [endianness](https://en.wikipedia.org/wiki/Endianness) of the current architecture.</span></span>

<span data-ttu-id="b3051-260">In un'architettura little-endian, la string costituita dai `[ D801 DCCC ]` punti di codice UTF-16 sarebbe disposta in memoria come bytes `[ 0x01, 0xD8, 0xCC, 0xDC ]`.</span><span class="sxs-lookup"><span data-stu-id="b3051-260">On a little-endian architecture, the string consisting of the UTF-16 code points `[ D801 DCCC ]` would be laid out in memory as the bytes `[ 0x01, 0xD8, 0xCC, 0xDC ]`.</span></span> <span data-ttu-id="b3051-261">In un'architettura big-endian che lo stesso string sarebbe `[ 0xD8, 0x01, 0xDC, 0xCC ]`disposto in memoria come i byte .</span><span class="sxs-lookup"><span data-stu-id="b3051-261">On a big-endian architecture that same string would be laid out in memory as the bytes `[ 0xD8, 0x01, 0xDC, 0xCC ]`.</span></span>

<span data-ttu-id="b3051-262">I sistemi informatici che comunicano tra loro devono concordare la rappresentazione dei dati che attraversano la rete.</span><span class="sxs-lookup"><span data-stu-id="b3051-262">Computer systems that communicate with each other must agree on the representation of data crossing the wire.</span></span> <span data-ttu-id="b3051-263">La maggior parte dei protocolli di rete utilizza UTF-8 come standard durante la trasmissione di testo, in parte per evitare problemi che potrebbero derivare da una macchina big-endian che comunica con una macchina little-endian.</span><span class="sxs-lookup"><span data-stu-id="b3051-263">Most network protocols use UTF-8 as a standard when transmitting text, partly to avoid issues that might result from a big-endian machine communicating with a little-endian machine.</span></span> <span data-ttu-id="b3051-264">La string parte costituita dai `[ F0 90 93 8C ]` punti di codice UTF-8 verrà sempre rappresentata come byte `[ 0xF0, 0x90, 0x93, 0x8C ]` indipendentemente dall'endianness.</span><span class="sxs-lookup"><span data-stu-id="b3051-264">The string consisting of the UTF-8 code points `[ F0 90 93 8C ]` will always be represented as the bytes `[ 0xF0, 0x90, 0x93, 0x8C ]` regardless of endianness.</span></span>

<span data-ttu-id="b3051-265">Per utilizzare UTF-8 per la trasmissione di testo, le applicazioni .NET spesso utilizzano codice simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b3051-265">To use UTF-8 for transmitting text, .NET applications often use code like the following example:</span></span>

```csharp
string stringToWrite = GetString();
byte[] stringAsUtf8Bytes = Encoding.UTF8.GetBytes(stringToWrite);
await outputStream.WriteAsync(stringAsUtf8Bytes, 0, stringAsUtf8Bytes.Length);
```

<span data-ttu-id="b3051-266">Nell'esempio precedente, il metodo [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) decodifica nuovamente `string` UTF-16 in una serie di valori scalari Unicode, quindi ricodifica tali valori `byte` scalari in UTF-8 e inserisce la sequenza risultante in una matrice.</span><span class="sxs-lookup"><span data-stu-id="b3051-266">In the preceding example, the method [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) decodes the UTF-16 `string` back into a series of Unicode scalar values, then it re-encodes those scalar values into UTF-8 and places the resulting sequence into a `byte` array.</span></span> <span data-ttu-id="b3051-267">Il metodo [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) esegue la trasformazione opposta, convertendo una matrice UTF-8 `byte` in un oggetto UTF-16 `string`.</span><span class="sxs-lookup"><span data-stu-id="b3051-267">The method [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) performs the opposite transformation, converting a UTF-8 `byte` array to a UTF-16 `string`.</span></span>

> [!WARNING]
> <span data-ttu-id="b3051-268">Poiché UTF-8 è all'ordine del giorno su Internet, si può essere tentati di leggere i byte non elaborati dalla rete e di trattare i dati come se fossero UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b3051-268">Since UTF-8 is commonplace on the internet, it may be tempting to read raw bytes from the wire and to treat the data as if it were UTF-8.</span></span> <span data-ttu-id="b3051-269">Tuttavia, è necessario verificare che sia effettivamente ben formato.</span><span class="sxs-lookup"><span data-stu-id="b3051-269">However, you should validate that it is indeed well-formed.</span></span> <span data-ttu-id="b3051-270">Un client dannoso potrebbe inviare UTF-8 in formato non corretto al servizio.</span><span class="sxs-lookup"><span data-stu-id="b3051-270">A malicious client might submit ill-formed UTF-8 to your service.</span></span> <span data-ttu-id="b3051-271">Se si opera su tali dati come se fossero ben formati, potrebbe causare errori o problemi di sicurezza nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b3051-271">If you operate on that data as if it were well-formed, it could cause errors or security holes in your application.</span></span> <span data-ttu-id="b3051-272">Per convalidare i dati UTF-8, `Encoding.UTF8.GetString`è possibile utilizzare un metodo come `string`, che eseguirà la convalida durante la conversione dei dati in ingresso in un oggetto .</span><span class="sxs-lookup"><span data-stu-id="b3051-272">To validate UTF-8 data, you can use a method like `Encoding.UTF8.GetString`, which will perform validation while converting the incoming data to a `string`.</span></span>

### <a name="well-formed-encoding"></a><span data-ttu-id="b3051-273">Codifica ben formata</span><span class="sxs-lookup"><span data-stu-id="b3051-273">Well-formed encoding</span></span>

<span data-ttu-id="b3051-274">Una codifica Unicode ben string formata è una delle unità di codice che possono essere decodificate in modo inequivocabile e senza errori in una sequenza di valori scalari Unicode.</span><span class="sxs-lookup"><span data-stu-id="b3051-274">A well-formed Unicode encoding is a string of code units that can be decoded unambiguously and without error into a sequence of Unicode scalar values.</span></span> <span data-ttu-id="b3051-275">I dati ben formati possono essere transcodificati liberamente avanti e indietro tra UTF-8, UTF-16 e UTF-32.</span><span class="sxs-lookup"><span data-stu-id="b3051-275">Well-formed data can be transcoded freely back and forth between UTF-8, UTF-16, and UTF-32.</span></span>

<span data-ttu-id="b3051-276">La questione se una sequenza di codifica è ben formata o meno non è correlata all'endianness dell'architettura di una macchina.</span><span class="sxs-lookup"><span data-stu-id="b3051-276">The question of whether an encoding sequence is well-formed or not is unrelated to the endianness of a machine's architecture.</span></span> <span data-ttu-id="b3051-277">Una sequenza UTF-8 non formata è formata male nello stesso modo su entrambe le macchine big-endian e little-endian.</span><span class="sxs-lookup"><span data-stu-id="b3051-277">An ill-formed UTF-8 sequence is ill-formed in the same way on both big-endian and little-endian machines.</span></span>

<span data-ttu-id="b3051-278">Ecco alcuni esempi di codifiche in formato non corretto:Here are some examples of unl-formed encodings:</span><span class="sxs-lookup"><span data-stu-id="b3051-278">Here are some examples of ill-formed encodings:</span></span>

* <span data-ttu-id="b3051-279">In UTF-8, `[ 6C C2 61 ]` la sequenza non `C2` è formata perché non può essere seguita da `61`.</span><span class="sxs-lookup"><span data-stu-id="b3051-279">In UTF-8, the sequence `[ 6C C2 61 ]` is ill-formed because `C2` cannot be followed by `61`.</span></span>

* <span data-ttu-id="b3051-280">In UTF-16, `[ DC00 DD00 ]` la sequenza (o, string `"\udc00\udd00"`in C, il ) non `DC00` è formata perché `DD00`il surrogato basso non può essere seguito da un altro surrogato basso .</span><span class="sxs-lookup"><span data-stu-id="b3051-280">In UTF-16, the sequence `[ DC00 DD00 ]` (or, in C#, the string `"\udc00\udd00"`) is ill-formed because the low surrogate `DC00` cannot be followed by another low surrogate `DD00`.</span></span>

* <span data-ttu-id="b3051-281">In UTF-32, `[ 0011ABCD ]` la sequenza non `0011ABCD` è formata perché non rientra nell'intervallo dei valori scalari Unicode.</span><span class="sxs-lookup"><span data-stu-id="b3051-281">In UTF-32, the sequence `[ 0011ABCD ]` is ill-formed because `0011ABCD` is outside the range of Unicode scalar values.</span></span>

<span data-ttu-id="b3051-282">In .NET, `string` le istanze contengono quasi sempre dati UTF-16 ben formati, ma ciò non è garantito.</span><span class="sxs-lookup"><span data-stu-id="b3051-282">In .NET, `string` instances almost always contain well-formed UTF-16 data, but that isn't guaranteed.</span></span> <span data-ttu-id="b3051-283">Negli esempi seguenti viene illustrato un codice valido in C, `string` che crea dati UTF-16 in formato non corretto nelle istanze.</span><span class="sxs-lookup"><span data-stu-id="b3051-283">The following examples show valid C# code that creates ill-formed UTF-16 data in `string` instances.</span></span>

* <span data-ttu-id="b3051-284">Un valore letterale formato in modo non corretto:</span><span class="sxs-lookup"><span data-stu-id="b3051-284">An ill-formed literal:</span></span>

  ```csharp
  const string s = "\ud800";
  ```

* <span data-ttu-id="b3051-285">Sottostringa che divide una coppia di surrogati:</span><span class="sxs-lookup"><span data-stu-id="b3051-285">A substring that splits up a surrogate pair:</span></span>

  ```csharp
  string x = "\ud83e\udd70"; // "🥰"
  string y = x.Substring(1, 1); // "\udd70" standalone low surrogate
  ```

<span data-ttu-id="b3051-286">LE API [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) come non restituiscono `string` mai istanze in formato non corretto.</span><span class="sxs-lookup"><span data-stu-id="b3051-286">APIs like [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) never return ill-formed `string` instances.</span></span> <span data-ttu-id="b3051-287">`Encoding.GetString`e `Encoding.GetBytes` i metodi rilevano sequenze in formato non corretto nell'input ed eseguono la sostituzione dei caratteri durante la generazione dell'output.</span><span class="sxs-lookup"><span data-stu-id="b3051-287">`Encoding.GetString` and `Encoding.GetBytes` methods detect ill-formed sequences in the input and perform character substitution when generating the output.</span></span> <span data-ttu-id="b3051-288">Ad esempio, [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) se viene visualizzato un byte non ASCII nell'input (al di fuori dell'intervallo U-0000..U-007F), viene inserito un '?' nell'istanza restituita. `string`</span><span class="sxs-lookup"><span data-stu-id="b3051-288">For example, if [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) sees a non-ASCII byte in the input (outside the range U+0000..U+007F), it inserts a '?' into the returned `string` instance.</span></span> <span data-ttu-id="b3051-289">[`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A)sostituisce le sequenze UTF-8 `U+FFFD REPLACEMENT CHARACTER ('�')` in formato `string` non corretto con nell'istanza restituita.</span><span class="sxs-lookup"><span data-stu-id="b3051-289">[`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A) replaces ill-formed UTF-8 sequences with `U+FFFD REPLACEMENT CHARACTER ('�')` in the returned `string` instance.</span></span> <span data-ttu-id="b3051-290">Per ulteriori informazioni, vedere i prodotti [standard Unicode](https://www.unicode.org/versions/latest/), Sections 5.22 e 3.9.</span><span class="sxs-lookup"><span data-stu-id="b3051-290">For more information, see [the Unicode Standard](https://www.unicode.org/versions/latest/), Sections 5.22 and 3.9.</span></span>

<span data-ttu-id="b3051-291">Le `Encoding` classi predefinite possono anche essere configurate per generare un'eccezione anziché eseguire la sostituzione dei caratteri quando vengono visualizzate sequenze in formato non corretto.</span><span class="sxs-lookup"><span data-stu-id="b3051-291">The built-in `Encoding` classes can also be configured to throw an exception rather than perform character substitution when ill-formed sequences are seen.</span></span> <span data-ttu-id="b3051-292">Questo approccio viene spesso utilizzato in applicazioni sensibili alla sicurezza in cui la sostituzione dei caratteri potrebbe non essere accettabile.</span><span class="sxs-lookup"><span data-stu-id="b3051-292">This approach is often used in security-sensitive applications where character substitution might not be acceptable.</span></span>

```csharp
byte[] utf8Bytes = ReadFromNetwork();
UTF8Encoding encoding = new UTF8Encoding(encoderShouldEmitUTF8Identifier: false, throwOnInvalidBytes: true);
string asString = encoding.GetString(utf8Bytes); // will throw if 'utf8Bytes' is ill-formed
```

<span data-ttu-id="b3051-293">Per informazioni su come utilizzare `Encoding` le classi incorporate, vedere Come utilizzare le classi di [codifica dei caratteri in .NET.](character-encoding.md)</span><span class="sxs-lookup"><span data-stu-id="b3051-293">For information about how to use the built-in `Encoding` classes, see [How to use character encoding classes in .NET](character-encoding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b3051-294">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3051-294">See also</span></span>

- <xref:System.String>
- <xref:System.Char>
- <xref:System.Text.Rune>
- [<span data-ttu-id="b3051-295">Globalizzazione e localizzazione</span><span class="sxs-lookup"><span data-stu-id="b3051-295">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)
