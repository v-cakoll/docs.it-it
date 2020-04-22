---
ms.openlocfilehash: cc3251e3b31143bd95793b407e50cf76e0e30142
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021581"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a>Tipo di eccezione `JsonException` del serializzatore Json modificato da a`NotSupportedException`

In .NET Core 3.0 Preview 6 a <xref:System.Text.Json.JsonException> 8, il serializzatore genera un quando viene rilevato un tipo di raccolta derivato non supportato. A partire da .NET Core 3.0 Preview <xref:System.NotSupportedException> 9, il serializzatore genera invece un eccezione.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Core 3.0 Preview 6 a Preview <xref:System.Text.Json.JsonException> 8, il serializzatore genera un quando viene rilevato un tipo di raccolta derivato non supportato. Un *tipo di raccolta derivato non supportato* è qualsiasi tipo di raccolta che non è assegnabile a uno dei tipi seguenti:An unsupported derived collection type is any collection type that isn't assignable to one of the following types:

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [Stringa\<IDictionary,>](xref:System.Collections.Generic.IDictionary%602)

A partire da .NET Core 3.0 Preview <xref:System.NotSupportedException> 9, il serializzatore genera un quando si rileva un tipo di raccolta non supportato. Il nuovo tipo di eccezione riflette meglio il motivo per cui l'operazione di deserializzazione ha esito negativo.

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 9

#### <a name="recommended-action"></a>Azione consigliata

Se si sta <xref:System.Text.Json.JsonException> intercettando durante la deserializzazione, <xref:System.NotSupportedException>si potrebbe prendere in considerazione anche l'intercettazione .

#### <a name="category"></a>Category

Librerie .NET di base

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
