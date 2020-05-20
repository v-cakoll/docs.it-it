---
title: ''
description: Questo articolo illustra come usare lo System.Text.Json spazio dei nomi per serializzare e deserializzare da JSON in .NET. Include il codice di esempio.
ms.date: ''
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords: []
ms.openlocfilehash: f1a5da448b08f9b4f1cf3fa6cba67fb376b00a6f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702244"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="dab64-103">Come serializzare e deserializzare (effettuare il marshalling e unmarshalling) JSON in .NET</span><span class="sxs-lookup"><span data-stu-id="dab64-103">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="dab64-104">Questo articolo illustra come usare lo <xref:System.Text.Json> spazio dei nomi per serializzare e deserializzare da e verso JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="dab64-104">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="dab64-105">Se si esegue il porting di codice esistente da `Newtonsoft.Json` , vedere [come eseguire `System.Text.Json` la migrazione a ](system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="dab64-105">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="dab64-106">Le direzioni e il codice di esempio usano la libreria direttamente, non tramite un Framework come [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="dab64-106">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="dab64-107">La maggior parte del codice di esempio di serializzazione imposta <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> su `true` "Pretty-Print" JSON (con rientri e spazi vuoti per la leggibilità umana).</span><span class="sxs-lookup"><span data-stu-id="dab64-107">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="dab64-108">Per l'uso in produzione, in genere si accetta il valore predefinito di `false` per questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="dab64-108">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="dab64-109">Gli esempi di codice fanno riferimento alla classe e alle varianti seguenti:</span><span class="sxs-lookup"><span data-stu-id="dab64-109">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="dab64-110">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="dab64-110">Namespaces</span></span>

<span data-ttu-id="dab64-111">Lo <xref:System.Text.Json> spazio dei nomi contiene tutti i punti di ingresso e i tipi principali.</span><span class="sxs-lookup"><span data-stu-id="dab64-111">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="dab64-112">Lo <xref:System.Text.Json.Serialization> spazio dei nomi contiene attributi e API per scenari avanzati e personalizzazione specifici per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="dab64-112">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="dab64-113">Gli esempi di codice illustrati in questo articolo richiedono `using` direttive per uno o entrambi gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dab64-113">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="dab64-114">Gli attributi dello <xref:System.Runtime.Serialization> spazio dei nomi non sono attualmente supportati in `System.Text.Json` .</span><span class="sxs-lookup"><span data-stu-id="dab64-114">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="dab64-115">Come scrivere oggetti .NET in JSON (Serialize)</span><span class="sxs-lookup"><span data-stu-id="dab64-115">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="dab64-116">Per scrivere JSON in una stringa o in un file, chiamare il <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="dab64-116">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="dab64-117">Nell'esempio seguente viene creato JSON come stringa:</span><span class="sxs-lookup"><span data-stu-id="dab64-117">The following example creates JSON as a string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="dab64-118">Nell'esempio seguente viene usato il codice sincrono per creare un file JSON:</span><span class="sxs-lookup"><span data-stu-id="dab64-118">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="dab64-119">Nell'esempio seguente viene usato il codice asincrono per creare un file JSON:</span><span class="sxs-lookup"><span data-stu-id="dab64-119">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="dab64-120">Negli esempi precedenti viene utilizzata l'inferenza del tipo per il tipo da serializzare.</span><span class="sxs-lookup"><span data-stu-id="dab64-120">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="dab64-121">Un overload di `Serialize()` accetta un parametro di tipo generico:</span><span class="sxs-lookup"><span data-stu-id="dab64-121">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="dab64-122">Esempio di serializzazione</span><span class="sxs-lookup"><span data-stu-id="dab64-122">Serialization example</span></span>

<span data-ttu-id="dab64-123">Di seguito è riportato un esempio di classe che contiene le raccolte e una classe annidata:</span><span class="sxs-lookup"><span data-stu-id="dab64-123">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="dab64-124">L'output JSON della serializzazione di un'istanza del tipo precedente è simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="dab64-124">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="dab64-125">Per impostazione predefinita, l'output JSON è minimizzati:</span><span class="sxs-lookup"><span data-stu-id="dab64-125">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="dab64-126">Nell'esempio seguente viene illustrato lo stesso JSON, formattato, ovvero abbastanza stampato con spazi vuoti e rientri:</span><span class="sxs-lookup"><span data-stu-id="dab64-126">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="dab64-127">Serializza in UTF-8</span><span class="sxs-lookup"><span data-stu-id="dab64-127">Serialize to UTF-8</span></span>

<span data-ttu-id="dab64-128">Per serializzare in UTF-8, chiamare il <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> Metodo:</span><span class="sxs-lookup"><span data-stu-id="dab64-128">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="dab64-129"><xref:System.Text.Json.JsonSerializer.Serialize%2A>È disponibile anche un overload che accetta un oggetto <xref:System.Text.Json.Utf8JsonWriter> .</span><span class="sxs-lookup"><span data-stu-id="dab64-129">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="dab64-130">La serializzazione in UTF-8 è più veloce del 5-10% rispetto all'uso dei metodi basati su stringa.</span><span class="sxs-lookup"><span data-stu-id="dab64-130">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="dab64-131">La differenza è dovuta al fatto che i byte (come UTF-8) non devono essere convertiti in stringhe (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="dab64-131">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="dab64-132">Comportamento della serializzazione</span><span class="sxs-lookup"><span data-stu-id="dab64-132">Serialization behavior</span></span>

