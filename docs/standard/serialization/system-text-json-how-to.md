---
title: Come serializzare e deserializzare JSON con C#-.NET
description: Questo articolo illustra come usare lo System.Text.Json spazio dei nomi per serializzare e deserializzare da JSON in .NET. Include il codice di esempio.
ms.date: 05/13/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 7ad2721f12c5d14b61b35ecf7696ff0d6a6f27da
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289512"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>Come serializzare e deserializzare (effettuare il marshalling e unmarshalling) JSON in .NET

Questo articolo illustra come usare lo <xref:System.Text.Json> spazio dei nomi per serializzare e deserializzare da e verso JavaScript Object Notation (JSON). Se si esegue il porting di codice esistente da `Newtonsoft.Json` , vedere [come eseguire `System.Text.Json` la migrazione a ](system-text-json-migrate-from-newtonsoft-how-to.md).

Le direzioni e il codice di esempio usano la libreria direttamente, non tramite un Framework come [ASP.NET Core](/aspnet/core/).

La maggior parte del codice di esempio di serializzazione imposta <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> su `true` "Pretty-Print" JSON (con rientri e spazi vuoti per la leggibilità umana). Per l'uso in produzione, in genere si accetta il valore predefinito di `false` per questa impostazione.

Gli esempi di codice fanno riferimento alla classe e alle varianti seguenti:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a>Spazi dei nomi

Lo <xref:System.Text.Json> spazio dei nomi contiene tutti i punti di ingresso e i tipi principali. Lo <xref:System.Text.Json.Serialization> spazio dei nomi contiene attributi e API per scenari avanzati e personalizzazione specifici per la serializzazione e la deserializzazione. Gli esempi di codice illustrati in questo articolo richiedono `using` direttive per uno o entrambi gli spazi dei nomi seguenti:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Gli attributi dello <xref:System.Runtime.Serialization> spazio dei nomi non sono attualmente supportati in `System.Text.Json` .

## <a name="how-to-write-net-objects-to-json-serialize"></a>Come scrivere oggetti .NET in JSON (Serialize)

Per scrivere JSON in una stringa o in un file, chiamare il <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> metodo.

Nell'esempio seguente viene creato JSON come stringa:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

Nell'esempio seguente viene usato il codice sincrono per creare un file JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

Nell'esempio seguente viene usato il codice asincrono per creare un file JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

Negli esempi precedenti viene utilizzata l'inferenza del tipo per il tipo da serializzare. Un overload di `Serialize()` accetta un parametro di tipo generico:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a>Esempio di serializzazione

Di seguito è riportato un esempio di classe che contiene le raccolte e una classe annidata:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

L'output JSON della serializzazione di un'istanza del tipo precedente è simile all'esempio seguente. Per impostazione predefinita, l'output JSON è minimizzati:

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

Nell'esempio seguente viene illustrato lo stesso JSON, formattato, ovvero abbastanza stampato con spazi vuoti e rientri:

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

### <a name="serialize-to-utf-8"></a>Serializza in UTF-8

Per serializzare in UTF-8, chiamare il <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> Metodo:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<xref:System.Text.Json.JsonSerializer.Serialize%2A>È disponibile anche un overload che accetta un oggetto <xref:System.Text.Json.Utf8JsonWriter> .

La serializzazione in UTF-8 è più veloce del 5-10% rispetto all'uso dei metodi basati su stringa. La differenza è dovuta al fatto che i byte (come UTF-8) non devono essere convertiti in stringhe (UTF-16).

## <a name="serialization-behavior"></a>Comportamento della serializzazione

