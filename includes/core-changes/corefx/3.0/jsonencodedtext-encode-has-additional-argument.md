---
ms.openlocfilehash: 2afe5ae80c2d7feca89737b767a6335950d04416
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021606"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a><span data-ttu-id="7d113-101">I metodi JsonEncodedText.Encode hanno un argomento JavaScriptEncoder aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="7d113-101">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>

<span data-ttu-id="7d113-102">A partire da .NET Core 3.0 Preview 8, i <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> metodi contengono un argomento facoltativo. <xref:System.Text.Encodings.Web.JavaScriptEncoder></span><span class="sxs-lookup"><span data-stu-id="7d113-102">Starting with .NET Core 3.0 Preview 8, the <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> methods contain an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> argument.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7d113-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="7d113-103">Change description</span></span>

<span data-ttu-id="7d113-104">.NET Core 3.0 include un nuovo tipo, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty,nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d113-104">.NET Core 3.0 includes a new type, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7d113-105">A partire da .NET Core 3.0 <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> Preview 8, la firma <xref:System.Text.Encodings.Web.JavaScriptEncoder> di tutti gli overload del metodo è stata modificata per includere un parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7d113-105">Starting with .NET Core 3.0 Preview 8, the signature of all <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> method overloads has changed to include an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> parameter.</span></span> <span data-ttu-id="7d113-106">Questa modifica è stata apportata per consentire un codificatore diverso o personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7d113-106">This change was made to allow for a different or custom encoder.</span></span>

<span data-ttu-id="7d113-107">La firma `Encode` dei metodi in .NET Core 3.0 Preview 7 è:</span><span class="sxs-lookup"><span data-stu-id="7d113-107">The signature of the `Encode` methods in .NET Core 3.0 Preview 7 is:</span></span>

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

<span data-ttu-id="7d113-108">La firma degli `Encode` stessi metodi in .NET Core 3.0 Preview 8 e versioni successive è:</span><span class="sxs-lookup"><span data-stu-id="7d113-108">The signature of the same `Encode` methods in .NET Core 3.0 Preview 8 and later versions is:</span></span>

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

#### <a name="version-introduced"></a><span data-ttu-id="7d113-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="7d113-109">Version introduced</span></span>

<span data-ttu-id="7d113-110">.NET Core 3.0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="7d113-110">.NET Core 3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7d113-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="7d113-111">Recommended action</span></span>

<span data-ttu-id="7d113-112">Si tratta solo di una modifica di interruzione binaria; una ricompilazione su .NET Core 3.0 Preview 8 o versione successiva risolverà eventuali problemi di runtime.</span><span class="sxs-lookup"><span data-stu-id="7d113-112">This is a binary breaking change only; a recompile against .NET Core 3.0 Preview 8 or a later version will fix any runtime issues.</span></span>

#### <a name="category"></a><span data-ttu-id="7d113-113">Category</span><span class="sxs-lookup"><span data-stu-id="7d113-113">Category</span></span>

<span data-ttu-id="7d113-114">Librerie .NET di base</span><span class="sxs-lookup"><span data-stu-id="7d113-114">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7d113-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="7d113-115">Affected APIs</span></span>

- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
