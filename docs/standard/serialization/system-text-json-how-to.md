---
title: Come serializzare JSON-.NET
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 8ccd7afe4abb928e7723aa740507774012fc85d1
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083101"
---
# <a name="how-to-serialize-json-in-net"></a><span data-ttu-id="4c0a8-102">Come serializzare JSON in .NET</span><span class="sxs-lookup"><span data-stu-id="4c0a8-102">How to serialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c0a8-103">La documentazione di serializzazione JSON è in costruzione.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="4c0a8-104">Questo articolo non copre tutti gli scenari.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="4c0a8-105">Per altre informazioni, esaminare i [problemi di System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) nel repository DotNet/CoreFx su GitHub, in particolare quelli con etichetta [JSON-funzionalità-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span><span class="sxs-lookup"><span data-stu-id="4c0a8-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="4c0a8-106">Questo articolo illustra come usare lo <xref:System.Text.Json> spazio dei nomi per serializzare e deserializzare da e verso JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="4c0a8-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="4c0a8-107">Le direzioni e il codice di esempio usano la libreria direttamente, non tramite un Framework come [ASP.NET Core](/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="4c0a8-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="4c0a8-108">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="4c0a8-108">Namespaces</span></span>

<span data-ttu-id="4c0a8-109">Lo <xref:System.Text.Json> spazio dei nomi contiene tutti i punti di ingresso e i tipi principali.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="4c0a8-110">Lo <xref:System.Text.Json.Serialization> spazio dei nomi contiene attributi e API per scenari avanzati e personalizzazione specifici per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="4c0a8-111">Gli esempi di codice illustrati in questo articolo richiedono pertanto una o entrambe le direttive seguenti `using` :</span><span class="sxs-lookup"><span data-stu-id="4c0a8-111">Therefore, the code examples shown in this article require one or both of the following `using` directives:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="4c0a8-112">Gli attributi `System.Text.Json`dello spaziodeinominonsono<xref:System.Runtime.Serialization> attualmente supportati in.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="4c0a8-113">Come scrivere oggetti .NET in JSON (Serialize)</span><span class="sxs-lookup"><span data-stu-id="4c0a8-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="4c0a8-114">Per scrivere JSON in una stringa, chiamare il <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-114">To write JSON to a string, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4c0a8-115">Nell'esempio seguente viene usato un overload con un parametro di tipo generico:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-115">The following example uses an overload with a generic type parameter:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="4c0a8-116">È possibile omettere il parametro di tipo generico e usare invece l'inferenza del tipo generico:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-116">You can omit the generic type parameter and use generic type inference instead:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="4c0a8-117">Di seguito è riportato un esempio di tipo da serializzare, che contiene le raccolte e le classi annidate:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-117">Here's an example type to be serialized, which contains collections and nested classes:</span></span>

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

<span data-ttu-id="4c0a8-118">Per impostazione predefinita, l'output JSON è minimizzati:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-118">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="4c0a8-119">Nell'esempio seguente viene illustrato lo stesso JSON, formattato, ovvero abbastanza stampato con spazi vuoti e rientri:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-119">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

<span data-ttu-id="4c0a8-120">Gli overload di consentono <xref:System.Text.Json.JsonSerializer.Serialize%2A> di eseguire la serializzazione <xref:System.IO.Stream>in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-120">Overloads of <xref:System.Text.Json.JsonSerializer.Serialize%2A> let you serialize to a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="4c0a8-121">Sono disponibili versioni asincrone `Stream` degli overload.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-121">Async versions of the `Stream` overloads are available.</span></span>

### <a name="serialize-to-utf-8"></a><span data-ttu-id="4c0a8-122">Serializza in UTF-8</span><span class="sxs-lookup"><span data-stu-id="4c0a8-122">Serialize to UTF-8</span></span>

<span data-ttu-id="4c0a8-123">Per serializzare in UTF-8, chiamare <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> il metodo:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-123">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] utf8Json = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="4c0a8-124">In alternativa, è disponibile <xref:System.Text.Json.JsonSerializer.Serialize%2A> un overload che accetta <xref:System.Text.Json.Utf8JsonWriter> un oggetto.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-124">As an alternative, a <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is available.</span></span>