* <span data-ttu-id="dab64-133">Per impostazione predefinita, tutte le proprietà pubbliche vengono serializzate.</span><span class="sxs-lookup"><span data-stu-id="dab64-133">By default, all public properties are serialized.</span></span> <span data-ttu-id="dab64-134">È possibile [specificare le proprietà da escludere](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="dab64-134">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="dab64-135">Il [codificatore predefinito](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) consente di eseguire il escape dei caratteri non ASCII, dei caratteri con distinzione HTML all'interno dell'intervallo ASCII e dei caratteri che devono essere preceduti da un carattere di escape in base alla [specifica JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="dab64-135">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="dab64-136">Per impostazione predefinita, JSON è minimizzati.</span><span class="sxs-lookup"><span data-stu-id="dab64-136">By default, JSON is minified.</span></span> <span data-ttu-id="dab64-137">È possibile [stampare](#serialize-to-formatted-json)in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="dab64-137">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="dab64-138">Per impostazione predefinita, le maiuscole e minuscole dei nomi JSON corrispondono ai nomi .NET.</span><span class="sxs-lookup"><span data-stu-id="dab64-138">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="dab64-139">È possibile [personalizzare la combinazione di maiuscole e minuscole](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="dab64-139">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="dab64-140">Vengono rilevati riferimenti circolari e vengono generate eccezioni.</span><span class="sxs-lookup"><span data-stu-id="dab64-140">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="dab64-141">Attualmente, i campi vengono esclusi.</span><span class="sxs-lookup"><span data-stu-id="dab64-141">Currently, fields are excluded.</span></span>

<span data-ttu-id="dab64-142">I tipi supportati includono:</span><span class="sxs-lookup"><span data-stu-id="dab64-142">Supported types include:</span></span>

* <span data-ttu-id="dab64-143">Primitive .NET mappate a primitive JavaScript, ad esempio tipi numerici, stringhe e valori booleani.</span><span class="sxs-lookup"><span data-stu-id="dab64-143">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="dab64-144">[Oggetti CLR obsoleti definiti dall'utente (poco)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="dab64-144">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="dab64-145">Matrici unidimensionali e irregolari ( `ArrayName[][]` ).</span><span class="sxs-lookup"><span data-stu-id="dab64-145">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="dab64-146">`Dictionary<string,TValue>`dove `TValue` è `object` , `JsonElement` o poco.</span><span class="sxs-lookup"><span data-stu-id="dab64-146">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="dab64-147">Raccolte dai seguenti spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dab64-147">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="dab64-148">È possibile [implementare convertitori personalizzati](system-text-json-converters-how-to.md) per gestire tipi aggiuntivi o per fornire funzionalità non supportate dai convertitori incorporati.</span><span class="sxs-lookup"><span data-stu-id="dab64-148">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="dab64-149">Come leggere JSON in oggetti .NET (deserializzare)</span><span class="sxs-lookup"><span data-stu-id="dab64-149">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="dab64-150">Per eseguire la deserializzazione da una stringa o da un file, chiamare il <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="dab64-150">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="dab64-151">Nell'esempio seguente viene letto JSON da una stringa e viene creata un'istanza della `WeatherForecast` classe illustrata in precedenza per l' [esempio di serializzazione](#serialization-example):</span><span class="sxs-lookup"><span data-stu-id="dab64-151">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="dab64-152">Per eseguire la deserializzazione da un file usando il codice sincrono, leggere il file in una stringa, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-152">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="dab64-153">Per eseguire la deserializzazione da un file usando il codice asincrono, chiamare il <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> Metodo:</span><span class="sxs-lookup"><span data-stu-id="dab64-153">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="dab64-154">Deserializzazione da UTF-8</span><span class="sxs-lookup"><span data-stu-id="dab64-154">Deserialize from UTF-8</span></span>

<span data-ttu-id="dab64-155">Per deserializzare da UTF-8, chiamare un <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> Overload che accetta un oggetto `Utf8JsonReader` o `ReadOnlySpan<byte>` , come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="dab64-155">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="dab64-156">Gli esempi presuppongono che JSON si trovi in una matrice di byte denominata jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="dab64-156">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="dab64-157">Comportamento di deserializzazione</span><span class="sxs-lookup"><span data-stu-id="dab64-157">Deserialization behavior</span></span>

* <span data-ttu-id="dab64-158">Per impostazione predefinita, la corrispondenza dei nomi di proprietà fa distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="dab64-158">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="dab64-159">È possibile specificare la distinzione tra [maiuscole e minuscole](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="dab64-159">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="dab64-160">Se il codice JSON contiene un valore per una proprietà di sola lettura, il valore viene ignorato e non viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="dab64-160">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="dab64-161">La deserializzazione ai tipi di riferimento senza un costruttore senza parametri non è supportata.</span><span class="sxs-lookup"><span data-stu-id="dab64-161">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="dab64-162">La deserializzazione a oggetti non modificabili o a proprietà di sola lettura non è supportata.</span><span class="sxs-lookup"><span data-stu-id="dab64-162">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="dab64-163">Per impostazione predefinita, le enumerazioni sono supportate come numeri.</span><span class="sxs-lookup"><span data-stu-id="dab64-163">By default, enums are supported as numbers.</span></span> <span data-ttu-id="dab64-164">È possibile [serializzare i nomi di enumerazione come stringhe](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="dab64-164">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="dab64-165">I campi non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="dab64-165">Fields aren't supported.</span></span>
* <span data-ttu-id="dab64-166">Per impostazione predefinita, i commenti o le virgole finali in JSON generano eccezioni.</span><span class="sxs-lookup"><span data-stu-id="dab64-166">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="dab64-167">È possibile [consentire i commenti e le virgole finali](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="dab64-167">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="dab64-168">La [profondità massima predefinita](xref:System.Text.Json.JsonReaderOptions.MaxDepth) è 64.</span><span class="sxs-lookup"><span data-stu-id="dab64-168">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="dab64-169">È possibile [implementare convertitori personalizzati](system-text-json-converters-how-to.md) per fornire funzionalità non supportate dai convertitori incorporati.</span><span class="sxs-lookup"><span data-stu-id="dab64-169">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="dab64-170">Serializza nel formato JSON formattato</span><span class="sxs-lookup"><span data-stu-id="dab64-170">Serialize to formatted JSON</span></span>

<span data-ttu-id="dab64-171">Per stampare l'output JSON, impostare <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> su `true` :</span><span class="sxs-lookup"><span data-stu-id="dab64-171">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="dab64-172">Di seguito è riportato un esempio di tipo da serializzare e da un output JSON abbastanza stampato:</span><span class="sxs-lookup"><span data-stu-id="dab64-172">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="dab64-173">Personalizzare i nomi e i valori JSON</span><span class="sxs-lookup"><span data-stu-id="dab64-173">Customize JSON names and values</span></span>

<span data-ttu-id="dab64-174">Per impostazione predefinita, i nomi delle proprietà e le chiavi del dizionario non cambiano nell'output JSON, inclusa la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="dab64-174">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="dab64-175">I valori enum sono rappresentati come numeri.</span><span class="sxs-lookup"><span data-stu-id="dab64-175">Enum values are represented as numbers.</span></span> <span data-ttu-id="dab64-176">Questa sezione illustra come eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="dab64-176">This section explains how to:</span></span>

* [<span data-ttu-id="dab64-177">Personalizzare i singoli nomi di proprietà</span><span class="sxs-lookup"><span data-stu-id="dab64-177">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="dab64-178">Converte tutti i nomi di proprietà in Camel case</span><span class="sxs-lookup"><span data-stu-id="dab64-178">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="dab64-179">Implementare i criteri di denominazione delle proprietà personalizzate</span><span class="sxs-lookup"><span data-stu-id="dab64-179">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="dab64-180">Converte le chiavi del dizionario in lettere maiuscole</span><span class="sxs-lookup"><span data-stu-id="dab64-180">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="dab64-181">Converte le enumerazioni in stringhe e maiuscole</span><span class="sxs-lookup"><span data-stu-id="dab64-181">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="dab64-182">Per altri scenari che richiedono una gestione speciale dei nomi e dei valori delle proprietà JSON, è possibile [implementare convertitori personalizzati](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="dab64-182">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="dab64-183">Personalizzare i singoli nomi di proprietà</span><span class="sxs-lookup"><span data-stu-id="dab64-183">Customize individual property names</span></span>

<span data-ttu-id="dab64-184">Per impostare il nome delle singole proprietà, utilizzare l'attributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="dab64-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="dab64-185">Di seguito è riportato un esempio di tipo da serializzare e JSON risultante:</span><span class="sxs-lookup"><span data-stu-id="dab64-185">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="dab64-186">Nome della proprietà impostato dall'attributo:</span><span class="sxs-lookup"><span data-stu-id="dab64-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="dab64-187">Si applica in entrambe le direzioni, per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="dab64-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="dab64-188">Ha la precedenza sui criteri di denominazione delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="dab64-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="dab64-189">Usa il caso Camel per tutti i nomi di proprietà JSON</span><span class="sxs-lookup"><span data-stu-id="dab64-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="dab64-190">Per usare il caso Camel per tutti i nomi di proprietà JSON, impostare <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> su `JsonNamingPolicy.CamelCase` , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="dab64-191">Ecco una classe di esempio per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="dab64-191">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="dab64-192">Criteri di denominazione delle proprietà Camel case:</span><span class="sxs-lookup"><span data-stu-id="dab64-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="dab64-193">Si applica alla serializzazione e alla deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="dab64-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="dab64-194">Viene sottoposto a override dagli `[JsonPropertyName]` attributi.</span><span class="sxs-lookup"><span data-stu-id="dab64-194">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="dab64-195">Questo è il motivo per cui il nome della proprietà JSON `Wind` nell'esempio non è un case Camel.</span><span class="sxs-lookup"><span data-stu-id="dab64-195">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="dab64-196">Usare un criterio personalizzato per la denominazione delle proprietà JSON</span><span class="sxs-lookup"><span data-stu-id="dab64-196">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="dab64-197">Per usare un criterio di denominazione delle proprietà JSON personalizzato, creare una classe che derivi da <xref:System.Text.Json.JsonNamingPolicy> ed eseguire l'override del <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> metodo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-197">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="dab64-198">Impostare quindi la <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> proprietà su un'istanza della classe di criteri di denominazione:</span><span class="sxs-lookup"><span data-stu-id="dab64-198">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="dab64-199">Ecco una classe di esempio per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="dab64-199">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="dab64-200">Criteri di denominazione delle proprietà JSON:</span><span class="sxs-lookup"><span data-stu-id="dab64-200">The JSON property naming policy:</span></span>

* <span data-ttu-id="dab64-201">Si applica alla serializzazione e alla deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="dab64-201">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="dab64-202">Viene sottoposto a override dagli `[JsonPropertyName]` attributi.</span><span class="sxs-lookup"><span data-stu-id="dab64-202">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="dab64-203">Questo è il motivo per cui il nome della proprietà JSON `Wind` nell'esempio non è maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="dab64-203">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="dab64-204">Chiavi del dizionario case Camel</span><span class="sxs-lookup"><span data-stu-id="dab64-204">Camel case dictionary keys</span></span>

<span data-ttu-id="dab64-205">Se una proprietà di un oggetto da serializzare è di tipo `Dictionary<string,TValue>` , le `string` chiavi possono essere convertite in maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="dab64-205">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="dab64-206">A tale scopo, impostare <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> su `JsonNamingPolicy.CamelCase` , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-206">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="dab64-207">La serializzazione di un oggetto con un dizionario denominato `TemperatureRanges` che include coppie chiave-valore `"ColdMinTemp", 20` e `"HotMinTemp", 40` genera output JSON come l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-207">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="dab64-208">I criteri di denominazione Camel case per le chiavi del dizionario si applicano solo alla serializzazione.</span><span class="sxs-lookup"><span data-stu-id="dab64-208">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="dab64-209">Se si deserializza un dizionario, le chiavi corrisponderanno al file JSON anche se si specifica `JsonNamingPolicy.CamelCase` per il `DictionaryKeyPolicy` .</span><span class="sxs-lookup"><span data-stu-id="dab64-209">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="dab64-210">Enumerazioni come stringhe</span><span class="sxs-lookup"><span data-stu-id="dab64-210">Enums as strings</span></span>

<span data-ttu-id="dab64-211">Per impostazione predefinita, le enumerazioni vengono serializzate come numeri.</span><span class="sxs-lookup"><span data-stu-id="dab64-211">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="dab64-212">Per serializzare i nomi di enumerazione come stringhe, usare <xref:System.Text.Json.Serialization.JsonStringEnumConverter> .</span><span class="sxs-lookup"><span data-stu-id="dab64-212">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="dab64-213">Si supponga, ad esempio, di dover serializzare la classe seguente che contiene un'enumerazione:</span><span class="sxs-lookup"><span data-stu-id="dab64-213">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="dab64-214">Se il riepilogo è `Hot` , per impostazione predefinita il JSON serializzato ha il valore numerico 3:</span><span class="sxs-lookup"><span data-stu-id="dab64-214">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="dab64-215">Il codice di esempio seguente serializza i nomi di enumerazione invece dei valori numerici e converte i nomi in lettere maiuscole:</span><span class="sxs-lookup"><span data-stu-id="dab64-215">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="dab64-216">Il codice JSON risultante è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-216">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="dab64-217">È anche possibile deserializzare i nomi di stringa enum, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-217">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="dab64-218">Escludi proprietà dalla serializzazione</span><span class="sxs-lookup"><span data-stu-id="dab64-218">Exclude properties from serialization</span></span>

<span data-ttu-id="dab64-219">Per impostazione predefinita, tutte le proprietà pubbliche vengono serializzate.</span><span class="sxs-lookup"><span data-stu-id="dab64-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="dab64-220">Se non si vuole che alcuni di essi vengano visualizzati nell'output JSON, sono disponibili diverse opzioni.</span><span class="sxs-lookup"><span data-stu-id="dab64-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="dab64-221">In questa sezione viene illustrato come escludere:</span><span class="sxs-lookup"><span data-stu-id="dab64-221">This section explains how to exclude:</span></span>

* [<span data-ttu-id="dab64-222">Singole proprietà</span><span class="sxs-lookup"><span data-stu-id="dab64-222">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="dab64-223">Tutte le proprietà di sola lettura</span><span class="sxs-lookup"><span data-stu-id="dab64-223">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="dab64-224">Tutte le proprietà con valore null</span><span class="sxs-lookup"><span data-stu-id="dab64-224">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="dab64-225">Escludi singole proprietà</span><span class="sxs-lookup"><span data-stu-id="dab64-225">Exclude individual properties</span></span>

<span data-ttu-id="dab64-226">Per ignorare le singole proprietà, utilizzare l'attributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="dab64-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="dab64-227">Ecco un esempio di tipo per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="dab64-227">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="dab64-228">Escludi tutte le proprietà di sola lettura</span><span class="sxs-lookup"><span data-stu-id="dab64-228">Exclude all read-only properties</span></span>

<span data-ttu-id="dab64-229">Una proprietà è di sola lettura se contiene un getter pubblico ma non un setter pubblico.</span><span class="sxs-lookup"><span data-stu-id="dab64-229">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="dab64-230">Per escludere tutte le proprietà di sola lettura, impostare <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> su `true` , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-230">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="dab64-231">Ecco un esempio di tipo per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="dab64-231">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="dab64-232">Questa opzione si applica solo alla serializzazione.</span><span class="sxs-lookup"><span data-stu-id="dab64-232">This option applies only to serialization.</span></span> <span data-ttu-id="dab64-233">Durante la deserializzazione, le proprietà di sola lettura vengono ignorate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="dab64-233">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="dab64-234">Escludi tutte le proprietà dei valori null</span><span class="sxs-lookup"><span data-stu-id="dab64-234">Exclude all null value properties</span></span>

<span data-ttu-id="dab64-235">Per escludere tutte le proprietà con valore null, impostare la <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> proprietà su `true` , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="dab64-236">Di seguito è riportato un esempio di oggetto da serializzare e output JSON:</span><span class="sxs-lookup"><span data-stu-id="dab64-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="dab64-237">Proprietà</span><span class="sxs-lookup"><span data-stu-id="dab64-237">Property</span></span> |<span data-ttu-id="dab64-238">Value</span><span class="sxs-lookup"><span data-stu-id="dab64-238">Value</span></span>  |
|---
<span data-ttu-id="dab64-239">title: Description:' questo articolo illustra come usare lo System.Text.Json spazio dei nomi per serializzare e deserializzare da JSON in .NET.</span><span class="sxs-lookup"><span data-stu-id="dab64-239">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="dab64-240">Include il codice di esempio ".</span><span class="sxs-lookup"><span data-stu-id="dab64-240">It includes sample code.'</span></span>
<span data-ttu-id="dab64-241">ms. Date: No-loc:</span><span class="sxs-lookup"><span data-stu-id="dab64-241">ms.date: no-loc:</span></span>
- <span data-ttu-id="dab64-242">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="dab64-242">'System.Text.Json'</span></span>
- <span data-ttu-id="dab64-243">' Newtonsoft.Json ' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="dab64-243">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="dab64-244">title: Description:' questo articolo illustra come usare lo System.Text.Json spazio dei nomi per serializzare e deserializzare da JSON in .NET.</span><span class="sxs-lookup"><span data-stu-id="dab64-244">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="dab64-245">Include il codice di esempio ".</span><span class="sxs-lookup"><span data-stu-id="dab64-245">It includes sample code.'</span></span>
<span data-ttu-id="dab64-246">ms. Date: No-loc:</span><span class="sxs-lookup"><span data-stu-id="dab64-246">ms.date: no-loc:</span></span>
- <span data-ttu-id="dab64-247">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="dab64-247">'System.Text.Json'</span></span>
- <span data-ttu-id="dab64-248">' Newtonsoft.Json ' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="dab64-248">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="dab64-249">-----|---title: Description:' questo articolo illustra come usare lo System.Text.Json spazio dei nomi per serializzare e deserializzare da JSON in .NET.</span><span class="sxs-lookup"><span data-stu-id="dab64-249">-----|--- title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="dab64-250">Include il codice di esempio ".</span><span class="sxs-lookup"><span data-stu-id="dab64-250">It includes sample code.'</span></span>
<span data-ttu-id="dab64-251">ms. Date: No-loc:</span><span class="sxs-lookup"><span data-stu-id="dab64-251">ms.date: no-loc:</span></span>
- <span data-ttu-id="dab64-252">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="dab64-252">'System.Text.Json'</span></span>
- <span data-ttu-id="dab64-253">' Newtonsoft.Json ' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="dab64-253">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="dab64-254">title: Description:' questo articolo illustra come usare lo System.Text.Json spazio dei nomi per serializzare e deserializzare da JSON in .NET.</span><span class="sxs-lookup"><span data-stu-id="dab64-254">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="dab64-255">Include il codice di esempio ".</span><span class="sxs-lookup"><span data-stu-id="dab64-255">It includes sample code.'</span></span>
<span data-ttu-id="dab64-256">ms. Date: No-loc:</span><span class="sxs-lookup"><span data-stu-id="dab64-256">ms.date: no-loc:</span></span>
- <span data-ttu-id="dab64-257">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="dab64-257">'System.Text.Json'</span></span>
- <span data-ttu-id="dab64-258">' Newtonsoft.Json ' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="dab64-258">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="dab64-259">-----| | Data | 8/1/2019 12:00:00 AM-07:00 | | TemperatureCelsius | 25 | | Riepilogo | null |</span><span class="sxs-lookup"><span data-stu-id="dab64-259">-----| | Date    | 8/1/2019 12:00:00 AM -07:00| | TemperatureCelsius| 25 | | Summary| null|</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="dab64-260">Questa impostazione si applica alla serializzazione e alla deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="dab64-260">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="dab64-261">Per informazioni sugli effetti sulla deserializzazione, vedere [Ignore null durante la deserializzazione](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="dab64-261">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="dab64-262">Personalizzare la codifica caratteri</span><span class="sxs-lookup"><span data-stu-id="dab64-262">Customize character encoding</span></span>

<span data-ttu-id="dab64-263">Per impostazione predefinita, il serializzatore viene sottoposto a escape per tutti i caratteri non ASCII.</span><span class="sxs-lookup"><span data-stu-id="dab64-263">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="dab64-264">Ovvero, li sostituisce con `\uxxxx` Where `xxxx` è il codice Unicode del carattere.</span><span class="sxs-lookup"><span data-stu-id="dab64-264">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="dab64-265">Se, ad esempio, la `Summary` proprietà è impostata su cirillico жарко, l' `WeatherForecast` oggetto viene serializzato come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-265">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="dab64-266">Serializza i set di caratteri della lingua</span><span class="sxs-lookup"><span data-stu-id="dab64-266">Serialize language character sets</span></span>

<span data-ttu-id="dab64-267">Per serializzare i set di caratteri di una o più lingue senza eseguire l'escape, specificare gli [intervalli Unicode](xref:System.Text.Unicode.UnicodeRanges) durante la creazione di un'istanza di <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-267">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="dab64-268">Questo codice non esegue l'escape di caratteri cirillici o greci.</span><span class="sxs-lookup"><span data-stu-id="dab64-268">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="dab64-269">Se la `Summary` proprietà è impostata su cirillico жарко, l' `WeatherForecast` oggetto viene serializzato come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-269">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="dab64-270">Per serializzare tutti i set di lingue senza escape, usare <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="dab64-270">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="dab64-271">Serializza caratteri specifici</span><span class="sxs-lookup"><span data-stu-id="dab64-271">Serialize specific characters</span></span>

<span data-ttu-id="dab64-272">In alternativa, è possibile specificare i singoli caratteri che si desidera consentire tramite senza che venga eseguito il escape.</span><span class="sxs-lookup"><span data-stu-id="dab64-272">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="dab64-273">Nell'esempio seguente vengono serializzati solo i primi due caratteri di жарко:</span><span class="sxs-lookup"><span data-stu-id="dab64-273">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="dab64-274">Di seguito è riportato un esempio di JSON prodotto dal codice precedente:</span><span class="sxs-lookup"><span data-stu-id="dab64-274">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="dab64-275">Serializza tutti i caratteri</span><span class="sxs-lookup"><span data-stu-id="dab64-275">Serialize all characters</span></span>

<span data-ttu-id="dab64-276">Per ridurre al minimo l'escape, è possibile usare <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-276">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="dab64-277">Rispetto al codificatore predefinito, il `UnsafeRelaxedJsonEscaping` codificatore è più permissivo per consentire il pass-through senza caratteri di escape:</span><span class="sxs-lookup"><span data-stu-id="dab64-277">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="dab64-278">Non esegue l'escape di caratteri con distinzione HTML come `<` ,, `>` `&` e `'` .</span><span class="sxs-lookup"><span data-stu-id="dab64-278">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="dab64-279">Non offre protezioni aggiuntive per la difesa in profondità da attacchi XSS o divulgazione di informazioni, ad esempio quelli che potrebbero risultare dal client e dal server che non accettano il *set di caratteri*.</span><span class="sxs-lookup"><span data-stu-id="dab64-279">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="dab64-280">Usare il codificatore unsafe solo quando è noto che il client interpreterà il payload risultante come JSON con codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="dab64-280">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="dab64-281">Ad esempio, è possibile usarlo se il server sta inviando l'intestazione della risposta `Content-Type: application/json; charset=utf-8` .</span><span class="sxs-lookup"><span data-stu-id="dab64-281">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="dab64-282">Non consentire mai l' `UnsafeRelaxedJsonEscaping` emissione dell'output non elaborato in una pagina HTML o in un `<script>` elemento.</span><span class="sxs-lookup"><span data-stu-id="dab64-282">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="dab64-283">Serializzare le proprietà delle classi derivate</span><span class="sxs-lookup"><span data-stu-id="dab64-283">Serialize properties of derived classes</span></span>

<span data-ttu-id="dab64-284">La serializzazione di una gerarchia di tipi polimorfici non è supportata.</span><span class="sxs-lookup"><span data-stu-id="dab64-284">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="dab64-285">Se, ad esempio, una proprietà è definita come interfaccia o classe astratta, verranno serializzate solo le proprietà definite nell'interfaccia o nella classe astratta, anche se il tipo di runtime dispone di proprietà aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="dab64-285">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="dab64-286">Le eccezioni a questo comportamento sono illustrate in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="dab64-286">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="dab64-287">Si supponga, ad esempio, di disporre di una `WeatherForecast` classe e di una classe derivata `WeatherForecastDerived` :</span><span class="sxs-lookup"><span data-stu-id="dab64-287">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="dab64-288">E si supponga che l'argomento di tipo del `Serialize` metodo in fase di compilazione sia `WeatherForecast` :</span><span class="sxs-lookup"><span data-stu-id="dab64-288">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="dab64-289">In questo scenario, la `WindSpeed` proprietà non viene serializzata anche se l' `weatherForecast` oggetto è effettivamente un `WeatherForecastDerived` oggetto.</span><span class="sxs-lookup"><span data-stu-id="dab64-289">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="dab64-290">Vengono serializzate solo le proprietà della classe base:</span><span class="sxs-lookup"><span data-stu-id="dab64-290">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="dab64-291">Questo comportamento è volto a impedire l'esposizione accidentale dei dati in un tipo creato dal runtime derivato.</span><span class="sxs-lookup"><span data-stu-id="dab64-291">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="dab64-292">Per serializzare le proprietà del tipo derivato nell'esempio precedente, usare uno degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="dab64-292">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="dab64-293">Chiamare un overload di <xref:System.Text.Json.JsonSerializer.Serialize%2A> che consente di specificare il tipo in fase di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="dab64-293">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="dab64-294">Dichiarare l'oggetto da serializzare come `object` .</span><span class="sxs-lookup"><span data-stu-id="dab64-294">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="dab64-295">Nello scenario di esempio precedente, entrambi gli approcci determinano l' `WindSpeed` inclusione della proprietà nell'output JSON:</span><span class="sxs-lookup"><span data-stu-id="dab64-295">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="dab64-296">Questi approcci forniscono la serializzazione polimorfica solo per l'oggetto radice da serializzare, non per le proprietà dell'oggetto radice.</span><span class="sxs-lookup"><span data-stu-id="dab64-296">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="dab64-297">È possibile ottenere la serializzazione polimorfica per gli oggetti di livello inferiore se vengono definiti come tipo `object` .</span><span class="sxs-lookup"><span data-stu-id="dab64-297">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="dab64-298">Si supponga, ad esempio, `WeatherForecast` che la classe disponga di una proprietà denominata `PreviousForecast` che può essere definita come Type `WeatherForecast` o `object` :</span><span class="sxs-lookup"><span data-stu-id="dab64-298">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="dab64-299">Se la `PreviousForecast` proprietà contiene un'istanza di `WeatherForecastDerived` :</span><span class="sxs-lookup"><span data-stu-id="dab64-299">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="dab64-300">L'output JSON della serializzazione `WeatherForecastWithPrevious` **non include** `WindSpeed` .</span><span class="sxs-lookup"><span data-stu-id="dab64-300">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="dab64-301">L'output JSON della serializzazione `WeatherForecastWithPreviousAsObject` **include** `WindSpeed` .</span><span class="sxs-lookup"><span data-stu-id="dab64-301">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="dab64-302">Per serializzare, non è `WeatherForecastWithPreviousAsObject` necessario chiamare `Serialize<object>` o `GetType` perché l'oggetto radice non è quello che può essere di un tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="dab64-302">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="dab64-303">L'esempio di codice seguente non chiama `Serialize<object>` o `GetType` :</span><span class="sxs-lookup"><span data-stu-id="dab64-303">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="dab64-304">Il codice precedente serializza correttamente `WeatherForecastWithPreviousAsObject` :</span><span class="sxs-lookup"><span data-stu-id="dab64-304">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

<span data-ttu-id="dab64-305">Lo stesso approccio per la definizione delle proprietà `object` funziona con le interfacce.</span><span class="sxs-lookup"><span data-stu-id="dab64-305">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="dab64-306">Si supponga di avere l'interfaccia e l'implementazione seguenti e di voler serializzare una classe con proprietà che contengono istanze di implementazione:</span><span class="sxs-lookup"><span data-stu-id="dab64-306">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

<span data-ttu-id="dab64-307">Quando si serializza un'istanza di `Forecasts` , `Tuesday` Mostra solo la `WindSpeed` proprietà, perché `Tuesday` è definita come `object` :</span><span class="sxs-lookup"><span data-stu-id="dab64-307">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="dab64-308">Nell'esempio seguente viene illustrato il codice JSON risultante dal codice precedente:</span><span class="sxs-lookup"><span data-stu-id="dab64-308">The following example shows the JSON that results from the preceding code:</span></span>

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

<span data-ttu-id="dab64-309">Per ulteriori informazioni sulla **serializzazione**polimorfica e per informazioni sulla **deserializzazione**, vedere [come eseguire la migrazione da Newtonsoft.Json a System.Text.Json ](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span><span class="sxs-lookup"><span data-stu-id="dab64-309">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="dab64-310">Consenti commenti e virgole finali</span><span class="sxs-lookup"><span data-stu-id="dab64-310">Allow comments and trailing commas</span></span>

<span data-ttu-id="dab64-311">Per impostazione predefinita, i commenti e le virgole finali non sono consentiti in JSON.</span><span class="sxs-lookup"><span data-stu-id="dab64-311">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="dab64-312">Per consentire i commenti in JSON, impostare la <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> proprietà su `JsonCommentHandling.Skip` .</span><span class="sxs-lookup"><span data-stu-id="dab64-312">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="dab64-313">Per consentire le virgole finali, impostare la <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> proprietà su `true` .</span><span class="sxs-lookup"><span data-stu-id="dab64-313">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="dab64-314">Nell'esempio seguente viene illustrato come consentire entrambi:</span><span class="sxs-lookup"><span data-stu-id="dab64-314">The following example shows how to allow both:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="dab64-315">Di seguito è riportato un esempio JSON con commenti e una virgola finale:</span><span class="sxs-lookup"><span data-stu-id="dab64-315">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="dab64-316">Corrispondenza proprietà senza distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="dab64-316">Case-insensitive property matching</span></span>

<span data-ttu-id="dab64-317">Per impostazione predefinita, la deserializzazione Cerca le corrispondenze tra i nomi delle proprietà con distinzione tra maiuscole e minuscole tra JSON e le proprietà dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="dab64-317">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="dab64-318">Per modificare tale comportamento, impostare <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> su `true` :</span><span class="sxs-lookup"><span data-stu-id="dab64-318">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="dab64-319">Di seguito è riportato il codice JSON di esempio con i nomi di proprietà Camel case.</span><span class="sxs-lookup"><span data-stu-id="dab64-319">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="dab64-320">Può essere deserializzato nel tipo seguente con i nomi di proprietà del case Pascal.</span><span class="sxs-lookup"><span data-stu-id="dab64-320">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="dab64-321">Gestione JSON di overflow</span><span class="sxs-lookup"><span data-stu-id="dab64-321">Handle overflow JSON</span></span>

<span data-ttu-id="dab64-322">Durante la deserializzazione, è possibile ricevere dati nel file JSON non rappresentato dalle proprietà del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dab64-322">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="dab64-323">Si supponga, ad esempio, che il tipo di destinazione sia il seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-323">For example, suppose your target type is this:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="dab64-324">Il codice JSON da deserializzare è il seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-324">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="dab64-325">Se si deserializza il codice JSON mostrato nel tipo visualizzato, le `DatesAvailable` proprietà e non `SummaryWords` hanno alcun luogo e andranno perse.</span><span class="sxs-lookup"><span data-stu-id="dab64-325">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="dab64-326">Per acquisire dati aggiuntivi, ad esempio queste proprietà, applicare l'attributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una proprietà di tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>` :</span><span class="sxs-lookup"><span data-stu-id="dab64-326">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="dab64-327">Quando si deserializza il codice JSON illustrato in precedenza in questo tipo di esempio, i dati aggiuntivi diventano coppie chiave-valore della `ExtensionData` proprietà:</span><span class="sxs-lookup"><span data-stu-id="dab64-327">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="dab64-328">Proprietà</span><span class="sxs-lookup"><span data-stu-id="dab64-328">Property</span></span> |<span data-ttu-id="dab64-329">Value</span><span class="sxs-lookup"><span data-stu-id="dab64-329">Value</span></span>  |<span data-ttu-id="dab64-330">Note</span><span class="sxs-lookup"><span data-stu-id="dab64-330">Notes</span></span>  |
|---
<span data-ttu-id="dab64-331">title: Description:' questo articolo illustra come usare lo System.Text.Json spazio dei nomi per serializzare e deserializzare da JSON in .NET.</span><span class="sxs-lookup"><span data-stu-id="dab64-331">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="dab64-332">Include il codice di esempio ".</span><span class="sxs-lookup"><span data-stu-id="dab64-332">It includes sample code.'</span></span>
<span data-ttu-id="dab64-333">ms. Date: No-loc:</span><span class="sxs-lookup"><span data-stu-id="dab64-333">ms.date: no-loc:</span></span>
- <span data-ttu-id="dab64-334">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="dab64-334">'System.Text.Json'</span></span>
- <span data-ttu-id="dab64-335">' Newtonsoft.Json ' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="dab64-335">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="dab64-336">title: Description:' questo articolo illustra come usare lo System.Text.Json spazio dei nomi per serializzare e deserializzare da JSON in .NET.</span><span class="sxs-lookup"><span data-stu-id="dab64-336">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="dab64-337">Include il codice di esempio ".</span><span class="sxs-lookup"><span data-stu-id="dab64-337">It includes sample code.'</span></span>
<span data-ttu-id="dab64-338">ms. Date: No-loc:</span><span class="sxs-lookup"><span data-stu-id="dab64-338">ms.date: no-loc:</span></span>
- <span data-ttu-id="dab64-339">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="dab64-339">'System.Text.Json'</span></span>
- <span data-ttu-id="dab64-340">' Newtonsoft.Json ' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="dab64-340">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="dab64-341">-----|---title: Description:' questo articolo illustra come usare lo System.Text.Json spazio dei nomi per serializzare e deserializzare da JSON in .NET.</span><span class="sxs-lookup"><span data-stu-id="dab64-341">-----|--- title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="dab64-342">Include il codice di esempio ".</span><span class="sxs-lookup"><span data-stu-id="dab64-342">It includes sample code.'</span></span>
<span data-ttu-id="dab64-343">ms. Date: No-loc:</span><span class="sxs-lookup"><span data-stu-id="dab64-343">ms.date: no-loc:</span></span>
- <span data-ttu-id="dab64-344">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="dab64-344">'System.Text.Json'</span></span>
- <span data-ttu-id="dab64-345">' Newtonsoft.Json ' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="dab64-345">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="dab64-346">title: Description:' questo articolo illustra come usare lo System.Text.Json spazio dei nomi per serializzare e deserializzare da JSON in .NET.</span><span class="sxs-lookup"><span data-stu-id="dab64-346">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="dab64-347">Include il codice di esempio ".</span><span class="sxs-lookup"><span data-stu-id="dab64-347">It includes sample code.'</span></span>
<span data-ttu-id="dab64-348">ms. Date: No-loc:</span><span class="sxs-lookup"><span data-stu-id="dab64-348">ms.date: no-loc:</span></span>
- <span data-ttu-id="dab64-349">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="dab64-349">'System.Text.Json'</span></span>
- <span data-ttu-id="dab64-350">' Newtonsoft.Json ' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="dab64-350">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="dab64-351">-----|---title: Description:' questo articolo illustra come usare lo System.Text.Json spazio dei nomi per serializzare e deserializzare da JSON in .NET.</span><span class="sxs-lookup"><span data-stu-id="dab64-351">-----|--- title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="dab64-352">Include il codice di esempio ".</span><span class="sxs-lookup"><span data-stu-id="dab64-352">It includes sample code.'</span></span>
<span data-ttu-id="dab64-353">ms. Date: No-loc:</span><span class="sxs-lookup"><span data-stu-id="dab64-353">ms.date: no-loc:</span></span>
- <span data-ttu-id="dab64-354">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="dab64-354">'System.Text.Json'</span></span>
- <span data-ttu-id="dab64-355">' Newtonsoft.Json ' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="dab64-355">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="dab64-356">title: Description:' questo articolo illustra come usare lo System.Text.Json spazio dei nomi per serializzare e deserializzare da JSON in .NET.</span><span class="sxs-lookup"><span data-stu-id="dab64-356">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="dab64-357">Include il codice di esempio ".</span><span class="sxs-lookup"><span data-stu-id="dab64-357">It includes sample code.'</span></span>
<span data-ttu-id="dab64-358">ms. Date: No-loc:</span><span class="sxs-lookup"><span data-stu-id="dab64-358">ms.date: no-loc:</span></span>
- <span data-ttu-id="dab64-359">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="dab64-359">'System.Text.Json'</span></span>
- <span data-ttu-id="dab64-360">' Newtonsoft.Json ' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="dab64-360">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="dab64-361">-----| | Data | 8/1/2019 12:00:00 AM-07:00 | | | TemperatureCelsius | 0 | Mancata corrispondenza tra maiuscole e minuscole ( `temperatureCelsius` in JSON), quindi la proprietà non è impostata.</span><span class="sxs-lookup"><span data-stu-id="dab64-361">-----| | Date    | 8/1/2019 12:00:00 AM -07:00|| | TemperatureCelsius| 0 | Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> <span data-ttu-id="dab64-362">| | Riepilogo | A caldo | | | ExtensionData | temperatureCelsius: 25 | Poiché il caso non corrisponde, questa proprietà JSON è un oggetto aggiuntivo e diventa una coppia chiave-valore nel dizionario. | || DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="dab64-362">| | Summary | Hot || | ExtensionData | temperatureCelsius: 25 |Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.| || DatesAvailable:</span></span><br>  <span data-ttu-id="dab64-363">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="dab64-363">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="dab64-364">8/2/2019 12:00:00 AM-07:00 | Una proprietà aggiuntiva da JSON diventa una coppia chiave-valore, con una matrice come oggetto valore. | | | SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="dab64-364">8/2/2019 12:00:00 AM -07:00 |Extra property from the JSON becomes a key-value pair, with an array as the value object.| | |SummaryWords:</span></span><br><span data-ttu-id="dab64-365">Accesso sporadico</span><span class="sxs-lookup"><span data-stu-id="dab64-365">Cool</span></span><br><span data-ttu-id="dab64-366">Ventoso</span><span class="sxs-lookup"><span data-stu-id="dab64-366">Windy</span></span><br><span data-ttu-id="dab64-367">Umido | Una proprietà aggiuntiva da JSON diventa una coppia chiave-valore, con una matrice come oggetto valore. |</span><span class="sxs-lookup"><span data-stu-id="dab64-367">Humid |Extra property from the JSON becomes a key-value pair, with an array as the value object.|</span></span>

<span data-ttu-id="dab64-368">Quando l'oggetto di destinazione viene serializzato, le coppie chiave-valore dei dati di estensione diventano proprietà JSON esattamente come nel codice JSON in ingresso:</span><span class="sxs-lookup"><span data-stu-id="dab64-368">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="dab64-369">Si noti che il `ExtensionData` nome della proprietà non viene visualizzato in JSON.</span><span class="sxs-lookup"><span data-stu-id="dab64-369">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="dab64-370">Questo comportamento consente a JSON di creare un round trip senza perdere dati aggiuntivi che altrimenti non sarebbero deserializzati.</span><span class="sxs-lookup"><span data-stu-id="dab64-370">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="dab64-371">Ignora null durante la deserializzazione</span><span class="sxs-lookup"><span data-stu-id="dab64-371">Ignore null when deserializing</span></span>

<span data-ttu-id="dab64-372">Per impostazione predefinita, se una proprietà in JSON è null, la proprietà corrispondente nell'oggetto di destinazione viene impostata su null.</span><span class="sxs-lookup"><span data-stu-id="dab64-372">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="dab64-373">In alcuni scenari, la proprietà di destinazione potrebbe avere un valore predefinito e non si vuole che un valore null esegua l'override del valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="dab64-373">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="dab64-374">Si supponga, ad esempio, che il codice seguente rappresenti l'oggetto di destinazione:</span><span class="sxs-lookup"><span data-stu-id="dab64-374">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="dab64-375">Si supponga che venga deserializzato il codice JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-375">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="dab64-376">Dopo la deserializzazione, la `Summary` proprietà dell' `WeatherForecastWithDefault` oggetto è null.</span><span class="sxs-lookup"><span data-stu-id="dab64-376">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="dab64-377">Per modificare questo comportamento, impostare <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> su `true` , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-377">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="dab64-378">Con questa opzione, la `Summary` proprietà dell' `WeatherForecastWithDefault` oggetto è il valore predefinito "nessun riepilogo" dopo la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="dab64-378">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="dab64-379">I valori null nel codice JSON vengono ignorati solo se sono validi.</span><span class="sxs-lookup"><span data-stu-id="dab64-379">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="dab64-380">I valori null per i tipi di valore non nullable generano eccezioni.</span><span class="sxs-lookup"><span data-stu-id="dab64-380">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="dab64-381">Utf8JsonReader, Utf8JsonWriter e JsonDocument</span><span class="sxs-lookup"><span data-stu-id="dab64-381">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="dab64-382"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>è un reader ad alte prestazioni, a bassa allocazione e di solo invio per testo JSON con codifica UTF-8, letto da `ReadOnlySpan<byte>` o `ReadOnlySequence<byte>` .</span><span class="sxs-lookup"><span data-stu-id="dab64-382"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="dab64-383">`Utf8JsonReader`È un tipo di basso livello che può essere utilizzato per compilare parser e deserializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="dab64-383">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="dab64-384">Il <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> metodo usa `Utf8JsonReader` dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="dab64-384">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="dab64-385"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>è un modo a prestazioni elevate per scrivere testo JSON con codifica UTF-8 da tipi .NET comuni come `String` , `Int32` e `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="dab64-385"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="dab64-386">Il writer è un tipo di basso livello che può essere utilizzato per compilare serializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="dab64-386">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="dab64-387">Il <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> metodo usa `Utf8JsonWriter` dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="dab64-387">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="dab64-388"><xref:System.Text.Json.JsonDocument?displayProperty=fullName>fornisce la possibilità di compilare un Document Object Model di sola lettura (DOM) utilizzando `Utf8JsonReader` .</span><span class="sxs-lookup"><span data-stu-id="dab64-388"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="dab64-389">Il DOM fornisce l'accesso casuale ai dati in un payload JSON.</span><span class="sxs-lookup"><span data-stu-id="dab64-389">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="dab64-390">È possibile accedere agli elementi JSON che compongono il payload tramite il <xref:System.Text.Json.JsonElement> tipo.</span><span class="sxs-lookup"><span data-stu-id="dab64-390">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="dab64-391">Il `JsonElement` tipo fornisce enumeratori di oggetti e matrici insieme alle API per convertire il testo JSON in tipi .NET comuni.</span><span class="sxs-lookup"><span data-stu-id="dab64-391">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="dab64-392">`JsonDocument`espone una <xref:System.Text.Json.JsonDocument.RootElement> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="dab64-392">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="dab64-393">Le sezioni seguenti illustrano come usare questi strumenti per la lettura e la scrittura di JSON.</span><span class="sxs-lookup"><span data-stu-id="dab64-393">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="dab64-394">Usare JsonDocument per l'accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="dab64-394">Use JsonDocument for access to data</span></span>

<span data-ttu-id="dab64-395">Nell'esempio seguente viene illustrato come utilizzare la <xref:System.Text.Json.JsonDocument> classe per l'accesso casuale ai dati in una stringa JSON:</span><span class="sxs-lookup"><span data-stu-id="dab64-395">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="dab64-396">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="dab64-396">The preceding code:</span></span>

* <span data-ttu-id="dab64-397">Presuppone che il codice JSON da analizzare si trovi in una stringa denominata `jsonString` .</span><span class="sxs-lookup"><span data-stu-id="dab64-397">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="dab64-398">Calcola un livello medio per gli oggetti in una `Students` matrice che dispongono di una `Grade` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="dab64-398">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="dab64-399">Assegna un livello predefinito di 70 per gli studenti che non hanno un livello.</span><span class="sxs-lookup"><span data-stu-id="dab64-399">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="dab64-400">Conta gli studenti incrementando una `count` variabile a ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="dab64-400">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="dab64-401"><xref:System.Text.Json.JsonElement.GetArrayLength%2A>In alternativa, è possibile chiamare, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-401">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="dab64-402">Di seguito è riportato un esempio del codice JSON elaborato da questo codice:</span><span class="sxs-lookup"><span data-stu-id="dab64-402">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="dab64-403">Usare JsonDocument per scrivere JSON</span><span class="sxs-lookup"><span data-stu-id="dab64-403">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="dab64-404">Nell'esempio seguente viene illustrato come scrivere JSON da un oggetto <xref:System.Text.Json.JsonDocument> :</span><span class="sxs-lookup"><span data-stu-id="dab64-404">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="dab64-405">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="dab64-405">The preceding code:</span></span>

* <span data-ttu-id="dab64-406">Legge un file JSON, carica i dati in un oggetto `JsonDocument` e scrive JSON formattato (abbastanza stampato) in un file.</span><span class="sxs-lookup"><span data-stu-id="dab64-406">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="dab64-407">USA <xref:System.Text.Json.JsonDocumentOptions> per specificare che i commenti nel codice JSON di input sono consentiti ma ignorati.</span><span class="sxs-lookup"><span data-stu-id="dab64-407">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="dab64-408">Al termine, chiama <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> sul writer.</span><span class="sxs-lookup"><span data-stu-id="dab64-408">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="dab64-409">In alternativa, è possibile lasciare che il writer AutoFlush quando viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="dab64-409">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="dab64-410">Di seguito è riportato un esempio di input JSON che verrà elaborato dal codice di esempio:</span><span class="sxs-lookup"><span data-stu-id="dab64-410">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

<span data-ttu-id="dab64-411">Il risultato è l'output JSON abbastanza stampato seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-411">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="dab64-412">Usare Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="dab64-412">Use Utf8JsonWriter</span></span>

<span data-ttu-id="dab64-413">Nell'esempio seguente viene illustrato come utilizzare la <xref:System.Text.Json.Utf8JsonWriter> classe:</span><span class="sxs-lookup"><span data-stu-id="dab64-413">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="dab64-414">Usare Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="dab64-414">Use Utf8JsonReader</span></span>

<span data-ttu-id="dab64-415">Nell'esempio seguente viene illustrato come utilizzare la <xref:System.Text.Json.Utf8JsonReader> classe:</span><span class="sxs-lookup"><span data-stu-id="dab64-415">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="dab64-416">Il codice precedente presuppone che la `jsonUtf8` variabile sia una matrice di byte che contiene JSON valido, codificato come UTF-8.</span><span class="sxs-lookup"><span data-stu-id="dab64-416">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="dab64-417">Filtrare i dati tramite Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="dab64-417">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="dab64-418">Nell'esempio seguente viene illustrato come leggere un file in modo sincrono e cercare un valore:</span><span class="sxs-lookup"><span data-stu-id="dab64-418">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="dab64-419">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="dab64-419">The preceding code:</span></span>

* <span data-ttu-id="dab64-420">Presuppone che JSON contenga una matrice di oggetti e che ogni oggetto possa contenere una proprietà "Name" di tipo String.</span><span class="sxs-lookup"><span data-stu-id="dab64-420">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="dab64-421">Conta gli oggetti e i valori della proprietà "Name" che terminano con "University".</span><span class="sxs-lookup"><span data-stu-id="dab64-421">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="dab64-422">Presuppone che il file sia codificato come UTF-16 e lo transcodifichi in UTF-8.</span><span class="sxs-lookup"><span data-stu-id="dab64-422">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="dab64-423">Un file codificato come UTF-8 può essere letto direttamente in `ReadOnlySpan<byte>` , usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="dab64-423">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="dab64-424">Se il file contiene un byte order mark UTF-8 (BOM), rimuoverlo prima di passare i byte a `Utf8JsonReader` , perché il Reader prevede il testo.</span><span class="sxs-lookup"><span data-stu-id="dab64-424">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="dab64-425">In caso contrario, l'indicatore dell'ordine dei byte viene considerato JSON non valido e il lettore genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="dab64-425">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="dab64-426">Di seguito è riportato un esempio JSON che il codice precedente può leggere.</span><span class="sxs-lookup"><span data-stu-id="dab64-426">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="dab64-427">Il messaggio di riepilogo risultante è "2 su 4 hanno nomi che terminano con" University "":</span><span class="sxs-lookup"><span data-stu-id="dab64-427">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="dab64-428">Leggere da un flusso usando Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="dab64-428">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="dab64-429">Quando si legge un file di grandi dimensioni (ad esempio, un gigabyte o più), è consigliabile evitare di caricare l'intero file in memoria contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="dab64-429">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="dab64-430">Per questo scenario, è possibile usare un <xref:System.IO.FileStream> .</span><span class="sxs-lookup"><span data-stu-id="dab64-430">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="dab64-431">Quando si usa `Utf8JsonReader` per leggere da un flusso, si applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="dab64-431">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="dab64-432">Il buffer che contiene il payload JSON parziale deve essere almeno uguale al token JSON più grande al suo interno, in modo che il lettore possa procedere.</span><span class="sxs-lookup"><span data-stu-id="dab64-432">The buffer containing the partial JSON payload must be at least as big as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="dab64-433">Il buffer deve avere una dimensione minima pari alla sequenza più grande di spazi vuoti all'interno di JSON.</span><span class="sxs-lookup"><span data-stu-id="dab64-433">The buffer must be at least as big as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="dab64-434">Il lettore non tiene traccia dei dati letti fino a quando non legge completamente il successivo <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> nel payload JSON.</span><span class="sxs-lookup"><span data-stu-id="dab64-434">The reader doesn't keep track of the data it has read until it completely reads the next <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="dab64-435">Quindi, quando ci sono byte rimasti nel buffer, è necessario passarli nuovamente al lettore.</span><span class="sxs-lookup"><span data-stu-id="dab64-435">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="dab64-436">È possibile utilizzare <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> per determinare il numero di byte rimanenti.</span><span class="sxs-lookup"><span data-stu-id="dab64-436">You can use <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="dab64-437">Il codice seguente illustra come leggere da un flusso.</span><span class="sxs-lookup"><span data-stu-id="dab64-437">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="dab64-438">Nell'esempio viene illustrato un oggetto <xref:System.IO.MemoryStream> .</span><span class="sxs-lookup"><span data-stu-id="dab64-438">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="dab64-439">Il codice simile funzionerà con un oggetto <xref:System.IO.FileStream> , tranne quando l'oggetto `FileStream` contiene un BOM UTF-8 all'inizio.</span><span class="sxs-lookup"><span data-stu-id="dab64-439">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="dab64-440">In tal caso, è necessario rimuovere questi tre byte dal buffer prima di passare i byte rimanenti a `Utf8JsonReader` .</span><span class="sxs-lookup"><span data-stu-id="dab64-440">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="dab64-441">In caso contrario, il lettore genererebbe un'eccezione poiché l'indicatore BOM non è considerato una parte valida di JSON.</span><span class="sxs-lookup"><span data-stu-id="dab64-441">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="dab64-442">Il codice di esempio inizia con un buffer 4KB e raddoppia le dimensioni del buffer ogni volta che rileva che le dimensioni non sono sufficientemente grandi per adattarsi a un token JSON completo, che è necessario per consentire al lettore di avanzare sul payload JSON.</span><span class="sxs-lookup"><span data-stu-id="dab64-442">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not big enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="dab64-443">L'esempio JSON fornito nel frammento di codice attiva un aumento delle dimensioni del buffer solo se si imposta una dimensione del buffer iniziale molto piccola, ad esempio 10 byte.</span><span class="sxs-lookup"><span data-stu-id="dab64-443">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="dab64-444">Se si imposta la dimensione del buffer iniziale su 10, le `Console.WriteLine` istruzioni illustrano la provocazione e l'effetto della dimensione del buffer.</span><span class="sxs-lookup"><span data-stu-id="dab64-444">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="dab64-445">Alla dimensione del buffer iniziale 4KB, l'intero codice JSON di esempio viene visualizzato da ciascuno `Console.WriteLine` e le dimensioni del buffer non devono mai essere aumentate.</span><span class="sxs-lookup"><span data-stu-id="dab64-445">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

<span data-ttu-id="dab64-446">Nell'esempio precedente non viene impostato alcun limite per le dimensioni del buffer.</span><span class="sxs-lookup"><span data-stu-id="dab64-446">The preceding example sets no limit to how big the buffer can grow.</span></span> <span data-ttu-id="dab64-447">Se la dimensione del token è troppo grande, il codice potrebbe avere esito negativo con un' <xref:System.OutOfMemoryException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="dab64-447">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="dab64-448">Questo problema può verificarsi se il file JSON contiene un token di circa 1 GB o più dimensioni, perché il raddoppio delle dimensioni di 1 GB comporta una dimensione troppo grande per adattarsi a un `int32` buffer.</span><span class="sxs-lookup"><span data-stu-id="dab64-448">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dab64-449">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dab64-449">Additional resources</span></span>

* <span data-ttu-id="dab64-450">[System.Text.JsonPanoramica](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="dab64-450">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* [<span data-ttu-id="dab64-451">Come scrivere convertitori personalizzati</span><span class="sxs-lookup"><span data-stu-id="dab64-451">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="dab64-452">[Come eseguire la migrazione daNewtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="dab64-452">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="dab64-453">[Supporto di DateTime e DateTimeOffset inSystem.Text.Json](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="dab64-453">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="dab64-454">[System.Text.JsonRiferimento API](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="dab64-454">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
