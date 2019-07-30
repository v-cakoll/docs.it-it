---
title: Valori Null
description: Informazioni sul modo in cui viene usato il valore F# null nel linguaggio di programmazione.
ms.date: 03/22/2019
ms.openlocfilehash: 2038c0a461fec9884c51edd50c3c9f336104e30e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630812"
---
# <a name="null-values"></a>Valori Null

In questo argomento viene descritto il modo in cui viene F#utilizzato il valore null in.

## <a name="null-value"></a>Valore null

Il valore null non viene in genere usato F# in per valori o variabili. Tuttavia, null viene visualizzato come valore anomalo in determinate situazioni. Se un tipo è definito in F#, null non è consentito come valore normale a meno che l'attributo [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) non venga applicato al tipo. Se un tipo è definito in un altro linguaggio .NET, null è un valore possibile e quando si interoperano con tali tipi, il F# codice potrebbe rilevare valori null.

Per un tipo definito in F# e usato esclusivamente da F#, l'unico modo per creare un valore null usando la F# libreria direttamente è quello di usare unchecked [. defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) o [Array. zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2). Tuttavia, per un F# tipo usato da altri linguaggi .NET o se si usa tale tipo con un'API non scritta in F#, ad esempio la .NET Framework, possono verificarsi valori null.

È possibile utilizzare il `option` tipo in F# quando è possibile utilizzare una variabile di riferimento con un possibile valore null in un altro linguaggio .NET. Anziché null, con un F# `option` tipo, è possibile usare il valore `None` dell'opzione se non è presente alcun oggetto. Il valore `Some(obj)` dell'opzione viene usato con un `obj` oggetto quando è presente un oggetto. Per altre informazioni, vedere [Opzioni](../options.md). Si noti che è comunque possibile comprimere `null` un valore in un'opzione se, per `Some x`, `null` `x` si verifica. Per questo motivo, è importante usare `None` quando un valore è. `null`

La `null` parola chiave è una parola chiave valida F# nel linguaggio ed è necessario usarla quando si lavora con .NET Framework API o altre API scritte in un altro linguaggio .NET. Le due situazioni in cui potrebbe essere necessario un valore null sono quando si chiama un'API .NET e si passa un valore null come argomento e quando si interpreta il valore restituito o un parametro di output da una chiamata al metodo .NET.

Per passare un valore null a un metodo .NET, è sufficiente usare `null` la parola chiave nel codice chiamante. Questo aspetto è illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Per interpretare un valore null ottenuto da un metodo .NET, usare i criteri di ricerca, se possibile. Nell'esempio di codice seguente viene illustrato come utilizzare i criteri di ricerca per interpretare il valore null `ReadLine` restituito da quando si tenta di leggere oltre la fine di un flusso di input.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

I valori null F# per i tipi possono essere generati anche in altri modi, ad esempio quando `Array.zeroCreate`si usa, `Unchecked.defaultof`che chiama. È necessario prestare attenzione con tale codice per tenere incapsulati i valori null. In una libreria destinata solo F#a, non è necessario verificare la presenza di valori null in ogni funzione. Se si scrive una libreria per l'interoperabilità con altri linguaggi .NET, potrebbe essere necessario aggiungere i controlli per i parametri di input null `ArgumentNullException`e generare un'analogia, C# come avviene in o Visual Basic codice.

È possibile utilizzare il codice seguente per verificare se un valore arbitrario è null.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Vedere anche

- [Valori](index.md)
- [Espressioni match](../match-expressions.md)
