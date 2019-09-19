---
ms.openlocfilehash: 39d1b2dba8077bf9bf998775f8967d455f36b549
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119282"
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
