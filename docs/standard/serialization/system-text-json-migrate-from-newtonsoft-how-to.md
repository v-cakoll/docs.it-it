---
title: Eseguire la migrazione da Newtonsoft.Json a System.Text.Json-.NET
author: tdykstra
ms.author: tdykstra
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 221d19ee6441614324d375b66e8b13a90f683890
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921281"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a>Come eseguire la migrazione da Newtonsoft. JSON a System. Text. JSON

Questo articolo illustra come eseguire la migrazione da [Newtonsoft. JSON](https://www.newtonsoft.com/json) a <xref:System.Text.Json>.

`System.Text.Json` è incentrato principalmente sulle prestazioni, la sicurezza e la conformità agli standard. Presenta alcune differenze principali nel comportamento predefinito e non ha lo scopo di avere una parità di funzionalità con `Newtonsoft.Json`. Per alcuni scenari, `System.Text.Json` non dispone di funzionalità predefinite, ma sono disponibili soluzioni alternative consigliate. Per altri scenari, le soluzioni alternative sono poco pratiche. Se l'applicazione dipende da una funzionalità mancante, provare a [presentare un problema](https://github.com/dotnet/runtime/issues/new) per verificare se è possibile aggiungere il supporto per lo scenario.

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

La maggior parte di questo articolo descrive come usare l'API <xref:System.Text.Json.JsonSerializer>, ma include anche informazioni aggiuntive su come usare il <xref:System.Text.Json.JsonDocument> (che rappresenta il Document Object Model o DOM), <xref:System.Text.Json.Utf8JsonReader>e i tipi di <xref:System.Text.Json.Utf8JsonWriter>.

## <a name="table-of-differences-between-newtonsoftjson-and-systemtextjson"></a>Tabella delle differenze tra Newtonsoft. JSON e System. Text. JSON

Nella tabella seguente sono elencate le funzionalità di `Newtonsoft.Json` e `System.Text.Json` equivalenti. Gli equivalenti rientrano nelle categorie seguenti:

* Supportato dalla funzionalità incorporata. Ottenere un comportamento simile da `System.Text.Json` potrebbe richiedere l'uso di un attributo o di un'opzione globale.
* Non supportato, è possibile una soluzione alternativa. Le soluzioni alternative sono [convertitori personalizzati](system-text-json-converters-how-to.md), che potrebbero non fornire una parità completa con `Newtonsoft.Json` funzionalità. Per alcuni di questi esempi, il codice di esempio viene fornito come esempio. Se si utilizzano queste funzionalità `Newtonsoft.Json`, la migrazione richiederà modifiche ai modelli a oggetti .NET o ad altre modifiche del codice.
* Non supportato, la soluzione alternativa non è pratica o possibile. Se si utilizzano queste funzionalità `Newtonsoft.Json`, la migrazione non sarà possibile senza modifiche significative.

| Funzionalità Newtonsoft. JSON                               | System. Text. JSON equivalente |
|-------------------------------------------------------|-----------------------------|
| Deserializzazione per impostazione predefinita senza distinzione tra maiuscole e minuscole           | [impostazione globale](#case-insensitive-deserialization) di ✔️ PropertyNameCaseInsensitive |
| Nomi delle proprietà della case Camel                             | [impostazione globale](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) di ✔️ PropertyNamingPolicy |
| Escape di caratteri minimo                            | ✔️ [caratteri di escape rigorosi, configurabili](#minimal-character-escaping) |
| impostazione globale `NullValueHandling.Ignore`             | ✔️ [opzione globale IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) |
| Consenti commenti                                        | [impostazione globale](#comments) di ✔️ ReadCommentHandling |
| Consenti virgole finali                                 | [impostazione globale](#trailing-commas) di ✔️ AllowTrailingCommas |
| Registrazione del convertitore personalizzato                         | il ✔️ [ordine di precedenza è diverso](#converter-registration-precedence) |
| Nessuna profondità massima per impostazione predefinita                           | ✔️ [profondità massima predefinita 64, configurabile](#maximum-depth) |
| Supporto per un'ampia gamma di tipi                    | ⚠️ [alcuni tipi richiedono convertitori personalizzati](#types-without-built-in-support) |
| Deserializzare stringhe come numeri                        | ⚠️ [non supportato, soluzione alternativa, esempio](#quoted-numbers) |
| Deserializzare `Dictionary` con chiave non di stringa          | ⚠️ [non supportato, soluzione alternativa, esempio](#dictionary-with-non-string-key) |
| Serializzazione polimorfica                             | ⚠️ [non supportato, soluzione alternativa, esempio](#polymorphic-serialization) |
| Deserializzazione polimorfica                           | ⚠️ [non supportato, soluzione alternativa, esempio](#polymorphic-deserialization) |
| Deserializzare il tipo derivato in proprietà `object`      | ⚠️ [non supportato, soluzione alternativa, esempio](#deserialization-of-object-properties) |
| Deserializzare il valore letterale `null` JSON in tipi non nullable | ⚠️ [non supportato, soluzione alternativa, esempio](#deserialize-null-to-non-nullable-type) |
| Deserializzare in classi e struct non modificabili          | ⚠️ [non supportato, soluzione alternativa, esempio](#deserialize-to-immutable-classes-and-structs) |
| Attributo `[JsonConstructor]`                         | ⚠️ [non supportato, soluzione alternativa, esempio](#specify-constructor-to-use) |
| impostazione `Required` sull'attributo `[JsonProperty]`        | ⚠️ [non supportato, soluzione alternativa, esempio](#required-properties) |
| impostazione `NullValueHandling` sull'attributo `[JsonProperty]` | ⚠️ [non supportato, soluzione alternativa, esempio](#conditionally-ignore-a-property)  |
| impostazione `DefaultValueHandling` sull'attributo `[JsonProperty]` | ⚠️ [non supportato, soluzione alternativa, esempio](#conditionally-ignore-a-property)  |
| impostazione globale `DefaultValueHandling`                 | ⚠️ [non supportato, soluzione alternativa, esempio](#conditionally-ignore-a-property) |
| `DefaultContractResolver` escludere le proprietà       | ⚠️ [non supportato, soluzione alternativa, esempio](#conditionally-ignore-a-property) |
| impostazioni di `DateTimeZoneHandling``DateFormatString`   | ⚠️ [non supportato, soluzione alternativa, esempio](#specify-date-format) |
| Callback                                             | ⚠️ [non supportato, soluzione alternativa, esempio](#callbacks) |
| Supporto per campi pubblici e non pubblici              | ⚠️ [non supportato, soluzione alternativa](#public-and-non-public-fields) |
| Supporto per metodi di impostazione e richiamo di proprietà interne e private | ⚠️ [non supportato, soluzione alternativa](#internal-and-private-property-setters-and-getters) |
| Metodo `JsonConvert.PopulateObject`                   | ⚠️ [non supportato, soluzione alternativa](#populate-existing-objects) |
| impostazione globale `ObjectCreationHandling`               | ⚠️ [non supportato, soluzione alternativa](#reuse-rather-than-replace-properties) |
| Aggiungi a raccolte senza Setter                    | ⚠️ [non supportato, soluzione alternativa](#add-to-collections-without-setters) |
| impostazione globale `PreserveReferencesHandling`           | ❌ [non supportato](#preserve-object-references-and-handle-loops) |
| impostazione globale `ReferenceLoopHandling`                | ❌ [non supportato](#preserve-object-references-and-handle-loops) |
| Supporto per attributi di `System.Runtime.Serialization` | ❌ [non supportato](#systemruntimeserialization-attributes) |
| impostazione globale `MissingMemberHandling`                | ❌ [non supportato](#missingmemberhandling) |
| Consenti nomi di proprietà senza virgolette                   | ❌ [non supportato](#json-strings-property-names-and-string-values) |
| Consenti virgolette singole intorno ai valori stringa              | ❌ [non supportato](#json-strings-property-names-and-string-values) |
| Consenti valori JSON non stringa per le proprietà di stringa    | ❌ [non supportato](#non-string-values-for-string-properties) |

Questo non è un elenco completo delle funzionalità di `Newtonsoft.Json`. L'elenco include molti degli scenari richiesti nei [problemi di GitHub](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) o nei post [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) . Se si implementa una soluzione alternativa per uno degli scenari elencati qui che attualmente non contiene codice di esempio e se si desidera condividere la soluzione, selezionare **Questa pagina** nella [sezione feedback](/dotnet/standard/serialization/system-text-json-migrate-from-newtonsoft-how-to#feedback) di questa pagina. Questo crea un problema di GitHub e lo elenca nella parte inferiore della pagina.

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a>Differenze nel comportamento predefinito di JsonSerializer rispetto a Newtonsoft. JSON

<xref:System.Text.Json> è rigorosa per impostazione predefinita ed evita qualsiasi ipotesi o interpretazione per conto del chiamante, enfatizzando il comportamento deterministico. La libreria è intenzionalmente progettata in modo da migliorare le prestazioni e la sicurezza. per impostazione predefinita, `Newtonsoft.Json` è flessibile. Questa differenza fondamentale nella progettazione è alla base di molte delle seguenti differenze specifiche del comportamento predefinito.

### <a name="case-insensitive-deserialization"></a>Deserializzazione senza distinzione tra maiuscole e minuscole 

Durante la deserializzazione, `Newtonsoft.Json` esegue la corrispondenza dei nomi di proprietà senza distinzione tra maiuscole e minuscole per impostazione predefinita. Per impostazione predefinita <xref:System.Text.Json> viene fatta distinzione tra maiuscole e minuscole, che offre prestazioni migliori in quanto esegue una corrispondenza esatta. Per informazioni su come eseguire la corrispondenza senza distinzione tra maiuscole e minuscole, vedere [corrispondenza di proprietà senza distinzione tra maiuscole](system-text-json-how-to.md#case-insensitive-property-matching)e minuscole.

Se si usa `System.Text.Json` indirettamente con ASP.NET Core, non è necessario eseguire alcuna operazione per ottenere un comportamento come `Newtonsoft.Json`. ASP.NET Core specifica le impostazioni per i [nomi di proprietà di maiuscole](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) e minuscole e la corrispondenza senza distinzione tra maiuscole e minuscole quando usa `System.Text.Json`.

### <a name="minimal-character-escaping"></a>Escape di caratteri minimo

Durante la serializzazione, `Newtonsoft.Json` è relativamente permissiva per consentire i caratteri senza eseguirne l'escape. Ovvero non li sostituisce con `\uxxxx` dove `xxxx` è il punto di codice del carattere. Se viene eseguita l'escape, viene creato un `\` prima del carattere (ad esempio, `"` diventa `\"`). per impostazione predefinita, <xref:System.Text.Json> esegue il escape di più caratteri per offrire protezioni di difesa in profondità da attacchi XSS (cross-site scripting) o di divulgazione di informazioni, usando la sequenza di sei caratteri. per impostazione predefinita, `System.Text.Json` esegue l'escape di tutti i caratteri non ASCII, pertanto non è necessario eseguire alcuna operazione se si usa `StringEscapeHandling.EscapeNonAscii` in `Newtonsoft.Json`. per impostazione predefinita, `System.Text.Json` inoltre caratteri di escape per i caratteri sensibili al codice HTML. Per informazioni su come eseguire l'override del comportamento predefinito di `System.Text.Json`, vedere [personalizzare la codifica dei caratteri](system-text-json-how-to.md#customize-character-encoding).

### <a name="comments"></a>Comments

Durante la deserializzazione, `Newtonsoft.Json` ignora i commenti in JSON per impostazione predefinita. Il <xref:System.Text.Json> valore predefinito consiste nel generare eccezioni per i commenti perché la specifica [RFC 8259](https://tools.ietf.org/html/rfc8259) non le include. Per informazioni su come consentire i commenti, vedere [Consenti commenti e virgole finali](system-text-json-how-to.md#allow-comments-and-trailing-commas).

### <a name="trailing-commas"></a>Virgole finali

Durante la deserializzazione, `Newtonsoft.Json` ignora le virgole finali per impostazione predefinita. Ignora inoltre più virgole finali, ad esempio `[{"Color":"Red"},{"Color":"Green"},,]`. Il <xref:System.Text.Json> valore predefinito consiste nel generare eccezioni per le virgole finali perché la specifica [RFC 8259](https://tools.ietf.org/html/rfc8259) non le consente. Per informazioni su come fare in modo che `System.Text.Json` accettarle, vedere [consentire i commenti e le virgole finali](system-text-json-how-to.md#allow-comments-and-trailing-commas). Non è possibile consentire più virgole finali.

### <a name="converter-registration-precedence"></a>Precedenza di registrazione del convertitore

La `Newtonsoft.Json` la precedenza di registrazione per i convertitori personalizzati è la seguente:

* Attributo sulla proprietà
* Attributo sul tipo
* Raccolta [Converters](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)

Questo ordine indica che un convertitore personalizzato nella raccolta `Converters` viene sottoposto a override da un convertitore registrato applicando un attributo a livello di tipo. Entrambe le registrazioni vengono sottoposte a override da un attributo a livello di proprietà.

La <xref:System.Text.Json> la precedenza di registrazione per i convertitori personalizzati è diversa:

* Attributo sulla proprietà
* raccolta <xref:System.Text.Json.JsonSerializerOptions.Converters>
* Attributo sul tipo

La differenza è che un convertitore personalizzato nella raccolta `Converters` esegue l'override di un attributo a livello di tipo. L'intenzione alla base di questo ordine di precedenza consiste nel fare in modo che le modifiche in fase di esecuzione sostituiscano le scelte della fase di progettazione. Non è possibile modificare la precedenza.

Per altre informazioni sulla registrazione di un convertitore personalizzato, vedere [registrare un convertitore personalizzato](system-text-json-converters-how-to.md#register-a-custom-converter).

### <a name="maximum-depth"></a>Profondità massima

per impostazione predefinita, `Newtonsoft.Json` non ha un limite di profondità massimo. Per <xref:System.Text.Json> esiste un limite predefinito di 64 ed è configurabile impostando <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>.

### <a name="json-strings-property-names-and-string-values"></a>Stringhe JSON (nomi di proprietà e valori di stringa)

Durante la deserializzazione, `Newtonsoft.Json` accetta i nomi di proprietà racchiusi tra virgolette doppie, virgolette singole o senza virgolette. Accetta valori stringa racchiusi tra virgolette doppie o virgolette singole. Ad esempio, `Newtonsoft.Json` accetta il codice JSON seguente:

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json` accetta solo nomi di proprietà e valori stringa tra virgolette doppie perché tale formato è richiesto dalla specifica [RFC 8259](https://tools.ietf.org/html/rfc8259) ed è l'unico formato JSON valido.

Un valore racchiuso tra virgolette singole restituisce una [jsonexception](xref:System.Text.Json.JsonException) con il messaggio seguente:

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>Valori non stringa per le proprietà di stringa

`Newtonsoft.Json` accetta valori non stringa, ad esempio un numero o i valori letterali `true` e `false`, per la deserializzazione in proprietà di tipo String. Di seguito è riportato un esempio di JSON che `Newtonsoft.Json` deserializza correttamente nella classe seguente:

```json
{
  "String1": 1,
  "String2": true,
  "String3": false
}
```

```csharp
public class ExampleClass
{
    public string String1 { get; set; }
    public string String2 { get; set; }
    public string String3 { get; set; }
}
```

`System.Text.Json` non deserializza i valori non stringa in proprietà di stringa. Un valore non stringa ricevuto per un campo stringa restituisce un oggetto [jsonexception](xref:System.Text.Json.JsonException) con il messaggio seguente:

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>Scenari che usano JsonSerializer che richiedono soluzioni alternative

Gli scenari seguenti non sono supportati dalla funzionalità incorporata, ma sono possibili soluzioni alternative. Le soluzioni alternative sono [convertitori personalizzati](system-text-json-converters-how-to.md), che potrebbero non fornire una parità completa con `Newtonsoft.Json` funzionalità. Per alcuni di questi esempi, il codice di esempio viene fornito come esempio. Se si utilizzano queste funzionalità `Newtonsoft.Json`, la migrazione richiederà modifiche ai modelli a oggetti .NET o ad altre modifiche del codice.

### <a name="types-without-built-in-support"></a>Tipi senza supporto incorporato

<xref:System.Text.Json> non fornisce supporto incorporato per i tipi seguenti:

* <xref:System.Data.DataTable> e tipi correlati
* F#tipi, ad esempio [unioni discriminate](../../fsharp/language-reference/discriminated-unions.md), [tipi di record](../../fsharp/language-reference/records.md)e [tipi di record anonimi](../../fsharp/language-reference/anonymous-records.md).
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple> e i tipi generici associati

I convertitori personalizzati possono essere implementati per i tipi che non dispongono del supporto incorporato.

### <a name="quoted-numbers"></a>Numeri tra virgolette

`Newtonsoft.Json` possibile serializzare o deserializzare numeri rappresentati da stringhe JSON (racchiusi tra virgolette). Ad esempio, può accettare: `{"DegreesCelsius":"23"}` anziché `{"DegreesCelsius":23}`. Per abilitare tale comportamento in <xref:System.Text.Json>, implementare un convertitore personalizzato come l'esempio seguente. Il convertitore gestisce le proprietà definite come `long`:

* Li serializza come stringhe JSON. 
* Accetta numeri e numeri JSON racchiusi tra virgolette durante la deserializzazione.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/LongToStringConverter.cs)]

Registrare questo convertitore personalizzato [usando un attributo](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) per le singole proprietà di `long` o [aggiungendo il convertitore](system-text-json-converters-how-to.md#registration-sample---converters-collection) alla raccolta di <xref:System.Text.Json.JsonSerializerOptions.Converters>.

### <a name="dictionary-with-non-string-key"></a>Dizionario con chiave non di stringa

`Newtonsoft.Json` supporta raccolte di tipo `Dictionary<TKey, TValue>`. Il supporto incorporato per le raccolte di dizionari in <xref:System.Text.Json> è limitato ai `Dictionary<string, TValue>`. Ovvero la chiave deve essere una stringa.

Per supportare un dizionario con un Integer o un altro tipo come chiave, creare un convertitore come l'esempio in [come scrivere convertitori personalizzati](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).

### <a name="polymorphic-serialization"></a>Serializzazione polimorfica

`Newtonsoft.Json` esegue automaticamente la serializzazione polimorfica. Per informazioni sulle funzionalità di serializzazione polimorfiche limitate di <xref:System.Text.Json>, vedere [serializzare le proprietà delle classi derivate](system-text-json-how-to.md#serialize-properties-of-derived-classes).

La soluzione alternativa descritta è la definizione di proprietà che possono contenere classi derivate come tipo `object`. Se ciò non è possibile, un'altra opzione consiste nel creare un convertitore con un metodo `Write` per l'intera gerarchia dei tipi di ereditarietà, come l'esempio in [come scrivere convertitori personalizzati](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="polymorphic-deserialization"></a>Deserializzazione polimorfica

`Newtonsoft.Json` dispone di un'impostazione di `TypeNameHandling` che aggiunge i metadati del nome del tipo al file JSON durante la serializzazione. USA i metadati durante la deserializzazione per eseguire la deserializzazione polimorfica. <xref:System.Text.Json> possibile eseguire un intervallo limitato di [serializzazione polimorfica](system-text-json-how-to.md#serialize-properties-of-derived-classes) , ma non di deserializzazione polimorfica.

Per supportare la deserializzazione polimorfica, creare un convertitore come l'esempio in [come scrivere convertitori personalizzati](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="deserialization-of-object-properties"></a>Deserializzazione di proprietà dell'oggetto

Quando `Newtonsoft.Json` deserializza <xref:System.Object>,:

* Deduce il tipo di valori primitivi nel payload JSON (diverso da `null`) e restituisce il `string`archiviato, `long`, `double`, `boolean`o `DateTime` come oggetto boxed. *I valori primitivi* sono valori JSON singoli, ad esempio un numero JSON, una stringa, `true`, `false`o `null`.
* Restituisce un `JObject` o `JArray` per i valori complessi nel payload JSON. *I valori complessi* sono raccolte di coppie chiave-valore JSON racchiuse tra parentesi graffe (`{}`) o elenchi di valori racchiusi tra parentesi quadre (`[]`). Le proprietà e i valori tra parentesi graffe o parentesi quadre possono avere proprietà o valori aggiuntivi.
* Restituisce un riferimento null quando il payload presenta il valore letterale JSON `null`.

<xref:System.Text.Json> archivia una `JsonElement` boxed per i valori primitivi e complessi ogni volta che si esegue la deserializzazione per <xref:System.Object>, ad esempio:

* Proprietà `object`.
* Valore del dizionario `object`.
* Valore di matrice `object`.
* `object`radice.

Tuttavia, `System.Text.Json` considera `null` lo stesso `Newtonsoft.Json` e restituisce un riferimento null quando il payload presenta il valore letterale JSON `null`.

Per implementare l'inferenza del tipo per le proprietà `object`, creare un convertitore come l'esempio in [come scrivere convertitori personalizzati](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).

### <a name="deserialize-null-to-non-nullable-type"></a>Deserializzazione di valori null in un tipo non nullable 

`Newtonsoft.Json` non genera un'eccezione nello scenario seguente:

* `NullValueHandling` è impostato su `Ignore`e
* Durante la deserializzazione, il codice JSON contiene un valore null per un tipo non nullable.

Nello stesso scenario, <xref:System.Text.Json> genera un'eccezione. L'impostazione di gestione dei valori null corrispondente è <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>.

Se si è proprietari del tipo di destinazione, la soluzione migliore consiste nel rendere la proprietà in questione Nullable (ad esempio, modificare `int` `int?`).

Un'altra soluzione alternativa consiste nel creare un convertitore per il tipo, ad esempio l'esempio seguente che gestisce i valori null per i tipi di `DateTimeOffset`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetNullHandlingConverter.cs)]

Registrare questo convertitore personalizzato [usando un attributo nella proprietà](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) o [aggiungendo il convertitore](system-text-json-converters-how-to.md#registration-sample---converters-collection) alla raccolta di <xref:System.Text.Json.JsonSerializerOptions.Converters>.

**Nota:** Il convertitore precedente **gestisce i valori null in modo diverso** rispetto a `Newtonsoft.Json` per i poco che specificano i valori predefiniti. Si supponga, ad esempio, che il codice seguente rappresenti l'oggetto di destinazione:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Si supponga che il codice JSON seguente venga deserializzato usando il convertitore precedente:

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Dopo la deserializzazione, la proprietà `Date` ha 1/1/0001 (`default(DateTimeOffset)`), ovvero il valore impostato nel costruttore viene sovrascritto. Dato lo stesso POCO e JSON, la deserializzazione `Newtonsoft.Json` lascerebbe 1/1/2001 nella proprietà `Date`.

### <a name="deserialize-to-immutable-classes-and-structs"></a>Deserializzare in classi e struct non modificabili

`Newtonsoft.Json` possibile deserializzare le classi e gli struct non modificabili perché può utilizzare costruttori che dispongono di parametri. <xref:System.Text.Json> supporta solo costruttori pubblici senza parametri. Come soluzione alternativa, è possibile chiamare un costruttore con parametri in un convertitore personalizzato.

Di seguito è riportato uno struct non modificabile con più parametri del costruttore:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePoint.cs#ImmutablePoint)]

Ecco un convertitore che serializza e deserializza questo struct:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePointConverter.cs)]

Registrare il convertitore personalizzato [aggiungendo il convertitore](system-text-json-converters-how-to.md#registration-sample---converters-collection) alla raccolta di <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Per un esempio di convertitore analogo che gestisce le proprietà generiche aperte, vedere il [convertitore predefinito per le coppie chiave-valore](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).

### <a name="specify-constructor-to-use"></a>Specificare il costruttore da usare

L'attributo `Newtonsoft.Json` `[JsonConstructor]` consente di specificare il costruttore da chiamare durante la deserializzazione in un oggetto POCO. <xref:System.Text.Json> supporta solo costruttori senza parametri. Come soluzione alternativa, è possibile chiamare qualsiasi costruttore necessario in un convertitore personalizzato. Vedere l'esempio per [deserializzare in classi e struct non modificabili](#deserialize-to-immutable-classes-and-structs).

### <a name="required-properties"></a>Proprietà obbligatorie

In `Newtonsoft.Json`si specifica che una proprietà è obbligatoria impostando `Required` sull'attributo `[JsonProperty]`. `Newtonsoft.Json` genera un'eccezione se non viene ricevuto alcun valore nel codice JSON per una proprietà contrassegnata come obbligatoria.

<xref:System.Text.Json> non genera un'eccezione se non viene ricevuto alcun valore per una delle proprietà del tipo di destinazione. Ad esempio, se si dispone di una classe `WeatherForecast`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Il codice JSON seguente viene deserializzato senza errori:

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

Per fare in modo che la deserializzazione non riesca se nel codice JSON non è presente alcuna proprietà `Date`, implementare un convertitore personalizzato. Il codice del convertitore di esempio seguente genera un'eccezione se la proprietà `Date` non è impostata al termine della deserializzazione:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRequiredPropertyConverter.cs)]

Registrare questo convertitore personalizzato [usando un attributo della classe poco](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) o [aggiungendo il convertitore](system-text-json-converters-how-to.md#registration-sample---converters-collection) alla raccolta di <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Se si segue questo modello, non passare l'oggetto Options quando si chiama in modo ricorsivo <xref:System.Text.Json.JsonSerializer.Serialize%2A> o <xref:System.Text.Json.JsonSerializer.Deserialize%2A>. L'oggetto options contiene la raccolta <xref:System.Text.Json.JsonSerializerOptions.Converters%2A>. Se lo si passa a `Serialize` o `Deserialize`, il convertitore personalizzato chiama se stesso, creando un ciclo infinito che restituisce un'eccezione di overflow dello stack. Se le opzioni predefinite non sono realizzabili, creare una nuova istanza delle opzioni con le impostazioni necessarie. Questo approccio sarà lento perché ogni nuova istanza viene memorizzata nella cache in modo indipendente.

Il codice del convertitore precedente è un esempio semplificato. Se è necessario gestire gli attributi (ad esempio, [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) o opzioni diverse, ad esempio i codificatori personalizzati, è necessaria una logica aggiuntiva. Il codice di esempio non gestisce inoltre le proprietà per le quali viene impostato un valore predefinito nel costruttore. Questo approccio non distingue gli scenari seguenti:

* Una proprietà non è presente in JSON.
* Una proprietà per un tipo che non ammette i valori null è presente nel codice JSON, ma il valore è l'impostazione predefinita per il tipo, ad esempio zero per un `int`.
* In JSON è presente una proprietà per un tipo nullable, ma il valore è null.

### <a name="conditionally-ignore-a-property"></a>Ignorare una proprietà in modo condizionale

`Newtonsoft.Json` dispone di diversi modi per ignorare in modo condizionale una proprietà durante la serializzazione o la deserializzazione:

* `DefaultContractResolver` consente di selezionare le proprietà da includere o escludere, in base ai criteri arbitrari. 
* Le impostazioni `NullValueHandling` e `DefaultValueHandling` in `JsonSerializerSettings` consentono di specificare che tutte le proprietà con valore null o valore predefinito devono essere ignorate.
* Le impostazioni `NullValueHandling` e `DefaultValueHandling` sull'attributo `[JsonProperty]` consentono di specificare le singole proprietà che devono essere ignorate se impostate su null o sul valore predefinito.

<xref:System.Text.Json> offre i modi seguenti per omettere le proprietà durante la serializzazione:

* L'attributo [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) in una proprietà causa l'omissione della proprietà da JSON durante la serializzazione.
* L'opzione globale [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) consente di escludere tutte le proprietà con valore null.
* L'opzione globale [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) consente di escludere tutte le proprietà di sola lettura.

Queste opzioni **non** consentono di:

* Ignorare tutte le proprietà che hanno il valore predefinito per il tipo.
* Ignora le proprietà selezionate che hanno il valore predefinito per il tipo.
* Ignora le proprietà selezionate se il relativo valore è null.
* Ignora le proprietà selezionate in base ai criteri arbitrari valutati in fase di esecuzione. 

Per questa funzionalità, è possibile scrivere un convertitore personalizzato. Ecco un esempio POCO e un convertitore personalizzato che illustra questo approccio:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

Il convertitore fa in modo che la proprietà `Summary` venga omessa dalla serializzazione se il relativo valore è null, una stringa vuota o "N/A". 

Registrare questo convertitore personalizzato [usando un attributo della classe](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) oppure [aggiungendo il convertitore](system-text-json-converters-how-to.md#registration-sample---converters-collection) alla raccolta di <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Questo approccio richiede una logica aggiuntiva se:

* Il POCO include proprietà complesse.
* È necessario gestire attributi come `[JsonIgnore]` o opzioni come codificatori personalizzati.

### <a name="specify-date-format"></a>Specificare il formato della data

`Newtonsoft.Json` offre diversi modi per controllare la modalità di serializzazione e deserializzazione delle proprietà dei tipi `DateTime` e `DateTimeOffset`:

* È possibile utilizzare l'impostazione `DateTimeZoneHandling` per serializzare tutti i valori `DateTime` come date UTC.
* Per personalizzare il formato delle stringhe di data, è possibile usare l'impostazione `DateFormatString` e i convertitori di `DateTime`.

In <xref:System.Text.Json>, l'unico formato con supporto incorporato è ISO 8601-1:2019 poiché è ampiamente adottato, non ambiguo e rende esattamente i round trip. Per utilizzare qualsiasi altro formato, creare un convertitore personalizzato. Per altre informazioni, vedere [supporto di DateTime e DateTimeOffset in System. Text. JSON](../datetime/system-text-json-support.md).

### <a name="callbacks"></a>Callback

`Newtonsoft.Json` consente di eseguire codice personalizzato in diversi punti del processo di serializzazione o deserializzazione:

* OnDeserializing (quando si inizia a deserializzare un oggetto)
* OnDeserialized (al termine della deserializzazione di un oggetto)
* Onserialize (quando si inizia a serializzare un oggetto)
* OnSerialized (al termine della serializzazione di un oggetto)

In <xref:System.Text.Json>, è possibile simulare i callback scrivendo un convertitore personalizzato. Nell'esempio seguente viene illustrato un convertitore personalizzato per un oggetto POCO. Il convertitore include codice che visualizza un messaggio in corrispondenza di ogni punto che corrisponde a un callback `Newtonsoft.Json`.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastCallbacksConverter.cs)]

Registrare questo convertitore personalizzato [usando un attributo della classe](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) oppure [aggiungendo il convertitore](system-text-json-converters-how-to.md#registration-sample---converters-collection) alla raccolta di <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Se si usa un convertitore personalizzato che segue l'esempio precedente:

* Il codice `OnDeserializing` non ha accesso alla nuova istanza POCO. Per modificare la nuova istanza POCO all'inizio della deserializzazione, inserire il codice nel costruttore POCO.
* Non passare l'oggetto Options quando si chiama in modo ricorsivo `Serialize` o `Deserialize`. L'oggetto options contiene la raccolta `Converters`. Se lo si passa a `Serialize` o `Deserialize`, verrà usato il convertitore, rendendo un ciclo infinito che restituisce un'eccezione di overflow dello stack.

### <a name="public-and-non-public-fields"></a>Campi pubblici e non pubblici

`Newtonsoft.Json` possibile serializzare e deserializzare i campi e le proprietà. <xref:System.Text.Json> funziona solo con proprietà pubbliche. I convertitori personalizzati possono fornire questa funzionalità.

### <a name="internal-and-private-property-setters-and-getters"></a>Metodi setter e getter delle proprietà interne e private

`Newtonsoft.Json` possibile utilizzare Setter e getter di proprietà privati e interni tramite l'attributo `JsonProperty`. <xref:System.Text.Json> supporta solo Setter pubblici. I convertitori personalizzati possono fornire questa funzionalità.

### <a name="populate-existing-objects"></a>Popola oggetti esistenti

Il metodo `JsonConvert.PopulateObject` in `Newtonsoft.Json` deserializza un documento JSON in un'istanza esistente di una classe, anziché creare una nuova istanza. <xref:System.Text.Json> crea sempre una nuova istanza del tipo di destinazione usando il costruttore pubblico senza parametri predefinito. I convertitori personalizzati possono eseguire la deserializzazione in un'istanza esistente.

### <a name="reuse-rather-than-replace-properties"></a>Riutilizza anziché sostituire le proprietà

L'impostazione `Newtonsoft.Json` `ObjectCreationHandling` consente di specificare che gli oggetti nelle proprietà devono essere riutilizzati anziché sostituiti durante la deserializzazione. <xref:System.Text.Json> sostituisce sempre gli oggetti nelle proprietà.  I convertitori personalizzati possono fornire questa funzionalità.

### <a name="add-to-collections-without-setters"></a>Aggiungi a raccolte senza Setter

Durante la deserializzazione, `Newtonsoft.Json` aggiunge oggetti a una raccolta anche se la proprietà non dispone di un metodo di impostazione. <xref:System.Text.Json> ignora le proprietà che non hanno Setter. I convertitori personalizzati possono fornire questa funzionalità.

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>Scenari attualmente non supportati da JsonSerializer

Per gli scenari seguenti, le soluzioni alternative non sono pratiche o possibili. Se si utilizzano queste funzionalità `Newtonsoft.Json`, la migrazione non sarà possibile senza modifiche significative.

### <a name="preserve-object-references-and-handle-loops"></a>Mantieni i riferimenti agli oggetti e i cicli di handle

Per impostazione predefinita, `Newtonsoft.Json` serializza per valore. Se, ad esempio, un oggetto contiene due proprietà che contengono un riferimento allo stesso oggetto `Person`, i valori delle proprietà dell'oggetto `Person` vengono duplicati in JSON.

`Newtonsoft.Json` dispone di un'impostazione di `PreserveReferencesHandling` su `JsonSerializerSettings` che consente di serializzare per riferimento:

* I metadati dell'identificatore vengono aggiunti al file JSON creato per il primo oggetto `Person`.
* Il codice JSON creato per il secondo oggetto `Person` contiene un riferimento a tale identificatore invece dei valori delle proprietà.

`Newtonsoft.Json` dispone inoltre di un'impostazione di `ReferenceLoopHandling` che consente di ignorare i riferimenti circolari anziché generare un'eccezione.

<xref:System.Text.Json> supporta solo la serializzazione per valore e genera un'eccezione per i riferimenti circolari.

### <a name="systemruntimeserialization-attributes"></a>Attributi System. Runtime. Serialization

<xref:System.Text.Json> non supporta gli attributi dello spazio dei nomi `System.Runtime.Serialization`, ad esempio `DataMemberAttribute` e `IgnoreDataMemberAttribute`.

### <a name="octal-numbers"></a>Numeri ottali

`Newtonsoft.Json` considera i numeri con uno zero iniziali come numeri ottali. <xref:System.Text.Json> non consente zeri iniziali perché la specifica [RFC 8259](https://tools.ietf.org/html/rfc8259) non li consente.

### <a name="missingmemberhandling"></a>MissingMemberHandling

`Newtonsoft.Json` può essere configurato in modo da generare eccezioni durante la deserializzazione se il codice JSON include proprietà mancanti nel tipo di destinazione. <xref:System.Text.Json> ignora le proprietà aggiuntive in JSON, tranne quando si usa l' [attributo [JsonExtensionData]](system-text-json-how-to.md#handle-overflow-json). Non esiste alcuna soluzione per la funzionalità membro mancante.

### <a name="tracewriter"></a>TraceWriter

`Newtonsoft.Json` consente di eseguire il debug usando un `TraceWriter` per visualizzare i log generati dalla serializzazione o deserializzazione. <xref:System.Text.Json> non esegue la registrazione.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>JsonDocument e Jsonelement rispetto a JToken (ad esempio, JObject, JArray)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> offre la possibilità di analizzare e compilare una Document Object Model di sola **lettura** (Dom) dai payload JSON esistenti. Il DOM fornisce l'accesso casuale ai dati in un payload JSON. È possibile accedere agli elementi JSON che compongono il payload tramite il tipo di <xref:System.Text.Json.JsonElement>. Il tipo di `JsonElement` fornisce le API per convertire il testo JSON in tipi .NET comuni. `JsonDocument` espone una proprietà <xref:System.Text.Json.JsonDocument.RootElement>.

### <a name="jsondocument-is-idisposable"></a>JsonDocument è IDisposable

`JsonDocument` compila una visualizzazione in memoria dei dati in un buffer in pool. Pertanto, a differenza `JObject` o `JArray` da `Newtonsoft.Json`, il tipo di `JsonDocument` implementa `IDisposable` e deve essere utilizzato all'interno di un blocco using. 

Restituire solo un `JsonDocument` dall'API se si vuole trasferire la proprietà della durata ed eliminare la responsabilità per il chiamante. Nella maggior parte degli scenari non è necessario. Se il chiamante deve usare l'intero documento JSON, restituire la <xref:System.Text.Json.JsonElement.Clone%2A> del <xref:System.Text.Json.JsonDocument.RootElement%2A>, che è un <xref:System.Text.Json.JsonElement>. Se il chiamante deve usare un particolare elemento nel documento JSON, restituire la <xref:System.Text.Json.JsonElement.Clone%2A> di tale <xref:System.Text.Json.JsonElement>. Se si restituisce il `RootElement` o un sottoelemento direttamente senza eseguire una `Clone`, il chiamante non sarà in grado di accedere al `JsonElement` restituito dopo che il `JsonDocument` a cui appartiene è stato eliminato.

Di seguito è riportato un esempio che richiede di creare un `Clone`:

```csharp
public JsonElement LookAndLoad(JsonElement source)
{
    string json = File.ReadAllText(source.GetProperty("fileName").GetString());
   
    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        return doc.RootElement.Clone();
    }
}
```

Il codice precedente prevede un `JsonElement` contenente una proprietà `fileName`. Viene aperto il file JSON e viene creato un `JsonDocument`. Il metodo presuppone che il chiamante voglia lavorare con l'intero documento, quindi restituisce la `Clone` del `RootElement`. 

Se si riceve un `JsonElement` e si restituisce un sottoelemento, non è necessario restituire una `Clone` del sottoelemento. Il chiamante ha la responsabilità di mantenere attivo il `JsonDocument` a cui appartiene l'`JsonElement` passata. Ad esempio:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>JsonDocument è di sola lettura

Il DOM <xref:System.Text.Json> non può aggiungere, rimuovere o modificare elementi JSON. Questo metodo è progettato per le prestazioni e per ridurre le allocazioni per l'analisi di dimensioni del payload JSON comuni (ovvero < 1 MB). Se lo scenario usa attualmente un DOM modificabile, potrebbe essere possibile una delle soluzioni alternative seguenti:

* Per compilare un `JsonDocument` da zero (ovvero senza passare un payload JSON esistente al metodo `Parse`), scrivere il testo JSON usando il `Utf8JsonWriter` e analizzare l'output da tale per creare un nuovo `JsonDocument`.
* Per modificare un `JsonDocument`esistente, usarlo per scrivere testo JSON, apportare modifiche durante la scrittura e analizzare l'output da tale per creare una nuova `JsonDocument`.
* Per unire i documenti JSON esistenti, equivalenti al `JObject.Merge` o `JContainer.Merge` API da `Newtonsoft.Json`, vedere [questo problema di GitHub](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).

### <a name="jsonelement-is-a-union-struct"></a>Jsonelement è uno struct Unione

`JsonDocument` espone la `RootElement` come proprietà di tipo <xref:System.Text.Json.JsonElement>, che è un tipo di struct Unione che comprende qualsiasi elemento JSON. `Newtonsoft.Json` usa tipi gerarchici dedicati come `JObject`,`JArray`, `JToken`e così via. `JsonElement` è ciò che è possibile ricercare ed enumerare ed è possibile usare `JsonElement` per materializzare gli elementi JSON in tipi .NET.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>Come eseguire una ricerca in JsonDocument e Jsonelement per sottoelementi

Cerca i token JSON usando `JObject` o `JArray` da `Newtonsoft.Json` tendono a essere relativamente veloci perché sono ricerche in un dizionario. Per confronto, le ricerche in `JsonElement` richiedono una ricerca sequenziale delle proprietà e pertanto sono relativamente lente, ad esempio quando si usa `TryGetProperty`. <xref:System.Text.Json> è progettato per ridurre al minimo il tempo di analisi iniziale anziché il tempo di ricerca. Per ottimizzare le prestazioni durante la ricerca in un oggetto `JsonDocument`, utilizzare quindi gli approcci seguenti:

* Usare gli enumeratori predefiniti (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> e <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) invece di eseguire l'indicizzazione o i cicli.
* Non eseguire una ricerca sequenziale sull'intero `JsonDocument` tramite ogni proprietà utilizzando `RootElement`. Cercare invece oggetti JSON annidati in base alla struttura nota dei dati JSON. Se, ad esempio, si sta cercando una proprietà `Grade` in `Student` oggetti, eseguire il ciclo degli oggetti `Student` e ottenere il valore di `Grade` per ognuno, invece di cercare tutti gli oggetti `JsonElement` cercando le proprietà di `Grade`. Se si esegue quest'ultimo, il passaggio non è necessario per gli stessi dati.

Per un esempio di codice, vedere [usare JsonDocument per l'accesso ai dati](system-text-json-how-to.md#use-jsondocument-for-access-to-data).

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Utf8JsonReader rispetto a JsonTextReader

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> è un reader a elevate prestazioni, a bassa allocazione e di sola trasmissione per il testo JSON con codifica UTF-8, letto da un [ReadOnlySpan\<byte >](xref:System.ReadOnlySpan%601) o [ReadOnlySequence\<byte >](xref:System.Buffers.ReadOnlySequence%601). Il `Utf8JsonReader` è un tipo di basso livello che può essere utilizzato per compilare parser e deserializzatori personalizzati.

Le sezioni seguenti illustrano i modelli di programmazione consigliati per l'uso di `Utf8JsonReader`.

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader è uno struct di riferimento

Poiché il tipo `Utf8JsonReader` è uno *struct Ref*, presenta [alcune limitazioni](../../csharp/language-reference/keywords/ref.md#ref-struct-types). Ad esempio, non può essere archiviato come campo in una classe o uno struct diverso da uno struct Ref. Per ottenere prestazioni elevate, questo tipo deve essere un `ref struct` perché deve memorizzare nella cache l'input [ReadOnlySpan\<> byte](xref:System.ReadOnlySpan%601), che a sua volta è uno struct Ref. Inoltre, questo tipo è modificabile perché include lo stato. Quindi, **passarlo per Ref** anziché per valore. Il passaggio per valore comporterebbe una copia dello struct e le modifiche dello stato non sarebbero visibili al chiamante. Questo comportamento è diverso da `Newtonsoft.Json` perché il `JsonTextReader` di `Newtonsoft.Json` è una classe. Per altre informazioni su come usare gli struct di riferimento, vedere [scrivere codice sicuro ed C# efficiente](../../csharp/write-safe-efficient-code.md).

### <a name="read-utf-8-text"></a>Leggi testo UTF-8

Per ottenere le migliori prestazioni possibili quando si usa il `Utf8JsonReader`, leggere i payload JSON già codificati come testo UTF-8 anziché come stringhe UTF-16. Per un esempio di codice, vedere [filtrare i dati usando Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).

### <a name="read-with-a-stream-or-pipereader"></a>Lettura con un flusso o PipeReader

Il `Utf8JsonReader` supporta la lettura da una codifica UTF-8 [ReadOnlySpan\<byte >](xref:System.ReadOnlySpan%601) o [ReadOnlySequence\<byte >](xref:System.Buffers.ReadOnlySequence%601) (ovvero il risultato della lettura da un <xref:System.IO.Pipelines.PipeReader>).

Per la lettura sincrona, è possibile leggere il payload JSON fino alla fine del flusso in una matrice di byte e passarlo al lettore. Per la lettura da una stringa (codificata come UTF-16), chiamare <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A> per innanzitutto transcodificare la stringa in una matrice di byte con codifica UTF-8. Passarlo quindi al `Utf8JsonReader`. 

Poiché il `Utf8JsonReader` considera l'input come testo JSON, un byte order mark UTF-8 (BOM) viene considerato JSON non valido. Il chiamante deve filtrare il timeout prima di passare i dati al lettore.

Per esempi di codice, vedere [usare Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).

### <a name="read-with-multi-segment-readonlysequence"></a>Leggi con ReadOnlySequence multisegmento

Se l'input JSON è un [ReadOnlySpan\<byte >](xref:System.ReadOnlySpan%601), è possibile accedere a ogni elemento JSON dalla proprietà `ValueSpan` nel Reader mentre si passa attraverso il ciclo Read. Tuttavia, se l'input è un [ReadOnlySequence\<byte >](xref:System.Buffers.ReadOnlySequence%601) (ovvero il risultato della lettura da un <xref:System.IO.Pipelines.PipeReader>), alcuni elementi JSON potrebbero risiedere in più segmenti dell'oggetto `ReadOnlySequence<byte>`. Questi elementi non saranno accessibili da <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> in un blocco di memoria contigua. Al contrario, ogni volta che si dispone di un `ReadOnlySequence<byte>` multisegmento come input, eseguire il polling della proprietà <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> sul Reader per capire come accedere all'elemento JSON corrente. Ecco un modello consigliato:

```csharp
while (reader.Read())
{
    switch (reader.TokenType)
    {
        // ...
        ReadOnlySpan<byte> jsonElement = reader.HasValueSequence ?
            reader.ValueSequence.ToArray() :
            reader.ValueSpan;
        // ...
    }
}
```

### <a name="use-valuetextequals-for-property-name-lookups"></a>Usare ValueTextEquals per le ricerche nome proprietà

Non utilizzare <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> per eseguire confronti byte per byte chiamando <xref:System.MemoryExtensions.SequenceEqual%2A> per le ricerche del nome di proprietà. Chiamare invece <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A>, perché il metodo esegue l'escape di tutti i caratteri di escape in JSON. Ecco un esempio che illustra come cercare una proprietà denominata "Name":

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>Lettura di valori null in tipi di valore Nullable

`Newtonsoft.Json` fornisce le API che restituiscono <xref:System.Nullable%601>, ad esempio `ReadAsBoolean`, che gestisce un `TokenType` `Null` per l'utente restituendo un `bool?`. Le API `System.Text.Json` predefinite restituiscono solo tipi di valore non nullable. Ad esempio, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> restituisce una `bool`. Genera un'eccezione se trova `Null` in JSON. Negli esempi seguenti vengono illustrati due modi per gestire i valori null, uno restituendo un tipo di valore nullable e l'altro restituendo il valore predefinito:

```csharp
public bool? ReadAsNullableBoolean()
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return null;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

```csharp
public bool ReadAsBoolean(bool defaultValue)
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return defaultValue;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

### <a name="multi-targeting"></a>Multitargeting

Se è necessario continuare a usare `Newtonsoft.Json` per alcuni framework di destinazione, è possibile usare più destinazioni e due implementazioni. Tuttavia, questo non è semplice e richiede alcuni `#ifdefs` e la duplicazione dell'origine. Un modo per condividere il maggior quantità possibile di codice consiste nel creare un wrapper `ref struct` attorno `Utf8JsonReader` e `Newtonsoft.Json` `JsonTextReader`. Questo wrapper unifica la superficie pubblica, isolando le differenze di comportamento. In questo modo è possibile isolare le modifiche principalmente alla costruzione del tipo, insieme al passaggio del nuovo tipo in base al riferimento. Questo è il modello che segue la libreria [Microsoft. Extensions. DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) :

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Utf8JsonWriter rispetto a JsonTextWriter

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> è un modo a prestazioni elevate per scrivere testo JSON con codifica UTF-8 da tipi .NET comuni come `String`, `Int32`e `DateTime`. Il writer è un tipo di basso livello che può essere utilizzato per compilare serializzatori personalizzati.

Le sezioni seguenti illustrano i modelli di programmazione consigliati per l'uso di `Utf8JsonWriter`.

### <a name="write-with-utf-8-text"></a>Scrivi con testo UTF-8

Per ottenere le migliori prestazioni possibili quando si usa il `Utf8JsonWriter`, scrivere payload JSON già codificati come testo UTF-8 anziché come stringhe UTF-16. Usare <xref:System.Text.Json.JsonEncodedText> per memorizzare nella cache e pre-codificare i nomi e i valori delle proprietà delle stringhe note come static e passarli al writer, anziché usare valori letterali stringa UTF-16. Questa operazione è più veloce rispetto alla memorizzazione nella cache e all'utilizzo di matrici di byte UTF-8.

Questo approccio funziona anche se è necessario eseguire l'escape personalizzato. `System.Text.Json` non consente di disabilitare l'escape durante la scrittura di una stringa. Tuttavia, è possibile passare il <xref:System.Text.Encodings.Web.JavaScriptEncoder> personalizzato come opzione al writer oppure creare un `JsonEncodedText` personalizzato che usi il `JavascriptEncoder` per eseguire l'escape e quindi scrivere il `JsonEncodedText` invece della stringa. Per altre informazioni, vedere [personalizzare la codifica dei caratteri](system-text-json-how-to.md#customize-character-encoding).

### <a name="write-raw-values"></a>Scrivi valori non elaborati

Il `Newtonsoft.Json` `WriteRawValue` metodo scrive JSON non elaborato in cui è previsto un valore. <xref:System.Text.Json> non ha un equivalente diretto, ma ecco una soluzione alternativa che garantisce che venga scritto solo JSON valido:

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>Personalizzare l'escape di caratteri

L'impostazione [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) di `JsonTextWriter` offre opzioni per l'escape di tutti i caratteri non ASCII **o** HTML. Per impostazione predefinita, `Utf8JsonWriter` caratteri di escape per tutti i caratteri non ASCII **e** HTML. Questa operazione di escape viene eseguita per motivi di sicurezza della difesa in profondità. Per specificare criteri di escape diversi, creare una <xref:System.Text.Encodings.Web.JavaScriptEncoder> e impostare <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>. Per altre informazioni, vedere [personalizzare la codifica dei caratteri](system-text-json-how-to.md#customize-character-encoding).

### <a name="customize-json-format"></a>Personalizzare il formato JSON

`JsonTextWriter` include le impostazioni seguenti, per le quali `Utf8JsonWriter` non ha un equivalente:

* [Rientro](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) : specifica il numero di caratteri da rientrare. `Utf8JsonWriter` esegue sempre il rientro a 2 caratteri.
* [IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) -specifica il carattere da utilizzare per il rientro.  `Utf8JsonWriter` utilizza sempre lo spazio vuoto.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) : specifica il carattere da usare per racchiudere i valori di stringa.  `Utf8JsonWriter` utilizza sempre le virgolette doppie.
* [QUOTENAME](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) -specifica se racchiudere o meno i nomi delle proprietà con virgolette.  `Utf8JsonWriter` sempre racchiuso tra virgolette.

Non esistono soluzioni alternative che consentono di personalizzare il codice JSON prodotto da `Utf8JsonWriter` in questi modi.

### <a name="write-null-values"></a>Scrivi valori null

Per scrivere valori null usando `Utf8JsonWriter`, chiamare:

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> scrivere una coppia chiave-valore con null come valore.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> scrivere null come elemento di una matrice JSON.

Per una proprietà di stringa, se la stringa è null, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> e <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> sono equivalenti a `WriteNull` e `WriteNullValue`.

### <a name="write-timespan-uri-or-char-values"></a>Scrivere valori TimeSpan, URI o char

`JsonTextWriter` fornisce metodi `WriteValue` per i valori [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [URI](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)e [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) . `Utf8JsonWriter` non dispone di metodi equivalenti. Formattare invece questi valori come stringhe (chiamando `ToString()`, ad esempio) e chiamare <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>.

### <a name="multi-targeting"></a>Multitargeting

Se è necessario continuare a usare `Newtonsoft.Json` per alcuni framework di destinazione, è possibile usare più destinazioni e due implementazioni. Tuttavia, questo non è semplice e richiede alcuni `#ifdefs` e la duplicazione dell'origine. Un modo per condividere il maggior quantità possibile di codice consiste nel creare un wrapper intorno `Utf8JsonWriter` e `Newtonsoft` `JsonTextWriter`. Questo wrapper unifica la superficie pubblica, isolando le differenze di comportamento. In questo modo è possibile isolare le modifiche principalmente alla costruzione del tipo. La libreria [Microsoft. Extensions. DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) segue:

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>Risorse aggiuntive

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [Panoramica di System.Text.Json](system-text-json-overview.md)
* [Come usare System.Text.Json](system-text-json-how-to.md)
* [Come scrivere convertitori personalizzati](system-text-json-converters-how-to.md)
* [Supporto di DateTime e DateTimeOffset in System.Text.Json](../datetime/system-text-json-support.md)
* [informazioni di riferimento sull'API System.Text.Json](xref:System.Text.Json)
* [System.Text.Json. Riferimento all'API di serializzazione](xref:System.Text.Json.Serialization)
