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
# <a name="how-to-serialize-json-in-net"></a>Come serializzare JSON in .NET

> [!IMPORTANT]
> La documentazione di serializzazione JSON è in costruzione. Questo articolo non copre tutti gli scenari. Per altre informazioni, esaminare i [problemi di System. Text. JSON](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) nel repository DotNet/CoreFx su GitHub, in particolare quelli con etichetta [JSON-funzionalità-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).

Questo articolo illustra come usare lo <xref:System.Text.Json> spazio dei nomi per serializzare e deserializzare da e verso JavaScript Object Notation (JSON). Le direzioni e il codice di esempio usano la libreria direttamente, non tramite un Framework come [ASP.NET Core](/aspnet/core/).

## <a name="namespaces"></a>Spazi dei nomi

Lo <xref:System.Text.Json> spazio dei nomi contiene tutti i punti di ingresso e i tipi principali. Lo <xref:System.Text.Json.Serialization> spazio dei nomi contiene attributi e API per scenari avanzati e personalizzazione specifici per la serializzazione e la deserializzazione. Gli esempi di codice illustrati in questo articolo richiedono pertanto una o entrambe le direttive seguenti `using` :

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Gli attributi `System.Text.Json`dello spaziodeinominonsono<xref:System.Runtime.Serialization> attualmente supportati in.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Come scrivere oggetti .NET in JSON (Serialize)

Per scrivere JSON in una stringa, chiamare il <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> metodo. Nell'esempio seguente viene usato un overload con un parametro di tipo generico:

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

È possibile omettere il parametro di tipo generico e usare invece l'inferenza del tipo generico:

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize(weatherForecast);
```

Di seguito è riportato un esempio di tipo da serializzare, che contiene le raccolte e le classi annidate:

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

Per impostazione predefinita, l'output JSON è minimizzati: 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

Nell'esempio seguente viene illustrato lo stesso JSON, formattato, ovvero abbastanza stampato con spazi vuoti e rientri:

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

Gli overload di consentono <xref:System.Text.Json.JsonSerializer.Serialize%2A> di eseguire la serializzazione <xref:System.IO.Stream>in un oggetto. Sono disponibili versioni asincrone `Stream` degli overload.

### <a name="serialize-to-utf-8"></a>Serializza in UTF-8

Per serializzare in UTF-8, chiamare <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> il metodo:

```csharp
byte[] utf8Json = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

In alternativa, è disponibile <xref:System.Text.Json.JsonSerializer.Serialize%2A> un overload che accetta <xref:System.Text.Json.Utf8JsonWriter> un oggetto.

La serializzazione in UTF-8 è più veloce del 5-10% rispetto all'uso dei metodi basati su stringa. La differenza è dovuta al fatto che i byte (come UTF-8) non devono essere convertiti in stringhe (UTF-16).

## <a name="serialization-behavior"></a>Comportamento della serializzazione

