---
title: Introduzione alla codifica di caratteri in .NET
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
ms.openlocfilehash: 086430a720e6dc7f39d459a4b99d5bbdb1cfcac3
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141297"
---
# <a name="character-encoding-in-net"></a>Codifica dei caratteri in .NET

Questo articolo fornisce un'introduzione ai sistemi di codifica dei caratteri usati da .NET. Questo articolo illustra come funzionano <xref:System.String>i <xref:System.Char>tipi <xref:System.Text.Rune>,, <xref:System.Globalization.StringInfo> e con Unicode, UTF-16 e UTF-8.

Il termine *carattere* viene usato in questo punto nel senso generale di *ciò che un lettore percepisce come un singolo elemento di visualizzazione*. Esempi comuni sono la lettera "a", il simbolo "@" e il emoji "🐂". In alcuni casi l'aspetto di un carattere è costituito da più elementi di visualizzazione indipendenti, come illustrato nella sezione dei [cluster grafema](#grapheme-clusters) .

## <a name="the-string-and-char-types"></a>Tipi stringa e carattere

Un'istanza della classe [String](xref:System.String) rappresenta il testo. Un `string` oggetto è logicamente una sequenza di valori a 16 bit, ciascuno dei quali è un'istanza dello struct [char](xref:System.Char) . [Stringa. ](xref:System.String.Length)La proprietà Length restituisce il numero `char` di istanze nell' `string` istanza di.

La funzione di esempio seguente stampa i valori in notazione esadecimale di tutte `char` le istanze in `string`un oggetto:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::

Passare la stringa "Hello" a questa funzione e ottenere l'output seguente:

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

Ogni carattere è rappresentato da un singolo `char` valore. Tale modello è valido per la maggior parte dei linguaggi del mondo. Ad esempio, di seguito è riportato l'output per due caratteri cinesi che suonano come *Nǐ hǎo* e Mean *Hello*:

```csharp
PrintChars("你好");
```

```output
"你好".Length = 2
s[0] = '你' ('\u4f60')
s[1] = '好' ('\u597d')
```

Tuttavia, per alcune lingue e per alcuni simboli e emoji, sono necessarie due `char` istanze per rappresentare un singolo carattere. Confrontare, ad esempio, i caratteri `char` e le istanze nella parola che significa *Osage* nella lingua Osage:

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

Nell'esempio precedente, ogni carattere eccetto lo spazio è rappresentato da due `char` istanze.

Un singolo emoji Unicode è rappresentato anche da due `char`, come illustrato nell'esempio seguente, che mostra il codice di un Emoji Ox:

```
"🐂".Length = 2
s[0] = '�' ('\ud83d')
s[1] = '�' ('\udc02')
```

In questi esempi viene illustrato che il `string.Length`valore di, che indica il `char` numero di istanze, non indica necessariamente il numero di caratteri visualizzati. Una sola `char` istanza di per sé non rappresenta necessariamente un carattere.

Le `char` coppie che eseguono il mapping a un singolo carattere sono denominate *coppie di surrogati*. Per comprendere il funzionamento, è necessario comprendere la codifica Unicode e UTF-16.

## <a name="unicode-code-points"></a>Punti di codice Unicode

Unicode è uno standard di codifica internazionale per l'uso su diverse piattaforme e con vari linguaggi e script.

