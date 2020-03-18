---
ms.openlocfilehash: 7c39fe7ffd59fa7a5564bb45f32a6a2fbe0ddb33
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568077"
---
### <a name="change-in-semantics-of-stringnull-in-utf8jsonwriter"></a><span data-ttu-id="fff82-101">Modifica della semantica di `(string)null` in Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="fff82-101">Change in semantics of `(string)null` in Utf8JsonWriter</span></span>

<span data-ttu-id="fff82-102">In .NET Core 3.0 Preview 7, la stringa <xref:System.Text.Json.Utf8JsonWriter>null viene considerata come la stringa vuota in .</span><span class="sxs-lookup"><span data-stu-id="fff82-102">In .NET Core 3.0 Preview 7, the null string is treated as the empty string in <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="fff82-103">A partire da .NET Core 3.0 Preview 8, la stringa null genera un'eccezione se utilizzata come nome di proprietà e genera il token JSON null quando viene utilizzato come valore.</span><span class="sxs-lookup"><span data-stu-id="fff82-103">Starting with .NET Core 3.0 Preview 8, the null string throws an exception when used as a property name, and it emits the JSON null token when used as a value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="fff82-104">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="fff82-104">Change description</span></span>

<span data-ttu-id="fff82-105">In .NET Core 3.0 `null` Preview 7, `""` la stringa è stata considerata sia come quando si scrivono i nomi delle proprietà che durante la scrittura dei valori.</span><span class="sxs-lookup"><span data-stu-id="fff82-105">In .NET Core 3.0 Preview 7, the `null` string was treated as `""` both when writing property names and when writing values.</span></span>  

<span data-ttu-id="fff82-106">A partire da .NET Core 3.0 Preview 8, `null` un nome di proprietà genera un' `ArgumentNullException`proprietà e un `null` valore viene considerato come una chiamata a <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> o <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fff82-106">Starting with .NET Core 3.0 Preview 8, a `null` property name throws an `ArgumentNullException`, and a `null` value is treated as a call to <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> or <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="fff82-107">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fff82-107">Consider the following code:</span></span>

```csharp
string propertyName1 = null;
string propertyValue1 = null;
string propertyName2 = "prop2";
string propertyValue2 = null;
string simpleValue1 = null;

using (Utf8JsonWriter writer = new Utf8JsonWriter(stream))
{
    writer.WriteStartArray();

    writer.WriteStartObject();
    writer.WriteString(propertyName1, propertyValue1);
    writer.WriteString(propertyName2, propertyValue2);
    writer.WriteEndObject();

    writer.WriteStringValue(simpleValue1);

    writer.WriteEndArray();
}
```

<span data-ttu-id="fff82-108">Se eseguito con .NET Core 3.0 Preview 7, il writer produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="fff82-108">If run with .NET Core 3.0 Preview 7, the writer produces the following output:</span></span>

```js
[{"":"","prop2":""},""]
```

<span data-ttu-id="fff82-109">A partire da .NET Core 3.0 `writer.WriteString(propertyName1, propertyValue1)` Preview <xref:System.ArgumentNullException>8, la chiamata a genera un'estensione .</span><span class="sxs-lookup"><span data-stu-id="fff82-109">Starting with .NET Core 3.0 Preview 8, the call to `writer.WriteString(propertyName1, propertyValue1)` throws an <xref:System.ArgumentNullException>.</span></span>  <span data-ttu-id="fff82-110">Se `propertyName1 = null` viene `propertyName1 = string.Empty`sostituito con , l'output sarà ora:</span><span class="sxs-lookup"><span data-stu-id="fff82-110">If `propertyName1 = null` is replaced with `propertyName1 = string.Empty`, the output would now be:</span></span>

```js
[{"":null,"prop2":null},null]
```

<span data-ttu-id="fff82-111">Questa modifica è stata apportata per `null` meglio allinearsi con le aspettative del chiamante per i valori.</span><span class="sxs-lookup"><span data-stu-id="fff82-111">This change was made to better align with caller expectations for `null` values.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fff82-112">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="fff82-112">Version introduced</span></span>

<span data-ttu-id="fff82-113">3.0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="fff82-113">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fff82-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="fff82-114">Recommended action</span></span>

<span data-ttu-id="fff82-115">Quando si scrivono nomi <xref:System.Text.Json.Utf8JsonWriter> e valori di proprietà con la classe:</span><span class="sxs-lookup"><span data-stu-id="fff82-115">When writing property names and values with the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

- <span data-ttu-id="fff82-116">Assicurarsi`null` che le stringhe non vengano utilizzate come nomi di proprietà.</span><span class="sxs-lookup"><span data-stu-id="fff82-116">Ensure non-`null` strings are used as property names.</span></span>

- <span data-ttu-id="fff82-117">Se si desidera il comportamento precedente, utilizzare una chiamata coalescing null; ad esempio, `writer.WriteString(propertyName1 ?? "", propertyValue1)`.</span><span class="sxs-lookup"><span data-stu-id="fff82-117">If the previous behavior is desired, use a null coalescing invocation; for example, `writer.WriteString(propertyName1 ?? "", propertyValue1)`.</span></span>

- <span data-ttu-id="fff82-118">Se la `null` scrittura `null` di un valore letterale per un valore stringa non è auspicabile, utilizzare una chiamata di coalescing null; ad esempio, `writer.WriteString(propertyName2, propertyValue2 ?? "")`.</span><span class="sxs-lookup"><span data-stu-id="fff82-118">If writing a `null` literal for a `null` string value is not desirable, use a null coalescing invocation; for example, `writer.WriteString(propertyName2, propertyValue2 ?? "")`.</span></span>

#### <a name="category"></a><span data-ttu-id="fff82-119">Category</span><span class="sxs-lookup"><span data-stu-id="fff82-119">Category</span></span>

<span data-ttu-id="fff82-120">CoreFx</span><span class="sxs-lookup"><span data-stu-id="fff82-120">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fff82-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="fff82-121">Affected APIs</span></span>

- <xref:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Char%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Char})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)`

-->
