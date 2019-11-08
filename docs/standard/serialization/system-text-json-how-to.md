---
title: Come serializzare e deserializzare JSON con C# -.NET
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: f0245feb710f33d5fcea2a7125b8753ba6064018
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740440"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="fd883-102">Come serializzare e deserializzare JSON in .NET</span><span class="sxs-lookup"><span data-stu-id="fd883-102">How to serialize and deserialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd883-103">La documentazione di serializzazione JSON è in costruzione.</span><span class="sxs-lookup"><span data-stu-id="fd883-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="fd883-104">Questo articolo non copre tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="fd883-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="fd883-105">Per altre informazioni, esaminare i [problemi di System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) nel repository DotNet/CoreFx su GitHub, in particolare quelli con etichetta [JSON-funzionalità-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span><span class="sxs-lookup"><span data-stu-id="fd883-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="fd883-106">Questo articolo illustra come usare lo spazio dei nomi <xref:System.Text.Json> per serializzare e deserializzare da e verso JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="fd883-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="fd883-107">Le direzioni e il codice di esempio usano la libreria direttamente, non tramite un Framework come [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="fd883-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="fd883-108">Namespaces</span><span class="sxs-lookup"><span data-stu-id="fd883-108">Namespaces</span></span>

<span data-ttu-id="fd883-109">Lo spazio dei nomi <xref:System.Text.Json> contiene tutti i punti di ingresso e i tipi principali.</span><span class="sxs-lookup"><span data-stu-id="fd883-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="fd883-110">Lo spazio dei nomi <xref:System.Text.Json.Serialization> contiene attributi e API per scenari avanzati e personalizzazione specifici per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="fd883-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="fd883-111">Gli esempi di codice illustrati in questo articolo richiedono direttive `using` per uno o entrambi gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd883-111">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="fd883-112">Gli attributi dello spazio dei nomi <xref:System.Runtime.Serialization> non sono attualmente supportati nel `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="fd883-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="fd883-113">Come scrivere oggetti .NET in JSON (Serialize)</span><span class="sxs-lookup"><span data-stu-id="fd883-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="fd883-114">Per scrivere JSON in una stringa o in un file, chiamare il metodo <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd883-114">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="fd883-115">Nell'esempio seguente viene creato JSON come stringa:</span><span class="sxs-lookup"><span data-stu-id="fd883-115">The following example creates JSON as a string:</span></span>

```csharp
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="fd883-116">Nell'esempio seguente viene usato il codice sincrono per creare un file JSON:</span><span class="sxs-lookup"><span data-stu-id="fd883-116">The following example uses synchronous code to create a JSON file:</span></span>

```csharp
File.WriteAllText(outputFileName, JsonSerializer.Serialize(weatherForecast));
```

<span data-ttu-id="fd883-117">Nell'esempio seguente viene usato il codice asincrono per creare un file JSON:</span><span class="sxs-lookup"><span data-stu-id="fd883-117">The following example uses asynchronous code to create a JSON file:</span></span>

```csharp
using (FileStream fs = File.Create(outputFileName))
{
    await JsonSerializer.SerializeAsync(fs, weatherForecast);
}
```

<span data-ttu-id="fd883-118">Negli esempi precedenti viene utilizzata l'inferenza del tipo per il tipo da serializzare.</span><span class="sxs-lookup"><span data-stu-id="fd883-118">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="fd883-119">Un overload di `Serialize()` accetta un parametro di tipo generico:</span><span class="sxs-lookup"><span data-stu-id="fd883-119">An overload of `Serialize()` takes a generic type parameter:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

### <a name="serialization-example"></a><span data-ttu-id="fd883-120">Esempio di serializzazione</span><span class="sxs-lookup"><span data-stu-id="fd883-120">Serialization example</span></span>

<span data-ttu-id="fd883-121">Di seguito è riportato un esempio di tipo che contiene le raccolte e le classi annidate:</span><span class="sxs-lookup"><span data-stu-id="fd883-121">Here's an example type that contains collections and nested classes:</span></span>

```csharp
public class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public IList<DateTimeOffset> DatesAvailable { get; set;}
    public Dictionary<string, HighLowTemperatures> TemperatureRanges { get; set; }
    public string [] SummaryWords { get; set; }
}

public class HighLowTemperatures
{
    public Temperature High { get; set; }
    public Temperature Low { get; set; }
}

public class Temperature
{
    public int DegreesCelsius { get; set; }
}
```

<span data-ttu-id="fd883-122">L'output JSON della serializzazione di un'istanza del tipo precedente è simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fd883-122">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="fd883-123">Per impostazione predefinita, l'output JSON è minimizzati:</span><span class="sxs-lookup"><span data-stu-id="fd883-123">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="fd883-124">Nell'esempio seguente viene illustrato lo stesso JSON, formattato, ovvero abbastanza stampato con spazi vuoti e rientri:</span><span class="sxs-lookup"><span data-stu-id="fd883-124">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": {
        "DegreesCelsius": 20
      },
      "Low": {
        "DegreesCelsius": -10
      }
    },
    "Hot": {
      "High": {
        "DegreesCelsius": 60
      },
      "Low": {
        "DegreesCelsius": 20
      }
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a><span data-ttu-id="fd883-125">Serializza in UTF-8</span><span class="sxs-lookup"><span data-stu-id="fd883-125">Serialize to UTF-8</span></span>

<span data-ttu-id="fd883-126">Per eseguire la serializzazione in UTF-8, chiamare il metodo <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="fd883-126">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] jsonUtf8Bytes = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="fd883-127">È disponibile anche un overload <xref:System.Text.Json.JsonSerializer.Serialize%2A> che accetta una <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="fd883-127">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="fd883-128">La serializzazione in UTF-8 è più veloce del 5-10% rispetto all'uso dei metodi basati su stringa.</span><span class="sxs-lookup"><span data-stu-id="fd883-128">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="fd883-129">La differenza è dovuta al fatto che i byte (come UTF-8) non devono essere convertiti in stringhe (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="fd883-129">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="fd883-130">Comportamento della serializzazione</span><span class="sxs-lookup"><span data-stu-id="fd883-130">Serialization behavior</span></span>

* <span data-ttu-id="fd883-131">Per impostazione predefinita, tutte le proprietà pubbliche vengono serializzate.</span><span class="sxs-lookup"><span data-stu-id="fd883-131">By default, all public properties are serialized.</span></span> <span data-ttu-id="fd883-132">È possibile [specificare le proprietà da escludere](#exclude-properties-from-serialization).</span><span class="sxs-lookup"><span data-stu-id="fd883-132">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="fd883-133">Il [codificatore predefinito](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) consente di eseguire l'escape dei caratteri non ASCII, dei caratteri con distinzione HTML nell'intervallo ASCII e dei caratteri che devono essere preceduti da un carattere di escape in base alla [specifica JSON](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="fd883-133">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="fd883-134">Per impostazione predefinita, JSON è minimizzati.</span><span class="sxs-lookup"><span data-stu-id="fd883-134">By default, JSON is minified.</span></span> <span data-ttu-id="fd883-135">È possibile [stampare](#serialize-to-formatted-json)in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="fd883-135">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="fd883-136">Per impostazione predefinita, le maiuscole e minuscole dei nomi JSON corrispondono ai nomi .NET.</span><span class="sxs-lookup"><span data-stu-id="fd883-136">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="fd883-137">È possibile [personalizzare la combinazione di maiuscole e minuscole](#customize-json-names-and-values).</span><span class="sxs-lookup"><span data-stu-id="fd883-137">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="fd883-138">Vengono rilevati riferimenti circolari e vengono generate eccezioni.</span><span class="sxs-lookup"><span data-stu-id="fd883-138">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="fd883-139">Per ulteriori informazioni, vedere il [problema relativo ai riferimenti circolari](https://github.com/dotnet/corefx/issues/38579) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="fd883-139">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="fd883-140">Attualmente, i campi vengono esclusi.</span><span class="sxs-lookup"><span data-stu-id="fd883-140">Currently, fields are excluded.</span></span>

<span data-ttu-id="fd883-141">I tipi supportati includono:</span><span class="sxs-lookup"><span data-stu-id="fd883-141">Supported types include:</span></span>

* <span data-ttu-id="fd883-142">Primitive .NET mappate a primitive JavaScript, ad esempio tipi numerici, stringhe e valori booleani.</span><span class="sxs-lookup"><span data-stu-id="fd883-142">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="fd883-143">[Oggetti CLR obsoleti definiti dall'utente (poco)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="fd883-143">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="fd883-144">Matrici unidimensionali e irregolari (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="fd883-144">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="fd883-145">`Dictionary<string,TValue>` dove `TValue` è `object`, `JsonElement`o un POCO.</span><span class="sxs-lookup"><span data-stu-id="fd883-145">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="fd883-146">Raccolte dai seguenti spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="fd883-146">Collections from the following namespaces.</span></span> <span data-ttu-id="fd883-147">Per ulteriori informazioni, vedere il [problema relativo al supporto della raccolta](https://github.com/dotnet/corefx/issues/36643) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="fd883-147">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="fd883-148">È possibile [implementare convertitori personalizzati](system-text-json-converters-how-to.md) per gestire tipi aggiuntivi o fornire funzionalità non supportate dai convertitori incorporati.</span><span class="sxs-lookup"><span data-stu-id="fd883-148">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="fd883-149">Come leggere JSON in oggetti .NET (deserializzare)</span><span class="sxs-lookup"><span data-stu-id="fd883-149">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="fd883-150">Per eseguire la deserializzazione da una stringa o da un file, chiamare il metodo <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd883-150">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="fd883-151">Nell'esempio seguente viene letto JSON da una stringa:</span><span class="sxs-lookup"><span data-stu-id="fd883-151">The following example reads JSON from a string:</span></span>

```csharp
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="fd883-152">Per eseguire la deserializzazione da un file usando il codice sincrono, leggere il file in una stringa, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-152">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="fd883-153">Per eseguire la deserializzazione da un file usando il codice asincrono, chiamare il metodo <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>:</span><span class="sxs-lookup"><span data-stu-id="fd883-153">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

```csharp
using (FileStream fs = File.OpenRead(inputFileName))
{
    weatherForecast = await JsonSerializer.DeserializeAsync<WeatherForecast>(fs);
}
```

<span data-ttu-id="fd883-154">Per un esempio di tipo e JSON corrispondente, vedere la sezione relativa all' [esempio di serializzazione](#serialization-example) .</span><span class="sxs-lookup"><span data-stu-id="fd883-154">For an example type and corresponding JSON, see the [Serialization example](#serialization-example) section.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="fd883-155">Deserializzazione da UTF-8</span><span class="sxs-lookup"><span data-stu-id="fd883-155">Deserialize from UTF-8</span></span>

<span data-ttu-id="fd883-156">Per deserializzare da UTF-8, chiamare un <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload che accetta un `Utf8JsonReader` o un `ReadOnlySpan<byte>`, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="fd883-156">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="fd883-157">Gli esempi presuppongono che JSON si trovi in una matrice di byte denominata jsonUtf8Bytes.</span><span class="sxs-lookup"><span data-stu-id="fd883-157">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

```csharp
var readOnlySpan = new ReadOnlySpan<byte>(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
var utf8Reader = new Utf8JsonReader(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="fd883-158">Comportamento di deserializzazione</span><span class="sxs-lookup"><span data-stu-id="fd883-158">Deserialization behavior</span></span>

* <span data-ttu-id="fd883-159">Per impostazione predefinita, la corrispondenza dei nomi di proprietà fa distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="fd883-159">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="fd883-160">È possibile specificare la distinzione tra [maiuscole e minuscole](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="fd883-160">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="fd883-161">Se il codice JSON contiene un valore per una proprietà di sola lettura, il valore viene ignorato e non viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="fd883-161">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="fd883-162">La deserializzazione ai tipi di riferimento senza un costruttore senza parametri non è supportata.</span><span class="sxs-lookup"><span data-stu-id="fd883-162">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="fd883-163">La deserializzazione a oggetti non modificabili o a proprietà di sola lettura non è supportata.</span><span class="sxs-lookup"><span data-stu-id="fd883-163">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="fd883-164">Per ulteriori informazioni, vedere il [problema GitHub sul supporto di oggetti non modificabili](https://github.com/dotnet/corefx/issues/38569) e il [problema relativo al supporto delle proprietà di sola lettura](https://github.com/dotnet/corefx/issues/38163) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="fd883-164">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="fd883-165">Per impostazione predefinita, le enumerazioni sono supportate come numeri.</span><span class="sxs-lookup"><span data-stu-id="fd883-165">By default, enums are supported as numbers.</span></span> <span data-ttu-id="fd883-166">È possibile [serializzare i nomi di enumerazione come stringhe](#enums-as-strings).</span><span class="sxs-lookup"><span data-stu-id="fd883-166">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="fd883-167">I campi non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="fd883-167">Fields aren't supported.</span></span>
* <span data-ttu-id="fd883-168">Per impostazione predefinita, i commenti o le virgole finali in JSON generano eccezioni.</span><span class="sxs-lookup"><span data-stu-id="fd883-168">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="fd883-169">È possibile [consentire i commenti e le virgole finali](#allow-comments-and-trailing-commas).</span><span class="sxs-lookup"><span data-stu-id="fd883-169">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="fd883-170">La [profondità massima predefinita](xref:System.Text.Json.JsonReaderOptions.MaxDepth) è 64.</span><span class="sxs-lookup"><span data-stu-id="fd883-170">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="fd883-171">È possibile [implementare convertitori personalizzati](system-text-json-converters-how-to.md) per fornire funzionalità non supportate dai convertitori incorporati.</span><span class="sxs-lookup"><span data-stu-id="fd883-171">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="fd883-172">Serializza nel formato JSON formattato</span><span class="sxs-lookup"><span data-stu-id="fd883-172">Serialize to formatted JSON</span></span>

<span data-ttu-id="fd883-173">Per stampare l'output JSON, impostare <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> su `true`:</span><span class="sxs-lookup"><span data-stu-id="fd883-173">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="fd883-174">Di seguito è riportato un esempio di tipo da serializzare e da un output JSON abbastanza stampato:</span><span class="sxs-lookup"><span data-stu-id="fd883-174">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="fd883-175">Personalizzare i nomi e i valori JSON</span><span class="sxs-lookup"><span data-stu-id="fd883-175">Customize JSON names and values</span></span>

<span data-ttu-id="fd883-176">Per impostazione predefinita, i nomi delle proprietà e le chiavi del dizionario non cambiano nell'output JSON, inclusa la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="fd883-176">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="fd883-177">I valori enum sono rappresentati come numeri.</span><span class="sxs-lookup"><span data-stu-id="fd883-177">Enum values are represented as numbers.</span></span> <span data-ttu-id="fd883-178">Questa sezione illustra come eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd883-178">This section explains how to:</span></span>

* <span data-ttu-id="fd883-179">Personalizzare i singoli nomi di proprietà</span><span class="sxs-lookup"><span data-stu-id="fd883-179">Customize individual property names</span></span>
* <span data-ttu-id="fd883-180">Converte tutti i nomi di proprietà in Camel case</span><span class="sxs-lookup"><span data-stu-id="fd883-180">Convert all property names to camel case</span></span>
* <span data-ttu-id="fd883-181">Implementare i criteri di denominazione delle proprietà personalizzate</span><span class="sxs-lookup"><span data-stu-id="fd883-181">Implement a custom property naming policy</span></span>
* <span data-ttu-id="fd883-182">Converte le chiavi del dizionario in lettere maiuscole</span><span class="sxs-lookup"><span data-stu-id="fd883-182">Convert dictionary keys to camel case</span></span>
* <span data-ttu-id="fd883-183">Converte le enumerazioni in stringhe e maiuscole</span><span class="sxs-lookup"><span data-stu-id="fd883-183">Convert enums to strings and camel case</span></span> 

<span data-ttu-id="fd883-184">Per altri scenari che richiedono una gestione speciale dei nomi e dei valori delle proprietà JSON, è possibile [implementare convertitori personalizzati](system-text-json-converters-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="fd883-184">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="fd883-185">Personalizzare i singoli nomi di proprietà</span><span class="sxs-lookup"><span data-stu-id="fd883-185">Customize individual property names</span></span>

<span data-ttu-id="fd883-186">Per impostare il nome delle singole proprietà, utilizzare l'attributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="fd883-186">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="fd883-187">Di seguito è riportato un esempio di tipo da serializzare e JSON risultante:</span><span class="sxs-lookup"><span data-stu-id="fd883-187">Here's an example type to serialize and resulting JSON:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="fd883-188">Nome della proprietà impostato dall'attributo:</span><span class="sxs-lookup"><span data-stu-id="fd883-188">The property name set by this attribute:</span></span>

* <span data-ttu-id="fd883-189">Si applica in entrambe le direzioni, per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="fd883-189">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="fd883-190">Ha la precedenza sui criteri di denominazione delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="fd883-190">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="fd883-191">Usa il caso Camel per tutti i nomi di proprietà JSON</span><span class="sxs-lookup"><span data-stu-id="fd883-191">Use camel case for all JSON property names</span></span>

<span data-ttu-id="fd883-192">Per usare il case Camel per tutti i nomi di proprietà JSON, impostare <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> su `JsonNamingPolicy.CamelCase`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-192">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="fd883-193">Ecco una classe di esempio per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="fd883-193">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureCelsius { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="fd883-194">Criteri di denominazione delle proprietà Camel case:</span><span class="sxs-lookup"><span data-stu-id="fd883-194">The camel case property naming policy:</span></span>

* <span data-ttu-id="fd883-195">Si applica alla serializzazione e alla deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="fd883-195">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="fd883-196">Viene sottoposto a override da `[JsonPropertyName]` attributi.</span><span class="sxs-lookup"><span data-stu-id="fd883-196">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="fd883-197">Questo è il motivo per cui il nome della proprietà JSON `Wind` nell'esempio non è un caso Camel.</span><span class="sxs-lookup"><span data-stu-id="fd883-197">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="fd883-198">Usare un criterio personalizzato per la denominazione delle proprietà JSON</span><span class="sxs-lookup"><span data-stu-id="fd883-198">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="fd883-199">Per usare un criterio di denominazione delle proprietà JSON personalizzato, creare una classe che deriva da <xref:System.Text.Json.JsonNamingPolicy> ed eseguire l'override del metodo <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-199">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="fd883-200">Impostare quindi la proprietà <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> su un'istanza della classe di criteri di denominazione:</span><span class="sxs-lookup"><span data-stu-id="fd883-200">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="fd883-201">Ecco una classe di esempio per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="fd883-201">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATUREC": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="fd883-202">Criteri di denominazione delle proprietà JSON:</span><span class="sxs-lookup"><span data-stu-id="fd883-202">The JSON property naming policy:</span></span>

* <span data-ttu-id="fd883-203">Si applica alla serializzazione e alla deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="fd883-203">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="fd883-204">Viene sottoposto a override da `[JsonPropertyName]` attributi.</span><span class="sxs-lookup"><span data-stu-id="fd883-204">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="fd883-205">Questo è il motivo per cui il nome della proprietà JSON `Wind` nell'esempio non è maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="fd883-205">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="fd883-206">Chiavi del dizionario case Camel</span><span class="sxs-lookup"><span data-stu-id="fd883-206">Camel case dictionary keys</span></span>

<span data-ttu-id="fd883-207">Se una proprietà di un oggetto da serializzare è di tipo `Dictionary<string,TValue>`, le chiavi di `string` possono essere convertite in maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="fd883-207">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="fd883-208">A tale scopo, impostare <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> su `JsonNamingPolicy.CamelCase`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-208">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="fd883-209">La serializzazione di un oggetto con un dizionario denominato `TemperatureRanges` con coppie chiave-valore `"ColdMinTemp", 20` e `"HotMinTemp", 40` comporterebbe l'output JSON come l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-209">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="fd883-210">I criteri di denominazione Camel case per le chiavi del dizionario si applicano solo alla serializzazione.</span><span class="sxs-lookup"><span data-stu-id="fd883-210">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="fd883-211">Se si deserializza un dizionario, le chiavi corrisponderanno al file JSON anche se si specifica `JsonNamingPolicy.CamelCase` per l'`DictionaryKeyPolicy`.</span><span class="sxs-lookup"><span data-stu-id="fd883-211">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="fd883-212">Enumerazioni come stringhe</span><span class="sxs-lookup"><span data-stu-id="fd883-212">Enums as strings</span></span>

<span data-ttu-id="fd883-213">Per impostazione predefinita, le enumerazioni vengono serializzate come numeri.</span><span class="sxs-lookup"><span data-stu-id="fd883-213">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="fd883-214">Per serializzare i nomi di enumerazione come stringhe, usare il <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span><span class="sxs-lookup"><span data-stu-id="fd883-214">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="fd883-215">Si supponga, ad esempio, di dover serializzare la classe seguente che contiene un'enumerazione:</span><span class="sxs-lookup"><span data-stu-id="fd883-215">For example, suppose you need to serialize the following class that has an enum:</span></span>

```csharp
class WeatherForecastWithEnum
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public Summary Summary { get; set; }
}

