---
ms.openlocfilehash: e6e10b2ec451c07bf397cbdcac51ef57c29dab47
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568160"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a>Il tipo di eccezione del serializzatore JSON è stato modificato da `JsonException` a `NotSupportedException`

In .NET Core 3,0 Preview da 6 a 8, il serializzatore genera un'<xref:System.Text.Json.JsonException> quando si verifica un tipo di raccolta derivato non supportato. A partire da .NET Core 3,0 Preview 9, il serializzatore genera invece un <xref:System.NotSupportedException>.

#### <a name="change-description"></a>Descrizione della modifica

In .NET Core 3,0 Preview 6 fino all'anteprima 8, il serializzatore genera un'<xref:System.Text.Json.JsonException> quando si verifica un tipo di raccolta derivato non supportato. Un *tipo di raccolta derivato non supportato* è un tipo di raccolta non assegnabile a uno dei tipi seguenti:

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [IDictionary\<stringa, T >](xref:System.Collections.Generic.IDictionary%602)

A partire da .NET Core 3,0 Preview 9, il serializzatore genera un'<xref:System.NotSupportedException> quando incontra un tipo di raccolta non supportato. Il nuovo tipo di eccezione riflette meglio il motivo per cui l'operazione di deserializzazione ha esito negativo.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Se si stanno intercettando <xref:System.Text.Json.JsonException> durante la deserializzazione, potrebbe essere opportuno prendere in considerazione anche <xref:System.NotSupportedException>.

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
