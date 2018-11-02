---
title: Valori Null (F#)
description: 'Informazioni su come viene utilizzato il valore null nel linguaggio di programmazione F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 8751ac402c43ddb07fb62e08b6c6d5403cbe9acc
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43787902"
---
# <a name="null-values"></a>Valori Null

Questo argomento descrive come viene utilizzato il valore null in F #.

## <a name="null-value"></a>Valore null

Il valore null non viene utilizzato in genere in F # per i valori o le variabili. Tuttavia, null viene visualizzato come valore anomalo in determinate situazioni. Se un tipo è definito in F #, non è consentito null come valore normale, a meno che il [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attributo viene applicato al tipo. Se un tipo è definito in un altro linguaggio .NET, null è un valore possibile, e quando si interagisce con tali tipi, il codice F # riscontrati valori null.

Per un tipo definito in F # e usato esclusivamente da F #, l'unico modo per creare un valore null con la libreria F # direttamente consiste nell'utilizzare [unchecked. defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) oppure [Array. zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2). Tuttavia, per un tipo di F # che verrà utilizzato da altri linguaggi .NET, o se si usa tale tipo di un'API che non viene scritto in F #, ad esempio .NET Framework, i valori null possono verificarsi.

È possibile usare il `option` tipo in F # quando è possibile utilizzare una variabile di riferimento con un valore null in un altro linguaggio .NET. Anziché null, con F # `option` tipo, si utilizza il valore dell'opzione `None` se è presente alcun oggetto. Si utilizza il valore dell'opzione `Some(obj)` con un oggetto `obj` quando è presente un oggetto. Per altre informazioni, vedere [opzioni](../options.md).

Il `null` (parola chiave) è una parola chiave valida nel linguaggio F # e si può essere utilizzato quando si lavora con API di .NET Framework o altre API che sono scritti in un altro linguaggio .NET. Due situazioni in cui potrebbe essere necessario un valore null sono quando si chiama un'API .NET e passa un valore null come argomento e quando si interpreta il valore restituito o parametro di output da una chiamata al metodo .NET.

Per passare un valore null a un metodo .NET, usare semplicemente il `null` parola chiave nel codice chiamante. Questo aspetto è illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Per interpretare un valore null che viene ottenuto da un metodo .NET, usare criteri di ricerca se possibile. Esempio di codice seguente viene illustrato come utilizzare criteri di ricerca per interpretare il valore null restituito da `ReadLine` quando tenta di leggere oltre la fine del flusso di input.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

I valori null per i tipi F # possono essere generati anche in altri modi, ad esempio quando Usa `Array.zeroCreate`, che chiama `Unchecked.defaultof`. È necessario prestare attenzione con tale codice per mantenere i valori null incapsulati. In una libreria destinata solo a F #, non è necessario verificare la presenza di valori null in tutte le funzioni. Se si scrive una libreria per essere interoperabile con altri linguaggi .NET, si potrebbe essere necessario aggiungere controlli null i parametri di input e generano un `ArgumentNullException`, esattamente come avviene nel codice c# o Visual Basic.

È possibile usare il codice seguente per verificare se un valore arbitrario è null.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Vedere anche

- [Valori](index.md)
- [Espressioni match](../match-expressions.md)