public enum Summary
{
    Cold, Cool, Warm, Hot
}
```

<span data-ttu-id="fd883-216">Se il riepilogo è `Hot`, per impostazione predefinita il JSON serializzato ha il valore numerico 3:</span><span class="sxs-lookup"><span data-stu-id="fd883-216">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": 3
}
```

<span data-ttu-id="fd883-217">Il codice di esempio seguente serializza i nomi enum in alternativa e li converte in Camel case:</span><span class="sxs-lookup"><span data-stu-id="fd883-217">The following sample code serializes the enum names instead, and converts them to camel case:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
jsonWithEnumsAsStrings = JsonSerializer.Serialize(weatherForecastWithEnum, options);
```

<span data-ttu-id="fd883-218">Il codice JSON risultante è simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-218">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="fd883-219">Il supporto per le enumerazioni come stringhe si applica anche alla deserializzazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-219">The support for enums as strings applies to deserialization also, as shown in the following example:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
weatherForecastWithEnum = JsonSerializer.Deserialize<WeatherForecastWithEnum>(jsonWithEnumsAsStrings, options);
```

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="fd883-220">Escludi proprietà dalla serializzazione</span><span class="sxs-lookup"><span data-stu-id="fd883-220">Exclude properties from serialization</span></span>

<span data-ttu-id="fd883-221">Per impostazione predefinita, tutte le proprietà pubbliche vengono serializzate.</span><span class="sxs-lookup"><span data-stu-id="fd883-221">By default, all public properties are serialized.</span></span> <span data-ttu-id="fd883-222">Se non si vuole che alcuni di essi vengano visualizzati nell'output JSON, sono disponibili diverse opzioni.</span><span class="sxs-lookup"><span data-stu-id="fd883-222">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="fd883-223">In questa sezione viene illustrato come escludere:</span><span class="sxs-lookup"><span data-stu-id="fd883-223">This section explains how to exclude:</span></span>

