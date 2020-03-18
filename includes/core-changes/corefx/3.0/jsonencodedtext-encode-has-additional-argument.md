---
ms.openlocfilehash: f5ae4669c85ae4f5d57d88ab55f6e1c758a625a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147588"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a>I metodi JsonEncodedText.Encode hanno un argomento JavaScriptEncoder aggiuntivo

A partire da .NET Core 3.0 Preview 8, i <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> metodi contengono un argomento facoltativo. <xref:System.Text.Encodings.Web.JavaScriptEncoder>

#### <a name="change-description"></a>Descrizione modifica:

.NET Core 3.0 include un nuovo tipo, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty,nameWithType>. A partire da .NET Core 3.0 <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> Preview 8, la firma <xref:System.Text.Encodings.Web.JavaScriptEncoder> di tutti gli overload del metodo è stata modificata per includere un parametro facoltativo. Questa modifica è stata apportata per consentire un codificatore diverso o personalizzato.

La firma `Encode` dei metodi in .NET Core 3.0 Preview 7 è:

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value);
        public static JsonEncodedText Encode(string value);
    }
}
```

La firma degli `Encode` stessi metodi in .NET Core 3.0 Preview 8 e versioni successive è:

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(string value, JavaScriptEncoder encoder = null);
    }
}
```

#### <a name="version-introduced"></a>Versione introdotta

.NET Core 3.0 Anteprima 8

#### <a name="recommended-action"></a>Azione consigliata

Si tratta solo di una modifica di interruzione binaria; una ricompilazione su .NET Core 3.0 Preview 8 o versione successiva risolverà eventuali problemi di runtime.

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
