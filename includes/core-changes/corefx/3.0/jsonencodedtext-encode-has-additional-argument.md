---
ms.openlocfilehash: d90996ae1b87cdea815daf979bece094d8602f70
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721699"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a>I metodi JsonEncodedText. Encode hanno un argomento JavaScriptEncoder aggiuntivo

A partire da .NET Core 3,0 Preview 8, i <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> metodi contengono un <xref:System.Text.Encodings.Web.JavaScriptEncoder> argomento facoltativo.

#### <a name="change-description"></a>Descrizione modifica:

.NET Core 3,0 include un nuovo tipo, xrif: System. Text. JSON. JsonEncodedText. Encode% 2A? displayProperty = nameWithType>. A partire da .NET Core 3,0 Preview 8, la firma di tutti gli <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> Overload del metodo è cambiata in modo da includere un <xref:System.Text.Encodings.Web.JavaScriptEncoder> parametro facoltativo. Questa modifica è stata apportata per consentire un codificatore diverso o personalizzato.

La firma dei `Encode` metodi in .NET Core 3,0 Preview 7 è:

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

La firma degli stessi `Encode` metodi in .NET Core 3,0 Preview 8 e versioni successive è la seguente:

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

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
