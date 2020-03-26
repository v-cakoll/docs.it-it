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
# <a name="character-encoding-in-net"></a>Codifica dei caratteri in .NET

In questo articolo viene fornita un'introduzione ai sistemi di codifica dei caratteri utilizzati da .NET. Nell'articolo viene <xref:System.String>illustrato <xref:System.Char> <xref:System.Text.Rune>il <xref:System.Globalization.StringInfo> funzionamento dei tipi , , e con Unicode, UTF-16 e UTF-8.

Il termine *carattere* viene utilizzato qui nel senso generale di *ciò che un lettore percepisce come un singolo elemento di visualizzazione*. Esempi comuni sono la lettera "a", il simbolo🐂"" e l'emoji " ". A volte ciò che sembra un carattere è in realtà composto da più elementi di visualizzazione indipendenti, come spiega la sezione sui [cluster di grafemi.](#grapheme-clusters)

## <a name="the-string-and-char-types"></a>I tipi string e char

Un'istanza della classe [string](xref:System.String) rappresenta del testo. A `string` è logicamente una sequenza di valori a 16 bit, ognuno dei quali è un'istanza della struttura [char.](xref:System.Char) [Stringa. Proprietà Length](xref:System.String.Length) restituisce `char` il `string` numero di istanze nell'istanza.

La seguente funzione di esempio stampa i valori in notazione esadecimale di tutte le `char` istanze in un: `string`

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::

Passare la stringa "Hello" a questa funzione e ottenere l'output seguente:Pass the string "Hello" to this function, and you get the following output:

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

Ogni carattere è `char` rappresentato da un singolo valore. Questo schema vale per la maggior parte delle lingue del mondo. Ad esempio, ecco l'output per due caratteri cinesi che suonano come *n ' h 'o* e significa *Ciao*:

```csharp
PrintChars("你好");
```

```output
"你好".Length = 2
s[0] = '你' ('\u4f60')
s[1] = '好' ('\u597d')
```

Tuttavia, per alcune lingue e per alcuni `char` simboli ed emoji, sono necessarie due istanze per rappresentare un singolo carattere. Ad esempio, confrontare `char` i caratteri e le istanze nella parola che indica *Osage* nella lingua di Osage:

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

Nell'esempio precedente, ogni carattere ad eccezione dello spazio è rappresentato da due `char` istanze.

Una singola emoji Unicode è `char`rappresentata anche da due s, come si vede nell'esempio seguente che mostra un emoji bue:

```
"🐂".Length = 2
s[0] = '�' ('\ud83d')
s[1] = '�' ('\udc02')
```

In questi esempi viene `string.Length`mostrato che il `char` valore di , che indica il numero di istanze, non indica necessariamente il numero di caratteri visualizzati. Una `char` singola istanza da sola non rappresenta necessariamente un carattere.

Le `char` coppie che eseguono il mapping a un singolo carattere sono *denominate coppie di surrogati*. Per capire come funzionano, è necessario comprendere la codifica Unicode e UTF-16.

## <a name="unicode-code-points"></a>Punti di codice Unicode

Unicode è uno standard di codifica internazionale per l'uso su varie piattaforme e con varie lingue e script.

