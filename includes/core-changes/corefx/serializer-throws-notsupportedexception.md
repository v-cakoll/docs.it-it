---
ms.openlocfilehash: a35439efce25db94e70420fc6aeaf04816525758
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71263310"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a>Tipo di eccezione del serializzatore `JsonException` JSON modificato da a`NotSupportedException`

In .NET Core 3,0 Preview da 6 a 8, il serializzatore genera <xref:System.Text.Json.JsonException> un'errore quando viene rilevato un tipo di raccolta derivato non supportato. A partire da .NET Core 3,0 Preview 9, il serializzatore <xref:System.NotSupportedException> genera invece un.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core 3,0 Preview 6 fino all'anteprima 8, il serializzatore genera <xref:System.Text.Json.JsonException> un'errore quando viene rilevato un tipo di raccolta derivato non supportato. Un *tipo di raccolta derivato non supportato* è un tipo di raccolta non assegnabile a uno dei tipi seguenti:

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>`
- <xref:System.Collections.IDictionary>
- [Stringa\<IDictionary, T >](xref:System.Collections.Generic.IDictionary%602)

A partire da .NET Core 3,0 Preview 9, il serializzatore <xref:System.NotSupportedException> genera un'eccezione quando incontra un tipo di raccolta non supportato. Il nuovo tipo di eccezione riflette meglio il motivo per cui l'operazione di deserializzazione ha esito negativo.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Se si sta <xref:System.Text.Json.JsonException> eseguendo la deserializzazione, è opportuno prendere in considerazione anche l' <xref:System.NotSupportedException>intercettazione.

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