<span data-ttu-id="4c0a8-125">La serializzazione in UTF-8 è più veloce del 5-10% rispetto all'uso dei metodi basati su stringa.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-125">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="4c0a8-126">La differenza è dovuta al fatto che i byte (come UTF-8) non devono essere convertiti in stringhe (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="4c0a8-126">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="4c0a8-127">Comportamento della serializzazione</span><span class="sxs-lookup"><span data-stu-id="4c0a8-127">Serialization behavior</span></span>

* <span data-ttu-id="4c0a8-128">Per impostazione predefinita, tutte le proprietà pubbliche vengono serializzate.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-128">By default, all public properties are serialized.</span></span> <span data-ttu-id="4c0a8-129">È possibile [specificare le proprietà da escludere](#exclude-properties).</span><span class="sxs-lookup"><span data-stu-id="4c0a8-129">You can [specify properties to exclude](#exclude-properties).</span></span>
* <span data-ttu-id="4c0a8-130">Il [codificatore predefinito](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) consente di eseguire l'escape dei caratteri non ASCII, dei caratteri con distinzione HTML nell'intervallo ASCII e dei caratteri che devono essere preceduti da un carattere di escape in base alla [specifica JSON](https://tools.ietf.org/html/rfc8259#section-7).</span><span class="sxs-lookup"><span data-stu-id="4c0a8-130">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="4c0a8-131">Per impostazione predefinita, JSON è minimizzati.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-131">By default, JSON is minified.</span></span> <span data-ttu-id="4c0a8-132">È possibile [stampare](#serialize-to-formatted-json)in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-132">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="4c0a8-133">Per impostazione predefinita, le maiuscole e minuscole dei nomi JSON corrispondono ai nomi .NET.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-133">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="4c0a8-134">È possibile [personalizzare la combinazione di maiuscole e minuscole](#customize-json-names).</span><span class="sxs-lookup"><span data-stu-id="4c0a8-134">You can [customize JSON name casing](#customize-json-names).</span></span>
* <span data-ttu-id="4c0a8-135">Vengono rilevati riferimenti circolari e vengono generate eccezioni.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-135">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="4c0a8-136">Per ulteriori informazioni, vedere il [problema relativo ai riferimenti circolari](https://github.com/dotnet/corefx/issues/38579) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-136">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="4c0a8-137">Attualmente, i campi vengono esclusi.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-137">Currently, fields are excluded.</span></span>

<span data-ttu-id="4c0a8-138">I tipi supportati includono:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-138">Supported types include:</span></span>

* <span data-ttu-id="4c0a8-139">Primitive .NET mappate a primitive JavaScript, ad esempio tipi numerici, stringhe e valori booleani.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-139">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="4c0a8-140">[Oggetti CLR obsoleti definiti dall'utente (poco)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="4c0a8-140">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="4c0a8-141">Matrici unidimensionali e irregolari (`ArrayName[][]`).</span><span class="sxs-lookup"><span data-stu-id="4c0a8-141">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="4c0a8-142">`Dictionary<string,TValue>`dove `TValue` è `object` ,`JsonElement`o poco.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-142">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="4c0a8-143">Raccolte dai seguenti spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-143">Collections from the following namespaces.</span></span> <span data-ttu-id="4c0a8-144">Per ulteriori informazioni, vedere il [problema relativo al supporto della raccolta](https://github.com/dotnet/corefx/issues/36643) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-144">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="4c0a8-145">Come leggere JSON in oggetti .NET (deserializzare)</span><span class="sxs-lookup"><span data-stu-id="4c0a8-145">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="4c0a8-146">Per deserializzare da una stringa, chiamare il <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> metodo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-146">To deserialize from a string, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method, as shown in the following example:</span></span>

```csharp
string json = ... ;

var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="4c0a8-147">Per un esempio, vedere la sezione [Serialize](#how-to-write-net-objects-to-json-serialize) .</span><span class="sxs-lookup"><span data-stu-id="4c0a8-147">For an example, see the [serialize](#how-to-write-net-objects-to-json-serialize) section.</span></span> <span data-ttu-id="4c0a8-148">L'oggetto JSON e .NET sono gli stessi, ma la direzione è invertita.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-148">The JSON and .NET object are the same, but the direction is reversed.</span></span>

<span data-ttu-id="4c0a8-149">Gli overload di consentono <xref:System.Text.Json.JsonSerializer.Deserialize*> di eseguire la deserializzazione da `Stream`un oggetto.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-149">Overloads of <xref:System.Text.Json.JsonSerializer.Deserialize*> let you deserialize from a `Stream`.</span></span>  <span data-ttu-id="4c0a8-150">Sono disponibili versioni asincrone `Stream` degli overload.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-150">Async versions of the `Stream` overloads are available.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="4c0a8-151">Deserializzazione da UTF-8</span><span class="sxs-lookup"><span data-stu-id="4c0a8-151">Deserialize from UTF-8</span></span>

<span data-ttu-id="4c0a8-152">Per deserializzare da UTF-8, chiamare un <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload che accetta un `Utf8JsonReader` oggetto o `ReadOnlySpan<byte>`, come illustrato negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-152">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples:</span></span>

```csharp
byte[] utf8Json;
//...
var readOnlySpan = new ReadOnlySpan<byte>(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
byte[] utf8Json;
//...
var utf8Reader = new Utf8JsonReader(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="4c0a8-153">Comportamento di deserializzazione</span><span class="sxs-lookup"><span data-stu-id="4c0a8-153">Deserialization behavior</span></span>

* <span data-ttu-id="4c0a8-154">Per impostazione predefinita, la corrispondenza dei nomi di proprietà fa distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="4c0a8-154">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="4c0a8-155">È possibile specificare la distinzione tra [maiuscole e minuscole](#case-insensitive-property-matching).</span><span class="sxs-lookup"><span data-stu-id="4c0a8-155">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="4c0a8-156">Se il codice JSON contiene un valore per una proprietà di sola lettura, il valore viene ignorato e non viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-156">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="4c0a8-157">La deserializzazione ai tipi di riferimento senza un costruttore senza parametri non è supportata.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-157">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="4c0a8-158">La deserializzazione a oggetti non modificabili o a proprietà di sola lettura non è supportata.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-158">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="4c0a8-159">Per ulteriori informazioni, vedere il [problema GitHub sul supporto di oggetti non modificabili](https://github.com/dotnet/corefx/issues/38569) e il [problema relativo al supporto delle proprietà di sola lettura](https://github.com/dotnet/corefx/issues/38163) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-159">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="4c0a8-160">Per impostazione predefinita, le enumerazioni sono supportate come numeri.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-160">By default, enums are supported as numbers.</span></span>
* <span data-ttu-id="4c0a8-161">I campi non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-161">Fields aren't supported.</span></span>
* <span data-ttu-id="4c0a8-162">Per impostazione predefinita, i commenti o le virgole finali in JSON generano eccezioni.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-162">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="4c0a8-163">Se necessario [, è possibile consentire i commenti e le virgole finali](#allow-comments-and-trailing-commas) .</span><span class="sxs-lookup"><span data-stu-id="4c0a8-163">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas) if needed.</span></span>
* <span data-ttu-id="4c0a8-164">La [profondità massima predefinita](xref:System.Text.Json.JsonReaderOptions.MaxDepth) è 64.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-164">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="4c0a8-165">Serializza nel formato JSON formattato</span><span class="sxs-lookup"><span data-stu-id="4c0a8-165">Serialize to formatted JSON</span></span>

<span data-ttu-id="4c0a8-166">Per stampare l'output JSON, impostare <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> su: `true`</span><span class="sxs-lookup"><span data-stu-id="4c0a8-166">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="4c0a8-167">Di seguito è riportato un esempio di tipo da serializzare e output JSON:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-167">Here's an example type to be serialized and JSON output:</span></span>

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

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="4c0a8-168">Consenti commenti e virgole finali</span><span class="sxs-lookup"><span data-stu-id="4c0a8-168">Allow comments and trailing commas</span></span>

<span data-ttu-id="4c0a8-169">Per impostazione predefinita, i commenti e le virgole finali non sono consentiti in JSON.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-169">By default comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="4c0a8-170">Per consentire i commenti in JSON, impostare la <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> proprietà su `JsonCommentHandling.Skip`.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-170">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="4c0a8-171">Per consentire le virgole finali, impostare la <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> proprietà su. `true`</span><span class="sxs-lookup"><span data-stu-id="4c0a8-171">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="4c0a8-172">Nell'esempio seguente viene illustrato come consentire entrambi:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-172">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="4c0a8-173">Di seguito è riportato un esempio JSON con commenti e una virgola finale:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-173">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="customize-json-names"></a><span data-ttu-id="4c0a8-174">Personalizzare i nomi JSON</span><span class="sxs-lookup"><span data-stu-id="4c0a8-174">Customize JSON names</span></span>

<span data-ttu-id="4c0a8-175">Per impostazione predefinita, i nomi delle proprietà e le chiavi del dizionario non cambiano nell'output JSON, inclusa la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-175">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="4c0a8-176">Questa sezione illustra come eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-176">This section explains how to:</span></span>

* <span data-ttu-id="4c0a8-177">Personalizzare i singoli nomi di proprietà</span><span class="sxs-lookup"><span data-stu-id="4c0a8-177">Customize individual property names</span></span>
* <span data-ttu-id="4c0a8-178">Converte tutti i nomi di proprietà in Camel case</span><span class="sxs-lookup"><span data-stu-id="4c0a8-178">Convert all property names to camel case</span></span>
* <span data-ttu-id="4c0a8-179">Implementare i criteri di denominazione delle proprietà personalizzate</span><span class="sxs-lookup"><span data-stu-id="4c0a8-179">Implement a custom property naming policy</span></span>
* <span data-ttu-id="4c0a8-180">Converte le chiavi del dizionario in lettere maiuscole</span><span class="sxs-lookup"><span data-stu-id="4c0a8-180">Convert dictionary keys to camel case</span></span>

<span data-ttu-id="4c0a8-181">Attualmente non è disponibile alcun supporto per la conversione automatica delle enumerazioni in maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-181">Currently, there's no support for automatically converting enums to camel case.</span></span> <span data-ttu-id="4c0a8-182">Per ulteriori informazioni, vedere il [problema relativo al supporto del case Camel enum](https://github.com/dotnet/corefx/issues/37725) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-182">For more information, see the [issue on enum camel case support](https://github.com/dotnet/corefx/issues/37725) in the dotnet/corefx repository on GitHub.</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="4c0a8-183">Personalizzare i singoli nomi di proprietà</span><span class="sxs-lookup"><span data-stu-id="4c0a8-183">Customize individual property names</span></span>

<span data-ttu-id="4c0a8-184">Per impostare il nome delle singole proprietà, utilizzare l'attributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .</span><span class="sxs-lookup"><span data-stu-id="4c0a8-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="4c0a8-185">Di seguito è riportato un esempio di tipo da serializzare e JSON risultante:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-185">Here's an example type to serialize and resulting JSON:</span></span>

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

<span data-ttu-id="4c0a8-186">Nome della proprietà impostato dall'attributo:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="4c0a8-187">Si applica in entrambe le direzioni, per la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="4c0a8-188">Ha la precedenza sui criteri di denominazione delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="4c0a8-189">Usa il caso Camel per tutti i nomi di proprietà JSON</span><span class="sxs-lookup"><span data-stu-id="4c0a8-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="4c0a8-190">Per usare il caso Camel per tutti i nomi di proprietà <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> JSON `JsonNamingPolicy.CamelCase`, impostare su, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="4c0a8-191">Ecco una classe di esempio per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-191">Here's an example class to serialize and JSON output:</span></span>

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
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="4c0a8-192">Criteri di denominazione delle proprietà Camel case:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="4c0a8-193">Si applica alla serializzazione e alla deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="4c0a8-194">Viene sottoposto a `[JsonPropertyName]` override dagli attributi.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-194">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="4c0a8-195">Usare un criterio personalizzato per la denominazione delle proprietà JSON</span><span class="sxs-lookup"><span data-stu-id="4c0a8-195">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="4c0a8-196">Per usare un criterio di denominazione delle proprietà JSON personalizzato, creare una classe che derivi <xref:System.Text.Json.JsonNamingPolicy> da ed eseguire <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> l'override del metodo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-196">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="4c0a8-197">Impostare quindi la <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> proprietà su un'istanza della classe di criteri di denominazione:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-197">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="4c0a8-198">Ecco una classe di esempio per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-198">Here's an example class to serialize and JSON output:</span></span>

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

<span data-ttu-id="4c0a8-199">Criteri di denominazione delle proprietà JSON:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-199">The JSON property naming policy:</span></span>

* <span data-ttu-id="4c0a8-200">Si applica alla serializzazione e alla deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-200">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="4c0a8-201">Viene sottoposto a `[JsonPropertyName]` override dagli attributi.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-201">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="4c0a8-202">Chiavi del dizionario case Camel</span><span class="sxs-lookup"><span data-stu-id="4c0a8-202">Camel case dictionary keys</span></span>

<span data-ttu-id="4c0a8-203">Se una proprietà di un oggetto da serializzare è di tipo `Dictionary<string,TValue>`, le `string` chiavi possono essere convertite in maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-203">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="4c0a8-204">A tale scopo, impostare <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> su `JsonNamingPolicy.CamelCase`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-204">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="4c0a8-205">Di seguito è riportato un esempio di oggetto da serializzare e output JSON:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-205">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="4c0a8-206">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4c0a8-206">Property</span></span> |<span data-ttu-id="4c0a8-207">Value</span><span class="sxs-lookup"><span data-stu-id="4c0a8-207">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="4c0a8-208">Date</span><span class="sxs-lookup"><span data-stu-id="4c0a8-208">Date</span></span>    | <span data-ttu-id="4c0a8-209">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="4c0a8-209">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="4c0a8-210">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="4c0a8-210">TemperatureC</span></span>| <span data-ttu-id="4c0a8-211">25</span><span class="sxs-lookup"><span data-stu-id="4c0a8-211">25</span></span> |
| <span data-ttu-id="4c0a8-212">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4c0a8-212">Summary</span></span>| <span data-ttu-id="4c0a8-213">A caldo</span><span class="sxs-lookup"><span data-stu-id="4c0a8-213">Hot</span></span>|
| <span data-ttu-id="4c0a8-214">TemperatureRanges</span><span class="sxs-lookup"><span data-stu-id="4c0a8-214">TemperatureRanges</span></span> | <span data-ttu-id="4c0a8-215">Freddo, 20</span><span class="sxs-lookup"><span data-stu-id="4c0a8-215">Cold, 20</span></span><br><span data-ttu-id="4c0a8-216">Caldo, 40</span><span class="sxs-lookup"><span data-stu-id="4c0a8-216">Hot, 40</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "cold": 20,
    "hot": 40
  }
}
```

<span data-ttu-id="4c0a8-217">I criteri di denominazione Camel case si applicano solo alla serializzazione.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-217">The camel case naming policy applies to serialization only.</span></span>

## <a name="exclude-properties"></a><span data-ttu-id="4c0a8-218">Escludi proprietà</span><span class="sxs-lookup"><span data-stu-id="4c0a8-218">Exclude properties</span></span>

<span data-ttu-id="4c0a8-219">Per impostazione predefinita, tutte le proprietà pubbliche vengono serializzate.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="4c0a8-220">Se non si vuole che alcuni di essi vengano visualizzati nell'output JSON, sono disponibili diverse opzioni.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="4c0a8-221">In questa sezione viene illustrato come escludere:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-221">This section explains how to exclude:</span></span>

* <span data-ttu-id="4c0a8-222">Singole proprietà</span><span class="sxs-lookup"><span data-stu-id="4c0a8-222">Individual properties</span></span>
* <span data-ttu-id="4c0a8-223">Tutte le proprietà di sola lettura</span><span class="sxs-lookup"><span data-stu-id="4c0a8-223">All read-only properties</span></span>
* <span data-ttu-id="4c0a8-224">Tutte le proprietà con valore null</span><span class="sxs-lookup"><span data-stu-id="4c0a8-224">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="4c0a8-225">Escludi singole proprietà</span><span class="sxs-lookup"><span data-stu-id="4c0a8-225">Exclude individual properties</span></span>

<span data-ttu-id="4c0a8-226">Per ignorare le singole proprietà, utilizzare l'attributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .</span><span class="sxs-lookup"><span data-stu-id="4c0a8-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="4c0a8-227">Ecco un esempio di tipo per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-227">Here's an example type to serialize and JSON output:</span></span>

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

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="4c0a8-228">Escludi tutte le proprietà di sola lettura</span><span class="sxs-lookup"><span data-stu-id="4c0a8-228">Exclude all read-only properties</span></span>

<span data-ttu-id="4c0a8-229">Per escludere tutte le proprietà <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> di sola lettura, impostare su `true`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-229">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="4c0a8-230">Ecco un esempio di tipo per serializzare e l'output JSON:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-230">Here's an example type to serialize and JSON output:</span></span>

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

<span data-ttu-id="4c0a8-231">Questa opzione si applica solo alla serializzazione.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-231">This option applies only to serialization.</span></span> <span data-ttu-id="4c0a8-232">Durante la deserializzazione, le proprietà di sola lettura vengono ignorate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-232">During deserialization, read-only properties are ignored by default.</span></span> <span data-ttu-id="4c0a8-233">Una proprietà è di sola lettura se contiene un getter pubblico ma non un setter pubblico.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-233">A property is read-only if it contains a public getter but not a public setter.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="4c0a8-234">Escludi tutte le proprietà dei valori null</span><span class="sxs-lookup"><span data-stu-id="4c0a8-234">Exclude all null value properties</span></span>

<span data-ttu-id="4c0a8-235">Per escludere tutte le proprietà con valore null <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> , impostare `true`la proprietà su, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="4c0a8-236">Di seguito è riportato un esempio di oggetto da serializzare e output JSON:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="4c0a8-237">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4c0a8-237">Property</span></span> |<span data-ttu-id="4c0a8-238">Value</span><span class="sxs-lookup"><span data-stu-id="4c0a8-238">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="4c0a8-239">Date</span><span class="sxs-lookup"><span data-stu-id="4c0a8-239">Date</span></span>    | <span data-ttu-id="4c0a8-240">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="4c0a8-240">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="4c0a8-241">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="4c0a8-241">TemperatureC</span></span>| <span data-ttu-id="4c0a8-242">25</span><span class="sxs-lookup"><span data-stu-id="4c0a8-242">25</span></span> |
| <span data-ttu-id="4c0a8-243">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4c0a8-243">Summary</span></span>| <span data-ttu-id="4c0a8-244">Null</span><span class="sxs-lookup"><span data-stu-id="4c0a8-244">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="4c0a8-245">Questa impostazione si applica alla serializzazione e alla deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-245">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="4c0a8-246">Durante la deserializzazione, i valori null nel codice JSON vengono ignorati solo se sono validi.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-246">During deserialization, null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="4c0a8-247">I valori null per i tipi di valore non nullable generano eccezioni.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-247">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="4c0a8-248">Per altre informazioni, vedere il [problema relativo ai tipi di valore non nullable](https://github.com/dotnet/corefx/issues/40922) nel repository DotNet/CoreFx su GitHub.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-248">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="4c0a8-249">Corrispondenza proprietà senza distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="4c0a8-249">Case-insensitive property matching</span></span>

<span data-ttu-id="4c0a8-250">Per impostazione predefinita, la deserializzazione Cerca le corrispondenze tra i nomi delle proprietà con distinzione tra maiuscole e minuscole tra JSON e le proprietà dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="4c0a8-250">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="4c0a8-251">Per modificare tale comportamento, impostare <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> su: `true`</span><span class="sxs-lookup"><span data-stu-id="4c0a8-251">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="4c0a8-252">Di seguito è riportato il codice JSON di esempio con i nomi di proprietà Camel case.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-252">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="4c0a8-253">Può essere deserializzato nel tipo seguente con i nomi di proprietà del case Pascal.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-253">It can be deserialized into the following type that has Pascal case property names.</span></span>

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

## <a name="include-properties-of-derived-classes"></a><span data-ttu-id="4c0a8-254">Includi proprietà di classi derivate</span><span class="sxs-lookup"><span data-stu-id="4c0a8-254">Include properties of derived classes</span></span>

<span data-ttu-id="4c0a8-255">La serializzazione polimorfica non è supportata quando si specifica in fase di compilazione il tipo da serializzare.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-255">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="4c0a8-256">Si supponga, ad esempio, di `WeatherForecast` disporre di una classe e `WeatherForecastWithWind`di una classe derivata:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-256">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

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

<span data-ttu-id="4c0a8-257">E si supponga che il tipo passato a, o dedotto da, `Serialize` il metodo in fase di `WeatherForecast`compilazione sia:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-257">And suppose the type passed to, or inferred by, the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

```csharp
WeatherForecast weatherForecast;
//...
json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="4c0a8-258">In questo scenario, la `WindSpeed` proprietà non viene serializzata anche se l' `weatherForecast` oggetto è effettivamente un `WeatherForecastWithWind` oggetto.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-258">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="4c0a8-259">Vengono serializzate solo le proprietà della classe base:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-259">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="4c0a8-260">Questo comportamento è volto a impedire l'esposizione accidentale dei dati in un tipo creato dal runtime derivato.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-260">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="4c0a8-261">Per serializzare le proprietà del tipo derivato, usare uno degli approcci seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-261">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="4c0a8-262">Chiamare un overload di <xref:System.Text.Json.JsonSerializer.Serialize%2A> che consente di specificare il tipo in fase di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-262">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="4c0a8-263">Dichiarare l'oggetto da serializzare come `object`.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-263">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="4c0a8-264">Nello scenario di esempio precedente, entrambi gli approcci determinano l'inclusione della `WindSpeed` proprietà nell'output JSON:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-264">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

## <a name="handle-overflow-json"></a><span data-ttu-id="4c0a8-265">Gestione JSON di overflow</span><span class="sxs-lookup"><span data-stu-id="4c0a8-265">Handle overflow JSON</span></span>

<span data-ttu-id="4c0a8-266">Durante la deserializzazione, è possibile ricevere dati nel file JSON non rappresentato dalle proprietà del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-266">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="4c0a8-267">Si supponga, ad esempio, che il tipo di destinazione sia il seguente:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-267">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="4c0a8-268">Il codice JSON da deserializzare è il seguente:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-268">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="4c0a8-269">Se si deserializza il codice JSON mostrato nel tipo visualizzato, le `DatesAvailable` proprietà e `SummaryWords` non hanno alcun luogo e andranno perse.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-269">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="4c0a8-270">Per acquisire dati aggiuntivi, ad esempio queste proprietà, applicare l'attributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una proprietà di `Dictionary<string,object>` tipo `Dictionary<string,JsonElement>`o:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-270">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

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

<span data-ttu-id="4c0a8-271">Quando si deserializza il codice JSON illustrato in precedenza in questo tipo di esempio, i dati aggiuntivi diventano coppie chiave-valore della `ExtensionData` proprietà:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-271">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="4c0a8-272">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4c0a8-272">Property</span></span> |<span data-ttu-id="4c0a8-273">Value</span><span class="sxs-lookup"><span data-stu-id="4c0a8-273">Value</span></span>  |<span data-ttu-id="4c0a8-274">Note</span><span class="sxs-lookup"><span data-stu-id="4c0a8-274">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="4c0a8-275">Date</span><span class="sxs-lookup"><span data-stu-id="4c0a8-275">Date</span></span>    | <span data-ttu-id="4c0a8-276">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="4c0a8-276">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="4c0a8-277">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="4c0a8-277">TemperatureC</span></span>| <span data-ttu-id="4c0a8-278">0</span><span class="sxs-lookup"><span data-stu-id="4c0a8-278">0</span></span> | <span data-ttu-id="4c0a8-279">Mancata corrispondenza tra maiuscole`temperatureC` e minuscole (in JSON), quindi la proprietà non è impostata.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-279">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="4c0a8-280">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4c0a8-280">Summary</span></span> | <span data-ttu-id="4c0a8-281">A caldo</span><span class="sxs-lookup"><span data-stu-id="4c0a8-281">Hot</span></span> ||
| <span data-ttu-id="4c0a8-282">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="4c0a8-282">ExtensionData</span></span> | <span data-ttu-id="4c0a8-283">temperatureC: 25</span><span class="sxs-lookup"><span data-stu-id="4c0a8-283">temperatureC: 25</span></span> |<span data-ttu-id="4c0a8-284">Poiché il caso non corrisponde, questa proprietà JSON è un oggetto aggiuntivo e diventa una coppia chiave-valore nel dizionario.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-284">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="4c0a8-285">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-285">DatesAvailable:</span></span><br>  <span data-ttu-id="4c0a8-286">8/1/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="4c0a8-286">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="4c0a8-287">8/2/2019 12:00:00 AM-07:00</span><span class="sxs-lookup"><span data-stu-id="4c0a8-287">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="4c0a8-288">Una proprietà aggiuntiva da JSON diventa una coppia chiave-valore, con una matrice come oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-288">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="4c0a8-289">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-289">SummaryWords:</span></span><br><span data-ttu-id="4c0a8-290">Comode</span><span class="sxs-lookup"><span data-stu-id="4c0a8-290">Cool</span></span><br><span data-ttu-id="4c0a8-291">Ventoso</span><span class="sxs-lookup"><span data-stu-id="4c0a8-291">Windy</span></span><br><span data-ttu-id="4c0a8-292">Umido</span><span class="sxs-lookup"><span data-stu-id="4c0a8-292">Humid</span></span> |<span data-ttu-id="4c0a8-293">Una proprietà aggiuntiva da JSON diventa una coppia chiave-valore, con una matrice come oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-293">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="4c0a8-294">Quando l'oggetto di destinazione viene serializzato, le coppie chiave-valore dei dati di estensione diventano proprietà JSON esattamente come nel codice JSON in ingresso:</span><span class="sxs-lookup"><span data-stu-id="4c0a8-294">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="4c0a8-295">Si noti che `ExtensionData` il nome della proprietà non viene visualizzato in JSON.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-295">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="4c0a8-296">Questo comportamento consente a JSON di creare un round trip senza perdere dati aggiuntivi che altrimenti non sarebbero deserializzati.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-296">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="use-utf8jsonwriter-directly"></a><span data-ttu-id="4c0a8-297">USA direttamente Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="4c0a8-297">Use Utf8JsonWriter directly</span></span>

<span data-ttu-id="4c0a8-298">Nell'esempio seguente viene illustrato come utilizzare direttamente <xref:System.Text.Json.Utf8JsonWriter> la classe.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-298">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class directly.</span></span>

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

## <a name="use-utf8jsonreader-directly"></a><span data-ttu-id="4c0a8-299">USA direttamente Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="4c0a8-299">Use Utf8JsonReader directly</span></span>

<span data-ttu-id="4c0a8-300">Nell'esempio seguente viene illustrato come utilizzare direttamente <xref:System.Text.Json.Utf8JsonReader> la classe.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-300">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class directly.</span></span> <span data-ttu-id="4c0a8-301">Il codice presuppone che la `jsonUtf8` variabile sia una matrice di byte che contiene JSON valido, codificato come UTF-8.</span><span class="sxs-lookup"><span data-stu-id="4c0a8-301">The code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="4c0a8-302">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4c0a8-302">Additional resources</span></span>

* [<span data-ttu-id="4c0a8-303">Panoramica di System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="4c0a8-303">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="4c0a8-304">Informazioni di riferimento sull'API System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="4c0a8-304">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="4c0a8-305">Supporto di DateTime e DateTimeOffset in System. Text. JSON</span><span class="sxs-lookup"><span data-stu-id="4c0a8-305">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