Lo standard Unicode definisce oltre 1,1 milioni di [punti di codice.](https://www.unicode.org/glossary/#code_point) Un punto di codice è un valore `U+10FFFF` intero compreso tra 0 e (decimale 1.114.111). Alcuni punti di codice vengono assegnati a lettere, simboli o emoji. Altri vengono assegnati ad azioni che controllano la modalità di visualizzazione del testo o dei caratteri, ad esempio l'avanzamento a una nuova riga. Molti punti di codice non sono ancora assegnati.

Di seguito sono riportati alcuni esempi di assegnazioni di punti di codice, con collegamenti a i grafici Unicode in cui vengono visualizzati:Here are some examples of code point assignments, with links to Unicode charts in which they appear:

|Decimal|Hex       |Esempio|Descrizione|
|------:|----------|-------|-----------|
|10     | `U+000A` |N/D| [AVANZAMENTO RIGA](https://www.unicode.org/charts/PDF/U0000.pdf) |
|65     | `U+0061` | a | [LATIN SMALL LETTER A](https://www.unicode.org/charts/PDF/U0000.pdf) |
|562    | `U+0232` | <a0>T | [LATIN MAIUSCOL ODMAIUSCOLO Con MACRON](https://www.unicode.org/charts/PDF/U0180.pdf) |
|68,675 | `U+10C43`| 𐱃 | [OLD TURKIC LETTER ORKHON AT](https://www.unicode.org/charts/PDF/U10C00.pdf) |
|127,801| `U+1F339`| 🌹 | [EMOJI ROSA](https://www.unicode.org/charts/PDF/U1F300.pdf) |

I punti di codice vengono in genere `U+xxxx`indicati utilizzando la sintassi , dove `xxxx` è il valore intero con codifica esadecimale.

All'interno dell'intera gamma di punti di codice ci sono due intervalli secondari:

* Il **piano multilingue di base (BMP)** nell'intervallo `U+0000..U+FFFF`. Questa gamma a 16 bit fornisce 65.536 punti di codice, sufficienti a coprire la maggior parte dei sistemi di scrittura del mondo.
* **Punti di codice supplementari** nell'intervallo `U+10000..U+10FFFF`. Questo intervallo a 21 bit fornisce più di un milione di punti di codice aggiuntivi che possono essere utilizzati per lingue meno conosciute e altri scopi come emoji.

Il diagramma seguente illustra la relazione tra il BMP e i punti di codice supplementari.

:::image type="content" source="media/character-encoding-introduction/bmp-and-supplementary.svg" alt-text="Punti BMP e codice supplementare":::

## <a name="utf-16-code-units"></a>Unità di codice UTF-16

Il formato di trasformazione Unicode a 16 bit ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) è un sistema di codifica dei caratteri che utilizza unità di *codice* a 16 bit per rappresentare i punti di codice Unicode. .NET utilizza UTF-16 per codificare `string`il testo in un oggetto . Un'istanza `char` rappresenta un'unità di codice a 16 bit.

Una singola unità di codice a 16 bit può rappresentare qualsiasi punto di codice nell'intervallo a 16 bit del piano multilingue di base. Ma per un punto di codice `char` nell'intervallo supplementare, sono necessarie due istanze.

## <a name="surrogate-pairs"></a>Coppie di surrogati

La conversione di due valori a 16 bit in un singolo valore a 21 bit `U+D800` `U+DFFF` è facilitata da un intervallo speciale denominato punti di *codice surrogato,* da (decimale 55.296 a 57.343), inclusivo.

Il diagramma seguente illustra la relazione tra BMP e i punti di codice surrogati.

:::image type="content" source="media/character-encoding-introduction/bmp-and-surrogate.svg" alt-text="Punti di codice BMP e surrogati":::

Quando un punto di`U+D800..U+DBFF`codice surrogato alto ( ) viene`U+DC00..U+DFFF`immediatamente seguito da un punto di codice *surrogato basso* ( ), la coppia viene interpretata come un punto di codice *supplementare* utilizzando la formula seguente:

```
code point = 0x10000 +
  ((high surrogate code point - 0xD800) * 0x0400) +
  (low surrogate code point - 0xDC00)
```

Ecco la stessa formula che usa la notazione decimale:

```
code point = 65,536 +
  ((high surrogate code point - 55,296) * 1,024) +
  (low surrogate code point - 56,320)
```

Un punto di codice surrogato *alto* non ha un valore numerico più alto di un punto di codice surrogato *basso.* Il punto di codice surrogato alto viene chiamato "alto" perché viene utilizzato per calcolare gli 11 bit di ordine superiore dell'intero intervallo di punti di codice a 21 bit. Il punto di codice surrogato basso viene utilizzato per calcolare i 10 bit di ordine inferiore.

Ad esempio, il punto di codice effettivo `0xD83C` `0xDF39` che corrisponde alla coppia di surrogati e viene calcolato come segue:

```
actual = 0x10000 + ((0xD83C - 0xD800) * 0x0400) + (0xDF39 - 0xDC00)
       = 0x10000 + (          0x003C  * 0x0400) +           0x0339
       = 0x10000 +                      0xF000  +           0x0339
       = 0x1F339
```

Ecco lo stesso calcolo utilizzando la notazione decimale:

```
actual =  65,536 + ((55,356 - 55,296) * 1,024) + (57,145 - 56320)
       =  65,536 + (              60  * 1,024) +             825
       =  65,536 +                     61,440  +             825
       = 127,801
```

Nell'esempio precedente `"\ud83c\udf39"` viene illustrato che è la `U+1F339 ROSE ('🌹')` codifica UTF-16 del punto di codice menzionato in precedenza.

## <a name="unicode-scalar-values"></a>Valori scalari Unicode

Il termine [valore scalare Unicode](https://www.unicode.org/glossary/#unicode_scalar_value) fa riferimento a tutti i punti di codice diversi dai punti di codice surrogati. In altre parole, un valore scalare è qualsiasi punto di codice a cui viene assegnato un carattere o a cui è possibile assegnare un carattere in futuro. "Carattere" qui si riferisce a tutto ciò che può essere assegnato a un punto di codice, che include elementi quali azioni che controllano la modalità di visualizzazione del testo o dei caratteri.

Il diagramma seguente illustra i punti di codice del valore scalare.

:::image type="content" source="media/character-encoding-introduction/scalar-values.svg" alt-text="Valori scalari":::

### <a name="the-opno-locrune-type-as-a-scalar-value"></a>Il Rune tipo come valore scalare

A partire da .NET Core <xref:System.Text.Rune?displayProperty=fullName> 3.0, il tipo rappresenta un valore scalare Unicode.Beginning with .NET Core 3.0, the type represents a Unicode scalar value. **`Rune`non è disponibile in .NET Core 2.x o .NET Framework 4.x.**

I `Rune` costruttori convalidano che l'istanza risultante sia un valore scalare Unicode valido, in caso contrario generano un'eccezione. L'esempio seguente mostra il `Rune` codice che crea correttamente un'istanza delle istanze perché l'input rappresenta valori scalari validi:The following example shows code that successfully instantiates instances because the input represents valid scalar values:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetValid":::

L'esempio seguente genera un'eccezione perché il punto di codice è nell'intervallo di surrogati e non fa parte di una coppia di surrogati:The following example throws an exception because the code point is in the surrogate range and isn't part of a surrogate pair:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidSurrogate":::

Nell'esempio seguente viene generata un'eccezione perché il punto di codice non rientra nell'intervallo supplementare:The following example throws an exception because the code point is beyond the supplementary range:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidHigh":::

### <a name="opno-locrune-usage-example-changing-letter-case"></a>Runeesempio di utilizzo: modifica della custodia per lettere

Un'API che `char` accetta un e presuppone che stia lavorando con un punto di `char` codice che è un valore scalare non funziona correttamente se l'è da una coppia di surrogati. Si consideri, ad esempio, char il stringmetodo seguente che chiama <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> ciascuno in un:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::

`input` string Se contiene la lettera `er` Deseret`𐑉`minuscola ( ), questo codice`𐐡`non la convertirà in maiuscolo ( ). Il codice `char.ToUpperInvariant` chiama separatamente su `U+D801` ogni `U+DC49`punto di codice surrogato e . Ma `U+D801` non ha abbastanza informazioni da solo per identificarlo `char.ToUpperInvariant` come una lettera minuscola, quindi lascialo solo. E gestisce `U+DC49` allo stesso modo. Il risultato è che il `input` string valore minuscolo ''' nella casella non viene convertito in lettere maiuscole '''.

Di seguito sono riportate string due opzioni per convertire correttamente una caratteri maiuscola:

* Chiamata <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> all'input string anziché `char`iterare`char`-by- . Il `string.ToUpperInvariant` metodo ha accesso a entrambe le parti di ogni coppia di surrogati, in modo da poter gestire correttamente tutti i punti di codice Unicode.The method has access to both parts of each surrogate pair, so it can handle all Unicode code points correctly.
* Scorrere i valori scalari `Rune` Unicode `char` come istanze anziché come istanze, come illustrato nell'esempio seguente. Poiché `Rune` un'istanza è un valore scalare Unicode valido, può essere passata alle API che prevedono di operare su un valore scalare. Ad esempio, <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType> la chiamata come illustrato nell'esempio seguente fornisce risultati corretti:For example, calling as shown in the following example gives correct results:

  :::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::

### <a name="other-opno-locrune-apis"></a>Altre Rune API

Il `Rune` tipo espone analoghi di `char` molte delle API. Ad esempio, i metodi seguenti rispecchiano le API statiche sul tipo:For example, the following methods mirror static APIs on the `char` type:

* <xref:System.Text.Rune.IsLetter%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsWhiteSpace%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsLetterOrDigit%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.GetUnicodeCategory%2A?displayProperty=nameWithType>

Per ottenere il valore scalare non elaborato da un'istanza, `Rune` usare la <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType> proprietà .

`Rune` Per riconvertire un'istanza `char`in una <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> sequenza di s, utilizzare o il <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType> metodo .

Poiché qualsiasi valore scalare Unicode `char` è rappresentabile da una `Rune` singola o da una `char` coppia di surrogati, qualsiasi istanza può essere rappresentata al massimo da 2 istanze. Utilizzare <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType> per vedere `char` quante istanze `Rune` sono necessarie per rappresentare un'istanza.

Per ulteriori informazioni sul `Rune` tipo .NET, vedere le [ `Rune` informazioni](xref:System.Text.Rune)di riferimento sulle API .

## <a name="grapheme-clusters"></a>Cluster di grafemi

L'aspetto di un carattere potrebbe derivare da una combinazione di più punti di codice, pertanto un termine più descrittivo che viene spesso utilizzato al posto di "carattere" è cluster di [grafemi](https://www.unicode.org/glossary/#grapheme_cluster). Il termine equivalente in .NET è elemento di [testo](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).

Considerare `string` le istanze "a", "z". "" e "`👩🏽‍🚒`". Se il sistema operativo li gestisce come specificato `string` dallo standard Unicode, ognuna di queste istanze viene visualizzata come un singolo elemento di testo o cluster di grafemi. Ma gli ultimi due sono rappresentati da più di un punto di codice di valore scalare.

* La string "a" è rappresentata da un `char` valore scalare e contiene un'istanza.

  * `U+0061 LATIN SMALL LETTER A`

* La string "z" è rappresentata da un `char` valore scalare e contiene un'istanza.

  * `U+00E1 LATIN SMALL LETTER E WITH ACUTE`

* Il string valore di "z" ha lo stesso aspetto di "" `char` ma è rappresentato da due valori scalari e contiene due istanze.

  * `U+0065 LATIN SMALL LETTER A`
  * `U+0301 COMBINING ACUTE ACCENT`

* Infine, string il`👩🏽‍🚒`" " è rappresentato da `char` quattro valori scalari e contiene sette istanze.

  * `U+1F469 WOMAN`(intervallo supplementare, richiede una coppia di surrogati)
  * `U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4`(intervallo supplementare, richiede una coppia di surrogati)
  * `U+200D ZERO WIDTH JOINER`
  * `U+1F692 FIRE ENGINE`(intervallo supplementare, richiede una coppia di surrogati)

In alcuni degli esempi precedenti, ad esempio il modificatore di accento combinato o il modificatore del tono della pelle, il punto di codice non viene visualizzato come elemento autonomo sullo schermo. Piuttosto, serve a modificare l'aspetto di un elemento di testo che è venuto prima di esso. Questi esempi mostrano che potrebbero essere presenti più valori scalari per costituiscono quelli che consideriamo un singolo "carattere" o "cluster di grafici".

Per enumerare i cluster di `string`grafemi di un oggetto , utilizzare la <xref:System.Globalization.StringInfo> classe come illustrato nell'esempio seguente. Se si ha familiarità con `StringInfo` Swift, il tipo .NET è concettualmente simile al [tipo `character` di Swift.](https://developer.apple.com/documentation/swift/character)

### <a name="example-count-opno-locchar-opno-locrune-and-text-element-instances"></a>Esempio: charistanze di elementi count , Runee text

Nelle API .NET un cluster di grafemi è denominato elemento di *testo.* Nel metodo riportato `char`di `Rune`seguito vengono illustrate `string`le differenze tra istanze di elementi , e text in un oggetto :

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::

Se si esegue questo codice in .NET Framework o .NET Core 3.1 `4`o versioni precedenti, il conteggio degli elementi di testo per l'emoji mostra . Ciò è dovuto a `StringInfo` un bug nella classe che viene risolto in .NET 5.

### <a name="example-splitting-opno-locstring-instances"></a>Esempio: divisione delle istanzeExample: splitting string instances

Quando si `string` suddividono le istanze, evitare di dividere coppie di surrogati e cluster di grafemi. Si consideri l'esempio seguente di codice non corretto, che stringintende inserire interruzioni di riga ogni 10 caratteri in un :

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::

Poiché questo `char` codice enumera le istanze, una coppia di`char` surrogati che si verifica a cavallo di un limite di 10 verrà divisa e verrà inserita una nuova riga tra di esse. Questo inserimento introduce il danneggiamento dei dati, perché i punti di codice surrogati sono significativi solo come coppie.

Il rischio di danneggiamento dei dati `Rune` non viene eliminato se `char` si enumerano le istanze (valori scalari) anziché le istanze. Un set `Rune` di istanze può creare un cluster di grafemi a cavallo di un`char` limite di 10. Se il set di cluster del grafeme è suddiviso, non può essere interpretato correttamente.

Un approccio migliore string consiste nell'interrompere il con il conteggio cluster di grafemi, o elementi di testo, come nell'esempio seguente:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::

Come indicato in precedenza, tuttavia, in implementazioni `StringInfo` di .NET diverse da .NET 5, la classe potrebbe gestire alcuni cluster di grafemi in modo non corretto.

## <a name="utf-8-and-utf-32"></a>UTF-8 e UTF-32

Le sezioni precedenti si concentravano su UTF-16 perché questo `string` è ciò che .NET utilizza per codificare le istanze. Esistono altri sistemi di codifica per Unicode - [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) e [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32). Queste codifiche utilizzano rispettivamente unità di codice a 8 bit e unità di codice a 32 bit.

Come UTF-16, UTF-8 richiede più unità di codice per rappresentare alcuni valori scalari Unicode. UTF-32 può rappresentare qualsiasi valore scalare in una singola unità di codice a 32 bit.

Di seguito sono riportati alcuni esempi che illustrano come lo stesso punto di codice Unicode viene rappresentato in ognuno di questi tre sistemi di codifica Unicode:Here are some examples showing how the same Unicode code point is represented in each of these three Unicode encoding systems:

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

Come indicato in precedenza, una singola unità di codice UTF-16 da una [coppia di surrogati](#surrogate-pairs) è priva di significato. Allo stesso modo, una singola unità di codice UTF-8 è priva di significato se si trova in una sequenza di due, tre o quattro utilizzati per calcolare un valore scalare.

### <a name="endianness"></a>Ordine dei byte

In .NET, le unità di codice string UTF-16 di un vengono archiviate nella memoria`char` contigua come sequenza di interi a 16 bit (istanze). I bit delle singole unità di codice vengono disposti in base [all'endianness](https://en.wikipedia.org/wiki/Endianness) dell'architettura corrente.

In un'architettura little-endian, la string costituita dai `[ D801 DCCC ]` punti di codice UTF-16 sarebbe disposta in memoria come bytes `[ 0x01, 0xD8, 0xCC, 0xDC ]`. In un'architettura big-endian che lo stesso string sarebbe `[ 0xD8, 0x01, 0xDC, 0xCC ]`disposto in memoria come i byte .

I sistemi informatici che comunicano tra loro devono concordare la rappresentazione dei dati che attraversano la rete. La maggior parte dei protocolli di rete utilizza UTF-8 come standard durante la trasmissione di testo, in parte per evitare problemi che potrebbero derivare da una macchina big-endian che comunica con una macchina little-endian. La string parte costituita dai `[ F0 90 93 8C ]` punti di codice UTF-8 verrà sempre rappresentata come byte `[ 0xF0, 0x90, 0x93, 0x8C ]` indipendentemente dall'endianness.

Per utilizzare UTF-8 per la trasmissione di testo, le applicazioni .NET spesso utilizzano codice simile all'esempio seguente:

```csharp
string stringToWrite = GetString();
byte[] stringAsUtf8Bytes = Encoding.UTF8.GetBytes(stringToWrite);
await outputStream.WriteAsync(stringAsUtf8Bytes, 0, stringAsUtf8Bytes.Length);
```

Nell'esempio precedente, il metodo [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) decodifica nuovamente `string` UTF-16 in una serie di valori scalari Unicode, quindi ricodifica tali valori `byte` scalari in UTF-8 e inserisce la sequenza risultante in una matrice. Il metodo [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) esegue la trasformazione opposta, convertendo una matrice UTF-8 `byte` in un oggetto UTF-16 `string`.

> [!WARNING]
> Poiché UTF-8 è all'ordine del giorno su Internet, si può essere tentati di leggere i byte non elaborati dalla rete e di trattare i dati come se fossero UTF-8. Tuttavia, è necessario verificare che sia effettivamente ben formato. Un client dannoso potrebbe inviare UTF-8 in formato non corretto al servizio. Se si opera su tali dati come se fossero ben formati, potrebbe causare errori o problemi di sicurezza nell'applicazione. Per convalidare i dati UTF-8, `Encoding.UTF8.GetString`è possibile utilizzare un metodo come `string`, che eseguirà la convalida durante la conversione dei dati in ingresso in un oggetto .

### <a name="well-formed-encoding"></a>Codifica ben formata

Una codifica Unicode ben string formata è una delle unità di codice che possono essere decodificate in modo inequivocabile e senza errori in una sequenza di valori scalari Unicode. I dati ben formati possono essere transcodificati liberamente avanti e indietro tra UTF-8, UTF-16 e UTF-32.

La questione se una sequenza di codifica è ben formata o meno non è correlata all'endianness dell'architettura di una macchina. Una sequenza UTF-8 non formata è formata male nello stesso modo su entrambe le macchine big-endian e little-endian.

Ecco alcuni esempi di codifiche in formato non corretto:Here are some examples of unl-formed encodings:

* In UTF-8, `[ 6C C2 61 ]` la sequenza non `C2` è formata perché non può essere seguita da `61`.

* In UTF-16, `[ DC00 DD00 ]` la sequenza (o, string `"\udc00\udd00"`in C, il ) non `DC00` è formata perché `DD00`il surrogato basso non può essere seguito da un altro surrogato basso .

* In UTF-32, `[ 0011ABCD ]` la sequenza non `0011ABCD` è formata perché non rientra nell'intervallo dei valori scalari Unicode.

In .NET, `string` le istanze contengono quasi sempre dati UTF-16 ben formati, ma ciò non è garantito. Negli esempi seguenti viene illustrato un codice valido in C, `string` che crea dati UTF-16 in formato non corretto nelle istanze.

* Un valore letterale formato in modo non corretto:

  ```csharp
  const string s = "\ud800";
  ```

* Sottostringa che divide una coppia di surrogati:

  ```csharp
  string x = "\ud83e\udd70"; // "🥰"
  string y = x.Substring(1, 1); // "\udd70" standalone low surrogate
  ```

LE API [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) come non restituiscono `string` mai istanze in formato non corretto. `Encoding.GetString`e `Encoding.GetBytes` i metodi rilevano sequenze in formato non corretto nell'input ed eseguono la sostituzione dei caratteri durante la generazione dell'output. Ad esempio, [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) se viene visualizzato un byte non ASCII nell'input (al di fuori dell'intervallo U-0000..U-007F), viene inserito un '?' nell'istanza restituita. `string` [`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A)sostituisce le sequenze UTF-8 `U+FFFD REPLACEMENT CHARACTER ('�')` in formato `string` non corretto con nell'istanza restituita. Per ulteriori informazioni, vedere i prodotti [standard Unicode](https://www.unicode.org/versions/latest/), Sections 5.22 e 3.9.

Le `Encoding` classi predefinite possono anche essere configurate per generare un'eccezione anziché eseguire la sostituzione dei caratteri quando vengono visualizzate sequenze in formato non corretto. Questo approccio viene spesso utilizzato in applicazioni sensibili alla sicurezza in cui la sostituzione dei caratteri potrebbe non essere accettabile.

```csharp
byte[] utf8Bytes = ReadFromNetwork();
UTF8Encoding encoding = new UTF8Encoding(encoderShouldEmitUTF8Identifier: false, throwOnInvalidBytes: true);
string asString = encoding.GetString(utf8Bytes); // will throw if 'utf8Bytes' is ill-formed
```

Per informazioni su come utilizzare `Encoding` le classi incorporate, vedere Come utilizzare le classi di [codifica dei caratteri in .NET.](character-encoding.md)

## <a name="see-also"></a>Vedere anche

- <xref:System.String>
- <xref:System.Char>
- <xref:System.Text.Rune>
- [Globalizzazione e localizzazione](../../../docs/standard/globalization-localization/index.md)
