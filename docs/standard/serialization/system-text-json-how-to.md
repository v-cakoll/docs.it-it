---
title: Come serializzare e deserializzare JSON con C# -.NET
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: a9c690e736a08c729a4099d5e7a519ed17ec282c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705795"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="f1b4f-102">Come serializzare e deserializzare JSON in .NET</span><span class="sxs-lookup"><span data-stu-id="f1b4f-102">How to serialize and deserialize JSON in .NET</span></span>

<span data-ttu-id="f1b4f-103">Questo articolo illustra come usare lo spazio dei nomi <xref:System.Text.Json> per serializzare e deserializzare da e verso JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-103">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="f1b4f-104">Le direzioni e il codice di esempio usano la libreria direttamente, non tramite un Framework come [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-104">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="f1b4f-105">La maggior parte del codice di esempio di serializzazione imposta <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> per `true` "Pretty-Print" JSON (con rientri e spazi vuoti per la leggibilità umana).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-105">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="f1b4f-106">Per l'uso in produzione, in genere si accetta il valore predefinito di `false` per questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-106">For production use, you would typically accept the default value of `false` for this setting.</span></span>

## <a name="namespaces"></a><span data-ttu-id="f1b4f-107">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="f1b4f-107">Namespaces</span></span>

<span data-ttu-id="f1b4f-108">Lo spazio dei nomi <xref:System.Text.Json> contiene tutti i punti di ingresso e i tipi principali.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-108">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="f1b4f-109">Lo spazio dei nomi <xref:System.Text.Json.Serialization> contiene attributi e API per scenari avanzati e personalizzazione specifici per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-109">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="f1b4f-110">Gli esempi di codice illustrati in questo articolo richiedono direttive `using` per uno o entrambi gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-110">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="f1b4f-111">Gli attributi dello spazio dei nomi <xref:System.Runtime.Serialization> non sono attualmente supportati nel `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-111">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="f1b4f-112">Come scrivere oggetti .NET in JSON (Serialize)</span><span class="sxs-lookup"><span data-stu-id="f1b4f-112">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="f1b4f-113">Per scrivere JSON in una stringa o in un file, chiamare il metodo <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-113">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="f1b4f-114">Nell'esempio seguente viene creato JSON come stringa:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-114">The following example creates JSON as a string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="f1b4f-115">Nell'esempio seguente viene usato il codice sincrono per creare un file JSON:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-115">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="f1b4f-116">Nell'esempio seguente viene usato il codice asincrono per creare un file JSON:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-116">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="f1b4f-117">Negli esempi precedenti viene utilizzata l'inferenza del tipo per il tipo da serializzare.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-117">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="f1b4f-118">Un overload di `Serialize()` accetta un parametro di tipo generico:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-118">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="f1b4f-119">Esempio di serializzazione</span><span class="sxs-lookup"><span data-stu-id="f1b4f-119">Serialization example</span></span>

<span data-ttu-id="f1b4f-120">Di seguito è riportato un esempio di classe che contiene le raccolte e una classe annidata:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-120">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="f1b4f-121">L'output JSON della serializzazione di un'istanza del tipo precedente è simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-121">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="f1b4f-122">Per impostazione predefinita, l'output JSON è minimizzati:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-122">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="f1b4f-123">Nell'esempio seguente viene illustrato lo stesso JSON, formattato, ovvero abbastanza stampato con spazi vuoti e rientri:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-123">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a><span data-ttu-id="f1b4f-124">Serializza in UTF-8</span><span class="sxs-lookup"><span data-stu-id="f1b4f-124">Serialize to UTF-8</span></span>

<span data-ttu-id="f1b4f-125">Per eseguire la serializzazione in UTF-8, chiamare il metodo <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-125">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="f1b4f-126">È disponibile anche un overload <xref:System.Text.Json.JsonSerializer.Serialize%2A> che accetta una <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-126">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="f1b4f-127">La serializzazione in UTF-8 è più veloce del 5-10% rispetto all'uso dei metodi basati su stringa.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-127">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="f1b4f-128">La differenza è dovuta al fatto che i byte (come UTF-8) non devono essere convertiti in stringhe (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-128">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="f1b4f-129">Comportamento della serializzazione</span><span class="sxs-lookup"><span data-stu-id="f1b4f-129">Serialization behavior</span></span>

