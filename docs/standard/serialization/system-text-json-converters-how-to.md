---
title: Come scrivere convertitori personalizzati per la serializzazione JSON-.NET
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 0f8b89ec7d7b1677de085631958b888e154aa4fa
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116718"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a>Come scrivere convertitori personalizzati per la serializzazione JSON (marshalling) in .NET

Questo articolo illustra come creare convertitori personalizzati per le classi di serializzazione JSON fornite nello spazio dei nomi <xref:System.Text.Json>. Per un'introduzione ai `System.Text.Json`, vedere [come serializzare e deserializzare JSON in .NET](system-text-json-how-to.md).

Un *convertitore* è una classe che converte un oggetto o un valore in e da JSON. Lo spazio dei nomi `System.Text.Json` dispone di convertitori predefiniti per la maggior parte dei tipi primitivi con mapping alle primitive JavaScript. È possibile scrivere convertitori personalizzati:

* Per eseguire l'override del comportamento predefinito di un convertitore incorporato. È ad esempio possibile che si desideri che i valori `DateTime` siano rappresentati dal formato mm/gg/aaaa anziché dal formato ISO 8601-1:2019 predefinito.
* Per supportare un tipo di valore personalizzato. Ad esempio, uno struct `PhoneNumber`.

È anche possibile scrivere convertitori personalizzati per personalizzare o estendere `System.Text.Json` con funzionalità non incluse nella versione corrente. Gli scenari seguenti sono trattati più avanti in questo articolo:

