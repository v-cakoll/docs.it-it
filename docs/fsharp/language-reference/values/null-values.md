---
title: Valori Null (F#)
description: 'Informazioni su come viene utilizzato il valore null in F # linguaggio di programmazione.'
ms.date: 05/16/2016
ms.openlocfilehash: 7367b35cb6e910f926179e52992d5533e5cdda0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563909"
---
# <a name="null-values"></a>Valori Null

In questo argomento viene descritto come il valore null viene utilizzato in F #.


## <a name="null-value"></a>Valore null
Il valore null non viene utilizzato in genere in F # per variabili o valori. Tuttavia, null come valore anomalo in determinate situazioni. Se un tipo è definito in F #, non è consentito null come valore normale, a meno che il [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attributo viene applicato al tipo. Se un tipo è definito in un altro linguaggio .NET, null è un possibile valore, e quando si interagisce con tali tipi, il codice F # riscontrati valori null.

Per un tipo definito in F # e utilizzato esclusivamente da F #, l'unico modo per creare un valore null utilizzando direttamente la libreria F # consiste nell'utilizzare [unchecked. defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) o [zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2). Tuttavia, per un tipo di F # che viene usato da altri linguaggi .NET o se si utilizza tale tipo con un'API che non viene scritta in F #, ad esempio .NET Framework, possono verificarsi i valori null.

È possibile utilizzare il `option` tipo in F # quando è possibile utilizzare una variabile di riferimento con un valore null in un altro linguaggio .NET. Invece di null, con F # `option` tipo, utilizzare il valore dell'opzione `None` se è presente alcun oggetto. Utilizzare il valore dell'opzione `Some(obj)` con un oggetto `obj` quando è presente un oggetto. Per ulteriori informazioni, vedere [opzioni](../options.md).

Il `null` (parola chiave) è una parola chiave valida nel linguaggio F # ed è necessario utilizzarla quando si lavora con API di .NET Framework o altre API che vengono scritti in un altro linguaggio .NET. Le due situazioni in cui potrebbe essere necessario un valore null sono quando si chiama un'API .NET e passa un valore null come argomento e quando si interpreta il valore restituito o parametro di output da una chiamata al metodo .NET.

Per passare un valore null a un metodo .NET, usare semplicemente il `null` (parola chiave) nel codice chiamante. Questo aspetto è illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Per interpretare un valore null viene ottenuto da un metodo .NET, usare criteri di ricerca se possibile. Esempio di codice seguente viene illustrato come utilizzare criteri di ricerca per interpretare il valore null restituito da `ReadLine` quando tenta di leggere oltre la fine di un flusso di input.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

Valori null per i tipi F # possono essere generati anche in altri modi, ad esempio quando si usa `Array.zeroCreate`, che chiama `Unchecked.defaultof`. È necessario prestare attenzione con tale codice per mantenere i valori null incapsulati. In una libreria destinata solo a F #, non è necessario verificare la presenza di valori null in ogni funzione. Se si scrive una raccolta per l'interoperabilità con altri linguaggi .NET, potrebbe essere necessario aggiungere i controlli per i valori null, i parametri di input e generano un `ArgumentNullException`, esattamente come avviene nel codice c# o Visual Basic.

È possibile utilizzare il codice seguente per verificare se un valore arbitrario è null.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Vedere anche
[Valori](index.md)

[Espressioni match](../match-expressions.md)