* <span data-ttu-id="f1b4f-130">Per impostazione predefinita, tutte le proprietà pubbliche vengono serializzate.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-130">By default, all public properties are serialized.</span></span> <span data-ttu-id="f1b4f-131">È possibile [specificare le proprietà da escludere](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-131">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="f1b4f-132">Il [codificatore predefinito](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) consente di eseguire il escape dei caratteri non ASCII, dei caratteri con distinzione HTML all'interno dell'intervallo ASCII e dei caratteri che devono essere preceduti da un carattere di escape in base alla [specifica JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-132">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="f1b4f-133">Per impostazione predefinita, JSON è minimizzati.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-133">By default, JSON is minified.</span></span> <span data-ttu-id="f1b4f-134">È possibile [stampare](#serialize-to-formatted-json)in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-134">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="f1b4f-135">Per impostazione predefinita, le maiuscole e minuscole dei nomi JSON corrispondono ai nomi .NET.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-135">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="f1b4f-136">È possibile [personalizzare la combinazione di maiuscole e minuscole](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-136">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="f1b4f-137">Vengono rilevati riferimenti circolari e vengono generate eccezioni.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-137">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="f1b4f-138">Per altre informazioni, vedere il [problema 38579 sui riferimenti circolari](https://github.com/dotnet/corefx/issues/38579) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-138">For more information, see [issue 38579 on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="f1b4f-139">Attualmente, i campi vengono esclusi.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-139">Currently, fields are excluded.</span></span>

<span data-ttu-id="f1b4f-140">I tipi supportati includono:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-140">Supported types include:</span></span>

* <span data-ttu-id="f1b4f-141">Primitive .NET mappate a primitive JavaScript, ad esempio tipi numerici, stringhe e valori booleani.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-141">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="f1b4f-142">[Oggetti CLR obsoleti definiti dall'utente (poco)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-142">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="f1b4f-143">Matrici unidimensionali e irregolari (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-143">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="f1b4f-144">`Dictionary<string,TValue>` dove `TValue` è `object`, `JsonElement`o un POCO.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-144">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="f1b4f-145">Raccolte dai seguenti spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-145">Collections from the following namespaces.</span></span> <span data-ttu-id="f1b4f-146">Per ulteriori informazioni, vedere il [problema relativo al supporto della raccolta](https://github.com/dotnet/corefx/issues/36643) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-146">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="f1b4f-147">È possibile [implementare convertitori personalizzati](system-text-json-converters-how-to.md) per gestire tipi aggiuntivi o per fornire funzionalità non supportate dai convertitori incorporati.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-147">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="f1b4f-148">Come leggere JSON in oggetti .NET (deserializzare)</span><span class="sxs-lookup"><span data-stu-id="f1b4f-148">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="f1b4f-149">Per eseguire la deserializzazione da una stringa o da un file, chiamare il metodo <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-149">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="f1b4f-150">Nell'esempio seguente viene letto JSON da una stringa e viene creata un'istanza della classe `WeatherForecast` illustrata in precedenza per l' [esempio di serializzazione](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="f1b4f-150">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="f1b4f-151">Per eseguire la deserializzazione da un file usando il codice sincrono, leggere il file in una stringa, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-151">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="f1b4f-152">Per eseguire la deserializzazione da un file usando il codice asincrono, chiamare il metodo <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-152">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="f1b4f-153">Deserializzazione da UTF-8</span><span class="sxs-lookup"><span data-stu-id="f1b4f-153">Deserialize from UTF-8</span></span>

<span data-ttu-id="f1b4f-154">Per deserializzare da UTF-8, chiamare un <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload che accetta un `Utf8JsonReader` o un `ReadOnlySpan<byte>`, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-154">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="f1b4f-155">Gli esempi presuppongono che JSON si trovi in una matrice di byte denominata jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-155">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="f1b4f-156">Comportamento di deserializzazione</span><span class="sxs-lookup"><span data-stu-id="f1b4f-156">Deserialization behavior</span></span>

* <span data-ttu-id="f1b4f-157">Per impostazione predefinita, la corrispondenza dei nomi di proprietà fa distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="f1b4f-157">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="f1b4f-158">È possibile specificare la distinzione tra [maiuscole e minuscole](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-158">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="f1b4f-159">Se il codice JSON contiene un valore per una proprietà di sola lettura, il valore viene ignorato e non viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-159">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="f1b4f-160">La deserializzazione ai tipi di riferimento senza un costruttore senza parametri non è supportata.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-160">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="f1b4f-161">La deserializzazione a oggetti non modificabili o a proprietà di sola lettura non è supportata.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-161">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="f1b4f-162">Per altre informazioni, vedere il [problema GitHub 38569 sul supporto di oggetti non modificabili](https://github.com/dotnet/corefx/issues/38569) e il [problema 38163 sul supporto delle proprietà di sola lettura](https://github.com/dotnet/corefx/issues/38163) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-162">For more information, see GitHub [issue 38569 on immutable object support](https://github.com/dotnet/corefx/issues/38569) and [issue 38163 on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="f1b4f-163">Per impostazione predefinita, le enumerazioni sono supportate come numeri.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-163">By default, enums are supported as numbers.</span></span> <span data-ttu-id="f1b4f-164">È possibile [serializzare i nomi di enumerazione come stringhe](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-164">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="f1b4f-165">I campi non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-165">Fields aren't supported.</span></span>
* <span data-ttu-id="f1b4f-166">Per impostazione predefinita, i commenti o le virgole finali in JSON generano eccezioni.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-166">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="f1b4f-167">È possibile [consentire i commenti e le virgole finali](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-167">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="f1b4f-168">La [profondità massima predefinita](xref:System.Text.Json.JsonReaderOptions.MaxDepth) è 64.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-168">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="f1b4f-169">È possibile [implementare convertitori personalizzati](system-text-json-converters-how-to.md) per fornire funzionalità non supportate dai convertitori incorporati.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-169">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="f1b4f-170">Serializza nel formato JSON formattato</span><span class="sxs-lookup"><span data-stu-id="f1b4f-170">Serialize to formatted JSON</span></span>

<span data-ttu-id="f1b4f-171">Per stampare l'output JSON, impostare <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> su `true`:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-171">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="f1b4f-172">Di seguito è riportato un esempio di tipo da serializzare e da un output JSON abbastanza stampato:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-172">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="f1b4f-173">Personalizzare i nomi e i valori JSON</span><span class="sxs-lookup"><span data-stu-id="f1b4f-173">Customize JSON names and values</span></span>

<span data-ttu-id="f1b4f-174">Per impostazione predefinita, i nomi delle proprietà e le chiavi del dizionario non cambiano nell'output JSON, inclusa la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-174">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="f1b4f-175">I valori enum sono rappresentati come numeri.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-175">Enum values are represented as numbers.</span></span> <span data-ttu-id="f1b4f-176">Questa sezione illustra come eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-176">This section explains how to:</span></span>

* [<span data-ttu-id="f1b4f-177">Personalizzare i singoli nomi di proprietà</span><span class="sxs-lookup"><span data-stu-id="f1b4f-177">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="f1b4f-178">Converte tutti i nomi di proprietà in Camel case</span><span class="sxs-lookup"><span data-stu-id="f1b4f-178">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="f1b4f-179">Implementare i criteri di denominazione delle proprietà personalizzate</span><span class="sxs-lookup"><span data-stu-id="f1b4f-179">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="f1b4f-180">Converte le chiavi del dizionario in lettere maiuscole</span><span class="sxs-lookup"><span data-stu-id="f1b4f-180">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="f1b4f-181">Converte le enumerazioni in stringhe e maiuscole</span><span class="sxs-lookup"><span data-stu-id="f1b4f-181">Convert enums to strings and camel case</span></span>](#enums-as-strings) 

<span data-ttu-id="f1b4f-182">Per altri scenari che richiedono una gestione speciale dei nomi e dei valori delle proprietà JSON, è possibile [implementare convertitori personalizzati](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-182">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="f1b4f-183">Personalizzare i singoli nomi di proprietà</span><span class="sxs-lookup"><span data-stu-id="f1b4f-183">Customize individual property names</span></span>

<span data-ttu-id="f1b4f-184">Per impostare il nome delle singole proprietà, utilizzare l'attributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="f1b4f-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="f1b4f-185">Di seguito è riportato un esempio di tipo da serializzare e JSON risultante:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-185">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="f1b4f-186">Nome della proprietà impostato dall'attributo:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="f1b4f-187">Si applica in entrambe le direzioni, per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="f1b4f-188">Ha la precedenza sui criteri di denominazione delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="f1b4f-189">Usa il caso Camel per tutti i nomi di proprietà JSON</span><span class="sxs-lookup"><span data-stu-id="f1b4f-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="f1b4f-190">Per usare il case Camel per tutti i nomi di proprietà JSON, impostare <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> su `JsonNamingPolicy.CamelCase`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="f1b4f-191">Ecco una classe di esempio per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-191">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="f1b4f-192">Criteri di denominazione delle proprietà Camel case:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="f1b4f-193">Si applica alla serializzazione e alla deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="f1b4f-194">Viene sottoposto a override da `[JsonPropertyName]` attributi.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-194">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="f1b4f-195">Questo è il motivo per cui il nome della proprietà JSON `Wind` nell'esempio non è un caso Camel.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-195">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="f1b4f-196">Usare un criterio personalizzato per la denominazione delle proprietà JSON</span><span class="sxs-lookup"><span data-stu-id="f1b4f-196">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="f1b4f-197">Per usare un criterio di denominazione delle proprietà JSON personalizzato, creare una classe che deriva da <xref:System.Text.Json.JsonNamingPolicy> ed eseguire l'override del metodo <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-197">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="f1b4f-198">Impostare quindi la proprietà <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> su un'istanza della classe di criteri di denominazione:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-198">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="f1b4f-199">Ecco una classe di esempio per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-199">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="f1b4f-200">Criteri di denominazione delle proprietà JSON:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-200">The JSON property naming policy:</span></span>

* <span data-ttu-id="f1b4f-201">Si applica alla serializzazione e alla deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-201">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="f1b4f-202">Viene sottoposto a override da `[JsonPropertyName]` attributi.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-202">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="f1b4f-203">Questo è il motivo per cui il nome della proprietà JSON `Wind` nell'esempio non è maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-203">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="f1b4f-204">Chiavi del dizionario case Camel</span><span class="sxs-lookup"><span data-stu-id="f1b4f-204">Camel case dictionary keys</span></span>

<span data-ttu-id="f1b4f-205">Se una proprietà di un oggetto da serializzare è di tipo `Dictionary<string,TValue>`, le chiavi di `string` possono essere convertite in maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-205">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="f1b4f-206">A tale scopo, impostare <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> su `JsonNamingPolicy.CamelCase`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-206">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="f1b4f-207">La serializzazione di un oggetto con un dizionario denominato `TemperatureRanges` con coppie chiave-valore `"ColdMinTemp", 20` e `"HotMinTemp", 40` comporterebbe l'output JSON come l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-207">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="f1b4f-208">I criteri di denominazione Camel case per le chiavi del dizionario si applicano solo alla serializzazione.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-208">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="f1b4f-209">Se si deserializza un dizionario, le chiavi corrisponderanno al file JSON anche se si specifica `JsonNamingPolicy.CamelCase` per l'`DictionaryKeyPolicy`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-209">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="f1b4f-210">Enumerazioni come stringhe</span><span class="sxs-lookup"><span data-stu-id="f1b4f-210">Enums as strings</span></span>

<span data-ttu-id="f1b4f-211">Per impostazione predefinita, le enumerazioni vengono serializzate come numeri.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-211">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="f1b4f-212">Per serializzare i nomi di enumerazione come stringhe, usare il <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-212">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="f1b4f-213">Si supponga, ad esempio, di dover serializzare la classe seguente che contiene un'enumerazione:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-213">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="f1b4f-214">Se il riepilogo è `Hot`, per impostazione predefinita il JSON serializzato ha il valore numerico 3:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-214">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="f1b4f-215">Il codice di esempio seguente serializza i nomi di enumerazione invece dei valori numerici e converte i nomi in lettere maiuscole:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-215">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="f1b4f-216">Il codice JSON risultante è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-216">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="f1b4f-217">È anche possibile deserializzare i nomi di stringa enum, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-217">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="f1b4f-218">Escludi proprietà dalla serializzazione</span><span class="sxs-lookup"><span data-stu-id="f1b4f-218">Exclude properties from serialization</span></span>

<span data-ttu-id="f1b4f-219">Per impostazione predefinita, tutte le proprietà pubbliche vengono serializzate.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="f1b4f-220">Se non si vuole che alcuni di essi vengano visualizzati nell'output JSON, sono disponibili diverse opzioni.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="f1b4f-221">In questa sezione viene illustrato come escludere:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-221">This section explains how to exclude:</span></span>

* [<span data-ttu-id="f1b4f-222">Singole proprietà</span><span class="sxs-lookup"><span data-stu-id="f1b4f-222">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="f1b4f-223">Tutte le proprietà di sola lettura</span><span class="sxs-lookup"><span data-stu-id="f1b4f-223">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="f1b4f-224">Tutte le proprietà con valore null</span><span class="sxs-lookup"><span data-stu-id="f1b4f-224">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="f1b4f-225">Escludi singole proprietà</span><span class="sxs-lookup"><span data-stu-id="f1b4f-225">Exclude individual properties</span></span>

<span data-ttu-id="f1b4f-226">Per ignorare le singole proprietà, utilizzare l'attributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="f1b4f-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="f1b4f-227">Ecco un esempio di tipo per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-227">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="f1b4f-228">Escludi tutte le proprietà di sola lettura</span><span class="sxs-lookup"><span data-stu-id="f1b4f-228">Exclude all read-only properties</span></span>

<span data-ttu-id="f1b4f-229">Una proprietà è di sola lettura se contiene un getter pubblico ma non un setter pubblico.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-229">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="f1b4f-230">Per escludere tutte le proprietà di sola lettura, impostare il <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> su `true`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-230">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="f1b4f-231">Ecco un esempio di tipo per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-231">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="f1b4f-232">Questa opzione si applica solo alla serializzazione.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-232">This option applies only to serialization.</span></span> <span data-ttu-id="f1b4f-233">Durante la deserializzazione, le proprietà di sola lettura vengono ignorate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-233">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="f1b4f-234">Escludi tutte le proprietà dei valori null</span><span class="sxs-lookup"><span data-stu-id="f1b4f-234">Exclude all null value properties</span></span>

<span data-ttu-id="f1b4f-235">Per escludere tutte le proprietà con valore null, impostare la proprietà <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> su `true`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="f1b4f-236">Di seguito è riportato un esempio di oggetto da serializzare e output JSON:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="f1b4f-237">Gli</span><span class="sxs-lookup"><span data-stu-id="f1b4f-237">Property</span></span> |<span data-ttu-id="f1b4f-238">Valore</span><span class="sxs-lookup"><span data-stu-id="f1b4f-238">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="f1b4f-239">Date</span><span class="sxs-lookup"><span data-stu-id="f1b4f-239">Date</span></span>    | <span data-ttu-id="f1b4f-240">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="f1b4f-240">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="f1b4f-241">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="f1b4f-241">TemperatureCelsius</span></span>| <span data-ttu-id="f1b4f-242">25</span><span class="sxs-lookup"><span data-stu-id="f1b4f-242">25</span></span> |
| <span data-ttu-id="f1b4f-243">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="f1b4f-243">Summary</span></span>| <span data-ttu-id="f1b4f-244">null</span><span class="sxs-lookup"><span data-stu-id="f1b4f-244">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="f1b4f-245">Questa impostazione si applica alla serializzazione e alla deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-245">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="f1b4f-246">Per informazioni sugli effetti sulla deserializzazione, vedere [Ignore null durante la deserializzazione](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-246">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="f1b4f-247">Personalizzare la codifica caratteri</span><span class="sxs-lookup"><span data-stu-id="f1b4f-247">Customize character encoding</span></span>

<span data-ttu-id="f1b4f-248">Per impostazione predefinita, il serializzatore viene sottoposto a escape per tutti i caratteri non ASCII.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-248">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="f1b4f-249">Ovvero, li sostituisce con `\uxxxx` dove `xxxx` è il codice Unicode del carattere.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-249">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="f1b4f-250">Se, ad esempio, la proprietà `Summary` è impostata su cirillico жарко, l'oggetto `WeatherForecast` viene serializzato come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-250">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="f1b4f-251">Serializza i set di caratteri della lingua</span><span class="sxs-lookup"><span data-stu-id="f1b4f-251">Serialize language character sets</span></span>

<span data-ttu-id="f1b4f-252">Per serializzare i set di caratteri di una o più lingue senza eseguire l'escape, specificare gli [intervalli Unicode](xref:System.Text.Unicode.UnicodeRanges) quando si crea un'istanza di <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-252">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="f1b4f-253">Questo codice non esegue l'escape di caratteri cirillici o greci.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-253">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="f1b4f-254">Se la proprietà `Summary` è impostata su cirillico жарко, l'oggetto `WeatherForecast` viene serializzato come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-254">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="f1b4f-255">Per serializzare tutti i set di lingue senza escape, utilizzare <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-255">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="f1b4f-256">Serializza caratteri specifici</span><span class="sxs-lookup"><span data-stu-id="f1b4f-256">Serialize specific characters</span></span>

<span data-ttu-id="f1b4f-257">In alternativa, è possibile specificare i singoli caratteri che si desidera consentire tramite senza che venga eseguito il escape.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-257">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="f1b4f-258">Nell'esempio seguente vengono serializzati solo i primi due caratteri di жарко:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-258">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="f1b4f-259">Di seguito è riportato un esempio di JSON prodotto dal codice precedente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-259">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="f1b4f-260">Serializza tutti i caratteri</span><span class="sxs-lookup"><span data-stu-id="f1b4f-260">Serialize all characters</span></span>

<span data-ttu-id="f1b4f-261">Per ridurre al minimo l'escape, è possibile usare <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-261">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="f1b4f-262">Rispetto al codificatore predefinito, il codificatore `UnsafeRelaxedJsonEscaping` è più permissivo per consentire il passaggio dei caratteri senza caratteri di escape:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-262">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="f1b4f-263">Non esegue l'escape di caratteri con distinzione HTML, ad esempio `<`, `>`, `&`e `'`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-263">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="f1b4f-264">Non offre protezioni aggiuntive per la difesa in profondità da attacchi XSS o divulgazione di informazioni, ad esempio quelli che potrebbero risultare dal client e dal server che non accettano il *set di caratteri*.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-264">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="f1b4f-265">Usare il codificatore unsafe solo quando è noto che il client interpreterà il payload risultante come JSON con codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-265">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="f1b4f-266">Ad esempio, è possibile usarlo se il server invia l'intestazione della risposta `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-266">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="f1b4f-267">Non consentire mai l'emissione dell'output `UnsafeRelaxedJsonEscaping` RAW in una pagina HTML o in un elemento `<script>`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-267">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="f1b4f-268">Serializzare le proprietà delle classi derivate</span><span class="sxs-lookup"><span data-stu-id="f1b4f-268">Serialize properties of derived classes</span></span>

<span data-ttu-id="f1b4f-269">La serializzazione polimorfica non è supportata quando si specifica in fase di compilazione il tipo da serializzare.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-269">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="f1b4f-270">Si supponga, ad esempio, di avere una classe `WeatherForecast` e una classe derivata `WeatherForecastDerived`:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-270">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="f1b4f-271">E si supponga che l'argomento di tipo del metodo `Serialize` in fase di compilazione sia `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-271">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="f1b4f-272">In questo scenario, la proprietà `WindSpeed` non viene serializzata anche se l'oggetto `weatherForecast` è effettivamente un oggetto `WeatherForecastDerived`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-272">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="f1b4f-273">Vengono serializzate solo le proprietà della classe base:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-273">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="f1b4f-274">Questo comportamento è volto a impedire l'esposizione accidentale dei dati in un tipo creato dal runtime derivato.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-274">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="f1b4f-275">Per serializzare le proprietà del tipo derivato, usare uno degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-275">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="f1b4f-276">Chiamare un overload di <xref:System.Text.Json.JsonSerializer.Serialize%2A> che consente di specificare il tipo in fase di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-276">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="f1b4f-277">Dichiarare l'oggetto da serializzare come `object`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-277">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="f1b4f-278">Nello scenario di esempio precedente, entrambi gli approcci determinano l'inclusione della proprietà `WindSpeed` nell'output JSON:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-278">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

<span data-ttu-id="f1b4f-279">Per informazioni sulla deserializzazione polimorfica, vedere [supportare la deserializzazione polimorfica](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-279">For information about polymorphic deserialization, see [Support polymorphic deserialization](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="f1b4f-280">Consenti commenti e virgole finali</span><span class="sxs-lookup"><span data-stu-id="f1b4f-280">Allow comments and trailing commas</span></span>

<span data-ttu-id="f1b4f-281">Per impostazione predefinita, i commenti e le virgole finali non sono consentiti in JSON.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-281">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="f1b4f-282">Per consentire i commenti nel codice JSON, impostare la proprietà <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> su `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-282">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="f1b4f-283">Per consentire le virgole finali, impostare la proprietà <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> su `true`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-283">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="f1b4f-284">Nell'esempio seguente viene illustrato come consentire entrambi:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-284">The following example shows how to allow both:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="f1b4f-285">Di seguito è riportato un esempio JSON con commenti e una virgola finale:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-285">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="f1b4f-286">Corrispondenza proprietà senza distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="f1b4f-286">Case-insensitive property matching</span></span>

<span data-ttu-id="f1b4f-287">Per impostazione predefinita, la deserializzazione Cerca le corrispondenze tra i nomi delle proprietà con distinzione tra maiuscole e minuscole tra JSON e le proprietà dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="f1b4f-287">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="f1b4f-288">Per modificare tale comportamento, impostare <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> su `true`:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-288">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="f1b4f-289">Di seguito è riportato il codice JSON di esempio con i nomi di proprietà Camel case.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-289">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="f1b4f-290">Può essere deserializzato nel tipo seguente con i nomi di proprietà del case Pascal.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-290">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="f1b4f-291">Gestione JSON di overflow</span><span class="sxs-lookup"><span data-stu-id="f1b4f-291">Handle overflow JSON</span></span>

<span data-ttu-id="f1b4f-292">Durante la deserializzazione, è possibile ricevere dati nel file JSON non rappresentato dalle proprietà del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-292">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="f1b4f-293">Si supponga, ad esempio, che il tipo di destinazione sia il seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-293">For example, suppose your target type is this:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="f1b4f-294">Il codice JSON da deserializzare è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-294">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="f1b4f-295">Se si deserializza il codice JSON mostrato nel tipo visualizzato, le proprietà `DatesAvailable` e `SummaryWords` non hanno alcun luogo e andranno perse.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-295">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="f1b4f-296">Per acquisire dati aggiuntivi, ad esempio queste proprietà, applicare l'attributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una proprietà di tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-296">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="f1b4f-297">Quando si deserializza il codice JSON illustrato in precedenza in questo tipo di esempio, i dati aggiuntivi diventano coppie chiave-valore della proprietà `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-297">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="f1b4f-298">Gli</span><span class="sxs-lookup"><span data-stu-id="f1b4f-298">Property</span></span> |<span data-ttu-id="f1b4f-299">Valore</span><span class="sxs-lookup"><span data-stu-id="f1b4f-299">Value</span></span>  |<span data-ttu-id="f1b4f-300">Note</span><span class="sxs-lookup"><span data-stu-id="f1b4f-300">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="f1b4f-301">Date</span><span class="sxs-lookup"><span data-stu-id="f1b4f-301">Date</span></span>    | <span data-ttu-id="f1b4f-302">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="f1b4f-302">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="f1b4f-303">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="f1b4f-303">TemperatureCelsius</span></span>| <span data-ttu-id="f1b4f-304">0</span><span class="sxs-lookup"><span data-stu-id="f1b4f-304">0</span></span> | <span data-ttu-id="f1b4f-305">Mancata corrispondenza tra maiuscole e minuscole (`temperatureCelsius` in JSON), quindi la proprietà non è impostata.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-305">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="f1b4f-306">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="f1b4f-306">Summary</span></span> | <span data-ttu-id="f1b4f-307">Alto</span><span class="sxs-lookup"><span data-stu-id="f1b4f-307">Hot</span></span> ||
| <span data-ttu-id="f1b4f-308">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="f1b4f-308">ExtensionData</span></span> | <span data-ttu-id="f1b4f-309">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="f1b4f-309">temperatureCelsius: 25</span></span> |<span data-ttu-id="f1b4f-310">Poiché il caso non corrisponde, questa proprietà JSON è un oggetto aggiuntivo e diventa una coppia chiave-valore nel dizionario.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-310">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="f1b4f-311">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-311">DatesAvailable:</span></span><br>  <span data-ttu-id="f1b4f-312">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="f1b4f-312">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="f1b4f-313">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="f1b4f-313">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="f1b4f-314">Una proprietà aggiuntiva da JSON diventa una coppia chiave-valore, con una matrice come oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-314">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="f1b4f-315">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-315">SummaryWords:</span></span><br><span data-ttu-id="f1b4f-316">Comode</span><span class="sxs-lookup"><span data-stu-id="f1b4f-316">Cool</span></span><br><span data-ttu-id="f1b4f-317">Ventoso</span><span class="sxs-lookup"><span data-stu-id="f1b4f-317">Windy</span></span><br><span data-ttu-id="f1b4f-318">Umido</span><span class="sxs-lookup"><span data-stu-id="f1b4f-318">Humid</span></span> |<span data-ttu-id="f1b4f-319">Una proprietà aggiuntiva da JSON diventa una coppia chiave-valore, con una matrice come oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-319">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="f1b4f-320">Quando l'oggetto di destinazione viene serializzato, le coppie chiave-valore dei dati di estensione diventano proprietà JSON esattamente come nel codice JSON in ingresso:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-320">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="f1b4f-321">Si noti che il nome della proprietà `ExtensionData` non viene visualizzato in JSON.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-321">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="f1b4f-322">Questo comportamento consente a JSON di creare un round trip senza perdere dati aggiuntivi che altrimenti non sarebbero deserializzati.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-322">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="f1b4f-323">Ignora null durante la deserializzazione</span><span class="sxs-lookup"><span data-stu-id="f1b4f-323">Ignore null when deserializing</span></span>

<span data-ttu-id="f1b4f-324">Per impostazione predefinita, se una proprietà in JSON è null, la proprietà corrispondente nell'oggetto di destinazione viene impostata su null.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-324">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="f1b4f-325">In alcuni scenari, la proprietà di destinazione potrebbe avere un valore predefinito e non si vuole che un valore null esegua l'override del valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-325">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="f1b4f-326">Si supponga, ad esempio, che il codice seguente rappresenti l'oggetto di destinazione:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-326">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="f1b4f-327">Si supponga che venga deserializzato il codice JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-327">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="f1b4f-328">Dopo la deserializzazione, la proprietà `Summary` dell'oggetto `WeatherForecastWithDefault` è null.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-328">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="f1b4f-329">Per modificare questo comportamento, impostare <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> su `true`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-329">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="f1b4f-330">Con questa opzione, la proprietà `Summary` dell'oggetto `WeatherForecastWithDefault` è il valore predefinito "nessun riepilogo" dopo la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-330">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="f1b4f-331">I valori null nel codice JSON vengono ignorati solo se sono validi.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-331">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="f1b4f-332">I valori null per i tipi di valore non nullable generano eccezioni.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-332">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="f1b4f-333">Per altre informazioni, vedere il [problema 40922 sui tipi di valore non nullable](https://github.com/dotnet/corefx/issues/40922) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-333">For more information, see [issue 40922 on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="f1b4f-334">Utf8JsonReader, Utf8JsonWriter e JsonDocument</span><span class="sxs-lookup"><span data-stu-id="f1b4f-334">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="f1b4f-335"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> è un lettore forward-only a prestazioni elevate e allocazione ridotta per il testo JSON con codifica UTF-8, letto da `ReadOnlySpan<byte>`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-335"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="f1b4f-336">Il `Utf8JsonReader` è un tipo di basso livello che può essere utilizzato per compilare parser e deserializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-336">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="f1b4f-337">Il metodo <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> utilizza `Utf8JsonReader` sotto le quinte.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-337">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="f1b4f-338"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> è un modo a prestazioni elevate per scrivere testo JSON con codifica UTF-8 da tipi .NET comuni come `String`, `Int32`e `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-338"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="f1b4f-339">Il writer è un tipo di basso livello che può essere utilizzato per compilare serializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-339">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="f1b4f-340">Il metodo <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> utilizza `Utf8JsonWriter` sotto le quinte.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-340">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="f1b4f-341"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> fornisce la possibilità di creare un Document Object Model di sola lettura (DOM) utilizzando `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-341"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="f1b4f-342">Il DOM fornisce l'accesso casuale ai dati in un payload JSON.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-342">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="f1b4f-343">È possibile accedere agli elementi JSON che compongono il payload tramite il tipo di <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-343">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="f1b4f-344">Il tipo di `JsonElement` fornisce enumeratori di oggetti e matrici insieme alle API per convertire il testo JSON in tipi .NET comuni.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-344">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="f1b4f-345">`JsonDocument` espone una proprietà <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-345">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="f1b4f-346">Le sezioni seguenti illustrano come usare questi strumenti per la lettura e la scrittura di JSON.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-346">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="f1b4f-347">Usare JsonDocument per l'accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="f1b4f-347">Use JsonDocument for access to data</span></span>

<span data-ttu-id="f1b4f-348">L'esempio seguente illustra come usare la classe <xref:System.Text.Json.JsonDocument> per l'accesso casuale ai dati in una stringa JSON:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-348">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="f1b4f-349">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-349">The preceding code:</span></span>

* <span data-ttu-id="f1b4f-350">Presuppone che il codice JSON da analizzare si trovi in una stringa denominata `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-350">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="f1b4f-351">Calcola un livello medio per gli oggetti in una matrice di `Students` con una proprietà `Grade`.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-351">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="f1b4f-352">Assegna un livello predefinito di 70 per gli studenti che non hanno un livello.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-352">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="f1b4f-353">Conta gli studenti incrementando una variabile di `count` a ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-353">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="f1b4f-354">In alternativa, è possibile chiamare <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-354">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="f1b4f-355">Di seguito è riportato un esempio del codice JSON elaborato da questo codice:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-355">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="f1b4f-356">Usare JsonDocument per scrivere JSON</span><span class="sxs-lookup"><span data-stu-id="f1b4f-356">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="f1b4f-357">Nell'esempio seguente viene illustrato come scrivere JSON da un <xref:System.Text.Json.JsonDocument>:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-357">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="f1b4f-358">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-358">The preceding code:</span></span>

* <span data-ttu-id="f1b4f-359">Legge un file JSON, carica i dati in un `JsonDocument`e scrive JSON formattato (abbastanza stampato) in un file.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-359">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="f1b4f-360">USA <xref:System.Text.Json.JsonDocumentOptions> per specificare che i commenti nel codice JSON di input sono consentiti ma ignorati.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-360">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="f1b4f-361">Al termine, chiama <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> sul writer.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-361">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="f1b4f-362">In alternativa, è possibile lasciare che il writer AutoFlush quando viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-362">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="f1b4f-363">Di seguito è riportato un esempio di input JSON che verrà elaborato dal codice di esempio:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-363">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

<span data-ttu-id="f1b4f-364">Il risultato è l'output JSON abbastanza stampato seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-364">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="f1b4f-365">Usare Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="f1b4f-365">Use Utf8JsonWriter</span></span>

<span data-ttu-id="f1b4f-366">Nell'esempio seguente viene illustrato come utilizzare la classe <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-366">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="f1b4f-367">Usare Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="f1b4f-367">Use Utf8JsonReader</span></span>

<span data-ttu-id="f1b4f-368">Nell'esempio seguente viene illustrato come utilizzare la classe <xref:System.Text.Json.Utf8JsonReader>:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-368">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="f1b4f-369">Il codice precedente presuppone che la variabile `jsonUtf8` sia una matrice di byte che contiene JSON valido, codificato come UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-369">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="f1b4f-370">Filtrare i dati tramite Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="f1b4f-370">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="f1b4f-371">Nell'esempio seguente viene illustrato come leggere un file in modo sincrono e cercare un valore:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-371">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="f1b4f-372">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-372">The preceding code:</span></span>

* <span data-ttu-id="f1b4f-373">Presuppone che il file sia codificato come UTF-16 e lo transcodifichi in UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-373">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="f1b4f-374">Un file codificato come UTF-8 può essere letto direttamente in una `ReadOnlySpan<byte>`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f1b4f-374">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* <span data-ttu-id="f1b4f-375">Presuppone che JSON contenga una matrice di oggetti e che ogni oggetto possa contenere una proprietà "Name" di tipo String.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-375">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="f1b4f-376">Conta gli oggetti e `name` i valori delle proprietà che terminano con "University".</span><span class="sxs-lookup"><span data-stu-id="f1b4f-376">Counts objects and `name` property values that end with "University".</span></span>

<span data-ttu-id="f1b4f-377">Di seguito è riportato un esempio JSON che il codice precedente può leggere.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-377">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="f1b4f-378">Il messaggio di riepilogo risultante è "2 su 4 hanno nomi che terminano con" University "":</span><span class="sxs-lookup"><span data-stu-id="f1b4f-378">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a><span data-ttu-id="f1b4f-379">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f1b4f-379">Additional resources</span></span>

* [<span data-ttu-id="f1b4f-380">Panoramica di System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="f1b4f-380">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="f1b4f-381">Informazioni di riferimento sull'API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="f1b4f-381">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="f1b4f-382">Scrivere convertitori personalizzati per System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="f1b4f-382">Write custom converters for System.Text.Json</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="f1b4f-383">Supporto di DateTime e DateTimeOffset in System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="f1b4f-383">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* [<span data-ttu-id="f1b4f-384">Problemi di GitHub nel repository DotNet/CoreFx con etichetta JSON-funzionalità-doc</span><span class="sxs-lookup"><span data-stu-id="f1b4f-384">GitHub issues in the dotnet/corefx repository labeled json-functionality-doc</span></span>](https://github.com/dotnet/corefx/labels/json-functionality-doc) 