* Per impostazione predefinita, tutte le proprietà pubbliche vengono serializzate. È possibile [specificare le proprietà da escludere](#exclude-properties-from-serialization).
* Il [codificatore predefinito](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) consente di eseguire il escape dei caratteri non ASCII, dei caratteri con distinzione HTML all'interno dell'intervallo ASCII e dei caratteri che devono essere preceduti da un carattere di escape in base alla [specifica JSON RFC 8259](https://tools.ietf.org/html/rfc8259#section-7).
* Per impostazione predefinita, JSON è minimizzati. È possibile [stampare](#serialize-to-formatted-json)in formato JSON.
* Per impostazione predefinita, le maiuscole e minuscole dei nomi JSON corrispondono ai nomi .NET. È possibile [personalizzare la combinazione di maiuscole e minuscole](#customize-json-names-and-values).
* Vengono rilevati riferimenti circolari e vengono generate eccezioni.
* Attualmente, i campi vengono esclusi.

I tipi supportati includono:

* Primitive .NET mappate a primitive JavaScript, ad esempio tipi numerici, stringhe e valori booleani.
* [Oggetti CLR obsoleti definiti dall'utente (poco)](https://stackoverflow.com/questions/250001/poco-definition).
* Matrici unidimensionali e irregolari ( `ArrayName[][]` ).
* `Dictionary<string,TValue>`dove `TValue` è `object` , `JsonElement` o poco.
* Raccolte dai seguenti spazi dei nomi.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

È possibile [implementare convertitori personalizzati](system-text-json-converters-how-to.md) per gestire tipi aggiuntivi o per fornire funzionalità non supportate dai convertitori incorporati.

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Come leggere JSON in oggetti .NET (deserializzare)

Per eseguire la deserializzazione da una stringa o da un file, chiamare il <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> metodo.

Nell'esempio seguente viene letto JSON da una stringa e viene creata un'istanza della `WeatherForecast` classe illustrata in precedenza per l' [esempio di serializzazione](#serialization-example):

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

Per eseguire la deserializzazione da un file usando il codice sincrono, leggere il file in una stringa, come illustrato nell'esempio seguente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

Per eseguire la deserializzazione da un file usando il codice asincrono, chiamare il <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> Metodo:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a>Deserializzazione da UTF-8

Per deserializzare da UTF-8, chiamare un <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> Overload che accetta un oggetto `Utf8JsonReader` o `ReadOnlySpan<byte>` , come illustrato negli esempi seguenti. Gli esempi presuppongono che JSON si trovi in una matrice di byte denominata jsonUtf8Bytes.

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a>Comportamento di deserializzazione

* Per impostazione predefinita, la corrispondenza dei nomi di proprietà fa distinzione tra maiuscole e minuscole È possibile specificare la distinzione tra [maiuscole e minuscole](#case-insensitive-property-matching).
* Se il codice JSON contiene un valore per una proprietà di sola lettura, il valore viene ignorato e non viene generata alcuna eccezione.
* La deserializzazione ai tipi di riferimento senza un costruttore senza parametri non è supportata.
* La deserializzazione a oggetti non modificabili o a proprietà di sola lettura non è supportata.
* Per impostazione predefinita, le enumerazioni sono supportate come numeri. È possibile [serializzare i nomi di enumerazione come stringhe](#enums-as-strings).
* I campi non sono supportati.
* Per impostazione predefinita, i commenti o le virgole finali in JSON generano eccezioni. È possibile [consentire i commenti e le virgole finali](#allow-comments-and-trailing-commas).
* La [profondità massima predefinita](xref:System.Text.Json.JsonReaderOptions.MaxDepth) è 64.

È possibile [implementare convertitori personalizzati](system-text-json-converters-how-to.md) per fornire funzionalità non supportate dai convertitori incorporati.

## <a name="serialize-to-formatted-json"></a>Serializza nel formato JSON formattato

Per stampare l'output JSON, impostare <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> su `true` :

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

Di seguito è riportato un esempio di tipo da serializzare e da un output JSON abbastanza stampato:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a>Personalizzare i nomi e i valori JSON

Per impostazione predefinita, i nomi delle proprietà e le chiavi del dizionario non cambiano nell'output JSON, inclusa la distinzione tra maiuscole e minuscole. I valori enum sono rappresentati come numeri. Questa sezione illustra come eseguire queste operazioni:

* [Personalizzare i singoli nomi di proprietà](#customize-individual-property-names)
* [Converte tutti i nomi di proprietà in Camel case](#use-camel-case-for-all-json-property-names)
* [Implementare i criteri di denominazione delle proprietà personalizzate](#use-a-custom-json-property-naming-policy)
* [Converte le chiavi del dizionario in lettere maiuscole](#camel-case-dictionary-keys)
* [Converte le enumerazioni in stringhe e maiuscole](#enums-as-strings)

Per altri scenari che richiedono una gestione speciale dei nomi e dei valori delle proprietà JSON, è possibile [implementare convertitori personalizzati](system-text-json-converters-how-to.md).

### <a name="customize-individual-property-names"></a>Personalizzare i singoli nomi di proprietà

Per impostare il nome delle singole proprietà, utilizzare l'attributo [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) .

Di seguito è riportato un esempio di tipo da serializzare e JSON risultante:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

Nome della proprietà impostato dall'attributo:

* Si applica in entrambe le direzioni, per la serializzazione e la deserializzazione.
* Ha la precedenza sui criteri di denominazione delle proprietà.

### <a name="use-camel-case-for-all-json-property-names"></a>Usa il caso Camel per tutti i nomi di proprietà JSON

Per usare il caso Camel per tutti i nomi di proprietà JSON, impostare <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> su `JsonNamingPolicy.CamelCase` , come illustrato nell'esempio seguente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

Ecco una classe di esempio per serializzare e l'output JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

Criteri di denominazione delle proprietà Camel case:

* Si applica alla serializzazione e alla deserializzazione.
* Viene sottoposto a override dagli `[JsonPropertyName]` attributi. Questo è il motivo per cui il nome della proprietà JSON `Wind` nell'esempio non è un case Camel.

### <a name="use-a-custom-json-property-naming-policy"></a>Usare un criterio personalizzato per la denominazione delle proprietà JSON

Per usare un criterio di denominazione delle proprietà JSON personalizzato, creare una classe che derivi da <xref:System.Text.Json.JsonNamingPolicy> ed eseguire l'override del <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> metodo, come illustrato nell'esempio seguente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

Impostare quindi la <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> proprietà su un'istanza della classe di criteri di denominazione:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

Ecco una classe di esempio per serializzare e l'output JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

Criteri di denominazione delle proprietà JSON:

* Si applica alla serializzazione e alla deserializzazione.
* Viene sottoposto a override dagli `[JsonPropertyName]` attributi. Questo è il motivo per cui il nome della proprietà JSON `Wind` nell'esempio non è maiuscolo.

### <a name="camel-case-dictionary-keys"></a>Chiavi del dizionario case Camel

Se una proprietà di un oggetto da serializzare è di tipo `Dictionary<string,TValue>` , le `string` chiavi possono essere convertite in maiuscole/minuscole. A tale scopo, impostare <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> su `JsonNamingPolicy.CamelCase` , come illustrato nell'esempio seguente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

La serializzazione di un oggetto con un dizionario denominato `TemperatureRanges` che include coppie chiave-valore `"ColdMinTemp", 20` e `"HotMinTemp", 40` genera output JSON come l'esempio seguente:

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

I criteri di denominazione Camel case per le chiavi del dizionario si applicano solo alla serializzazione. Se si deserializza un dizionario, le chiavi corrisponderanno al file JSON anche se si specifica `JsonNamingPolicy.CamelCase` per il `DictionaryKeyPolicy` .

### <a name="enums-as-strings"></a>Enumerazioni come stringhe

Per impostazione predefinita, le enumerazioni vengono serializzate come numeri. Per serializzare i nomi di enumerazione come stringhe, usare <xref:System.Text.Json.Serialization.JsonStringEnumConverter> .

Si supponga, ad esempio, di dover serializzare la classe seguente che contiene un'enumerazione:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

Se il riepilogo è `Hot` , per impostazione predefinita il JSON serializzato ha il valore numerico 3:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

Il codice di esempio seguente serializza i nomi di enumerazione invece dei valori numerici e converte i nomi in lettere maiuscole:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

Il codice JSON risultante è simile all'esempio seguente:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

È anche possibile deserializzare i nomi di stringa enum, come illustrato nell'esempio seguente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a>Escludi proprietà dalla serializzazione

Per impostazione predefinita, tutte le proprietà pubbliche vengono serializzate. Se non si vuole che alcuni di essi vengano visualizzati nell'output JSON, sono disponibili diverse opzioni. In questa sezione viene illustrato come escludere:

* [Singole proprietà](#exclude-individual-properties)
* [Tutte le proprietà di sola lettura](#exclude-all-read-only-properties)
* [Tutte le proprietà con valore null](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a>Escludi singole proprietà

Per ignorare le singole proprietà, utilizzare l'attributo [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) .

Ecco un esempio di tipo per serializzare e l'output JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a>Escludi tutte le proprietà di sola lettura

Una proprietà è di sola lettura se contiene un getter pubblico ma non un setter pubblico. Per escludere tutte le proprietà di sola lettura, impostare <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> su `true` , come illustrato nell'esempio seguente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

Ecco un esempio di tipo per serializzare e l'output JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Questa opzione si applica solo alla serializzazione. Durante la deserializzazione, le proprietà di sola lettura vengono ignorate per impostazione predefinita.

### <a name="exclude-all-null-value-properties"></a>Escludi tutte le proprietà dei valori null

Per escludere tutte le proprietà con valore null, impostare la <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> proprietà su `true` , come illustrato nell'esempio seguente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

Di seguito è riportato un esempio di oggetto da serializzare e output JSON:

|Proprietà |Valore  |
|---------|---------|
| Data    | 8/1/2019 12:00:00 AM-07:00|
| TemperatureCelsius| 25 |
| Riepilogo| Null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

Questa impostazione si applica alla serializzazione e alla deserializzazione. Per informazioni sugli effetti sulla deserializzazione, vedere [Ignore null durante la deserializzazione](#ignore-null-when-deserializing).

## <a name="customize-character-encoding"></a>Personalizzare la codifica caratteri

Per impostazione predefinita, il serializzatore viene sottoposto a escape per tutti i caratteri non ASCII.  Ovvero, li sostituisce con `\uxxxx` Where `xxxx` è il codice Unicode del carattere.  Se, ad esempio, la `Summary` proprietà è impostata su cirillico жарко, l' `WeatherForecast` oggetto viene serializzato come illustrato nell'esempio seguente:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>Serializza i set di caratteri della lingua

Per serializzare i set di caratteri di una o più lingue senza eseguire l'escape, specificare gli [intervalli Unicode](xref:System.Text.Unicode.UnicodeRanges) durante la creazione di un'istanza di <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> , come illustrato nell'esempio seguente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

Questo codice non esegue l'escape di caratteri cirillici o greci. Se la `Summary` proprietà è impostata su cirillico жарко, l' `WeatherForecast` oggetto viene serializzato come illustrato nell'esempio seguente:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Per serializzare tutti i set di lingue senza escape, usare <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType> .

### <a name="serialize-specific-characters"></a>Serializza caratteri specifici

In alternativa, è possibile specificare i singoli caratteri che si desidera consentire tramite senza che venga eseguito il escape. Nell'esempio seguente vengono serializzati solo i primi due caratteri di жарко:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

Di seguito è riportato un esempio di JSON prodotto dal codice precedente:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>Serializza tutti i caratteri

Per ridurre al minimo l'escape, è possibile usare <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType> , come illustrato nell'esempio seguente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> Rispetto al codificatore predefinito, il `UnsafeRelaxedJsonEscaping` codificatore è più permissivo per consentire il pass-through senza caratteri di escape:
>
> * Non esegue l'escape di caratteri con distinzione HTML come `<` ,, `>` `&` e `'` .
> * Non offre protezioni aggiuntive per la difesa in profondità da attacchi XSS o divulgazione di informazioni, ad esempio quelli che potrebbero risultare dal client e dal server che non accettano il *set di caratteri*.
>
> Usare il codificatore unsafe solo quando è noto che il client interpreterà il payload risultante come JSON con codifica UTF-8. Ad esempio, è possibile usarlo se il server sta inviando l'intestazione della risposta `Content-Type: application/json; charset=utf-8` . Non consentire mai l' `UnsafeRelaxedJsonEscaping` emissione dell'output non elaborato in una pagina HTML o in un `<script>` elemento.

## <a name="serialize-properties-of-derived-classes"></a>Serializzare le proprietà delle classi derivate

La serializzazione di una gerarchia di tipi polimorfici non è supportata. Se, ad esempio, una proprietà è definita come interfaccia o classe astratta, verranno serializzate solo le proprietà definite nell'interfaccia o nella classe astratta, anche se il tipo di runtime dispone di proprietà aggiuntive. Le eccezioni a questo comportamento sono illustrate in questa sezione.

Si supponga, ad esempio, di disporre di una `WeatherForecast` classe e di una classe derivata `WeatherForecastDerived` :

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

E si supponga che l'argomento di tipo del `Serialize` metodo in fase di compilazione sia `WeatherForecast` :

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

In questo scenario, la `WindSpeed` proprietà non viene serializzata anche se l' `weatherForecast` oggetto è effettivamente un `WeatherForecastDerived` oggetto. Vengono serializzate solo le proprietà della classe base:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Questo comportamento è volto a impedire l'esposizione accidentale dei dati in un tipo creato dal runtime derivato.

Per serializzare le proprietà del tipo derivato nell'esempio precedente, usare uno degli approcci seguenti:

* Chiamare un overload di <xref:System.Text.Json.JsonSerializer.Serialize%2A> che consente di specificare il tipo in fase di esecuzione:

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* Dichiarare l'oggetto da serializzare come `object` .

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

Nello scenario di esempio precedente, entrambi gli approcci determinano l' `WindSpeed` inclusione della proprietà nell'output JSON:

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> Questi approcci forniscono la serializzazione polimorfica solo per l'oggetto radice da serializzare, non per le proprietà dell'oggetto radice.

È possibile ottenere la serializzazione polimorfica per gli oggetti di livello inferiore se vengono definiti come tipo `object` . Si supponga, ad esempio, `WeatherForecast` che la classe disponga di una proprietà denominata `PreviousForecast` che può essere definita come Type `WeatherForecast` o `object` :

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

Se la `PreviousForecast` proprietà contiene un'istanza di `WeatherForecastDerived` :

* L'output JSON della serializzazione `WeatherForecastWithPrevious` **non include** `WindSpeed` .
* L'output JSON della serializzazione `WeatherForecastWithPreviousAsObject` **include** `WindSpeed` .

Per serializzare, non è `WeatherForecastWithPreviousAsObject` necessario chiamare `Serialize<object>` o `GetType` perché l'oggetto radice non è quello che può essere di un tipo derivato. L'esempio di codice seguente non chiama `Serialize<object>` o `GetType` :

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

Il codice precedente serializza correttamente `WeatherForecastWithPreviousAsObject` :

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

Lo stesso approccio per la definizione delle proprietà `object` funziona con le interfacce. Si supponga di avere l'interfaccia e l'implementazione seguenti e di voler serializzare una classe con proprietà che contengono istanze di implementazione:

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

Quando si serializza un'istanza di `Forecasts` , `Tuesday` Mostra solo la `WindSpeed` proprietà, perché `Tuesday` è definita come `object` :

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

Nell'esempio seguente viene illustrato il codice JSON risultante dal codice precedente:

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

Per ulteriori informazioni sulla **serializzazione**polimorfica e per informazioni sulla **deserializzazione**, vedere [come eseguire la migrazione da Newtonsoft.Json a System.Text.Json ](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).

## <a name="allow-comments-and-trailing-commas"></a>Consenti commenti e virgole finali

Per impostazione predefinita, i commenti e le virgole finali non sono consentiti in JSON. Per consentire i commenti in JSON, impostare la <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> proprietà su `JsonCommentHandling.Skip` .
Per consentire le virgole finali, impostare la <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> proprietà su `true` . Nell'esempio seguente viene illustrato come consentire entrambi:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

Di seguito è riportato un esempio JSON con commenti e una virgola finale:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a>Corrispondenza proprietà senza distinzione tra maiuscole e minuscole

Per impostazione predefinita, la deserializzazione Cerca le corrispondenze tra i nomi delle proprietà con distinzione tra maiuscole e minuscole tra JSON e le proprietà dell'oggetto Per modificare tale comportamento, impostare <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> su `true` :

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

Di seguito è riportato il codice JSON di esempio con i nomi di proprietà Camel case. Può essere deserializzato nel tipo seguente con i nomi di proprietà del case Pascal.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a>Gestione JSON di overflow

Durante la deserializzazione, è possibile ricevere dati nel file JSON non rappresentato dalle proprietà del tipo di destinazione. Si supponga, ad esempio, che il tipo di destinazione sia il seguente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

Il codice JSON da deserializzare è il seguente:

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

Se si deserializza il codice JSON mostrato nel tipo visualizzato, le `DatesAvailable` proprietà e non `SummaryWords` hanno alcun luogo e andranno perse. Per acquisire dati aggiuntivi, ad esempio queste proprietà, applicare l'attributo [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) a una proprietà di tipo `Dictionary<string,object>` o `Dictionary<string,JsonElement>` :

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

Quando si deserializza il codice JSON illustrato in precedenza in questo tipo di esempio, i dati aggiuntivi diventano coppie chiave-valore della `ExtensionData` proprietà:

|Proprietà |Valore  |Note  |
|---------|---------|---------|
| Data    | 8/1/2019 12:00:00 AM-07:00||
| TemperatureCelsius| 0 | Mancata corrispondenza tra maiuscole e minuscole ( `temperatureCelsius` in JSON), quindi la proprietà non è impostata. |
| Riepilogo | Accesso frequente ||
| ExtensionData | temperatureCelsius: 25 |Poiché il caso non corrisponde, questa proprietà JSON è un oggetto aggiuntivo e diventa una coppia chiave-valore nel dizionario.|
|| DatesAvailable:<br>  8/1/2019 12:00:00 AM-07:00<br>8/2/2019 12:00:00 AM-07:00 |Una proprietà aggiuntiva da JSON diventa una coppia chiave-valore, con una matrice come oggetto valore.|
| |SummaryWords:<br>Accesso sporadico<br>Ventoso<br>Umido |Una proprietà aggiuntiva da JSON diventa una coppia chiave-valore, con una matrice come oggetto valore.|

Quando l'oggetto di destinazione viene serializzato, le coppie chiave-valore dei dati di estensione diventano proprietà JSON esattamente come nel codice JSON in ingresso:

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

Si noti che il `ExtensionData` nome della proprietà non viene visualizzato in JSON. Questo comportamento consente a JSON di creare un round trip senza perdere dati aggiuntivi che altrimenti non sarebbero deserializzati.

## <a name="ignore-null-when-deserializing"></a>Ignora null durante la deserializzazione

Per impostazione predefinita, se una proprietà in JSON è null, la proprietà corrispondente nell'oggetto di destinazione viene impostata su null. In alcuni scenari, la proprietà di destinazione potrebbe avere un valore predefinito e non si vuole che un valore null esegua l'override del valore predefinito.

Si supponga, ad esempio, che il codice seguente rappresenti l'oggetto di destinazione:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Si supponga che venga deserializzato il codice JSON seguente:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Dopo la deserializzazione, la `Summary` proprietà dell' `WeatherForecastWithDefault` oggetto è null.

Per modificare questo comportamento, impostare <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> su `true` , come illustrato nell'esempio seguente:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

Con questa opzione, la `Summary` proprietà dell' `WeatherForecastWithDefault` oggetto è il valore predefinito "nessun riepilogo" dopo la deserializzazione.

I valori null nel codice JSON vengono ignorati solo se sono validi. I valori null per i tipi di valore non nullable generano eccezioni.

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>Utf8JsonReader, Utf8JsonWriter e JsonDocument

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>è un reader ad alte prestazioni, a bassa allocazione e di solo invio per testo JSON con codifica UTF-8, letto da `ReadOnlySpan<byte>` o `ReadOnlySequence<byte>` . `Utf8JsonReader`È un tipo di basso livello che può essere utilizzato per compilare parser e deserializzatori personalizzati. Il <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> metodo usa `Utf8JsonReader` dietro le quinte.

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>è un modo a prestazioni elevate per scrivere testo JSON con codifica UTF-8 da tipi .NET comuni come `String` , `Int32` e `DateTime` . Il writer è un tipo di basso livello che può essere utilizzato per compilare serializzatori personalizzati. Il <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> metodo usa `Utf8JsonWriter` dietro le quinte.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName>fornisce la possibilità di compilare un Document Object Model di sola lettura (DOM) utilizzando `Utf8JsonReader` . Il DOM fornisce l'accesso casuale ai dati in un payload JSON. È possibile accedere agli elementi JSON che compongono il payload tramite il <xref:System.Text.Json.JsonElement> tipo. Il `JsonElement` tipo fornisce enumeratori di oggetti e matrici insieme alle API per convertire il testo JSON in tipi .NET comuni. `JsonDocument`espone una <xref:System.Text.Json.JsonDocument.RootElement> Proprietà.

Le sezioni seguenti illustrano come usare questi strumenti per la lettura e la scrittura di JSON.

## <a name="use-jsondocument-for-access-to-data"></a>Usare JsonDocument per l'accesso ai dati

Nell'esempio seguente viene illustrato come utilizzare la <xref:System.Text.Json.JsonDocument> classe per l'accesso casuale ai dati in una stringa JSON:

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

Il codice precedente:

* Presuppone che il codice JSON da analizzare si trovi in una stringa denominata `jsonString` .
* Calcola un livello medio per gli oggetti in una `Students` matrice che dispongono di una `Grade` Proprietà.
* Assegna un livello predefinito di 70 per gli studenti che non hanno un livello.
* Conta gli studenti incrementando una `count` variabile a ogni iterazione. <xref:System.Text.Json.JsonElement.GetArrayLength%2A>In alternativa, è possibile chiamare, come illustrato nell'esempio seguente:

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

Di seguito è riportato un esempio del codice JSON elaborato da questo codice:

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a>Usare JsonDocument per scrivere JSON

Nell'esempio seguente viene illustrato come scrivere JSON da un oggetto <xref:System.Text.Json.JsonDocument> :

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

Il codice precedente:

* Legge un file JSON, carica i dati in un oggetto `JsonDocument` e scrive JSON formattato (abbastanza stampato) in un file.
* USA <xref:System.Text.Json.JsonDocumentOptions> per specificare che i commenti nel codice JSON di input sono consentiti ma ignorati.
* Al termine, chiama <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> sul writer. In alternativa, è possibile lasciare che il writer AutoFlush quando viene eliminato.

Di seguito è riportato un esempio di input JSON che verrà elaborato dal codice di esempio:

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

Il risultato è l'output JSON abbastanza stampato seguente:

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a>Usare Utf8JsonWriter

Nell'esempio seguente viene illustrato come utilizzare la <xref:System.Text.Json.Utf8JsonWriter> classe:

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a>Usare Utf8JsonReader

Nell'esempio seguente viene illustrato come utilizzare la <xref:System.Text.Json.Utf8JsonReader> classe:

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

Il codice precedente presuppone che la `jsonUtf8` variabile sia una matrice di byte che contiene JSON valido, codificato come UTF-8.

### <a name="filter-data-using-utf8jsonreader"></a>Filtrare i dati tramite Utf8JsonReader

Nell'esempio seguente viene illustrato come leggere un file in modo sincrono e cercare un valore:

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

Il codice precedente:

* Presuppone che JSON contenga una matrice di oggetti e che ogni oggetto possa contenere una proprietà "Name" di tipo String.
* Conta gli oggetti e i valori della proprietà "Name" che terminano con "University".
* Presuppone che il file sia codificato come UTF-16 e lo transcodifichi in UTF-8. Un file codificato come UTF-8 può essere letto direttamente in `ReadOnlySpan<byte>` , usando il codice seguente:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  Se il file contiene un byte order mark UTF-8 (BOM), rimuoverlo prima di passare i byte a `Utf8JsonReader` , perché il Reader prevede il testo. In caso contrario, l'indicatore dell'ordine dei byte viene considerato JSON non valido e il lettore genera un'eccezione.

Di seguito è riportato un esempio JSON che il codice precedente può leggere. Il messaggio di riepilogo risultante è "2 su 4 hanno nomi che terminano con" University "":

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a>Leggere da un flusso usando Utf8JsonReader

Quando si legge un file di grandi dimensioni (ad esempio, un gigabyte o più), è consigliabile evitare di caricare l'intero file in memoria contemporaneamente. Per questo scenario, è possibile usare un <xref:System.IO.FileStream> .

Quando si usa `Utf8JsonReader` per leggere da un flusso, si applicano le regole seguenti:

* Il buffer che contiene il payload JSON parziale deve essere almeno uguale al token JSON più grande al suo interno, in modo che il lettore possa procedere.
* Il buffer deve avere una dimensione minima pari alla sequenza più grande di spazi vuoti all'interno di JSON.
* Il lettore non tiene traccia dei dati letti fino a quando non legge completamente il successivo <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> nel payload JSON. Quindi, quando ci sono byte rimasti nel buffer, è necessario passarli nuovamente al lettore. È possibile utilizzare <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> per determinare il numero di byte rimanenti.

Il codice seguente illustra come leggere da un flusso. Nell'esempio viene illustrato un oggetto <xref:System.IO.MemoryStream> . Il codice simile funzionerà con un oggetto <xref:System.IO.FileStream> , tranne quando l'oggetto `FileStream` contiene un BOM UTF-8 all'inizio. In tal caso, è necessario rimuovere questi tre byte dal buffer prima di passare i byte rimanenti a `Utf8JsonReader` . In caso contrario, il lettore genererebbe un'eccezione poiché l'indicatore BOM non è considerato una parte valida di JSON.

Il codice di esempio inizia con un buffer 4KB e raddoppia le dimensioni del buffer ogni volta che rileva che le dimensioni non sono sufficientemente grandi per adattarsi a un token JSON completo, che è necessario per consentire al lettore di avanzare sul payload JSON. L'esempio JSON fornito nel frammento di codice attiva un aumento delle dimensioni del buffer solo se si imposta una dimensione del buffer iniziale molto piccola, ad esempio 10 byte. Se si imposta la dimensione del buffer iniziale su 10, le `Console.WriteLine` istruzioni illustrano la provocazione e l'effetto della dimensione del buffer. Alla dimensione del buffer iniziale 4KB, l'intero codice JSON di esempio viene visualizzato da ciascuno `Console.WriteLine` e le dimensioni del buffer non devono mai essere aumentate.

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

Nell'esempio precedente non viene impostato alcun limite per le dimensioni del buffer. Se la dimensione del token è troppo grande, il codice potrebbe avere esito negativo con un' <xref:System.OutOfMemoryException> eccezione. Questo problema può verificarsi se il file JSON contiene un token di circa 1 GB o più dimensioni, perché il raddoppio delle dimensioni di 1 GB comporta una dimensione troppo grande per adattarsi a un `int32` buffer.

## <a name="additional-resources"></a>Risorse aggiuntive

* [System.Text.JsonPanoramica](system-text-json-overview.md)
* [Come scrivere convertitori personalizzati](system-text-json-converters-how-to.md)
* [Come eseguire la migrazione daNewtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Supporto di DateTime e DateTimeOffset inSystem.Text.Json](../datetime/system-text-json-support.md)
* [System.Text.JsonRiferimento API](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
