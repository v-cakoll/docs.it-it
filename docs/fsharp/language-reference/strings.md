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
# <a name="strings"></a>Stringhe

> [!NOTE]
I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Il `string` tipo rappresenta il testo non modificabile come una sequenza di caratteri Unicode. `string` è un alias per `System.String` in .NET Framework.

## <a name="remarks"></a>Note
Valori letterali stringa sono delimitati dal carattere di virgolette doppie ("). Il carattere barra rovesciata (\) viene utilizzato per codificare alcuni caratteri speciali. La barra rovesciata e il carattere successivo insieme sono note come un *sequenza di escape*. Supportato in F # stringa i valori letterali vengono visualizzati nella tabella seguente sequenze di escape.

|Carattere|Sequenza di escape|
|---------|---------------|
|Backspace|\b|
|Nuova riga|\n|
|Ritorno a capo|\r|
|Scheda|\t|
|Barra rovesciata|\\|
|Virgolette|\"|
|Apostrofo|\'|
|Carattere Unicode|\u*XXXX* o \U*XXXXXXXX* (dove *X* indica una cifra esadecimale)|

Se è preceduto dal simbolo @, il valore letterale è una stringa verbatim. Ciò significa che le sequenze di escape vengono ignorate, ad eccezione del fatto che i due caratteri segno di virgolette doppie vengono interpretate come carattere un segno di virgolette.

Inoltre, una stringa può essere racchiusi tra virgolette triple. In questo caso, vengono ignorate tutte le sequenze di escape, inclusi i caratteri di virgoletta doppia. Per specificare una stringa che contiene un elemento incorporato stringa tra virgolette, è possibile utilizzare una stringa lettera o una stringa tra virgolette triple. Se si utilizza una stringa lettera, è necessario specificare due caratteri di virgoletta per indicare un carattere di virgoletta singola. Se si utilizza una stringa con virgolette triple, è possibile utilizzare i caratteri di virgoletta singola senza di essi viene analizzato come la fine della stringa. Questa tecnica può rivelarsi utile quando lavora con XML o altre strutture contenenti virgolette incorporate.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

Nel codice vengono accettate le stringhe che presentano le interruzioni di riga e le interruzioni di riga vengono interpretate letteralmente come caratteri di nuova riga, a meno che un carattere barra rovesciata è l'ultimo carattere prima dell'interruzione di riga. Gli spazi iniziali nella riga successiva viene ignorato quando viene utilizzato il carattere barra rovesciata. Il codice seguente produce una stringa `str1` con valore `"abc\n     def"` e una stringa `str2` con valore `"abcdef"`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

È possibile accedere a singoli caratteri in una stringa utilizzando la sintassi di tipo matrice, come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

L'output è `b`.

Oppure è possibile estrarre sottostringhe utilizzando la sintassi di sezione di matrice, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

L'output è indicato di seguito.

```
abc
def
```

È possibile rappresentare le stringhe ASCII matrici di byte senza segno, tipo `byte[]`. Aggiungere il suffisso `B` a una stringa letterale per indicare che è una stringa ASCII. Valori letterali di stringa ASCII utilizzati con le matrici di byte supportano le sequenze di escape stesso come stringhe Unicode, ad eccezione di sequenze di escape Unicode.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]
    
## <a name="string-operators"></a>Operatori di stringa
Esistono due modi per concatenare stringhe: tramite il `+` operatore o utilizzando il `^` operatore. Il `+` operatore mantiene la compatibilità con la stringa di .NET Framework di gestione delle funzionalità.

L'esempio seguente illustra la concatenazione di stringhe.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]
    
## <a name="string-class"></a>Classe di stringa
Poiché il tipo di stringa in F # è effettivamente un .NET Framework `System.String` digitare tutti i `System.String` membri sono disponibili. Sono inclusi il `+` operatore, che viene utilizzato per concatenare stringhe, il `Length` , proprietà e `Chars` proprietà, che restituisce la stringa come matrice di caratteri Unicode. Per ulteriori informazioni sulle stringhe, vedere `System.String`.

Tramite il `Chars` proprietà `System.String`, è possibile accedere a singoli caratteri in una stringa, specificando un indice, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]
    
## <a name="string-module"></a>Modulo di stringa
Funzionalità aggiuntive per la gestione delle stringhe è incluso nel `String` modulo il `FSharp.Core` dello spazio dei nomi. Per ulteriori informazioni, vedere [modulo Core. String](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)
