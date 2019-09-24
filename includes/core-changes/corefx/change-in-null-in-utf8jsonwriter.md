---
ms.openlocfilehash: 7c39fe7ffd59fa7a5564bb45f32a6a2fbe0ddb33
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117091"
---
### <a name="change-in-semantics-of-stringnull-in-utf8jsonwriter"></a><span data-ttu-id="81cb4-101">Modificare la semantica di `(string)null` in Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="81cb4-101">Change in semantics of `(string)null` in Utf8JsonWriter</span></span>

<span data-ttu-id="81cb4-102">In .NET Core 3,0 Preview 7 la stringa null viene considerata come una stringa vuota in <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="81cb4-102">In .NET Core 3.0 Preview 7, the null string is treated as the empty string in <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="81cb4-103">A partire da .NET Core 3,0 Preview 8, la stringa null genera un'eccezione quando viene usata come nome di proprietà e genera il token null JSON quando viene usato come valore.</span><span class="sxs-lookup"><span data-stu-id="81cb4-103">Starting with .NET Core 3.0 Preview 8, the null string throws an exception when used as a property name, and it emits the JSON null token when used as a value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="81cb4-104">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="81cb4-104">Change description</span></span>

<span data-ttu-id="81cb4-105">In .NET Core 3,0 Preview 7 la `null` stringa è stata trattata come quando si scrivono i nomi di proprietà e durante la `""` scrittura dei valori.</span><span class="sxs-lookup"><span data-stu-id="81cb4-105">In .NET Core 3.0 Preview 7, the `null` string was treated as `""` both when writing property names and when writing values.</span></span>  

<span data-ttu-id="81cb4-106">A partire da .NET Core 3,0 Preview 8, `null` un nome di proprietà `ArgumentNullException`genera un'eccezione `null` e un valore viene considerato come una <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> chiamata <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>a o.</span><span class="sxs-lookup"><span data-stu-id="81cb4-106">Starting with .NET Core 3.0 Preview 8, a `null` property name throws an `ArgumentNullException`, and a `null` value is treated as a call to <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> or <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="81cb4-107">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="81cb4-107">Consider the following code:</span></span>

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

<span data-ttu-id="81cb4-108">Se viene eseguito con .NET Core 3,0 Preview 7, il writer produce l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="81cb4-108">If run with .NET Core 3.0 Preview 7, the writer produces the following output:</span></span>

```js
[{"":"","prop2":""},""]
```

<span data-ttu-id="81cb4-109">A partire da .NET Core 3,0 Preview 8, la chiamata `writer.WriteString(propertyName1, propertyValue1)` a genera <xref:System.ArgumentNullException>un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="81cb4-109">Starting with .NET Core 3.0 Preview 8, the call to `writer.WriteString(propertyName1, propertyValue1)` throws an <xref:System.ArgumentNullException>.</span></span>  <span data-ttu-id="81cb4-110">Se `propertyName1 = null` viene sostituito con `propertyName1 = string.Empty`, l'output sarà il seguente:</span><span class="sxs-lookup"><span data-stu-id="81cb4-110">If `propertyName1 = null` is replaced with `propertyName1 = string.Empty`, the output would now be:</span></span>

```js
[{"":null,"prop2":null},null]
```

<span data-ttu-id="81cb4-111">Questa modifica è stata apportata per un migliore allineamento `null` con le aspettative del chiamante per i valori.</span><span class="sxs-lookup"><span data-stu-id="81cb4-111">This change was made to better align with caller expectations for `null` values.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="81cb4-112">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="81cb4-112">Version introduced</span></span>

<span data-ttu-id="81cb4-113">3,0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="81cb4-113">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="81cb4-114">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="81cb4-114">Recommended action</span></span>

<span data-ttu-id="81cb4-115">Quando si scrivono nomi e valori di proprietà <xref:System.Text.Json.Utf8JsonWriter> con la classe:</span><span class="sxs-lookup"><span data-stu-id="81cb4-115">When writing property names and values with the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

- <span data-ttu-id="81cb4-116">Verificare che le`null` stringhe non siano utilizzate come nomi di proprietà.</span><span class="sxs-lookup"><span data-stu-id="81cb4-116">Ensure non-`null` strings are used as property names.</span></span>

- <span data-ttu-id="81cb4-117">Se si desidera il comportamento precedente, utilizzare una chiamata a Unione null; ad esempio, `writer.WriteString(propertyName1 ?? "", propertyValue1)`.</span><span class="sxs-lookup"><span data-stu-id="81cb4-117">If the previous behavior is desired, use a null coalescing invocation; for example, `writer.WriteString(propertyName1 ?? "", propertyValue1)`.</span></span>

- <span data-ttu-id="81cb4-118">Se non si `null` desidera scrivere un `null` valore letterale per un valore stringa, utilizzare una `writer.WriteString(propertyName2, propertyValue2 ?? "")`chiamata a Unione null, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="81cb4-118">If writing a `null` literal for a `null` string value is not desirable, use a null coalescing invocation; for example, `writer.WriteString(propertyName2, propertyValue2 ?? "")`.</span></span>

#### <a name="category"></a><span data-ttu-id="81cb4-119">Category</span><span class="sxs-lookup"><span data-stu-id="81cb4-119">Category</span></span>

<span data-ttu-id="81cb4-120">CoreFx</span><span class="sxs-lookup"><span data-stu-id="81cb4-120">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="81cb4-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="81cb4-121">Affected APIs</span></span>

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