* <span data-ttu-id="fd883-224">Singole proprietà</span><span class="sxs-lookup"><span data-stu-id="fd883-224">Individual properties</span></span>
* <span data-ttu-id="fd883-225">Tutte le proprietà di sola lettura</span><span class="sxs-lookup"><span data-stu-id="fd883-225">All read-only properties</span></span>
* <span data-ttu-id="fd883-226">Tutte le proprietà con valore null</span><span class="sxs-lookup"><span data-stu-id="fd883-226">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="fd883-227">Escludi singole proprietà</span><span class="sxs-lookup"><span data-stu-id="fd883-227">Exclude individual properties</span></span>

<span data-ttu-id="fd883-228">Per ignorare le singole proprietà, utilizzare l'attributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="fd883-228">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="fd883-229">Ecco un esempio di tipo per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="fd883-229">Here's an example type to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonIgnore]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="fd883-230">Escludi tutte le proprietà di sola lettura</span><span class="sxs-lookup"><span data-stu-id="fd883-230">Exclude all read-only properties</span></span>

<span data-ttu-id="fd883-231">Una proprietà è di sola lettura se contiene un getter pubblico ma non un setter pubblico.</span><span class="sxs-lookup"><span data-stu-id="fd883-231">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="fd883-232">Per escludere tutte le proprietà di sola lettura, impostare il <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> su `true`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-232">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="fd883-233">Ecco un esempio di tipo per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="fd883-233">Here's an example type to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public int WindSpeed { get; private set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="fd883-234">Questa opzione si applica solo alla serializzazione.</span><span class="sxs-lookup"><span data-stu-id="fd883-234">This option applies only to serialization.</span></span> <span data-ttu-id="fd883-235">Durante la deserializzazione, le proprietà di sola lettura vengono ignorate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fd883-235">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="fd883-236">Escludi tutte le proprietà dei valori null</span><span class="sxs-lookup"><span data-stu-id="fd883-236">Exclude all null value properties</span></span>

