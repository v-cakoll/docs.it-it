---
title: Valori Null
description: Informazioni su come viene usato il valore null in di F# linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: 58c54065a98a84c4d4e912cbc42d59cfea8c6de1
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610996"
---
# <a name="null-values"></a>Valori Null

In questo argomento viene descritto come utilizzare il valore null in F#.

## <a name="null-value"></a>Valore null

Il valore null non è in genere usato F# per i valori o le variabili. Tuttavia, null viene visualizzato come valore anomalo in determinate situazioni. Se un tipo viene definito in F#, non è consentito null come valore normale, a meno che il [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attributo viene applicato al tipo. Se un tipo è definito in un altro linguaggio .NET, null è un valore possibile, e quando si interagisce con tali tipi, il F# codice riscontrati valori null.

Per un tipo definito F# e viene usato esclusivamente dal F#, l'unico modo per creare un valore null tramite il F# libreria direttamente consiste nell'utilizzare [unchecked. defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) oppure [Array. zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2). Tuttavia, per un F# tipo che viene usato da altri linguaggi .NET, o se si usa un'API che non viene scritto in tale tipo F#, come .NET Framework, possono verificarsi i valori null.

È possibile usare la `option` digitare F# quando è possibile usare una variabile di riferimento con un valore null in un altro linguaggio .NET. Anziché null, con un F# `option` tipo, si utilizza il valore dell'opzione `None` se è presente alcun oggetto. Si utilizza il valore dell'opzione `Some(obj)` con un oggetto `obj` quando è presente un oggetto. Per altre informazioni, vedere [opzioni](../options.md).

Il `null` parola chiave è una parola chiave valida nel F# lingua e si può essere utilizzato quando si lavora con API di .NET Framework o altre API che sono scritti in un altro linguaggio .NET. Due situazioni in cui potrebbe essere necessario un valore null sono quando si chiama un'API .NET e passa un valore null come argomento e quando si interpreta il valore restituito o parametro di output da una chiamata al metodo .NET.

Per passare un valore null a un metodo .NET, usare semplicemente il `null` parola chiave nel codice chiamante. Questo aspetto è illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Per interpretare un valore null che viene ottenuto da un metodo .NET, usare criteri di ricerca se possibile. Esempio di codice seguente viene illustrato come utilizzare criteri di ricerca per interpretare il valore null restituito da `ReadLine` quando tenta di leggere oltre la fine del flusso di input.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

I valori null per F# tipi possono essere generati anche in altri modi, ad esempio quando Usa `Array.zeroCreate`, che chiama `Unchecked.defaultof`. È necessario prestare attenzione con tale codice per mantenere i valori null incapsulati. In una libreria destinata solo a F#, non è necessario verificare la presenza di valori null in tutte le funzioni. Se si scrive una libreria per essere interoperabile con altri linguaggi .NET, si potrebbe essere necessario aggiungere controlli null i parametri di input e generano un `ArgumentNullException`, esattamente come avviene nel codice c# o Visual Basic.

È possibile usare il codice seguente per verificare se un valore arbitrario è null.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Vedere anche

- [Valori](index.md)
- [Espressioni match](../match-expressions.md)