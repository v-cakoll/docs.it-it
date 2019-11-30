---
ms.openlocfilehash: 375a6f57a867c2a11fe95753c1085d6d708db2bd
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568190"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a>I metodi JsonEncodedText. Encode hanno un argomento JavaScriptEncoder aggiuntivo

A partire da .NET Core 3,0 Preview 8, i <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> metodi contengono un argomento facoltativo di <xref:System.Text.Encodings.Web.JavaScriptEncoder>.

#### <a name="change-description"></a>Descrizione della modifica

.NET Core 3,0 include un nuovo tipo, xrif: System. Text. JSON. JsonEncodedText. Encode% 2A? displayProperty = nameWithType >. A partire da .NET Core 3,0 Preview 8, la firma di tutti gli overload del metodo <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> è stata modificata in modo da includere un parametro facoltativo di <xref:System.Text.Encodings.Web.JavaScriptEncoder>. Questa modifica è stata apportata per consentire un codificatore diverso o personalizzato.

La firma dei metodi `Encode` in .NET Core 3,0 Preview 7 è:

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

La firma degli stessi metodi di `Encode` in .NET Core 3,0 Preview 8 e versioni successive è la seguente:

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

.NET Core 3,0 Preview 8

#### <a name="recommended-action"></a>Azione consigliata

Si tratta solo di una modifica di rilievo binaria. una ricompilazione con .NET Core 3,0 Preview 8 o versione successiva risolverà eventuali problemi di Runtime.

#### <a name="category"></a>Category

CoreFx

#### <a name="affected-apis"></a>API interessate

<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