* [Deserializzare i tipi dedotti nelle proprietà dell'oggetto](#deserialize-inferred-types-to-object-properties).
* [Dizionario di supporto con chiave non di stringa](#support-dictionary-with-non-string-key).
* [Supporta la deserializzazione polimorfica](#support-polymorphic-deserialization).

## <a name="custom-converter-patterns"></a>Modelli di convertitore personalizzati

Per la creazione di un convertitore personalizzato sono disponibili due modelli: il modello di base e il modello di Factory. Il modello Factory è per i convertitori che gestiscono il tipo `Enum` o i generics aperti. Il modello di base è per i tipi generici non generici e chiusi.  I convertitori per i tipi seguenti, ad esempio, richiedono il modello Factory:

* `Dictionary<TKey, TValue>`
* `Enum`
* `List<T>`

Di seguito sono riportati alcuni esempi di tipi che possono essere gestiti tramite il modello di base:

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* `DateTime`
* `Int32`

Il modello di base crea una classe in grado di gestire un tipo. Il modello factory crea una classe che determina in fase di esecuzione quale tipo specifico è obbligatorio e crea dinamicamente il convertitore appropriato.

## <a name="sample-basic-converter"></a>Convertitore di base di esempio

L'esempio seguente è un convertitore che esegue l'override della serializzazione predefinita per un tipo di dati esistente. Il convertitore usa il formato mm/gg/aaaa per le proprietà `DateTimeOffset`.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetConverter.cs)]

## <a name="sample-factory-pattern-converter"></a>Convertitore di modelli Factory di esempio

Il codice seguente illustra un convertitore personalizzato che funziona con `Dictionary<Enum,TValue>`. Il codice segue il modello Factory perché il primo parametro di tipo generico è `Enum` e il secondo è aperto. Il metodo `CanConvert` restituisce `true` solo per un `Dictionary` con due parametri generici, il primo dei quali è un tipo `Enum`. Il convertitore interno ottiene un convertitore esistente per gestire qualsiasi tipo fornito in fase di esecuzione per `TValue`. 

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

Il codice precedente è identico a quello visualizzato nel [dizionario di supporto con chiave non stringa](#support-dictionary-with-non-string-key) più avanti in questo articolo.

## <a name="steps-to-follow-the-basic-pattern"></a>Passaggi per seguire il modello di base

Nei passaggi seguenti viene illustrato come creare un convertitore seguendo il modello di base:

* Creare una classe che deriva da <xref:System.Text.Json.Serialization.JsonConverter%601> dove `T` è il tipo da serializzare e deserializzare.
* Eseguire l'override del metodo `Read` per deserializzare il codice JSON in ingresso e convertirlo nel tipo `T`. Usare il <xref:System.Text.Json.Utf8JsonReader> passato al metodo per leggere il file JSON.
* Eseguire l'override del metodo `Write` per serializzare l'oggetto in ingresso di tipo `T`. Usare il <xref:System.Text.Json.Utf8JsonWriter> passato al metodo per scrivere il codice JSON.
* Eseguire l'override del metodo `CanConvert` solo se necessario. L'implementazione predefinita restituisce `true` quando il tipo da convertire è di tipo `T`. Pertanto, i convertitori che supportano solo il tipo `T` non devono eseguire l'override di questo metodo. Per un esempio di convertitore che deve eseguire l'override di questo metodo, vedere la sezione relativa alla [deserializzazione polimorfica](#support-polymorphic-deserialization) più avanti in questo articolo.

È possibile fare riferimento al [codice sorgente dei convertitori predefiniti](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/) come implementazioni di riferimento per la scrittura di convertitori personalizzati.

## <a name="steps-to-follow-the-factory-pattern"></a>Passaggi per seguire il modello Factory

Nei passaggi seguenti viene illustrato come creare un convertitore seguendo il modello Factory:

* Creare una classe che deriva da <xref:System.Text.Json.Serialization.JsonConverterFactory>.
* Eseguire l'override del metodo `CanConvert` per restituire true quando il tipo da convertire è quello che può essere gestito dal convertitore. Ad esempio, se il convertitore è per `List<T>` potrebbe gestire solo `List<int>`, `List<string>`e `List<DateTime>`. 
* Eseguire l'override del metodo `CreateConverter` per restituire un'istanza di una classe Converter che gestirà il tipo da convertire fornito in fase di esecuzione.
* Creare la classe del convertitore di cui il metodo `CreateConverter` crea un'istanza. 

Il modello Factory è obbligatorio per i generics aperti perché il codice per convertire un oggetto in e da una stringa non è lo stesso per tutti i tipi. Un convertitore per un tipo generico aperto (ad esempio`List<T>`) deve creare un convertitore per un tipo generico chiuso (ad esempio,`List<DateTime>`) dietro le quinte. Il codice deve essere scritto in modo da gestire ogni tipo generico chiuso che il convertitore è in grado di gestire.

Il tipo di `Enum` è simile a un tipo generico aperto: un convertitore per `Enum` deve creare un convertitore per un `Enum` specifico (ad esempio,`WeekdaysEnum`) dietro le quinte. 

## <a name="error-handling"></a>Gestione degli errori

Se è necessario generare un'eccezione nel codice di gestione degli errori, provare a generare un <xref:System.Text.Json.JsonException> senza un messaggio. Questo tipo di eccezione crea automaticamente un messaggio che include il percorso della parte di JSON che ha causato l'errore. Ad esempio, l'istruzione `throw new JsonException();` genera un messaggio di errore simile all'esempio seguente:

```
Unhandled exception. System.Text.Json.JsonException: 
The JSON value could not be converted to System.Object. 
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

Se si fornisce un messaggio, ad esempio `throw new JsonException("Error occurred")`, l'eccezione fornisce ancora il percorso nella proprietà <xref:System.Text.Json.JsonException.Path>.

## <a name="register-a-custom-converter"></a>Registrare un convertitore personalizzato

*Registrare* un convertitore personalizzato per fare in modo che i metodi `Serialize` e `Deserialize` lo usino. Scegliere uno degli approcci seguenti:

* Aggiungere un'istanza della classe Converter alla raccolta <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType>.
* Applicare l'attributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) alle proprietà che richiedono il convertitore personalizzato.
* Applicare l'attributo [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) a una classe o a uno struct che rappresenta un tipo di valore personalizzato.

## <a name="registration-sample---converters-collection"></a>Esempio di registrazione-raccolta Converters 

Di seguito è riportato un esempio che rende il <xref:System.ComponentModel.DateTimeOffsetConverter> il valore predefinito per le proprietà di tipo <xref:System.DateTimeOffset>:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetSerialize)]

Si supponga di serializzare un'istanza del tipo seguente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Di seguito è riportato un esempio di output JSON che mostra il convertitore personalizzato usato:

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Il codice seguente usa lo stesso approccio per deserializzare usando il convertitore di `DateTimeOffset` personalizzato:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithConvertersCollection.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-property"></a>Esempio di registrazione-[JsonConverter] in una proprietà

Il codice seguente consente di selezionare un convertitore personalizzato per la proprietà `Date`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithConverterAttribute)]

Il codice per serializzare `WeatherForecastWithConverterAttribute` non richiede l'uso di `JsonSerializeOptions.Converters`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetSerialize)]

Anche il codice da deserializzare non richiede l'uso di `Converters`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RegisterConverterWithAttributeOnProperty.cs?name=SnippetDeserialize)]

## <a name="registration-sample---jsonconverter-on-a-type"></a>Esempio di registrazione-[JsonConverter] in un tipo

Di seguito è riportato il codice che consente di creare uno struct e di applicare l'attributo `[JsonConverter]`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Temperature.cs)]

Ecco il convertitore personalizzato per lo struct precedente:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/TemperatureConverter.cs)]

L'attributo `[JsonConvert]` nello struct registra il convertitore personalizzato come valore predefinito per le proprietà di tipo `Temperature`. Il convertitore viene usato automaticamente nella proprietà `TemperatureCelsius` del tipo seguente quando viene serializzato o deserializzato:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithTemperatureStruct)]

## <a name="converter-registration-precedence"></a>Precedenza di registrazione del convertitore

Durante la serializzazione o la deserializzazione, viene scelto un convertitore per ogni elemento JSON nell'ordine seguente, elencato dalla priorità più alta a quella più bassa:

* `[JsonConverter]` applicato a una proprietà.
* Convertitore aggiunto alla raccolta di `Converters`.
* `[JsonConverter]` applicato a un tipo di valore personalizzato o POCO.

Se nella raccolta `Converters` vengono registrati più convertitori personalizzati per un tipo, viene utilizzato il primo convertitore che restituisce true per `CanConvert`.

Un convertitore predefinito viene scelto solo se non è registrato alcun convertitore personalizzato applicabile.

## <a name="converter-samples-for-common-scenarios"></a>Esempi di convertitore per scenari comuni

Le sezioni seguenti forniscono esempi di convertitore che affrontano alcuni scenari comuni non gestiti dalla funzionalità incorporata.

* [Deserializzare i tipi dedotti nelle proprietà dell'oggetto](#deserialize-inferred-types-to-object-properties)
* [Dizionario di supporto con chiave non di stringa](#support-dictionary-with-non-string-key)
* [Supportare la deserializzazione polimorfica](#support-polymorphic-deserialization)

### <a name="deserialize-inferred-types-to-object-properties"></a>Deserializzare i tipi dedotti nelle proprietà dell'oggetto

Quando si esegue la deserializzazione in una proprietà di tipo `object`, viene creato un oggetto `JsonElement`. Il motivo è che il deserializzatore non conosce il tipo CLR da creare e non tenta di indovinare. Se, ad esempio, una proprietà JSON ha "true", il deserializzatore non deduce che il valore è un `Boolean`e se un elemento ha "01/01/2019", il deserializzatore non deduce che si tratta di un `DateTime`.

L'inferenza del tipo può non essere corretta. Se il deserializzatore analizza un numero JSON senza separatore decimale come `long`, ciò potrebbe causare problemi fuori intervallo se il valore è stato serializzato originariamente come `ulong` o `BigInteger`. L'analisi di un numero con un separatore decimale come `double` potrebbe perdere precisione se il numero è stato originariamente serializzato come `decimal`.

Per gli scenari che richiedono l'inferenza del tipo, nel codice seguente viene illustrato un convertitore personalizzato per `object` proprietà. Il codice esegue la conversione:

* `true` e `false` per `Boolean`
* Numeri senza decimali da `long`
* Numeri con un numero decimale da `double`
* Data di `DateTime`
* Stringhe da `string`
* Tutti gli altri elementi da `JsonElement`

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ObjectToInferredTypesConverter.cs)]

Il codice seguente registra il convertitore:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeInferredTypesToObject.cs?name=SnippetRegister)]

Di seguito è riportato un esempio di tipo con proprietà `object`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithObjectProperties)]

L'esempio seguente di JSON da deserializzare contiene valori che verranno deserializzati come `DateTime`, `long`e `string`:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Senza il convertitore personalizzato, la deserializzazione inserisce una `JsonElement` in ogni proprietà.

La [cartella unit test](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) nello spazio dei nomi `System.Text.Json.Serialization` contiene altri esempi di convertitori personalizzati che gestiscono la deserializzazione per `object` proprietà.

### <a name="support-dictionary-with-non-string-key"></a>Dizionario di supporto con chiave non di stringa

Il supporto incorporato per le raccolte di dizionari è per `Dictionary<string, TValue>`. Ovvero la chiave deve essere una stringa. Per supportare un dizionario con un numero intero o un altro tipo come chiave, è necessario un convertitore personalizzato.

Il codice seguente illustra un convertitore personalizzato che funziona con `Dictionary<Enum,TValue>`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DictionaryTKeyEnumTValueConverter.cs)]

Il codice seguente registra il convertitore:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripDictionaryTkeyEnumTValue.cs?name=SnippetRegister)]

Il convertitore è in grado di serializzare e deserializzare la proprietà `TemperatureRanges` della classe seguente che usa i `Enum`seguenti:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnumDictionary)]

L'output JSON dalla serializzazione è simile all'esempio seguente:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

La [cartella unit test](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) nello spazio dei nomi `System.Text.Json.Serialization` contiene altri esempi di convertitori personalizzati che gestiscono dizionari non di stringa.

### <a name="support-polymorphic-deserialization"></a>Supportare la deserializzazione polimorfica

Le funzionalità predefinite forniscono una gamma limitata di [serializzazione polimorfica](system-text-json-how-to.md#serialize-properties-of-derived-classes) , ma non supportano affatto la deserializzazione. La deserializzazione richiede un convertitore personalizzato.

Si supponga, ad esempio, di disporre di una classe di base astratta `Person`, con `Employee` e `Customer` classi derivate. La deserializzazione polimorfica significa che in fase di progettazione è possibile specificare `Person` come destinazione della deserializzazione e gli oggetti `Customer` e `Employee` nel file JSON vengono deserializzati correttamente in fase di esecuzione. Durante la deserializzazione, è necessario trovare indizi che identifichino il tipo richiesto nel codice JSON. I tipi di indizi disponibili variano in ogni scenario. Ad esempio, una proprietà discriminatore potrebbe essere disponibile o potrebbe essere necessario basarsi sulla presenza o sull'assenza di una particolare proprietà. La versione corrente di `System.Text.Json` non fornisce attributi per specificare la modalità di gestione degli scenari di deserializzazione polimorfica, quindi i convertitori personalizzati sono obbligatori.

Nel codice seguente viene illustrata una classe di base, due classi derivate e un convertitore personalizzato. Il convertitore usa una proprietà discriminatore per eseguire la deserializzazione polimorfica. Il discriminatore di tipo non è incluso nelle definizioni di classe ma viene creato durante la serializzazione e viene letto durante la deserializzazione.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Person.cs?name=SnippetPerson)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/PersonConverterWithTypeDiscriminator.cs)]

Il codice seguente registra il convertitore:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPolymorphic.cs?name=SnippetRegister)]

Il convertitore può deserializzare JSON creato con lo stesso convertitore da serializzare, ad esempio:

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

Il codice del convertitore nell'esempio precedente legge e scrive ogni proprietà manualmente. In alternativa, è possibile chiamare `Deserialize` o `Serialize` per eseguire alcune operazioni. Per un esempio, vedere [questo post di StackOverflow](https://stackoverflow.com/a/59744873/12509023).

## <a name="other-custom-converter-samples"></a>Altri esempi di convertitore personalizzati

L'articolo [migrate from Newtonsoft. JSON to System. Text. JSON](system-text-json-migrate-from-newtonsoft-how-to.md) contiene esempi aggiuntivi di convertitori personalizzati.

La [cartella unit test](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/) nel codice sorgente `System.Text.Json.Serialization` include altri esempi di convertitore personalizzati, ad esempio:

* [Convertitore Int32 che converte il valore null in 0 per la deserializzazione](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)
* [Convertitore Int32 che consente di deserializzare sia i valori di stringa che di numeri](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)
* [Convertitore enum](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)
* [Elenco\<convertitore di > T che accetta dati esterni](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)
* [Long [] Converter che funziona con un elenco delimitato da virgole di numeri](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs) 

Se è necessario creare un convertitore che modifichi il comportamento di un convertitore incorporato esistente, è possibile ottenere [il codice sorgente del convertitore esistente](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters) per fungere da punto di partenza per la personalizzazione.

## <a name="additional-resources"></a>Risorse aggiuntive

* [Codice sorgente per convertitori predefiniti](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)
* [Supporto di DateTime e DateTimeOffset in System. Text. JSON](../datetime/system-text-json-support.md)
* [Panoramica di System. Text. JSON](system-text-json-overview.md)
* [Come usare System. Text. JSON](system-text-json-how-to.md)
* [Come eseguire la migrazione da Newtonsoft. JSON](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Informazioni di riferimento sull'API System. Text. JSON](xref:System.Text.Json)
* [Riferimento all'API System. Text. JSON. Serialization](xref:System.Text.Json.Serialization)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