<span data-ttu-id="fd883-237">Per escludere tutte le proprietà con valore null, impostare la proprietà <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> su `true`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-237">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="fd883-238">Di seguito è riportato un esempio di oggetto da serializzare e output JSON:</span><span class="sxs-lookup"><span data-stu-id="fd883-238">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="fd883-239">proprietà</span><span class="sxs-lookup"><span data-stu-id="fd883-239">Property</span></span> |<span data-ttu-id="fd883-240">Value</span><span class="sxs-lookup"><span data-stu-id="fd883-240">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="fd883-241">Data</span><span class="sxs-lookup"><span data-stu-id="fd883-241">Date</span></span>    | <span data-ttu-id="fd883-242">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="fd883-242">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="fd883-243">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="fd883-243">TemperatureC</span></span>| <span data-ttu-id="fd883-244">25</span><span class="sxs-lookup"><span data-stu-id="fd883-244">25</span></span> |
| <span data-ttu-id="fd883-245">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="fd883-245">Summary</span></span>| <span data-ttu-id="fd883-246">null</span><span class="sxs-lookup"><span data-stu-id="fd883-246">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="fd883-247">Questa impostazione si applica alla serializzazione e alla deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="fd883-247">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="fd883-248">Per informazioni sugli effetti sulla deserializzazione, vedere [Ignore null durante la deserializzazione](#ignore-null-when-deserializing).</span><span class="sxs-lookup"><span data-stu-id="fd883-248">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="fd883-249">Personalizzare la codifica caratteri</span><span class="sxs-lookup"><span data-stu-id="fd883-249">Customize character encoding</span></span>

<span data-ttu-id="fd883-250">Per impostazione predefinita, il serializzatore viene sottoposto a escape per tutti i caratteri non ASCII.</span><span class="sxs-lookup"><span data-stu-id="fd883-250">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="fd883-251">Ovvero, li sostituisce con `\uxxxx` dove `xxxxx` è il codice Unicode del carattere.</span><span class="sxs-lookup"><span data-stu-id="fd883-251">That is, it replaces them with `\uxxxx` where `xxxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="fd883-252">Se, ad esempio, la proprietà `Summary` è impostata su cirillico жарко, l'oggetto `WeatherForecast` viene serializzato come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-252">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="fd883-253">Serializza i set di caratteri della lingua</span><span class="sxs-lookup"><span data-stu-id="fd883-253">Serialize language character sets</span></span>

<span data-ttu-id="fd883-254">Per serializzare i set di caratteri di una o più lingue, specificare gli [intervalli Unicode](xref:System.Text.Unicode.UnicodeRanges) quando si crea un'istanza di <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-254">To serialize the character set(s) of one or more languages, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(UnicodeRanges.Cyrillic, UnicodeRanges.GreekExtended)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="fd883-255">Questo codice serializza i caratteri cirillici e greci.</span><span class="sxs-lookup"><span data-stu-id="fd883-255">This code serializes Cyrillic and Greek characters.</span></span> <span data-ttu-id="fd883-256">Nell'esempio seguente vengono illustrati i caratteri cirillici:</span><span class="sxs-lookup"><span data-stu-id="fd883-256">Cyrillic characters are shown in the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жарко",
}
```

<span data-ttu-id="fd883-257">Per specificare tutte le lingue, utilizzare <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd883-257">To specify all languages, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="fd883-258">Serializza caratteri specifici</span><span class="sxs-lookup"><span data-stu-id="fd883-258">Serialize specific characters</span></span>

<span data-ttu-id="fd883-259">In alternativa, è possibile specificare i singoli caratteri che si desidera consentire tramite senza che venga eseguito il escape.</span><span class="sxs-lookup"><span data-stu-id="fd883-259">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="fd883-260">Nell'esempio seguente vengono serializzati solo i primi due caratteri di жарко:</span><span class="sxs-lookup"><span data-stu-id="fd883-260">The following example serializes only the first two characters of жарко:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var encoderSettings = new TextEncoderSettings();
encoderSettings.AllowCharacters('\u0436', '\u0430');
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(encoderSettings)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="fd883-261">Di seguito è riportato un esempio di JSON prodotto dal codice precedente:</span><span class="sxs-lookup"><span data-stu-id="fd883-261">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="fd883-262">Serializza tutti i caratteri</span><span class="sxs-lookup"><span data-stu-id="fd883-262">Serialize all characters</span></span>

<span data-ttu-id="fd883-263">Per ridurre al minimo l'escape, è possibile usare <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-263">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
```

```csharp
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.UnsafeRelaxedJsonEscaping
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

> [!CAUTION]
> <span data-ttu-id="fd883-264">A differenza del codificatore predefinito, il codificatore `UnsafeRelaxedJsonEscaping`:</span><span class="sxs-lookup"><span data-stu-id="fd883-264">Unlike the default encoder, the `UnsafeRelaxedJsonEscaping` encoder:</span></span>
>
> * <span data-ttu-id="fd883-265">Non esegue l'escape di caratteri con distinzione HTML, ad esempio `<`, `>`, `&`e `'`.</span><span class="sxs-lookup"><span data-stu-id="fd883-265">Doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="fd883-266">Non offre protezioni aggiuntive per la difesa in profondità da attacchi XSS o divulgazione di informazioni, ad esempio quelli che potrebbero risultare dal client e dal server che non accettano il set di *caratteri*.</span><span class="sxs-lookup"><span data-stu-id="fd883-266">Doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
> * <span data-ttu-id="fd883-267">È più permissiva del codificatore predefinito in cui è consentito il passaggio senza caratteri di escape.</span><span class="sxs-lookup"><span data-stu-id="fd883-267">Is more permissive than the default encoder on which characters are allowed to pass through unescaped.</span></span>
>
> <span data-ttu-id="fd883-268">Usare il codificatore unsafe solo quando è noto che il client interpreterà il payload risultante come JSON con codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="fd883-268">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="fd883-269">Ad esempio, è possibile usarlo se il server invia l'intestazione della risposta `Content-Type: application/json; charset=utf-8`.</span><span class="sxs-lookup"><span data-stu-id="fd883-269">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="fd883-270">Non consentire mai l'emissione dell'output `UnsafeRelaxedJsonEscaping` RAW in una pagina HTML o in un elemento `<script>`.</span><span class="sxs-lookup"><span data-stu-id="fd883-270">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="fd883-271">Serializzare le proprietà delle classi derivate</span><span class="sxs-lookup"><span data-stu-id="fd883-271">Serialize properties of derived classes</span></span>

<span data-ttu-id="fd883-272">La serializzazione polimorfica non è supportata quando si specifica in fase di compilazione il tipo da serializzare.</span><span class="sxs-lookup"><span data-stu-id="fd883-272">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="fd883-273">Si supponga, ad esempio, di avere una classe `WeatherForecast` e una classe derivata `WeatherForecastWithWind`:</span><span class="sxs-lookup"><span data-stu-id="fd883-273">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
class WeatherForecastWithWind : WeatherForecast
{
    public int WindSpeed { get; set; }
}
```

<span data-ttu-id="fd883-274">E si supponga che l'argomento di tipo del metodo `Serialize` in fase di compilazione sia `WeatherForecast`:</span><span class="sxs-lookup"><span data-stu-id="fd883-274">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="fd883-275">In questo scenario, la proprietà `WindSpeed` non viene serializzata anche se l'oggetto `weatherForecast` è effettivamente un oggetto `WeatherForecastWithWind`.</span><span class="sxs-lookup"><span data-stu-id="fd883-275">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="fd883-276">Vengono serializzate solo le proprietà della classe base:</span><span class="sxs-lookup"><span data-stu-id="fd883-276">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="fd883-277">Questo comportamento è volto a impedire l'esposizione accidentale dei dati in un tipo creato dal runtime derivato.</span><span class="sxs-lookup"><span data-stu-id="fd883-277">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="fd883-278">Per serializzare le proprietà del tipo derivato, usare uno degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd883-278">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="fd883-279">Chiamare un overload di <xref:System.Text.Json.JsonSerializer.Serialize%2A> che consente di specificare il tipo in fase di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="fd883-279">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="fd883-280">Dichiarare l'oggetto da serializzare come `object`.</span><span class="sxs-lookup"><span data-stu-id="fd883-280">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="fd883-281">Nello scenario di esempio precedente, entrambi gli approcci determinano l'inclusione della proprietà `WindSpeed` nell'output JSON:</span><span class="sxs-lookup"><span data-stu-id="fd883-281">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

<span data-ttu-id="fd883-282">Per informazioni sulla deserializzazione polimorfica, vedere [supportare la deserializzazione polimorfica](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span><span class="sxs-lookup"><span data-stu-id="fd883-282">For information about polymorphic deserialization, see [Support polymorphic deserialization](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="fd883-283">Consenti commenti e virgole finali</span><span class="sxs-lookup"><span data-stu-id="fd883-283">Allow comments and trailing commas</span></span>

<span data-ttu-id="fd883-284">Per impostazione predefinita, i commenti e le virgole finali non sono consentiti in JSON.</span><span class="sxs-lookup"><span data-stu-id="fd883-284">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="fd883-285">Per consentire i commenti nel codice JSON, impostare la proprietà <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> su `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="fd883-285">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="fd883-286">Per consentire le virgole finali, impostare la proprietà <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> su `true`.</span><span class="sxs-lookup"><span data-stu-id="fd883-286">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="fd883-287">Nell'esempio seguente viene illustrato come consentire entrambi:</span><span class="sxs-lookup"><span data-stu-id="fd883-287">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="fd883-288">Di seguito è riportato un esempio JSON con commenti e una virgola finale:</span><span class="sxs-lookup"><span data-stu-id="fd883-288">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="fd883-289">Corrispondenza proprietà senza distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="fd883-289">Case-insensitive property matching</span></span>

<span data-ttu-id="fd883-290">Per impostazione predefinita, la deserializzazione Cerca le corrispondenze tra i nomi delle proprietà con distinzione tra maiuscole e minuscole tra JSON e le proprietà dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="fd883-290">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="fd883-291">Per modificare tale comportamento, impostare il <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> su `true`:</span><span class="sxs-lookup"><span data-stu-id="fd883-291">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="fd883-292">Di seguito è riportato il codice JSON di esempio con i nomi di proprietà Camel case.</span><span class="sxs-lookup"><span data-stu-id="fd883-292">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="fd883-293">Può essere deserializzato nel tipo seguente con i nomi di proprietà del case Pascal.</span><span class="sxs-lookup"><span data-stu-id="fd883-293">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
}
```

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="handle-overflow-json"></a><span data-ttu-id="fd883-294">Gestione JSON di overflow</span><span class="sxs-lookup"><span data-stu-id="fd883-294">Handle overflow JSON</span></span>

<span data-ttu-id="fd883-295">Durante la deserializzazione, è possibile ricevere dati nel file JSON non rappresentato dalle proprietà del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fd883-295">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="fd883-296">Si supponga, ad esempio, che il tipo di destinazione sia il seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-296">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="fd883-297">Il codice JSON da deserializzare è il seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-297">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
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

<span data-ttu-id="fd883-298">Se si deserializza il codice JSON mostrato nel tipo visualizzato, le proprietà `DatesAvailable` e `SummaryWords` non hanno alcun luogo e andranno perse.</span><span class="sxs-lookup"><span data-stu-id="fd883-298">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="fd883-299">Per acquisire dati aggiuntivi, ad esempio queste proprietà, applicare l'attributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una proprietà di tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>`:</span><span class="sxs-lookup"><span data-stu-id="fd883-299">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonExtensionData]
    public Dictionary<string, object> ExtensionData { get; set; }
}
```

<span data-ttu-id="fd883-300">Quando si deserializza il codice JSON illustrato in precedenza in questo tipo di esempio, i dati aggiuntivi diventano coppie chiave-valore della proprietà `ExtensionData`:</span><span class="sxs-lookup"><span data-stu-id="fd883-300">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="fd883-301">proprietà</span><span class="sxs-lookup"><span data-stu-id="fd883-301">Property</span></span> |<span data-ttu-id="fd883-302">Value</span><span class="sxs-lookup"><span data-stu-id="fd883-302">Value</span></span>  |<span data-ttu-id="fd883-303">Note</span><span class="sxs-lookup"><span data-stu-id="fd883-303">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="fd883-304">Data</span><span class="sxs-lookup"><span data-stu-id="fd883-304">Date</span></span>    | <span data-ttu-id="fd883-305">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="fd883-305">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="fd883-306">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="fd883-306">TemperatureC</span></span>| <span data-ttu-id="fd883-307">0</span><span class="sxs-lookup"><span data-stu-id="fd883-307">0</span></span> | <span data-ttu-id="fd883-308">Mancata corrispondenza tra maiuscole e minuscole (`temperatureC` in JSON), quindi la proprietà non è impostata.</span><span class="sxs-lookup"><span data-stu-id="fd883-308">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="fd883-309">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="fd883-309">Summary</span></span> | <span data-ttu-id="fd883-310">A caldo</span><span class="sxs-lookup"><span data-stu-id="fd883-310">Hot</span></span> ||
| <span data-ttu-id="fd883-311">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="fd883-311">ExtensionData</span></span> | <span data-ttu-id="fd883-312">temperatureC: 25</span><span class="sxs-lookup"><span data-stu-id="fd883-312">temperatureC: 25</span></span> |<span data-ttu-id="fd883-313">Poiché il caso non corrisponde, questa proprietà JSON è un oggetto aggiuntivo e diventa una coppia chiave-valore nel dizionario.</span><span class="sxs-lookup"><span data-stu-id="fd883-313">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="fd883-314">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="fd883-314">DatesAvailable:</span></span><br>  <span data-ttu-id="fd883-315">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="fd883-315">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="fd883-316">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="fd883-316">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="fd883-317">Una proprietà aggiuntiva da JSON diventa una coppia chiave-valore, con una matrice come oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="fd883-317">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="fd883-318">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="fd883-318">SummaryWords:</span></span><br><span data-ttu-id="fd883-319">Comode</span><span class="sxs-lookup"><span data-stu-id="fd883-319">Cool</span></span><br><span data-ttu-id="fd883-320">Ventoso</span><span class="sxs-lookup"><span data-stu-id="fd883-320">Windy</span></span><br><span data-ttu-id="fd883-321">Umido</span><span class="sxs-lookup"><span data-stu-id="fd883-321">Humid</span></span> |<span data-ttu-id="fd883-322">Una proprietà aggiuntiva da JSON diventa una coppia chiave-valore, con una matrice come oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="fd883-322">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="fd883-323">Quando l'oggetto di destinazione viene serializzato, le coppie chiave-valore dei dati di estensione diventano proprietà JSON esattamente come nel codice JSON in ingresso:</span><span class="sxs-lookup"><span data-stu-id="fd883-323">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 0,
  "Summary": "Hot",
  "temperatureC": 25,
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

<span data-ttu-id="fd883-324">Si noti che il nome della proprietà `ExtensionData` non viene visualizzato in JSON.</span><span class="sxs-lookup"><span data-stu-id="fd883-324">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="fd883-325">Questo comportamento consente a JSON di creare un round trip senza perdere dati aggiuntivi che altrimenti non sarebbero deserializzati.</span><span class="sxs-lookup"><span data-stu-id="fd883-325">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="fd883-326">Ignora null durante la deserializzazione</span><span class="sxs-lookup"><span data-stu-id="fd883-326">Ignore null when deserializing</span></span>

<span data-ttu-id="fd883-327">Per impostazione predefinita, se una proprietà in JSON è null, la proprietà corrispondente nell'oggetto di destinazione viene impostata su null.</span><span class="sxs-lookup"><span data-stu-id="fd883-327">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="fd883-328">In alcuni scenari, la proprietà di destinazione potrebbe avere un valore predefinito e non si vuole che un valore null esegua l'override del valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="fd883-328">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="fd883-329">Si supponga, ad esempio, che il codice seguente rappresenti l'oggetto di destinazione:</span><span class="sxs-lookup"><span data-stu-id="fd883-329">For example, suppose the following code represents your target object:</span></span>

```csharp
class WeatherForecastWithDefault
{
    public WeatherForecastWithDefault()
    {
        Summary = "No summary";
    }
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="fd883-330">Si supponga che venga deserializzato il codice JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-330">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": null,
}
```

<span data-ttu-id="fd883-331">Dopo la deserializzazione, la proprietà `Summary` dell'oggetto `WeatherForecastWithDefault` è null.</span><span class="sxs-lookup"><span data-stu-id="fd883-331">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="fd883-332">Per modificare questo comportamento, impostare <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> su `true`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-332">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithDefault>(json, options);
```

<span data-ttu-id="fd883-333">Con questa opzione, la proprietà `Summary` dell'oggetto `WeatherForecastWithDefault` è il valore predefinito "nessun riepilogo" dopo la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="fd883-333">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="fd883-334">I valori null nel codice JSON vengono ignorati solo se sono validi.</span><span class="sxs-lookup"><span data-stu-id="fd883-334">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="fd883-335">I valori null per i tipi di valore non nullable generano eccezioni.</span><span class="sxs-lookup"><span data-stu-id="fd883-335">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="fd883-336">Per altre informazioni, vedere il [problema relativo ai tipi di valore non nullable](https://github.com/dotnet/corefx/issues/40922) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="fd883-336">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="fd883-337">Utf8JsonReader, Utf8JsonWriter e JsonDocument</span><span class="sxs-lookup"><span data-stu-id="fd883-337">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="fd883-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> è un lettore forward-only a prestazioni elevate e allocazione ridotta per il testo JSON con codifica UTF-8, letto da `ReadOnlySpan<byte>`.</span><span class="sxs-lookup"><span data-stu-id="fd883-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="fd883-339">Il `Utf8JsonReader` è un tipo di basso livello che può essere utilizzato per compilare parser e deserializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="fd883-339">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="fd883-340">Il metodo <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> utilizza `Utf8JsonReader` sotto le quinte.</span><span class="sxs-lookup"><span data-stu-id="fd883-340">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="fd883-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> è un modo a prestazioni elevate per scrivere testo JSON con codifica UTF-8 da tipi .NET comuni come `String`, `Int32`e `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="fd883-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="fd883-342">Il writer è un tipo di basso livello che può essere utilizzato per compilare serializzatori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="fd883-342">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="fd883-343">Il metodo <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> utilizza `Utf8JsonWriter` sotto le quinte.</span><span class="sxs-lookup"><span data-stu-id="fd883-343">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="fd883-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> fornisce la possibilità di creare un Document Object Model di sola lettura (DOM) utilizzando `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="fd883-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="fd883-345">Il DOM fornisce l'accesso casuale ai dati in un payload JSON.</span><span class="sxs-lookup"><span data-stu-id="fd883-345">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="fd883-346">È possibile accedere agli elementi JSON che compongono il payload tramite il tipo di <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="fd883-346">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="fd883-347">Il `JsonElement` fornisce enumeratori di oggetti e matrici insieme alle API per convertire il testo JSON in tipi .NET comuni.</span><span class="sxs-lookup"><span data-stu-id="fd883-347">The `JsonElement` provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="fd883-348">`JsonDocument` espone una proprietà <xref:System.Text.Json.JsonDocument.RootElement>.</span><span class="sxs-lookup"><span data-stu-id="fd883-348">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="fd883-349">Le sezioni seguenti illustrano come usare questi strumenti per la lettura e la scrittura di JSON.</span><span class="sxs-lookup"><span data-stu-id="fd883-349">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="fd883-350">Usare JsonDocument per l'accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="fd883-350">Use JsonDocument for access to data</span></span>

<span data-ttu-id="fd883-351">Nell'esempio seguente viene illustrato come utilizzare la classe <xref:System.Text.Json.JsonDocument> per l'accesso casuale ai dati:</span><span class="sxs-lookup"><span data-stu-id="fd883-351">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data:</span></span>

```csharp
double sum = 0;
int count = 0;

using (JsonDocument document = JsonDocument.Parse(jsonString))
{
    JsonElement root = document.RootElement;
    JsonElement studentsElement = root.GetProperty("Students");
    foreach (JsonElement student in studentsElement.EnumerateArray())
    {
        if (student.TryGetProperty("Grade", out JsonElement gradeElement))
        {
            sum += gradeElement.GetDouble();
        }
        else
        {
            sum += 70;
        }
        count++;
    }
}

double average = sum / count;
Console.WriteLine($"Average grade: {average}");
```

<span data-ttu-id="fd883-352">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="fd883-352">The preceding code:</span></span>

* <span data-ttu-id="fd883-353">Presuppone che il codice JSON da analizzare si trovi in una stringa denominata `jsonString`.</span><span class="sxs-lookup"><span data-stu-id="fd883-353">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="fd883-354">Calcola un livello medio per gli oggetti in una matrice di `Students` con una proprietà `Grade`.</span><span class="sxs-lookup"><span data-stu-id="fd883-354">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="fd883-355">Assegna un livello predefinito di 70 per gli studenti che non hanno un livello.</span><span class="sxs-lookup"><span data-stu-id="fd883-355">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="fd883-356">Conta gli studenti incrementando una variabile di `count` a ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="fd883-356">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="fd883-357">In alternativa, è possibile chiamare <xref:System.Text.Json.JsonElement.GetArrayLength%2A>:</span><span class="sxs-lookup"><span data-stu-id="fd883-357">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>:</span></span>

  ```csharp
  count = studentsElement.GetArrayLength();
  ```

<span data-ttu-id="fd883-358">Di seguito è riportato un esempio del codice JSON elaborato da questo codice:</span><span class="sxs-lookup"><span data-stu-id="fd883-358">Here's an example of the JSON that this code processes:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher's Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="fd883-359">Usare JsonDocument per scrivere JSON</span><span class="sxs-lookup"><span data-stu-id="fd883-359">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="fd883-360">Nell'esempio seguente viene illustrato come scrivere JSON da un <xref:System.Text.Json.JsonDocument>:</span><span class="sxs-lookup"><span data-stu-id="fd883-360">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);

var writerOptions = new JsonWriterOptions { Indented = true };
var documentOptions = new JsonDocumentOptions { CommentHandling = JsonCommentHandling.Skip };

using (FileStream fs = File.Create(outputFileName))
using (var writer = new Utf8JsonWriter(fs, options: writerOptions))
using (JsonDocument document = JsonDocument.Parse(jsonString, documentOptions))
{
    JsonElement root = document.RootElement;

    if (root.ValueKind == JsonValueKind.Object)
    {
        writer.WriteStartObject();
    }
    else
    {
        return;
    }

    foreach (JsonProperty property in root.EnumerateObject())
    {
        property.WriteTo(writer);
    }

    writer.WriteEndObject();

    writer.Flush();
}
```

<span data-ttu-id="fd883-361">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="fd883-361">The preceding code:</span></span>

* <span data-ttu-id="fd883-362">Legge un file JSON, carica i dati in un `JsonDocument`e scrive JSON formattato (abbastanza stampato) in un file.</span><span class="sxs-lookup"><span data-stu-id="fd883-362">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="fd883-363">USA <xref:System.Text.Json.JsonDocumentOptions> per specificare che i commenti nel codice JSON di input sono consentiti ma ignorati.</span><span class="sxs-lookup"><span data-stu-id="fd883-363">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="fd883-364">Al termine, chiama <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> sul writer.</span><span class="sxs-lookup"><span data-stu-id="fd883-364">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="fd883-365">In alternativa, è possibile lasciare che il writer AutoFlush quando viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="fd883-365">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="fd883-366">Di seguito è riportato un esempio di input JSON che verrà elaborato dal codice di esempio:</span><span class="sxs-lookup"><span data-stu-id="fd883-366">Here's an example of JSON input to be processed by the example code:</span></span>

```json
{"Class Name": "Science","Teacher's Name": "Jane","Semester": "2019-01-01","Students": [{"Name": "John","Grade": 94.3},{"Name": "James","Grade": 81.0},{"Name": "Julia","Grade": 91.9},{"Name": "Jessica","Grade": 72.4},{"Name": "Johnathan"}],"Final": true}
```

<span data-ttu-id="fd883-367">Il risultato è l'output JSON abbastanza stampato seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-367">The result is the following pretty-printed JSON output:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher\u0027s Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="fd883-368">Usare Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="fd883-368">Use Utf8JsonWriter</span></span>

<span data-ttu-id="fd883-369">Nell'esempio seguente viene illustrato come utilizzare la classe <xref:System.Text.Json.Utf8JsonWriter>:</span><span class="sxs-lookup"><span data-stu-id="fd883-369">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

```csharp
var options = new JsonWriterOptions
{
    Indented = true
};

using (var stream = new MemoryStream())
{
    using (var writer = new Utf8JsonWriter(stream, options))
    {
        writer.WriteStartObject();
        writer.WriteString("date", DateTimeOffset.UtcNow);
        writer.WriteNumber("temp", 42);
        writer.WriteEndObject();
    }

    string json = Encoding.UTF8.GetString(stream.ToArray());
    Console.WriteLine(json);
}
```

## <a name="use-utf8jsonreader"></a><span data-ttu-id="fd883-370">Usare Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="fd883-370">Use Utf8JsonReader</span></span>

<span data-ttu-id="fd883-371">Nell'esempio seguente viene illustrato come utilizzare la classe <xref:System.Text.Json.Utf8JsonReader>:</span><span class="sxs-lookup"><span data-stu-id="fd883-371">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

```csharp
var options = new JsonReaderOptions
{
    AllowTrailingCommas = true,
    CommentHandling = JsonCommentHandling.Skip
};
Utf8JsonReader reader = new Utf8JsonReader(jsonUtf8, options);

while (reader.Read())
{
    Console.Write(reader.TokenType);

    switch (reader.TokenType)
    {
        case JsonTokenType.PropertyName:
        case JsonTokenType.String:
            {
                string text = reader.GetString();
                Console.Write(" ");
                Console.Write(text);
                break;
            }

        case JsonTokenType.Number:
            {
                int value = reader.GetInt32();
                Console.Write(" ");
                Console.Write(value);
                break;
            }

            // Other token types elided for brevity
    }

    Console.WriteLine();
}
```

<span data-ttu-id="fd883-372">Il codice precedente presuppone che la variabile `jsonUtf8` sia una matrice di byte che contiene JSON valido, codificato come UTF-8.</span><span class="sxs-lookup"><span data-stu-id="fd883-372">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="fd883-373">Filtrare i dati tramite Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="fd883-373">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="fd883-374">Nell'esempio seguente viene illustrato come leggere un file in modo sincrono e cercare un valore:</span><span class="sxs-lookup"><span data-stu-id="fd883-374">The following example shows how to read a file synchronously and search for a value:</span></span>

```csharp
class Program
{
    private static readonly byte[] s_nameUtf8 = Encoding.UTF8.GetBytes("name");
    private static readonly byte[] s_universityUtf8 = Encoding.UTF8.GetBytes("University");

    private static void ReaderFromFileSync(string fileName)
    {
         string jsonString = File.ReadAllText(fileName);
         ReadOnlySpan<byte> jsonReadOnlySpan = Encoding.UTF8.GetBytes(jsonString);

        int count = 0;
        int total = 0;

        var json = new Utf8JsonReader(jsonReadOnlySpan, isFinalBlock: true, state: default);

        while (json.Read())
        {
            JsonTokenType tokenType = json.TokenType;

            switch (tokenType)
            {
                case JsonTokenType.StartObject:
                    total++;
                    break;
                case JsonTokenType.PropertyName:
                    if (json.ValueSpan.SequenceEqual(s_nameUtf8))
                    {
                        bool result = json.Read();

                        Debug.Assert(result);  // Assume valid JSON
                        Debug.Assert(json.TokenType == JsonTokenType.String);   // Assume known, valid JSON schema

                        if (json.ValueSpan.EndsWith(s_universityUtf8))
                        {
                            count++;
                        }
                    }
                    break;
            }
        }
        Console.WriteLine($"{count} out of {total} have names that end with 'University'");
    }
}
```

<span data-ttu-id="fd883-375">Il codice precedente:</span><span class="sxs-lookup"><span data-stu-id="fd883-375">The preceding code:</span></span>

* <span data-ttu-id="fd883-376">Presuppone che il file sia codificato come UTF-16 e lo transcodifichi in UTF-8.</span><span class="sxs-lookup"><span data-stu-id="fd883-376">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="fd883-377">Un file codificato come UTF-8 può essere letto direttamente in una `ReadOnlySpan<byte>`, usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fd883-377">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* <span data-ttu-id="fd883-378">Presuppone che JSON contenga una matrice di oggetti e che ogni oggetto possa contenere una proprietà "Name" di tipo String.</span><span class="sxs-lookup"><span data-stu-id="fd883-378">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="fd883-379">Conta gli oggetti e `name` i valori delle proprietà che terminano con "University".</span><span class="sxs-lookup"><span data-stu-id="fd883-379">Counts objects and `name` property values that end with "University".</span></span>

<span data-ttu-id="fd883-380">Di seguito è riportato un esempio JSON che il codice precedente può leggere.</span><span class="sxs-lookup"><span data-stu-id="fd883-380">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="fd883-381">Il messaggio di riepilogo risultante è "2 su 4 hanno nomi che terminano con" University "":</span><span class="sxs-lookup"><span data-stu-id="fd883-381">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

```json
[
  {
    "web_pages": [ "https://contoso.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contoso.edu" ],
    "name": "Contoso Community College"
  },
  {
    "web_pages": [ "http://fabrikam.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikam.edu" ],
    "name": "Fabrikam Community College"
  },
  {
    "web_pages": [ "http://www.contosouniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contosouniversity.edu" ],
    "name": "Contoso University"
  },
  {
    "web_pages": [ "http://www.fabrikamuniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikamuniversity.edu" ],
    "name": "Fabrikam University"
  }
]
```

## <a name="additional-resources"></a><span data-ttu-id="fd883-382">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fd883-382">Additional resources</span></span>

* [<span data-ttu-id="fd883-383">Panoramica di System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="fd883-383">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="fd883-384">Informazioni di riferimento sull'API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="fd883-384">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="fd883-385">Scrivere convertitori personalizzati per System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="fd883-385">Write custom converters for System.Text.Json</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="fd883-386">Supporto di DateTime e DateTimeOffset in System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="fd883-386">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