* Per impostazione predefinita, tutte le proprietà pubbliche vengono serializzate. È possibile [specificare le proprietà da escludere](#exclude-properties).
* Il [codificatore predefinito](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) consente di eseguire l'escape dei caratteri non ASCII, dei caratteri con distinzione HTML nell'intervallo ASCII e dei caratteri che devono essere preceduti da un carattere di escape in base alla [specifica JSON](https://tools.ietf.org/html/rfc8259#section-7).
* Per impostazione predefinita, JSON è minimizzati. È possibile [stampare](#serialize-to-formatted-json)in formato JSON.
* Per impostazione predefinita, le maiuscole e minuscole dei nomi JSON corrispondono ai nomi .NET. È possibile [personalizzare la combinazione di maiuscole e minuscole](#customize-json-names).
* Vengono rilevati riferimenti circolari e vengono generate eccezioni. Per ulteriori informazioni, vedere il [problema relativo ai riferimenti circolari](https://github.com/dotnet/corefx/issues/38579) nel repository DotNet/CoreFx su GitHub.
* Attualmente, i campi vengono esclusi.

I tipi supportati includono:

* Primitive .NET mappate a primitive JavaScript, ad esempio tipi numerici, stringhe e valori booleani.
* [Oggetti CLR obsoleti definiti dall'utente (poco)](https://stackoverflow.com/questions/250001/poco-definition).
* Matrici unidimensionali e irregolari (`ArrayName[][]`).
* `Dictionary<string,TValue>`dove `TValue` è `object` ,`JsonElement`o poco.
* Raccolte dai seguenti spazi dei nomi. Per ulteriori informazioni, vedere il [problema relativo al supporto della raccolta](https://github.com/dotnet/corefx/issues/36643) nel repository DotNet/CoreFx su GitHub.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Come leggere JSON in oggetti .NET (deserializzare)

Per deserializzare da una stringa, chiamare il <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> metodo, come illustrato nell'esempio seguente:

```csharp
string json = ... ;

var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

Per un esempio, vedere la sezione [Serialize](#how-to-write-net-objects-to-json-serialize) . L'oggetto JSON e .NET sono gli stessi, ma la direzione è invertita.

Gli overload di consentono <xref:System.Text.Json.JsonSerializer.Deserialize*> di eseguire la deserializzazione da `Stream`un oggetto.  Sono disponibili versioni asincrone `Stream` degli overload.

### <a name="deserialize-from-utf-8"></a>Deserializzazione da UTF-8

Per deserializzare da UTF-8, chiamare un <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload che accetta un `Utf8JsonReader` oggetto o `ReadOnlySpan<byte>`, come illustrato negli esempi seguenti:

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

## <a name="deserialization-behavior"></a>Comportamento di deserializzazione

* Per impostazione predefinita, la corrispondenza dei nomi di proprietà fa distinzione tra maiuscole e minuscole È possibile specificare la distinzione tra [maiuscole e minuscole](#case-insensitive-property-matching).
* Se il codice JSON contiene un valore per una proprietà di sola lettura, il valore viene ignorato e non viene generata alcuna eccezione.
* La deserializzazione ai tipi di riferimento senza un costruttore senza parametri non è supportata.
* La deserializzazione a oggetti non modificabili o a proprietà di sola lettura non è supportata. Per ulteriori informazioni, vedere il [problema GitHub sul supporto di oggetti non modificabili](https://github.com/dotnet/corefx/issues/38569) e il [problema relativo al supporto delle proprietà di sola lettura](https://github.com/dotnet/corefx/issues/38163) nel repository DotNet/CoreFx su GitHub.
* Per impostazione predefinita, le enumerazioni sono supportate come numeri.
* I campi non sono supportati.
* Per impostazione predefinita, i commenti o le virgole finali in JSON generano eccezioni. Se necessario [, è possibile consentire i commenti e le virgole finali](#allow-comments-and-trailing-commas) .
* La [profondità massima predefinita](xref:System.Text.Json.JsonReaderOptions.MaxDepth) è 64.

## <a name="serialize-to-formatted-json"></a>Serializza nel formato JSON formattato

Per stampare l'output JSON, impostare <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> su: `true`

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Di seguito è riportato un esempio di tipo da serializzare e output JSON:

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

## <a name="allow-comments-and-trailing-commas"></a>Consenti commenti e virgole finali

Per impostazione predefinita, i commenti e le virgole finali non sono consentiti in JSON. Per consentire i commenti in JSON, impostare la <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> proprietà su `JsonCommentHandling.Skip`. Per consentire le virgole finali, impostare la <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> proprietà su. `true` Nell'esempio seguente viene illustrato come consentire entrambi:

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

Di seguito è riportato un esempio JSON con commenti e una virgola finale:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="customize-json-names"></a>Personalizzare i nomi JSON

Per impostazione predefinita, i nomi delle proprietà e le chiavi del dizionario non cambiano nell'output JSON, inclusa la distinzione tra maiuscole e minuscole. Questa sezione illustra come eseguire queste operazioni:

* Personalizzare i singoli nomi di proprietà
* Converte tutti i nomi di proprietà in Camel case
* Implementare i criteri di denominazione delle proprietà personalizzate
* Converte le chiavi del dizionario in lettere maiuscole

Attualmente non è disponibile alcun supporto per la conversione automatica delle enumerazioni in maiuscole e minuscole. Per ulteriori informazioni, vedere il [problema relativo al supporto del case Camel enum](https://github.com/dotnet/corefx/issues/37725) nel repository DotNet/CoreFx su GitHub.

### <a name="customize-individual-property-names"></a>Personalizzare i singoli nomi di proprietà

Per impostare il nome delle singole proprietà, utilizzare l'attributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .

Di seguito è riportato un esempio di tipo da serializzare e JSON risultante:

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

Nome della proprietà impostato dall'attributo:

* Si applica in entrambe le direzioni, per la serializzazione e la deserializzazione.
* Ha la precedenza sui criteri di denominazione delle proprietà.

### <a name="use-camel-case-for-all-json-property-names"></a>Usa il caso Camel per tutti i nomi di proprietà JSON

Per usare il caso Camel per tutti i nomi di proprietà <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> JSON `JsonNamingPolicy.CamelCase`, impostare su, come illustrato nell'esempio seguente:

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Ecco una classe di esempio per serializzare e l'output JSON:

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

Criteri di denominazione delle proprietà Camel case:

* Si applica alla serializzazione e alla deserializzazione.
* Viene sottoposto a `[JsonPropertyName]` override dagli attributi.

### <a name="use-a-custom-json-property-naming-policy"></a>Usare un criterio personalizzato per la denominazione delle proprietà JSON

Per usare un criterio di denominazione delle proprietà JSON personalizzato, creare una classe che derivi <xref:System.Text.Json.JsonNamingPolicy> da ed eseguire <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> l'override del metodo, come illustrato nell'esempio seguente:

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

Impostare quindi la <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> proprietà su un'istanza della classe di criteri di denominazione:

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Ecco una classe di esempio per serializzare e l'output JSON:

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

Criteri di denominazione delle proprietà JSON:

* Si applica alla serializzazione e alla deserializzazione.
* Viene sottoposto a `[JsonPropertyName]` override dagli attributi.

### <a name="camel-case-dictionary-keys"></a>Chiavi del dizionario case Camel

Se una proprietà di un oggetto da serializzare è di tipo `Dictionary<string,TValue>`, le `string` chiavi possono essere convertite in maiuscole/minuscole. A tale scopo, impostare <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> su `JsonNamingPolicy.CamelCase`, come illustrato nell'esempio seguente:

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Di seguito è riportato un esempio di oggetto da serializzare e output JSON:

|Proprietà |Value  |
|---------|---------|
| Date    | 8/1/2019 12:00:00 AM-07:00|
| TemperatureC| 25 |
| Riepilogo| A caldo|
| TemperatureRanges | Freddo, 20<br>Caldo, 40|

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

I criteri di denominazione Camel case si applicano solo alla serializzazione.

## <a name="exclude-properties"></a>Escludi proprietà

Per impostazione predefinita, tutte le proprietà pubbliche vengono serializzate. Se non si vuole che alcuni di essi vengano visualizzati nell'output JSON, sono disponibili diverse opzioni. In questa sezione viene illustrato come escludere:

* Singole proprietà
* Tutte le proprietà di sola lettura
* Tutte le proprietà con valore null 

### <a name="exclude-individual-properties"></a>Escludi singole proprietà

Per ignorare le singole proprietà, utilizzare l'attributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .

Ecco un esempio di tipo per serializzare e l'output JSON:

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

### <a name="exclude-all-read-only-properties"></a>Escludi tutte le proprietà di sola lettura

Per escludere tutte le proprietà <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> di sola lettura, impostare su `true`, come illustrato nell'esempio seguente:

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Ecco un esempio di tipo per serializzare e l'output JSON:

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

Questa opzione si applica solo alla serializzazione. Durante la deserializzazione, le proprietà di sola lettura vengono ignorate per impostazione predefinita. Una proprietà è di sola lettura se contiene un getter pubblico ma non un setter pubblico.

### <a name="exclude-all-null-value-properties"></a>Escludi tutte le proprietà dei valori null

Per escludere tutte le proprietà con valore null <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> , impostare `true`la proprietà su, come illustrato nell'esempio seguente:

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

Di seguito è riportato un esempio di oggetto da serializzare e output JSON:

|Proprietà |Value  |
|---------|---------|
| Date    | 8/1/2019 12:00:00 AM-07:00|
| TemperatureC| 25 |
| Riepilogo| Null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

Questa impostazione si applica alla serializzazione e alla deserializzazione. Durante la deserializzazione, i valori null nel codice JSON vengono ignorati solo se sono validi. I valori null per i tipi di valore non nullable generano eccezioni. Per altre informazioni, vedere il [problema relativo ai tipi di valore non nullable](https://github.com/dotnet/corefx/issues/40922) nel repository DotNet/CoreFx su GitHub.

## <a name="case-insensitive-property-matching"></a>Corrispondenza proprietà senza distinzione tra maiuscole e minuscole

Per impostazione predefinita, la deserializzazione Cerca le corrispondenze tra i nomi delle proprietà con distinzione tra maiuscole e minuscole tra JSON e le proprietà dell'oggetto Per modificare tale comportamento, impostare <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> su: `true`

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

Di seguito è riportato il codice JSON di esempio con i nomi di proprietà Camel case. Può essere deserializzato nel tipo seguente con i nomi di proprietà del case Pascal.

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

## <a name="include-properties-of-derived-classes"></a>Includi proprietà di classi derivate

La serializzazione polimorfica non è supportata quando si specifica in fase di compilazione il tipo da serializzare. Si supponga, ad esempio, di `WeatherForecast` disporre di una classe e `WeatherForecastWithWind`di una classe derivata:

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

E si supponga che il tipo passato a, o dedotto da, `Serialize` il metodo in fase di `WeatherForecast`compilazione sia:

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

```csharp
WeatherForecast weatherForecast;
//...
json = JsonSerializer.Serialize(weatherForecast);
```

In questo scenario, la `WindSpeed` proprietà non viene serializzata anche se l' `weatherForecast` oggetto è effettivamente un `WeatherForecastWithWind` oggetto. Vengono serializzate solo le proprietà della classe base:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

Questo comportamento è volto a impedire l'esposizione accidentale dei dati in un tipo creato dal runtime derivato.

Per serializzare le proprietà del tipo derivato, usare uno degli approcci seguenti:

* Chiamare un overload di <xref:System.Text.Json.JsonSerializer.Serialize%2A> che consente di specificare il tipo in fase di esecuzione:

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* Dichiarare l'oggetto da serializzare come `object`.

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

Nello scenario di esempio precedente, entrambi gli approcci determinano l'inclusione della `WindSpeed` proprietà nell'output JSON:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

## <a name="handle-overflow-json"></a>Gestione JSON di overflow

Durante la deserializzazione, è possibile ricevere dati nel file JSON non rappresentato dalle proprietà del tipo di destinazione. Si supponga, ad esempio, che il tipo di destinazione sia il seguente:

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

Il codice JSON da deserializzare è il seguente:

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

Se si deserializza il codice JSON mostrato nel tipo visualizzato, le `DatesAvailable` proprietà e `SummaryWords` non hanno alcun luogo e andranno perse. Per acquisire dati aggiuntivi, ad esempio queste proprietà, applicare l'attributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una proprietà di `Dictionary<string,object>` tipo `Dictionary<string,JsonElement>`o:

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

Quando si deserializza il codice JSON illustrato in precedenza in questo tipo di esempio, i dati aggiuntivi diventano coppie chiave-valore della `ExtensionData` proprietà:

|Proprietà |Value  |Note  |
|---------|---------|---------|
| Date    | 8/1/2019 12:00:00 AM-07:00||
| TemperatureC| 0 | Mancata corrispondenza tra maiuscole`temperatureC` e minuscole (in JSON), quindi la proprietà non è impostata. |
| Riepilogo | A caldo ||
| ExtensionData | temperatureC: 25 |Poiché il caso non corrisponde, questa proprietà JSON è un oggetto aggiuntivo e diventa una coppia chiave-valore nel dizionario.|
|| DatesAvailable:<br>  8/1/2019 12:00:00 AM-07:00<br>8/2/2019 12:00:00 AM-07:00 |Una proprietà aggiuntiva da JSON diventa una coppia chiave-valore, con una matrice come oggetto valore.|
| |SummaryWords:<br>Comode<br>Ventoso<br>Umido |Una proprietà aggiuntiva da JSON diventa una coppia chiave-valore, con una matrice come oggetto valore.|

Quando l'oggetto di destinazione viene serializzato, le coppie chiave-valore dei dati di estensione diventano proprietà JSON esattamente come nel codice JSON in ingresso:

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

Si noti che `ExtensionData` il nome della proprietà non viene visualizzato in JSON. Questo comportamento consente a JSON di creare un round trip senza perdere dati aggiuntivi che altrimenti non sarebbero deserializzati.

## <a name="use-utf8jsonwriter-directly"></a>USA direttamente Utf8JsonWriter

Nell'esempio seguente viene illustrato come utilizzare direttamente <xref:System.Text.Json.Utf8JsonWriter> la classe.

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

## <a name="use-utf8jsonreader-directly"></a>USA direttamente Utf8JsonReader

Nell'esempio seguente viene illustrato come utilizzare direttamente <xref:System.Text.Json.Utf8JsonReader> la classe. Il codice presuppone che la `jsonUtf8` variabile sia una matrice di byte che contiene JSON valido, codificato come UTF-8.

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

## <a name="additional-resources"></a>Risorse aggiuntive

* [Panoramica di System. Text. JSON](system-text-json-overview.md)
* [Informazioni di riferimento sull'API System. Text. JSON](xref:System.Text.Json)
* [Supporto di DateTime e DateTimeOffset in System. Text. JSON](../datetime/system-text-json-support.md)
