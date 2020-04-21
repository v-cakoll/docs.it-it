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
# <a name="strings"></a>Stringhe

> [!NOTE]
> I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Il `string` tipo rappresenta il testo non modificabile come una sequenza di caratteri Unicode. `string` è un alias per `System.String` in .NET Framework.

## <a name="remarks"></a>Osservazioni

I valori letterali stringa sono delimitati dal carattere virgolette ("). Il carattere \\ barra rovesciata ( ) viene utilizzato per codificare determinati caratteri speciali. La barra rovesciata e il carattere successivo insieme sono noti come sequenza di *escape.* Le sequenze di escape supportate nei valori letterali stringa F sono illustrate nella tabella seguente.

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
|carattere Unicode|`\DDD`(dove `D` indica una cifra decimale; intervallo di 000 `\231` - 255; ad esempio,|
|carattere Unicode|`\xHH`(dove `H` indica una cifra esadecimale; intervallo di 00 `\xE7` - FF; ad esempio,|
|carattere Unicode|`\uHHHH`(UTF-16) (dove `H` indica una cifra esadecimale; intervallo di 0000 - FFFF;  ad esempio, `\u00E7` "z")|
|carattere Unicode|`\U00HHHHHH`(UTF-32) (dove `H` indica una cifra esadecimale; intervallo di 000000 - 10FFFF;  ad esempio, `\U0001F47D` 👽" ")|

> [!IMPORTANT]
> La `\DDD` sequenza di escape è la notazione decimale, non la notazione ottale come nella maggior parte delle altre lingue. Di conseguenza, le `8` cifre e `9` sono valide e una sequenza di `\032` rappresenta uno spazio (U-0020), mentre lo stesso punto di codice in notazione ottale sarebbe `\040`.

> [!NOTE]
> Essendo vincolato a un intervallo compreso tra `\DDD` 0 `\x` e 255 (0xFF), le sequenze di escape e sono effettivamente il set di caratteri [ISO-8859-1,](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) poiché corrisponde ai primi 256 punti di codice Unicode.

## <a name="verbatim-strings"></a>Stringhe Verbatim

Se preceduto dal simbolo , il valore letterale è una stringa verbatim. Ciò significa che tutte le sequenze di escape vengono ignorate, ad eccezione del fatto che due caratteri di virgolette vengono interpretati come un carattere di virgoletta.

## <a name="triple-quoted-strings"></a>Stringhe triple quotate

Inoltre, una stringa può essere racchiusa tra virgolette triple. In questo caso, tutte le sequenze di escape vengono ignorate, inclusi i caratteri virgolette doppie. Per specificare una stringa che contiene una stringa tra virgolette incorporata, è possibile utilizzare una stringa verbatim o una stringa tra virgolette triple. Se si utilizza una stringa verbatim, è necessario specificare due caratteri di virgolette per indicare un carattere di virgoletta singola. Se si utilizza una stringa tra virgolette triple, è possibile utilizzare i caratteri virgolette singole senza che vengano analizzati come fine della stringa. Questa tecnica può essere utile quando si lavora con XML o altre strutture che includono virgolette incorporate.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

Nel codice, le stringhe con interruzioni di riga vengono accettate e le interruzioni di riga vengono interpretate letteralmente come nuove righe, a meno che un carattere barra rovesciata non sia l'ultimo carattere prima dell'interruzione di riga. Lo spazio vuoto iniziale nella riga successiva viene ignorato quando viene utilizzato il carattere barra rovesciata. Il codice seguente `str1` produce una `"abc\ndef"` stringa `str2` con valore `"abcdef"`e una stringa con valore .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a>Indicizzazione e sezionamento delle stringheString Indexing and Slicing

È possibile accedere ai singoli caratteri in una stringa utilizzando una sintassi di tipo matrice, come indicato di seguito.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

L'output è `b`.

In alternativa, è possibile estrarre le sottostringhe usando la sintassi della sezione di matrice, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

L'output è indicato di seguito.

```console
abc
def
```

È possibile rappresentare stringhe ASCII in base `byte[]`a matrici di byte senza segno, digitare . Aggiungere il `B` suffisso a un valore letterale stringa per indicare che si tratta di una stringa ASCII. I valori letterali stringa ASCII utilizzati con le matrici di byte supportano le stesse sequenze di escape delle stringhe Unicode, ad eccezione delle sequenze di escape Unicode.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>Operatori stringa

L'operatore `+` può essere utilizzato per concatenare stringhe, mantenendo la compatibilità con le funzionalità di gestione delle stringhe di .NET Framework. Nell'esempio seguente viene illustrata la concatenazione di stringhe.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>Classe String

Poiché il tipo di stringa in `System.String` F è `System.String` in realtà un tipo .NET Framework, tutti i membri sono disponibili. Ciò `+` include l'operatore , che viene `Length` utilizzato per `Chars` concatenare le stringhe, la proprietà e la proprietà , che restituisce la stringa come matrice di caratteri Unicode. Per ulteriori informazioni sulle `System.String`stringhe, vedere .

Utilizzando la `Chars` proprietà `System.String`di , è possibile accedere ai singoli caratteri di una stringa specificando un indice, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>Modulo stringa

Funzionalità aggiuntive per la gestione `String` delle `FSharp.Core` stringhe è inclusa nel modulo nello spazio dei nomi. Per ulteriori informazioni, vedere [Modulo Core.String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento al linguaggio F](index.md)