Lo standard Unicode definisce oltre 1,1 milioni [punti di codice](https://www.unicode.org/glossary/#code_point). Un punto di codice è un valore intero che può variare da 0 `U+10FFFF` a (decimale 1.114.111). Alcuni punti di codice sono assegnati a lettere, simboli o emoji. Altri vengono assegnati alle azioni che controllano la modalità di visualizzazione di testo o caratteri, ad esempio l'avanzamento di una nuova riga. Molti punti di codice non sono ancora stati assegnati.

Di seguito sono riportati alcuni esempi di assegnazioni dei punti di codice, con collegamenti a grafici Unicode in cui vengono visualizzati:

|Decimal|Hex       |Esempio|Descrizione|
|------:|----------|-------|-----------|
|10     | `U+000A` |N/D| [AVANZAMENTO RIGA](https://www.unicode.org/charts/PDF/U0000.pdf) |
|65     | `U+0061` | a | [LETTERA LATINA MINUSCOLA A](https://www.unicode.org/charts/PDF/U0000.pdf) |
|562    | `U+0232` | Ȳ | [LETTERA LATINA MAIUSCOLA Y CON MACRON](https://www.unicode.org/charts/PDF/U0180.pdf) |
|68.675 | `U+10C43`| 𐱃 | [VECCHIA LETTERA TURCA ORKHON AT](https://www.unicode.org/charts/PDF/U10C00.pdf) |
|127.801| `U+1F339`| 🌹 | [ROSA emoji](https://www.unicode.org/charts/PDF/U1F300.pdf) |

I punti di codice sono abitualmente a cui si fa `U+xxxx`riferimento usando `xxxx` la sintassi, dove è il valore integer con codifica esadecimale.

All'interno dell'intera gamma di punti di codice sono presenti due intervalli secondari:

* Il **piano multilingue di base (BMP)** nell'intervallo `U+0000..U+FFFF`. Questo intervallo a 16 bit fornisce punti di codice 65.536, sufficienti per coprire la maggior parte dei sistemi di scrittura del mondo.
* **Punti di codice supplementari** nell'intervallo `U+10000..U+10FFFF`. Questo intervallo a 21 bit offre più di un milione di punti di codice aggiuntivi che possono essere usati per linguaggi meno noti e altri scopi, ad esempio emoji.

Il diagramma seguente illustra la relazione tra il BMP e i punti di codice supplementari.

:::image type="content" source="media/character-encoding-introduction/bmp-and-supplementary.svg" alt-text="BMP e punti di codice supplementari":::

## <a name="utf-16-code-units"></a>Unità di codice UTF-16

Unicode Transformation Format ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) a 16 bit è un sistema di codifica caratteri che usa unità di *codice* a 16 bit per rappresentare i punti di codice Unicode. .NET usa UTF-16 per codificare il testo in `string`un oggetto. Un' `char` istanza rappresenta un'unità di codice a 16 bit.

Una singola unità di codice a 16 bit può rappresentare qualsiasi punto di codice nell'intervallo a 16 bit del piano multilingue di base. Tuttavia, per un punto di codice nell'intervallo supplementare, sono `char` necessarie due istanze.

## <a name="surrogate-pairs"></a>Coppie di surrogati

La conversione dei valori a 2 16 bit in un singolo valore a 21 bit viene facilitata da un intervallo speciale denominato *punti di codice surrogato*, `U+D800` da `U+DFFF` a (decimale da 55.296 a 57.343), inclusi.

Il diagramma seguente illustra la relazione tra il BMP e i punti di codice surrogati.

:::image type="content" source="media/character-encoding-introduction/bmp-and-surrogate.svg" alt-text="Punti di codice BMP e surrogati":::

Quando un punto di codice *surrogato alto* (`U+D800..U+DBFF`) è immediatamente seguito da un punto di codice`U+DC00..U+DFFF` *surrogato basso* (), la coppia viene interpretata come punto di codice supplementare usando la formula seguente:

```
code point = 0x10000 +
  ((high surrogate code point - 0xD800) * 0x0400) +
  (low surrogate code point - 0xDC00)
```

Di seguito è illustrata la stessa formula con la notazione decimale:

```
code point = 65,536 +
  ((high surrogate code point - 55,296) * 1,024) +
  (low surrogate code point - 56,320)
```

Un punto di codice surrogato *alto* non ha un valore numerico più elevato rispetto a un punto di codice surrogato *basso* . Il punto di codice surrogato alto è denominato "High" perché viene usato per calcolare gli 11 bit di ordine superiore dell'intervallo completo di punti di codice a 21 bit. Il punto di codice surrogato basso viene usato per calcolare i 10 bit di ordine inferiore.

Ad esempio, il punto di codice effettivo che corrisponde alla coppia `0xD83C` di surrogati e `0xDF39` viene calcolato come segue:

```
actual = 0x10000 + ((0xD83C - 0xD800) * 0x0400) + (0xDF39 - 0xDC00)
       = 0x10000 + (          0x003C  * 0x0400) +           0x0339
       = 0x10000 +                      0xF000  +           0x0339
       = 0x1F339
```

Di seguito è riportato lo stesso calcolo con la notazione decimale:

```
actual =  65,536 + ((55,356 - 55,296) * 1,024) + (57,145 - 56320)
       =  65,536 + (              60  * 1,024) +             825
       =  65,536 +                     61,440  +             825
       = 127,801
```

L'esempio precedente dimostra che `"\ud83c\udf39"` è la codifica UTF-16 del punto `U+1F339 ROSE ('🌹')` di codice indicato in precedenza.

## <a name="unicode-scalar-values"></a>Valori scalari Unicode

Il termine [valore scalare Unicode](https://www.unicode.org/glossary/#unicode_scalar_value) si riferisce a tutti i punti di codice diversi dai punti di codice surrogati. In altre parole, un valore scalare è qualsiasi punto di codice a cui viene assegnato un carattere o a cui può essere assegnato un carattere in futuro. "Character" si riferisce a qualsiasi elemento che può essere assegnato a un punto di codice, che include elementi come azioni che controllano la modalità di visualizzazione del testo o dei caratteri.

Il diagramma seguente illustra i punti di codice valore scalare.

:::image type="content" source="media/character-encoding-introduction/scalar-values.svg" alt-text="Valori scalari":::

### <a name="the-opno-locrune-type-as-a-scalar-value"></a>Rune Tipo come valore scalare

A partire da .NET Core 3,0, <xref:System.Text.Rune?displayProperty=fullName> il tipo rappresenta un valore scalare Unicode. **`Rune`non è disponibile in .NET Core 2. x o .NET Framework 4. x.**

I `Rune` costruttori convalidano che l'istanza risultante sia un valore scalare Unicode valido; in caso contrario, generano un'eccezione. Nell'esempio seguente viene illustrato il codice che crea `Rune` correttamente le istanze di perché l'input rappresenta valori scalari validi:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetValid":::

Nell'esempio seguente viene generata un'eccezione perché il punto di codice si trova nell'intervallo di surrogati e non fa parte di una coppia di surrogati:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidSurrogate":::

Nell'esempio seguente viene generata un'eccezione perché il punto di codice è oltre l'intervallo supplementare:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidHigh":::

### <a name="opno-locrune-usage-example-changing-letter-case"></a>Runeesempio di utilizzo: modifica della lettera maiuscola

Un'API che accetta un `char` oggetto e presuppone che funzioni con un punto di codice che è un valore scalare non funzioni correttamente `char` se è da una coppia di surrogati. Si consideri, ad esempio, il <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> metodo seguente char che chiama stringsu ogni in un:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::

`input` string Se contiene la lettera `er` Deseret minuscola (`𐑉`), questo codice non lo convertirà in maiuscolo`𐐡`(). Il codice chiama `char.ToUpperInvariant` separatamente per ogni punto di codice `U+D801` surrogato `U+DC49`, e. Ma `U+D801` non dispone di informazioni sufficienti per identificarlo come lettera minuscola, quindi `char.ToUpperInvariant` lasciarlo invariato. E gestisce `U+DC49` lo stesso modo. Il risultato è che il minuscolo ' 𐑉' `input` string in non viene convertito in maiuscolo ' 𐑉'.

Ecco due opzioni per la conversione corretta di string un in maiuscolo:

* Chiamare <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> sull'input string invece che su iteration `char`-by`char`-. Il `string.ToUpperInvariant` metodo ha accesso a entrambe le parti di ogni coppia di surrogati, in modo che sia in grado di gestire correttamente tutti i punti di codice Unicode.
* Scorrere i valori scalari Unicode come `Rune` istanze anziché come `char` istanze, come illustrato nell'esempio seguente. Poiché un' `Rune` istanza è un valore scalare Unicode valido, può essere passata alle API che prevedono l'utilizzo di un valore scalare. Ad esempio, la <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType> chiamata a come illustrato nell'esempio seguente restituisce i risultati corretti:

  :::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::

### <a name="other-opno-locrune-apis"></a>Altre Rune API

Il `Rune` tipo espone gli analoghi di molte `char` API. Ad esempio, i metodi seguenti rispecchiano le API `char` statiche nel tipo:

* <xref:System.Text.Rune.IsLetter%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsWhiteSpace%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsLetterOrDigit%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.GetUnicodeCategory%2A?displayProperty=nameWithType>

Per ottenere il valore scalare non elaborato `Rune` da un'istanza di <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType> , utilizzare la proprietà.

Per riconvertire `Rune` un'istanza di in una sequenza `char`di s, <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> utilizzare o <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType> il metodo.

Poiché qualsiasi valore scalare Unicode è rappresentabile da un singolo `char` o da una coppia di surrogati `Rune` , qualsiasi istanza può essere rappresentata da `char` al massimo 2 istanze. Utilizzare <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType> per visualizzare il numero `char` di istanze necessarie per rappresentare un' `Rune` istanza di.

Per ulteriori informazioni sul tipo .NET `Rune` , vedere le [ `Rune` ](xref:System.Text.Rune)informazioni di riferimento sulle API.

## <a name="grapheme-clusters"></a>Cluster grafema

Un aspetto simile a un carattere può essere causato da una combinazione di più punti di codice, quindi un termine più descrittivo spesso usato al posto di "character" è il [cluster grafema](https://www.unicode.org/glossary/#grapheme_cluster). Il termine equivalente in .NET è un [elemento di testo](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).

Prendere in `string` considerazione le istanze "a", "á". "á" e "`👩🏽‍🚒`". Se il sistema operativo li gestisce come specificato dallo standard Unicode, ognuna di queste `string` istanze viene visualizzata come un singolo elemento di testo o cluster grafema. Tuttavia, gli ultimi due sono rappresentati da più di un punto di codice valore scalare.

* string "A" è rappresentato da un valore scalare e contiene un' `char` istanza.

  * `U+0061 LATIN SMALL LETTER A`

* string "Á" è rappresentato da un valore scalare e contiene un' `char` istanza.

  * `U+00E1 LATIN SMALL LETTER A WITH ACUTE`

* string "Á" ha lo stesso aspetto di "á" ma è rappresentato da due valori scalari e contiene `char` due istanze.

  * `U+0065 LATIN SMALL LETTER A`
  * `U+0301 COMBINING ACUTE ACCENT`

* Infine, string "`👩🏽‍🚒`" è rappresentato da quattro valori scalari e contiene sette `char` istanze.

  * `U+1F469 WOMAN`(intervallo supplementare, richiede una coppia di surrogati)
  * `U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4`(intervallo supplementare, richiede una coppia di surrogati)
  * `U+200D ZERO WIDTH JOINER`
  * `U+1F692 FIRE ENGINE`(intervallo supplementare, richiede una coppia di surrogati)

In alcuni degli esempi precedenti, ad esempio il modificatore dell'accento di combinazione o il modificatore del tono della pelle, il punto di codice non viene visualizzato come elemento autonomo sullo schermo. Piuttosto, serve a modificare l'aspetto di un elemento di testo che è stato prima di esso. Questi esempi mostrano che è possibile che vengano accettati più valori scalari per creare quello che consideriamo come un singolo "carattere" o "cluster grafema".

Per enumerare i cluster grafema di un `string`, usare la <xref:System.Globalization.StringInfo> classe come illustrato nell'esempio seguente. Se si ha familiarità con Swift, il `StringInfo` tipo .NET è concettualmente simile al [ `character` tipo di Swift](https://developer.apple.com/documentation/swift/character).

### <a name="example-count-opno-locchar-opno-locrune-and-text-element-instances"></a>Esempio: Count char, Runee istanze di elementi di testo

Nelle API .NET un cluster grafema viene chiamato elemento di *testo*. Il metodo seguente illustra le differenze tra `char`le `Rune`istanze di elementi di testo, e `string`in un oggetto:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::

Se si esegue questo codice in .NET Framework o .NET Core 3,1 o versioni precedenti, viene visualizzato `4`il numero di elementi di testo per emoji. Ciò è dovuto a un bug della `StringInfo` classe che è stato risolto in .NET 5.

### <a name="example-splitting-opno-locstring-instances"></a>Esempio: suddivisione di string istanze

Per suddividere `string` le istanze, evitare di suddividere coppie di surrogati e cluster grafema. Si consideri l'esempio seguente di codice errato, che prevede l'inserimento di interruzioni di riga ogni string10 caratteri in un:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::

Poiché questo codice enumera le `char` istanze, una coppia di surrogati che viene eseguita a cavalcioni di`char` un limite di 10 verrà divisa e verrà inserita una nuova riga tra di essi. Questo inserimento introduce il danneggiamento dei dati, perché i punti di codice surrogati sono significativi solo come coppie.

Il rischio di danneggiamento dei dati non viene eliminato `Rune` se si enumerano le istanze ( `char` valori scalari) anziché le istanze. Un set di `Rune` istanze può costituire un cluster grafema che si riferisce a`char` un limite di 10. Se il set di cluster grafema è suddiviso, non può essere interpretato correttamente.

Un approccio migliore consiste nel suddividere string il conteggio dei cluster grafema o degli elementi di testo, come nell'esempio seguente:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::

Come indicato in precedenza, tuttavia, nelle implementazioni di .NET diverse da .NET 5 la `StringInfo` classe potrebbe gestire in modo errato alcuni cluster grafema.

## <a name="utf-8-and-utf-32"></a>UTF-8 e UTF-32

Le sezioni precedenti hanno incentrato sulla codifica UTF-16, in quanto .NET `string` USA per codificare le istanze. Sono disponibili altri sistemi di codifica per Unicode- [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) e [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32). Queste codifiche utilizzano rispettivamente unità di codice a 8 bit e unità di codice a 32 bit.

Analogamente a UTF-16, UTF-8 richiede più unità di codice per rappresentare alcuni valori scalari Unicode. UTF-32 può rappresentare qualsiasi valore scalare in una singola unità di codice a 32 bit.

Di seguito sono riportati alcuni esempi che illustrano come viene rappresentato lo stesso punto di codice Unicode in ognuno dei tre sistemi di codifica Unicode seguenti:

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

Come indicato in precedenza, una singola unità di codice UTF-16 da una [coppia di surrogati](#surrogate-pairs) non ha alcun significato. Allo stesso modo, una singola unità di codice UTF-8 non ha significato da solo se si trova in una sequenza di due, tre o quattro usati per calcolare un valore scalare.

### <a name="endianness"></a>Ordine dei byte

In .NET le unità di codice UTF-16 di un string vengono archiviate in memoria contigua come sequenza di interi a 16 bit`char` (istanze). I bit delle singole unità di codice sono disposti in base alla [caratteristica](https://en.wikipedia.org/wiki/Endianness) dell'architettura corrente.

In un'architettura little endian, il string costituito dai punti `[ D801 DCCC ]` di codice UTF-16 verrebbe disposto in memoria come byte. `[ 0x01, 0xD8, 0xCC, 0xDC ]` In un'architettura big-endian lo stesso string sarebbe disposto in memoria come byte `[ 0xD8, 0x01, 0xDC, 0xCC ]`.

I sistemi informatici che comunicano tra loro devono accettare la rappresentazione dei dati attraverso la rete. La maggior parte dei protocolli di rete usa UTF-8 come standard per la trasmissione di testo, in parte per evitare problemi che potrebbero derivare da una macchina big endian che comunica con un computer little-endian. L' string oggetto costituito dai punti `[ F0 90 93 8C ]` di codice UTF-8 sarà sempre rappresentato come byte `[ 0xF0, 0x90, 0x93, 0x8C ]` indipendentemente dall'ordine di utilizzo.

Per usare UTF-8 per la trasmissione di testo, le applicazioni .NET usano spesso codice come l'esempio seguente:

```csharp
string stringToWrite = GetString();
byte[] stringAsUtf8Bytes = Encoding.UTF8.GetBytes(stringToWrite);
await outputStream.WriteAsync(stringAsUtf8Bytes, 0, stringAsUtf8Bytes.Length);
```

Nell'esempio precedente, il metodo [Encoding. UTF8. GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) decodifica la codifica UTF-16 `string` in una serie di valori scalari Unicode, quindi codifica di nuovo i valori scalari in UTF-8 e inserisce la sequenza risultante in una `byte` matrice. Il metodo [Encoding. UTF8. GetString](xref:System.Text.UTF8Encoding.GetString%2A) esegue la trasformazione opposta, convertendo una matrice `byte` UTF-8 in UTF- `string`16.

> [!WARNING]
> Poiché UTF-8 è comune su Internet, è possibile che si stia tentando di leggere i byte non elaborati dalla rete e di trattare i dati come se fossero UTF-8. Tuttavia, è necessario verificare che sia effettivamente formato correttamente. Un client malintenzionato potrebbe inviare il formato UTF-8 non valido al servizio. Se si opera su tali dati come se fossero ben formati, potrebbero verificarsi errori o buchi di sicurezza nell'applicazione. Per convalidare i dati UTF-8, è possibile usare `Encoding.UTF8.GetString`un metodo come, che eseguirà la convalida durante la conversione dei `string`dati in ingresso in un oggetto.

### <a name="well-formed-encoding"></a>Codifica ben formata

Una codifica Unicode ben formata è un' string unità di codice che può essere decodificata in modo non ambiguo e senza errori in una sequenza di valori scalari Unicode. I dati ben formati possono essere transcodificati liberamente tra UTF-8, UTF-16 e UTF-32.

Se una sequenza di codifica è ben formata o meno, non è correlata all'espressione dell'architettura di un computer. Una sequenza UTF-8 in formato non corretto è mal formata in modo analogo sia nei computer big endian che in quelli little-endian.

Di seguito sono riportati alcuni esempi di codifiche con formato non valido:

* In UTF-8 la sequenza `[ 6C C2 61 ]` non è in formato corretto perché `C2` non può essere seguita `61`da.

* In UTF-16 `[ DC00 DD00 ]` la sequenza (o, in C#, string `"\udc00\udd00"`) non è in formato corretto perché il surrogato `DC00` basso non può essere seguito da un altro `DD00`surrogato basso.

* In UTF-32 la sequenza `[ 0011ABCD ]` non è in formato corretto perché `0011ABCD` non è compresa nell'intervallo dei valori scalari Unicode.

In .NET le `string` istanze contengono quasi sempre dati UTF-16 ben formati, ma ciò non è garantito. Negli esempi seguenti viene illustrato il codice C# valido che consente di creare dati UTF-16 `string` in formato non corretto nelle istanze di.

* Valore letterale con formato non valido:

  ```csharp
  const string s = "\ud800";
  ```

* Una sottostringa che suddivide una coppia di surrogati:

  ```csharp
  string x = "\ud83e\udd70"; // "🥰"
  string y = x.Substring(1, 1); // "\udd70" standalone low surrogate
  ```

API come [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) non restituiscono mai istanze `string` con formato non valido. `Encoding.GetString`i `Encoding.GetBytes` metodi e rilevano sequenze in formato non corretto nell'input ed eseguono la sostituzione dei caratteri durante la generazione dell'output. Se [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) , ad esempio, rileva un byte non ASCII nell'input (al di fuori dell'intervallo u + 0000.. U + 007F), inserisce un'?' nell'istanza restituita `string` . [`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A)sostituisce le sequenze UTF-8 con formato non valido `U+FFFD REPLACEMENT CHARACTER ('�')` con nell'istanza `string` restituita. Per ulteriori informazioni, vedere le sezioni 5,22 e 3,9 [dello standard Unicode](https://www.unicode.org/versions/latest/).

Le `Encoding` classi predefinite possono anche essere configurate in modo da generare un'eccezione anziché eseguire la sostituzione dei caratteri quando vengono visualizzate sequenze in formato non valido. Questo approccio viene spesso usato nelle applicazioni sensibili alla sicurezza, in cui la sostituzione dei caratteri potrebbe non essere accettabile.

```csharp
byte[] utf8Bytes = ReadFromNetwork();
UTF8Encoding encoding = new UTF8Encoding(encoderShouldEmitUTF8Identifier: false, throwOnInvalidBytes: true);
string asString = encoding.GetString(utf8Bytes); // will throw if 'utf8Bytes' is ill-formed
```

Per informazioni sull'uso delle `Encoding` classi predefinite, vedere [come usare le classi di codifica dei caratteri in .NET](character-encoding.md).

## <a name="see-also"></a>Vedi anche

- <xref:System.String>
- <xref:System.Char>
- <xref:System.Text.Rune>
- [Globalizzazione e localizzazione](../../../docs/standard/globalization-localization/index.md)
