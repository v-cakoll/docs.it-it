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
# <a name="strings"></a>Stringhe

> [!NOTE]
> I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Il `string` tipo rappresenta il testo non modificabile come sequenza di caratteri Unicode. `string` è un alias per `System.String` in .NET Framework.

## <a name="remarks"></a>Note

Valori letterali stringa sono delimitati dal carattere di virgolette doppie ("). Il carattere barra rovesciata ( \\ ) viene usato per codificare alcuni caratteri speciali. La barra rovesciata e il carattere successivo insieme sono note come un *sequenza di escape*. Supportato in sequenze di escape F# valori letterali stringa vengono visualizzati nella tabella seguente.

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
|Carattere Unicode|`\DDD` (dove `D` indica un valore decimal digit; intervallo di 000 - 255, ad esempio `\231` = "ç")|
|Carattere Unicode|`\xHH` (dove `H` indica una cifra esadecimale; intervallo 00 - FF; ad esempio, `\xE7` = "ç")|
|Carattere Unicode|`\uHHHH` (UTF-16) (in cui `H` indica una cifra esadecimale; intervallo di 0000 - FFFF.  ad esempio, `\u00E7` = "ç")|
|Carattere Unicode|`\U00HHHHHH` (UTF-32) (in cui `H` indica una cifra esadecimale; intervallo di 000000 - 10FFFF;  ad esempio, `\U0001F47D` = "👽")|

> [!IMPORTANT]
> Il `\DDD` sequenza di escape è la notazione decimale, notazione non ottale, ad esempio la maggior parte degli altri linguaggi. Pertanto, cifre `8` e `9` siano valide e una sequenza di `\032` rappresenta uno spazio (u+0020), mentre tale stesso punto di codice in notazione ottale sarebbe `\040`.

> [!NOTE]
> Che è vincolato a un intervallo pari a 0 - 255 (0xFF), il `\DDD` e `\x` sequenze di escape sono effettivamente il [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) set di caratteri e poiché i primi 256 punti di codice Unicode corrispondente.

Se è preceduto dal simbolo @, il valore letterale è una stringa verbatim. Ciò significa che tutte le sequenze di escape vengono ignorate, ad eccezione del fatto che i due caratteri segno di virgolette doppie vengono interpretate come carattere un segno di virgolette.

Inoltre, una stringa può essere racchiusi tra virgolette triple. In questo caso, vengono ignorate tutte le sequenze di escape, inclusi i caratteri di virgoletta doppia. Per specificare una stringa che contiene un embedded stringa tra virgolette, è possibile utilizzare una stringa verbatim o una stringa racchiusa tra virgolette triple. Se si usa una stringa verbatim, è necessario specificare due caratteri segno di virgolette per indicare un carattere di virgoletta singola. Se si usa una stringa racchiusa tra virgolette triple, è possibile utilizzare i caratteri di virgoletta singola senza di essi in fase di analisi come la fine della stringa. Questa tecnica può essere utile quando si lavora con XML o altre strutture contenenti virgolette incorporate.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

Nel codice, vengono accettate le stringhe con interruzioni di riga e le interruzioni di riga vengono interpretate letteralmente come caratteri di nuova riga, a meno che un carattere di barra rovesciata è l'ultimo carattere prima dell'interruzione di riga. Lo spazio vuoto iniziale nella riga successiva viene ignorato quando viene utilizzato il carattere barra rovesciata. Il codice seguente produce una stringa `str1` con valore `"abc\ndef"` e una stringa `str2` con valore `"abcdef"`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

È possibile accedere a singoli caratteri in una stringa usando la sintassi di tipo matrice, come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

L'output è `b`.

Oppure è possibile estrarre le sottostringhe utilizzando la sintassi di sezione di matrice, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

L'output è indicato di seguito.

```
abc
def
```

È possibile rappresentare le stringhe ASCII da matrici di byte senza segno, tipo `byte[]`. Si aggiunge il suffisso `B` a una valore letterale stringa per indicare che si tratta di una stringa ASCII. Valori letterali di stringa ASCII usati con le matrici di byte supportano le sequenze di escape stessa sotto forma di stringhe Unicode, fatta eccezione per le sequenze di escape Unicode.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>Operatori di stringa

Esistono due modi per concatenare le stringhe: usando il `+` operatore o utilizzando il `^` operatore. Il `+` operatore mantiene la compatibilità con le funzionalità di gestione delle stringhe di .NET Framework.

L'esempio seguente illustra la concatenazione di stringhe.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>Classe di stringa

Dal momento che la stringa di tipo F# è effettivamente un Framework .NET `System.String` digitare, tutti i `System.String` membri sono disponibili. Ciò include la `+` operatore, che viene usato per concatenare le stringhe, il `Length` proprietà e il `Chars` proprietà, che restituisce la stringa come una matrice di caratteri Unicode. Per altre informazioni sulle stringhe, vedere `System.String`.

Tramite il `Chars` proprietà di `System.String`, è possibile accedere ai singoli caratteri in una stringa specificando un indice, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>Modulo della stringa

Funzionalità aggiuntive per la gestione delle stringhe è incluso nel `String` modulo nel `FSharp.Core` dello spazio dei nomi. Per altre informazioni, vedere [modulo Core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
