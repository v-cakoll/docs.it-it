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
# <a name="strings"></a>Stringhe

> [!NOTE]
> I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Il tipo di `string` rappresenta il testo non modificabile sotto forma di sequenza di caratteri Unicode. `string` è un alias per `System.String` in .NET Framework.

## <a name="remarks"></a>Note

I valori letterali stringa sono delimitati dal carattere virgolette ("). Il carattere barra rovesciata (\\) viene usato per codificare alcuni caratteri speciali. La barra rovesciata e il carattere successivo insieme sono noti come *sequenza di escape*. Le sequenze di escape supportate F# nei valori letterali stringa sono illustrate nella tabella seguente.

|Carattere|Sequenza di escape|
|---------|---------------|
|Avviso|`\a`|
|Backspace|`\b`|
|Avanzamento carta|`\f`|
|Nuova riga|`\n`|
|Ritorno a capo|`\r`|
|Scheda|`\t`|
|Tabulazione verticale|`\v`|
|Barra rovesciata|`\\`|
|Virgoletta|`\"`|
|Apostrofo|`\'`|
|Carattere Unicode|`\DDD` (dove `D` indica una cifra decimale, ovvero un intervallo di 000-255, ad esempio `\231` = "ç")|
|Carattere Unicode|`\xHH` (dove `H` indica una cifra esadecimale, ovvero un intervallo di 00-FF, ad esempio `\xE7` = "ç")|
|Carattere Unicode|`\uHHHH` (UTF-16) (dove `H` indica una cifra esadecimale, ovvero un intervallo di 0000-FFFF;  ad esempio, `\u00E7` = "ç")|
|Carattere Unicode|`\U00HHHHHH` (UTF-32) (dove `H` indica una cifra esadecimale, ovvero un intervallo di 000000-10FFFF;  ad esempio, `\U0001F47D` = "👽")|

> [!IMPORTANT]
> La sequenza di escape `\DDD` è la notazione decimale, non la notazione ottale come nella maggior parte degli altri linguaggi. Pertanto, le cifre `8` e `9` sono valide e una sequenza di `\032` rappresenta uno spazio (U + 0020), mentre lo stesso punto di codice nella notazione ottale verrebbe `\040`.

> [!NOTE]
> Essendo vincolato a un intervallo di 0-255 (0xFF), le sequenze di escape `\DDD` e `\x` sono in effetti il set di caratteri [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) , dal momento che corrisponde ai primi 256 punti di codice Unicode.

## <a name="verbatim-strings"></a>Stringhe verbatim

Se preceduto dal simbolo @, il valore letterale è una stringa Verbatim. Ciò significa che tutte le sequenze di escape vengono ignorate, ad eccezione del fatto che due caratteri di virgolette sono interpretati come un carattere di virgolette.

## <a name="triple-quoted-strings"></a>Stringhe tra virgolette triple

Inoltre, una stringa può essere racchiusa tra virgolette triple. In questo caso, tutte le sequenze di escape vengono ignorate, incluse le virgolette doppie. Per specificare una stringa che contiene una stringa racchiusa tra virgolette, è possibile usare una stringa Verbatim o una stringa racchiusa tra virgolette triple. Se si utilizza una stringa Verbatim, è necessario specificare due virgolette per indicare un carattere virgoletta singola. Se si usa una stringa racchiusa tra virgolette triple, è possibile usare i caratteri delle virgolette singole senza che vengano analizzati come estremità della stringa. Questa tecnica può essere utile quando si lavora con XML o altre strutture che includono virgolette incorporate.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

Nel codice sono accettate stringhe con interruzioni di riga e le interruzioni di riga vengono interpretate letteralmente come nuove righe, a meno che un carattere barra rovesciata non sia l'ultimo carattere prima dell'interruzione di riga. Gli spazi vuoti iniziali nella riga successiva vengono ignorati quando si usa il carattere barra rovesciata. Il codice seguente produce un `str1` di stringa con valore `"abc\ndef"` e una stringa `str2` con valore `"abcdef"`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a>Indicizzazione e sezionamento di stringhe

È possibile accedere ai singoli caratteri di una stringa usando la sintassi di tipo matrice, come indicato di seguito.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

L'output è `b`.

In alternativa, è possibile estrarre le sottostringhe usando la sintassi della sezione della matrice, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

L'output è indicato di seguito.

```console
abc
def
```

È possibile rappresentare stringhe ASCII in base a matrici di byte senza segno, digitare `byte[]`. Aggiungere il suffisso `B` a un valore letterale stringa per indicare che si tratta di una stringa ASCII. I valori letterali stringa ASCII utilizzati con matrici di byte supportano le stesse sequenze di escape delle stringhe Unicode, ad eccezione delle sequenze di escape Unicode.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>Operatori di stringa

Esistono due modi per concatenare le stringhe: usando l'operatore `+` o l'operatore `^`. L'operatore `+` mantiene la compatibilità con le funzionalità di gestione delle stringhe .NET Framework.

Nell'esempio seguente viene illustrata la concatenazione di stringhe.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>Classe String

Poiché il tipo di stringa F# in è in realtà un .NET Framework tipo di `System.String`, sono disponibili tutti i membri di `System.String`. Questo include l'operatore `+`, che viene usato per concatenare le stringhe, la proprietà `Length` e la proprietà `Chars`, che restituisce la stringa come matrice di caratteri Unicode. Per ulteriori informazioni sulle stringhe, vedere `System.String`.

Utilizzando la proprietà `Chars` di `System.String`, è possibile accedere ai singoli caratteri di una stringa specificando un indice, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>Modulo stringa

Funzionalità aggiuntive per la gestione delle stringhe sono incluse nel modulo `String` nello spazio dei nomi `FSharp.Core`. Per altre informazioni, vedere [modulo core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
