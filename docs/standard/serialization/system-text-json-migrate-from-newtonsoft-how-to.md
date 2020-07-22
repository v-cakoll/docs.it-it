---
title: Eseguire la migrazione da Newtonsoft.Json a System.Text.Json -.NET
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
ms.openlocfilehash: 78a47b01cc8fba4cb45a686adad901784552c1c1
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865333"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a>Come eseguire la migrazione da Newtonsoft.Json aSystem.Text.Json

Questo articolo illustra come eseguire la migrazione da [Newtonsoft.Json](https://www.newtonsoft.com/json) a <xref:System.Text.Json> .

Lo `System.Text.Json` spazio dei nomi fornisce funzionalità per la serializzazione e la deserializzazione da JavaScript Object Notation (JSON). La `System.Text.Json` libreria è inclusa nel Framework condiviso di [.net core 3,0](https://aka.ms/netcore3download) . Per altri Framework di destinazione, installare il [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) pacchetto NuGet. Il pacchetto supporta:

* .NET Standard 2,0 e versioni successive
* .NET Framework 4.7.2 e versioni successive
* .NET Core 2,0, 2,1 e 2,2

`System.Text.Json`si concentra principalmente sulle prestazioni, sulla sicurezza e sulla conformità agli standard. Presenta alcune differenze principali nel comportamento predefinito e non ha lo scopo di ottenere la parità di funzionalità con `Newtonsoft.Json` . Per alcuni scenari, `System.Text.Json` non dispone di funzionalità predefinite, ma sono disponibili soluzioni alternative consigliate. Per altri scenari, le soluzioni alternative sono poco pratiche. Se l'applicazione dipende da una funzionalità mancante, provare a [presentare un problema](https://github.com/dotnet/runtime/issues/new) per verificare se è possibile aggiungere il supporto per lo scenario.

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

La maggior parte di questo articolo descrive come usare l' <xref:System.Text.Json.JsonSerializer> API, ma include anche informazioni aggiuntive su come usare <xref:System.Text.Json.JsonDocument> (che rappresenta i tipi di Document Object Model o Dom), <xref:System.Text.Json.Utf8JsonReader> e <xref:System.Text.Json.Utf8JsonWriter> .

## <a name="table-of-differences-between-newtonsoftjson-and-systemtextjson"></a>Tabella delle differenze tra Newtonsoft.Json eSystem.Text.Json

Nella tabella seguente sono elencate le `Newtonsoft.Json` funzionalità e gli `System.Text.Json` equivalenti di. Gli equivalenti rientrano nelle categorie seguenti:

* Supportato dalla funzionalità incorporata. Per ottenere un comportamento simile da `System.Text.Json` può essere necessario usare un attributo o un'opzione globale.
* Non supportato, è possibile una soluzione alternativa. Le soluzioni alternative sono [convertitori personalizzati](system-text-json-converters-how-to.md), che potrebbero non fornire una parità completa con la `Newtonsoft.Json` funzionalità. Per alcuni di questi esempi, il codice di esempio viene fornito come esempio. Se si usano queste `Newtonsoft.Json` funzionalità, la migrazione richiederà modifiche ai modelli a oggetti .NET o ad altre modifiche al codice.
* Non supportato, la soluzione alternativa non è pratica o possibile. Se si usano queste `Newtonsoft.Json` funzionalità, la migrazione non sarà possibile senza modifiche significative.

| Funzionalità di Newtonsoft.Json                               | System.Text.Jsonequivalente |
|-------------------------------------------------------|-----------------------------|
| Deserializzazione per impostazione predefinita senza distinzione tra maiuscole e minuscole           | [impostazione globale](#case-insensitive-deserialization) di ✔️ PropertyNameCaseInsensitive |
| Nomi delle proprietà della case Camel                             | [impostazione globale](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) di ✔️ PropertyNamingPolicy |
| Escape di caratteri minimo                            | ✔️ [caratteri di escape rigorosi, configurabili](#minimal-character-escaping) |
| `NullValueHandling.Ignore`impostazione globale             | ✔️ [opzione globale IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) |
| Consenti commenti                                        | [impostazione globale](#comments) di ✔️ ReadCommentHandling |
| Consenti virgole finali                                 | [impostazione globale](#trailing-commas) di ✔️ AllowTrailingCommas |
| Registrazione del convertitore personalizzato                         | il ✔️ [ordine di precedenza è diverso](#converter-registration-precedence) |
| Nessuna profondità massima per impostazione predefinita                           | ✔️ [profondità massima predefinita 64, configurabile](#maximum-depth) |
| Supporto per un'ampia gamma di tipi                    | ⚠️[Alcuni tipi richiedono convertitori personalizzati](#types-without-built-in-support) |
| Deserializzare stringhe come numeri                        | ⚠️[Non supportato, soluzione alternativa, esempio](#quoted-numbers) |
| Deserializzare `Dictionary` con chiave non di stringa          | ⚠️[Non supportato, soluzione alternativa, esempio](#dictionary-with-non-string-key) |
| Serializzazione polimorfica                             | ⚠️[Non supportato, soluzione alternativa, esempio](#polymorphic-serialization) |
| Deserializzazione polimorfica                           | ⚠️[Non supportato, soluzione alternativa, esempio](#polymorphic-deserialization) |
| Deserializzare il tipo derivato in `object` Proprietà      | ⚠️[Non supportato, soluzione alternativa, esempio](#deserialization-of-object-properties) |
| Deserializzare il `null` valore letterale JSON in tipi valore non nullable | ⚠️[Non supportato, soluzione alternativa, esempio](#deserialize-null-to-non-nullable-type) |
| Deserializzare in classi e struct non modificabili          | ⚠️[Non supportato, soluzione alternativa, esempio](#deserialize-to-immutable-classes-and-structs) |
| Attributo `[JsonConstructor]`                         | ⚠️[Non supportato, soluzione alternativa, esempio](#specify-constructor-to-use) |
| `Required`impostazione sull' `[JsonProperty]` attributo        | ⚠️[Non supportato, soluzione alternativa, esempio](#required-properties) |
| `NullValueHandling`impostazione sull' `[JsonProperty]` attributo | ⚠️[Non supportato, soluzione alternativa, esempio](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`impostazione sull' `[JsonProperty]` attributo | ⚠️[Non supportato, soluzione alternativa, esempio](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`impostazione globale                 | ⚠️[Non supportato, soluzione alternativa, esempio](#conditionally-ignore-a-property) |
| `DefaultContractResolver`per escludere le proprietà       | ⚠️[Non supportato, soluzione alternativa, esempio](#conditionally-ignore-a-property) |
| `DateTimeZoneHandling`, `DateFormatString` impostazioni   | ⚠️[Non supportato, soluzione alternativa, esempio](#specify-date-format) |
| Callback                                             | ⚠️[Non supportato, soluzione alternativa, esempio](#callbacks) |
| Supporto per campi pubblici e non pubblici              | ⚠️[Non supportato, soluzione alternativa](#public-and-non-public-fields) |
| Supporto per metodi di impostazione e richiamo di proprietà interne e private | ⚠️[Non supportato, soluzione alternativa](#internal-and-private-property-setters-and-getters) |
| Metodo `JsonConvert.PopulateObject`                   | ⚠️[Non supportato, soluzione alternativa](#populate-existing-objects) |
| `ObjectCreationHandling`impostazione globale               | ⚠️[Non supportato, soluzione alternativa](#reuse-rather-than-replace-properties) |
| Aggiungi a raccolte senza Setter                    | ⚠️[Non supportato, soluzione alternativa](#add-to-collections-without-setters) |
| `PreserveReferencesHandling`impostazione globale           | ❌[Non supportato](#preserve-object-references-and-handle-loops) |
| `ReferenceLoopHandling`impostazione globale                | ❌[Non supportato](#preserve-object-references-and-handle-loops) |
| Supporto per `System.Runtime.Serialization` gli attributi | ❌[Non supportato](#systemruntimeserialization-attributes) |
| `MissingMemberHandling`impostazione globale                | ❌[Non supportato](#missingmemberhandling) |
| Consenti nomi di proprietà senza virgolette                   | ❌[Non supportato](#json-strings-property-names-and-string-values) |
| Consenti virgolette singole intorno ai valori stringa              | ❌[Non supportato](#json-strings-property-names-and-string-values) |
| Consenti valori JSON non stringa per le proprietà di stringa    | ❌[Non supportato](#non-string-values-for-string-properties) |

Non si tratta di un elenco completo di `Newtonsoft.Json` funzionalità. L'elenco include molti degli scenari richiesti nei [problemi di GitHub](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) o nei post [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) . Se si implementa una soluzione alternativa per uno degli scenari elencati qui che attualmente non contiene codice di esempio e se si desidera condividere la soluzione, selezionare **Questa pagina** nella sezione **commenti e suggerimenti** nella parte inferiore della pagina. Questo crea un problema nel repository GitHub della documentazione e lo elenca nella sezione **feedback** in questa pagina.

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a>Differenze nel comportamento predefinito di JsonSerializer rispetto aNewtonsoft.Json

<xref:System.Text.Json>è rigida per impostazione predefinita ed evita qualsiasi ipotesi o interpretazione per conto del chiamante, enfatizzando il comportamento deterministico. La libreria è intenzionalmente progettata in modo da migliorare le prestazioni e la sicurezza. `Newtonsoft.Json`è flessibile per impostazione predefinita. Questa differenza fondamentale nella progettazione è alla base di molte delle seguenti differenze specifiche del comportamento predefinito.

### <a name="case-insensitive-deserialization"></a>Deserializzazione senza distinzione tra maiuscole e minuscole

Durante la deserializzazione, `Newtonsoft.Json` la corrispondenza dei nomi di proprietà senza distinzione tra maiuscole e minuscole per impostazione predefinita. Per <xref:System.Text.Json> impostazione predefinita viene applicata la distinzione tra maiuscole e minuscole, che offre prestazioni migliori in quanto esegue una corrispondenza esatta. Per informazioni su come eseguire la corrispondenza senza distinzione tra maiuscole e minuscole, vedere [corrispondenza di proprietà senza distinzione tra maiuscole](system-text-json-how-to.md#case-insensitive-property-matching)e minuscole.

Se si usa `System.Text.Json` indirettamente usando ASP.NET Core, non è necessario eseguire alcuna operazione per ottenere un comportamento simile a `Newtonsoft.Json` . ASP.NET Core specifica le impostazioni per i [nomi di proprietà di maiuscole](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) e minuscole e la corrispondenza senza distinzione tra maiuscole e minuscole quando usa `System.Text.Json` .

### <a name="minimal-character-escaping"></a>Escape di caratteri minimo

Durante la serializzazione, `Newtonsoft.Json` è relativamente permissivo per consentire i caratteri senza eseguirne l'escape. Ovvero non li sostituisce con `\uxxxx` Where `xxxx` è il punto di codice del carattere. Se viene eseguita l'escape, viene creato un oggetto `\` prima del carattere (ad esempio, `"` diventa `\"` ). <xref:System.Text.Json>per impostazione predefinita, in vengono usati caratteri di escape per più caratteri per offrire protezioni di difesa in profondità contro gli attacchi XSS (cross-site scripting) o la divulgazione di informazioni, usando la sequenza di sei caratteri. `System.Text.Json`per impostazione predefinita, in vengono utilizzati caratteri di escape per tutti i caratteri non ASCII, pertanto non è necessario eseguire alcuna operazione se si utilizza `StringEscapeHandling.EscapeNonAscii` in `Newtonsoft.Json` . `System.Text.Json`per impostazione predefinita, inoltre, vengono ignorati i caratteri sensibili all'HTML. Per informazioni su come eseguire l'override del `System.Text.Json` comportamento predefinito, vedere [personalizzare la codifica dei caratteri](system-text-json-how-to.md#customize-character-encoding).

### <a name="comments"></a>Commenti

Durante la deserializzazione, `Newtonsoft.Json` Ignora i commenti in JSON per impostazione predefinita. Per <xref:System.Text.Json> impostazione predefinita, vengono generate eccezioni per i commenti, perché la specifica [RFC 8259](https://tools.ietf.org/html/rfc8259) non le include. Per informazioni su come consentire i commenti, vedere [Consenti commenti e virgole finali](system-text-json-how-to.md#allow-comments-and-trailing-commas).

### <a name="trailing-commas"></a>Virgole finali

Durante la deserializzazione, `Newtonsoft.Json` Ignora le virgole finali per impostazione predefinita. Ignora inoltre più virgole finali (ad esempio, `[{"Color":"Red"},{"Color":"Green"},,]` ). Per <xref:System.Text.Json> impostazione predefinita, vengono generate eccezioni per le virgole finali perché la specifica [RFC 8259](https://tools.ietf.org/html/rfc8259) non le consente. Per informazioni su come effettuare l' `System.Text.Json` accettazione, vedere [consentire i commenti e le virgole finali](system-text-json-how-to.md#allow-comments-and-trailing-commas). Non è possibile consentire più virgole finali.

### <a name="converter-registration-precedence"></a>Precedenza di registrazione del convertitore

La `Newtonsoft.Json` precedenza di registrazione per i convertitori personalizzati è la seguente:

* Attributo sulla proprietà
* Attributo sul tipo
* Raccolta [Converters](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)

Questo ordine indica che un convertitore personalizzato nella `Converters` raccolta viene sottoposto a override da un convertitore registrato applicando un attributo a livello di tipo. Entrambe le registrazioni vengono sottoposte a override da un attributo a livello di proprietà.

La <xref:System.Text.Json> precedenza di registrazione per i convertitori personalizzati è diversa:

* Attributo sulla proprietà
* <xref:System.Text.Json.JsonSerializerOptions.Converters>raccolta
* Attributo sul tipo

La differenza è che un convertitore personalizzato nella `Converters` raccolta esegue l'override di un attributo a livello di tipo. L'intenzione alla base di questo ordine di precedenza consiste nel fare in modo che le modifiche in fase di esecuzione sostituiscano le scelte della fase di progettazione. Non è possibile modificare la precedenza.

Per altre informazioni sulla registrazione di un convertitore personalizzato, vedere [registrare un convertitore personalizzato](system-text-json-converters-how-to.md#register-a-custom-converter).

### <a name="maximum-depth"></a>Profondità massima

`Newtonsoft.Json`per impostazione predefinita, non ha un limite di profondità massimo. Per <xref:System.Text.Json> esiste un limite predefinito di 64 ed è configurabile impostando <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType> .

### <a name="json-strings-property-names-and-string-values"></a>Stringhe JSON (nomi di proprietà e valori di stringa)

Durante la deserializzazione, `Newtonsoft.Json` accetta i nomi di proprietà racchiusi tra virgolette doppie, virgolette singole o senza virgolette. Accetta valori stringa racchiusi tra virgolette doppie o virgolette singole. Ad esempio, `Newtonsoft.Json` accetta il codice JSON seguente:

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json`accetta solo nomi di proprietà e valori stringa tra virgolette doppie perché tale formato è richiesto dalla specifica [RFC 8259](https://tools.ietf.org/html/rfc8259) ed è l'unico formato JSON valido.

Un valore racchiuso tra virgolette singole restituisce una [jsonexception](xref:System.Text.Json.JsonException) con il messaggio seguente:

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>Valori non stringa per le proprietà di stringa

`Newtonsoft.Json`accetta valori non stringa, ad esempio un numero o i valori letterali `true` e `false` , per la deserializzazione delle proprietà di tipo String. Di seguito è riportato un esempio di JSON che `Newtonsoft.Json` deserializza correttamente la classe seguente:

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

`System.Text.Json`non deserializza i valori non stringa in proprietà di stringa. Un valore non stringa ricevuto per un campo stringa restituisce un oggetto [jsonexception](xref:System.Text.Json.JsonException) con il messaggio seguente:

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>Scenari che usano JsonSerializer che richiedono soluzioni alternative

Gli scenari seguenti non sono supportati dalla funzionalità incorporata, ma sono possibili soluzioni alternative. Le soluzioni alternative sono [convertitori personalizzati](system-text-json-converters-how-to.md), che potrebbero non fornire una parità completa con la `Newtonsoft.Json` funzionalità. Per alcuni di questi esempi, il codice di esempio viene fornito come esempio. Se si usano queste `Newtonsoft.Json` funzionalità, la migrazione richiederà modifiche ai modelli a oggetti .NET o ad altre modifiche al codice.

### <a name="types-without-built-in-support"></a>Tipi senza supporto incorporato

<xref:System.Text.Json>non fornisce il supporto incorporato per i tipi seguenti:

* <xref:System.Data.DataTable>e tipi correlati
* Tipi F #, ad esempio [unioni discriminate](../../fsharp/language-reference/discriminated-unions.md), [tipi di record](../../fsharp/language-reference/records.md)e [tipi di record anonimi](../../fsharp/language-reference/anonymous-records.md).
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple>e i tipi generici associati

I convertitori personalizzati possono essere implementati per i tipi che non dispongono del supporto incorporato.

### <a name="quoted-numbers"></a>Numeri tra virgolette

`Newtonsoft.Json`consente di serializzare o deserializzare numeri rappresentati da stringhe JSON (racchiusi tra virgolette). Ad esempio, può accettare: `{"DegreesCelsius":"23"}` anziché `{"DegreesCelsius":23}` . Per abilitare questo comportamento in <xref:System.Text.Json> , implementare un convertitore personalizzato come l'esempio seguente. Il convertitore gestisce le proprietà definite come segue `long` :

* Li serializza come stringhe JSON.
* Accetta numeri e numeri JSON racchiusi tra virgolette durante la deserializzazione.

[!code-csharp[](snippets/system-text-json-how-to/csharp/LongToStringConverter.cs)]

Registrare questo convertitore personalizzato [usando un attributo](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) `long` per le singole proprietà o [aggiungendo il convertitore](system-text-json-converters-how-to.md#registration-sample---converters-collection) alla <xref:System.Text.Json.JsonSerializerOptions.Converters> raccolta.

### <a name="dictionary-with-non-string-key"></a>Dizionario con chiave non di stringa

`Newtonsoft.Json`supporta raccolte di tipo `Dictionary<TKey, TValue>` . Il supporto incorporato per le raccolte dizionario in <xref:System.Text.Json> è limitato a `Dictionary<string, TValue>` . Ovvero la chiave deve essere una stringa.

Per supportare un dizionario con un Integer o un altro tipo come chiave, creare un convertitore come l'esempio in [come scrivere convertitori personalizzati](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).

### <a name="polymorphic-serialization"></a>Serializzazione polimorfica

`Newtonsoft.Json`esegue automaticamente la serializzazione polimorfica. Per informazioni sulle funzionalità di serializzazione polimorfiche limitate di <xref:System.Text.Json> , vedere [serializzare le proprietà delle classi derivate](system-text-json-how-to.md#serialize-properties-of-derived-classes).

La soluzione alternativa descritta è la definizione di proprietà che possono contenere classi derivate come tipo `object` . Se ciò non è possibile, un'altra opzione consiste nel creare un convertitore con un `Write` metodo per l'intera gerarchia dei tipi di ereditarietà, come l'esempio in [come scrivere convertitori personalizzati](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="polymorphic-deserialization"></a>Deserializzazione polimorfica

`Newtonsoft.Json`dispone `TypeNameHandling` di un'impostazione che aggiunge metadati del nome del tipo al JSON durante la serializzazione. USA i metadati durante la deserializzazione per eseguire la deserializzazione polimorfica. <xref:System.Text.Json>consente di eseguire un intervallo limitato di [serializzazione polimorfica](system-text-json-how-to.md#serialize-properties-of-derived-classes) , ma non di deserializzazione polimorfica.

Per supportare la deserializzazione polimorfica, creare un convertitore come l'esempio in [come scrivere convertitori personalizzati](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="deserialization-of-object-properties"></a>Deserializzazione di proprietà dell'oggetto

Quando `Newtonsoft.Json` viene deserializzato in, viene eseguita una delle operazioni seguenti <xref:System.Object> :

* Deduce il tipo di valori primitivi nel payload JSON (diverso da `null` ) e restituisce l'oggetto archiviato `string` ,,, `long` `double` `boolean` o `DateTime` come oggetto boxed. *I valori primitivi* sono valori JSON singoli, ad esempio un numero JSON, una stringa, `true` , `false` o `null` .
* Restituisce un oggetto `JObject` o `JArray` per i valori complessi nel payload JSON. *I valori complessi* sono raccolte di coppie chiave-valore JSON racchiuse tra parentesi graffe ( `{}` ) o elenchi di valori racchiusi tra parentesi quadre ( `[]` ). Le proprietà e i valori tra parentesi graffe o parentesi quadre possono avere proprietà o valori aggiuntivi.
* Restituisce un riferimento null quando il payload presenta il `null` valore letterale JSON.

<xref:System.Text.Json>Archivia un oggetto boxed `JsonElement` per i valori primitivi e complessi ogni volta che si esegue la deserializzazione in <xref:System.Object> , ad esempio:

* Proprietà `object`.
* `object`Valore del dizionario.
* `object`Valore di matrice.
* Oggetto radice `object` .

Tuttavia, `System.Text.Json` tratta `null` lo stesso di `Newtonsoft.Json` e restituisce un riferimento null quando il payload contiene il `null` valore letterale JSON.

Per implementare l'inferenza del tipo per `object` le proprietà, creare un convertitore come l'esempio in [come scrivere convertitori personalizzati](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).

### <a name="deserialize-null-to-non-nullable-type"></a>Deserializzazione di valori null in un tipo non nullable

`Newtonsoft.Json`non genera un'eccezione nello scenario seguente:

* `NullValueHandling`è impostato su `Ignore` e
* Durante la deserializzazione, il codice JSON contiene un valore null per un tipo di valore non nullable.

Nello stesso scenario, <xref:System.Text.Json> genera un'eccezione. L'impostazione di gestione dei valori null corrispondente è <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> .

Se si è proprietari del tipo di destinazione, la soluzione migliore consiste nel rendere la proprietà in questione Nullable (ad esempio, modificare `int` in `int?` ).

Un'altra soluzione alternativa consiste nel creare un convertitore per il tipo, ad esempio l'esempio seguente che gestisce i valori null per i `DateTimeOffset` tipi:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DateTimeOffsetNullHandlingConverter.cs)]

Registrare questo convertitore personalizzato [usando un attributo nella proprietà](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) o [aggiungendo il convertitore](system-text-json-converters-how-to.md#registration-sample---converters-collection) alla <xref:System.Text.Json.JsonSerializerOptions.Converters> raccolta.

**Nota:** Il convertitore precedente **gestisce i valori null in modo diverso** rispetto `Newtonsoft.Json` a quelli di poco che specificano valori predefiniti. Si supponga, ad esempio, che il codice seguente rappresenti l'oggetto di destinazione:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Si supponga che il codice JSON seguente venga deserializzato usando il convertitore precedente:

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Dopo la deserializzazione, la `Date` proprietà dispone di 1/1/0001 ( `default(DateTimeOffset)` ), ovvero il valore impostato nel costruttore viene sovrascritto. Dato lo stesso POCO e JSON, `Newtonsoft.Json` la deserializzazione lascia 1/1/2001 nella `Date` Proprietà.

### <a name="deserialize-to-immutable-classes-and-structs"></a>Deserializzare in classi e struct non modificabili

`Newtonsoft.Json`può deserializzare in classi e struct non modificabili perché può usare costruttori con parametri. <xref:System.Text.Json>supporta solo costruttori pubblici senza parametri. Come soluzione alternativa, è possibile chiamare un costruttore con parametri in un convertitore personalizzato.

Di seguito è riportato uno struct non modificabile con più parametri del costruttore:

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePoint.cs#ImmutablePoint)]

Ecco un convertitore che serializza e deserializza questo struct:

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePointConverter.cs)]

Registrare questo convertitore personalizzato [aggiungendo il convertitore](system-text-json-converters-how-to.md#registration-sample---converters-collection) alla <xref:System.Text.Json.JsonSerializerOptions.Converters> raccolta.

Per un esempio di convertitore analogo che gestisce le proprietà generiche aperte, vedere il [convertitore predefinito per le coppie chiave-valore](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).

### <a name="specify-constructor-to-use"></a>Specificare il costruttore da usare

L' `Newtonsoft.Json` `[JsonConstructor]` attributo consente di specificare il costruttore da chiamare durante la deserializzazione in un oggetto poco. <xref:System.Text.Json>supporta solo costruttori senza parametri. Come soluzione alternativa, è possibile chiamare qualsiasi costruttore necessario in un convertitore personalizzato. Vedere l'esempio per [deserializzare in classi e struct non modificabili](#deserialize-to-immutable-classes-and-structs).

### <a name="required-properties"></a>Proprietà obbligatorie

In `Newtonsoft.Json` è possibile specificare che una proprietà è obbligatoria impostando `Required` sull' `[JsonProperty]` attributo. `Newtonsoft.Json`genera un'eccezione se non viene ricevuto alcun valore nel codice JSON per una proprietà contrassegnata come obbligatoria.

<xref:System.Text.Json>non genera un'eccezione se non viene ricevuto alcun valore per una delle proprietà del tipo di destinazione. Ad esempio, se si dispone di una `WeatherForecast` classe:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

Il codice JSON seguente viene deserializzato senza errori:

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

Per rendere la deserializzazione non riuscita se non è presente alcuna `Date` proprietà nel codice JSON, implementare un convertitore personalizzato. Il codice del convertitore di esempio seguente genera un'eccezione se la proprietà non è impostata al termine della `Date` deserializzazione:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverter.cs)]

Registrare questo convertitore personalizzato [aggiungendo il convertitore](system-text-json-converters-how-to.md#registration-sample---converters-collection) alla <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> raccolta.

Questo modello di chiamata ricorsiva del convertitore richiede la registrazione del convertitore tramite <xref:System.Text.Json.JsonSerializerOptions> , non tramite un attributo. Se si registra il convertitore usando un attributo, il convertitore personalizzato esegue una chiamata in modo ricorsivo a se stesso. Il risultato è un ciclo infinito che termina in un'eccezione di overflow dello stack.

Quando si registra il convertitore usando l'oggetto options, evitare un ciclo infinito senza passare l'oggetto Options quando si chiama o in modo ricorsivo <xref:System.Text.Json.JsonSerializer.Serialize%2A> <xref:System.Text.Json.JsonSerializer.Deserialize%2A> . L'oggetto options contiene la <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> raccolta. Se lo si passa a `Serialize` o `Deserialize` , il convertitore personalizzato chiama se stesso, rendendo un ciclo infinito che restituisce un'eccezione di overflow dello stack. Se le opzioni predefinite non sono realizzabili, creare una nuova istanza delle opzioni con le impostazioni necessarie. Questo approccio sarà lento perché ogni nuova istanza viene memorizzata nella cache in modo indipendente.

È disponibile un modello alternativo che può usare `JsonConverterAttribute` la registrazione per la classe da convertire. Con questo approccio, il codice del convertitore chiama `Serialize` o `Deserialize` su una classe che deriva dalla classe da convertire. Alla classe derivata non è applicato alcun oggetto `JsonConverterAttribute` . Nell'esempio seguente di questa alternativa:

* `WeatherForecastWithRequiredPropertyConverterAttribute`è la classe da deserializzare e a cui è `JsonConverterAttribute` applicato.
* `WeatherForecastWithoutRequiredPropertyConverterAttribute`è la classe derivata che non dispone dell'attributo Converter.
* Il codice nel convertitore chiama `Serialize` e `Deserialize` on `WeatherForecastWithoutRequiredPropertyConverterAttribute` per evitare un ciclo infinito. Questo approccio comporta un costo in termini di prestazioni per la serializzazione a causa della creazione di un'istanza di oggetto aggiuntiva e della copia dei valori delle proprietà.

Di seguito sono riportati i `WeatherForecast*` tipi:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithReqPptyConverterAttr)]

Ecco il convertitore:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverterForAttributeRegistration.cs)]

Il convertitore di proprietà necessario richiede una logica aggiuntiva se è necessario gestire attributi come [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) o opzioni diverse, ad esempio i codificatori personalizzati. Il codice di esempio non gestisce inoltre le proprietà per le quali viene impostato un valore predefinito nel costruttore. Questo approccio non distingue gli scenari seguenti:

* Una proprietà non è presente in JSON.
* Una proprietà per un tipo che non ammette i valori null è presente nel codice JSON, ma il valore è l'impostazione predefinita per il tipo, ad esempio zero per un oggetto `int` .
* In JSON è presente una proprietà per un tipo di valore Nullable, ma il valore è null.

### <a name="conditionally-ignore-a-property"></a>Ignorare una proprietà in modo condizionale

`Newtonsoft.Json`in sono disponibili diversi modi per ignorare in modo condizionale una proprietà durante la serializzazione o la deserializzazione:

* `DefaultContractResolver`consente di selezionare le proprietà da includere o escludere, in base a criteri arbitrari.
* Le `NullValueHandling` `DefaultValueHandling` Impostazioni e in `JsonSerializerSettings` consentono di specificare che tutte le proprietà con valore null o valore predefinito devono essere ignorate.
* Le `NullValueHandling` Impostazioni e nell' `DefaultValueHandling` `[JsonProperty]` attributo consentono di specificare le singole proprietà che devono essere ignorate se impostate su null o sul valore predefinito.

<xref:System.Text.Json>in sono disponibili i metodi seguenti per omettere le proprietà durante la serializzazione:

* L'attributo [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) in una proprietà causa l'omissione della proprietà da JSON durante la serializzazione.
* L'opzione globale [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) consente di escludere tutte le proprietà con valore null.
* L'opzione globale [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) consente di escludere tutte le proprietà di sola lettura.

Queste opzioni **non** consentono di:

* Ignorare tutte le proprietà che hanno il valore predefinito per il tipo.
* Ignora le proprietà selezionate che hanno il valore predefinito per il tipo.
* Ignora le proprietà selezionate se il relativo valore è null.
* Ignora le proprietà selezionate in base ai criteri arbitrari valutati in fase di esecuzione.

Per questa funzionalità, è possibile scrivere un convertitore personalizzato. Ecco un esempio POCO e un convertitore personalizzato che illustra questo approccio:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

Il convertitore fa `Summary` in modo che la proprietà venga omessa dalla serializzazione se il relativo valore è null, una stringa vuota o "N/A".

Registrare questo convertitore personalizzato [usando un attributo della classe](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) oppure [aggiungendo il convertitore](system-text-json-converters-how-to.md#registration-sample---converters-collection) alla <xref:System.Text.Json.JsonSerializerOptions.Converters> raccolta.

Questo approccio richiede una logica aggiuntiva se:

* Il POCO include proprietà complesse.
* È necessario gestire attributi come `[JsonIgnore]` o opzioni come i codificatori personalizzati.

### <a name="specify-date-format"></a>Specificare il formato della data

`Newtonsoft.Json`in sono disponibili diversi modi per controllare il modo in cui le proprietà dei `DateTime` `DateTimeOffset` tipi e vengono serializzate e deserializzate:

* L' `DateTimeZoneHandling` impostazione può essere utilizzata per serializzare tutti `DateTime` i valori come date UTC.
* L' `DateFormatString` impostazione e i `DateTime` convertitori possono essere usati per personalizzare il formato delle stringhe di data.

In <xref:System.Text.Json> , l'unico formato con supporto incorporato è ISO 8601-1:2019 poiché è ampiamente adottato, non ambiguo, ed esegue con precisione i round trip. Per utilizzare qualsiasi altro formato, creare un convertitore personalizzato. Per ulteriori informazioni, vedere il [supporto di DateTime e System.Text.Json DateTimeOffset in ](../datetime/system-text-json-support.md).

### <a name="callbacks"></a>Callback

`Newtonsoft.Json`consente di eseguire codice personalizzato in diversi punti del processo di serializzazione o deserializzazione:

* OnDeserializing (quando si inizia a deserializzare un oggetto)
* OnDeserialized (al termine della deserializzazione di un oggetto)
* Onserialize (quando si inizia a serializzare un oggetto)
* OnSerialized (al termine della serializzazione di un oggetto)

In <xref:System.Text.Json> è possibile simulare i callback scrivendo un convertitore personalizzato. Nell'esempio seguente viene illustrato un convertitore personalizzato per un oggetto POCO. Il convertitore include codice che visualizza un messaggio in corrispondenza di ogni punto che corrisponde a un `Newtonsoft.Json` callback.

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastCallbacksConverter.cs)]

Registrare questo convertitore personalizzato [usando un attributo della classe](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) oppure [aggiungendo il convertitore](system-text-json-converters-how-to.md#registration-sample---converters-collection) alla <xref:System.Text.Json.JsonSerializerOptions.Converters> raccolta.

Se si usa un convertitore personalizzato che segue l'esempio precedente:

* Il `OnDeserializing` codice non ha accesso alla nuova istanza poco. Per modificare la nuova istanza POCO all'inizio della deserializzazione, inserire il codice nel costruttore POCO.
* Evitare un ciclo infinito registrando il convertitore nell'oggetto Options e non passando l'oggetto Options quando si chiama o in modo ricorsivo `Serialize` `Deserialize` . Per altre informazioni, vedere la sezione [proprietà obbligatorie](#required-properties) più indietro in questo articolo.

### <a name="public-and-non-public-fields"></a>Campi pubblici e non pubblici

`Newtonsoft.Json`consente di serializzare e deserializzare campi e proprietà. <xref:System.Text.Json>funziona solo con proprietà pubbliche. I convertitori personalizzati possono fornire questa funzionalità.

### <a name="internal-and-private-property-setters-and-getters"></a>Metodi setter e getter delle proprietà interne e private

`Newtonsoft.Json`può usare metodi setter e getter di proprietà privati e interni tramite l' `JsonProperty` attributo. <xref:System.Text.Json>supporta solo Setter pubblici. I convertitori personalizzati possono fornire questa funzionalità.

### <a name="populate-existing-objects"></a>Popola oggetti esistenti

Il `JsonConvert.PopulateObject` metodo in `Newtonsoft.Json` deserializza un documento JSON in un'istanza esistente di una classe, anziché creare una nuova istanza. <xref:System.Text.Json>Crea sempre una nuova istanza del tipo di destinazione usando il costruttore pubblico senza parametri predefinito. I convertitori personalizzati possono eseguire la deserializzazione in un'istanza esistente.

### <a name="reuse-rather-than-replace-properties"></a>Riutilizza anziché sostituire le proprietà

L' `Newtonsoft.Json` `ObjectCreationHandling` impostazione consente di specificare che gli oggetti nelle proprietà devono essere riutilizzati anziché sostituiti durante la deserializzazione. <xref:System.Text.Json>sostituisce sempre gli oggetti nelle proprietà.  I convertitori personalizzati possono fornire questa funzionalità.

### <a name="add-to-collections-without-setters"></a>Aggiungi a raccolte senza Setter

Durante la deserializzazione, `Newtonsoft.Json` aggiunge oggetti a una raccolta anche se la proprietà non dispone di un metodo di impostazione. <xref:System.Text.Json>Ignora le proprietà che non hanno Setter. I convertitori personalizzati possono fornire questa funzionalità.

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>Scenari attualmente non supportati da JsonSerializer

Per gli scenari seguenti, le soluzioni alternative non sono pratiche o possibili. Se si usano queste `Newtonsoft.Json` funzionalità, la migrazione non sarà possibile senza modifiche significative.

### <a name="preserve-object-references-and-handle-loops"></a>Mantieni i riferimenti agli oggetti e i cicli di handle

Per impostazione predefinita, `Newtonsoft.Json` serializza per valore. Se, ad esempio, un oggetto contiene due proprietà che contengono un riferimento allo stesso `Person` oggetto, i valori delle proprietà di tale `Person` oggetto vengono duplicati in JSON.

`Newtonsoft.Json`dispone di un' `PreserveReferencesHandling` impostazione in `JsonSerializerSettings` che consente di serializzare per riferimento:

* I metadati dell'identificatore vengono aggiunti al file JSON creato per il primo `Person` oggetto.
* Il codice JSON creato per il secondo `Person` oggetto contiene un riferimento a tale identificatore invece dei valori delle proprietà.

`Newtonsoft.Json`dispone inoltre di un' `ReferenceLoopHandling` impostazione che consente di ignorare i riferimenti circolari anziché generare un'eccezione.

<xref:System.Text.Json>supporta solo la serializzazione per valore e genera un'eccezione per i riferimenti circolari.

### <a name="systemruntimeserialization-attributes"></a>Attributi System. Runtime. Serialization

<xref:System.Text.Json>non supporta gli attributi dello `System.Runtime.Serialization` spazio dei nomi, ad esempio `DataMemberAttribute` e `IgnoreDataMemberAttribute` .

### <a name="octal-numbers"></a>Numeri ottali

`Newtonsoft.Json`Considera i numeri con uno zero iniziali come numeri ottali. <xref:System.Text.Json>non consente zeri iniziali perché la specifica [RFC 8259](https://tools.ietf.org/html/rfc8259) non li consente.

### <a name="missingmemberhandling"></a>MissingMemberHandling

`Newtonsoft.Json`può essere configurato in modo da generare eccezioni durante la deserializzazione se il codice JSON include proprietà mancanti nel tipo di destinazione. <xref:System.Text.Json>Ignora le proprietà aggiuntive in JSON, tranne quando si usa l' [attributo [JsonExtensionData]](system-text-json-how-to.md#handle-overflow-json). Non esiste alcuna soluzione per la funzionalità membro mancante.

### <a name="tracewriter"></a>TraceWriter

`Newtonsoft.Json`consente di eseguire il debug utilizzando un `TraceWriter` per visualizzare i log generati dalla serializzazione o deserializzazione. <xref:System.Text.Json>non esegue la registrazione.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>JsonDocument e Jsonelement rispetto a JToken (ad esempio, JObject, JArray)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName>offre la possibilità di analizzare e compilare un Document Object Model di **sola lettura** (Dom) dai payload JSON esistenti. Il DOM fornisce l'accesso casuale ai dati in un payload JSON. È possibile accedere agli elementi JSON che compongono il payload tramite il <xref:System.Text.Json.JsonElement> tipo. Il `JsonElement` tipo fornisce API per convertire il testo JSON in tipi .NET comuni. `JsonDocument`espone una <xref:System.Text.Json.JsonDocument.RootElement> Proprietà.

### <a name="jsondocument-is-idisposable"></a>JsonDocument è IDisposable

`JsonDocument`Compila una visualizzazione in memoria dei dati in un buffer in pool. Pertanto, a differenza `JObject` `JArray` di o da `Newtonsoft.Json` , il `JsonDocument` tipo implementa `IDisposable` e deve essere utilizzato all'interno di un blocco using.

Restituire un oggetto `JsonDocument` dall'API solo se si vuole trasferire la proprietà della durata ed eliminare la responsabilità per il chiamante. Nella maggior parte degli scenari non è necessario. Se il chiamante deve usare l'intero documento JSON, restituire l'oggetto <xref:System.Text.Json.JsonElement.Clone%2A> di <xref:System.Text.Json.JsonDocument.RootElement%2A> , che è un <xref:System.Text.Json.JsonElement> . Se il chiamante deve usare un elemento specifico all'interno del documento JSON, restituire l'oggetto <xref:System.Text.Json.JsonElement.Clone%2A> di <xref:System.Text.Json.JsonElement> . Se si restituisce l'oggetto `RootElement` o un sottoelemento direttamente senza eseguire un'attività `Clone` , il chiamante non sarà in grado di accedere all'oggetto restituito `JsonElement` dopo `JsonDocument` che il proprietario è stato eliminato.

Di seguito è riportato un esempio che richiede di creare un `Clone` :

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

Il codice precedente prevede un oggetto `JsonElement` che contiene una `fileName` Proprietà. Viene aperto il file JSON e viene creato un oggetto `JsonDocument` . Il metodo presuppone che il chiamante voglia lavorare con l'intero documento, quindi restituisce l'oggetto `Clone` di `RootElement` .

Se si riceve una `JsonElement` classe e si restituisce un sottoelemento, non è necessario restituire un oggetto `Clone` del sottoelemento. Il chiamante è responsabile di mantenere attivo l'oggetto `JsonDocument` a cui appartiene l'oggetto passato `JsonElement` . ad esempio:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>JsonDocument è di sola lettura

Il <xref:System.Text.Json> Dom non può aggiungere, rimuovere o modificare elementi JSON. Questo metodo è progettato per le prestazioni e per ridurre le allocazioni per l'analisi di dimensioni del payload JSON comuni (ovvero < 1 MB). Se lo scenario usa attualmente un DOM modificabile, potrebbe essere possibile una delle soluzioni alternative seguenti:

* Per creare un oggetto `JsonDocument` da zero (ovvero senza passare un payload JSON esistente al `Parse` metodo), scrivere il testo JSON usando `Utf8JsonWriter` e analizzare l'output da tale per creare un nuovo oggetto `JsonDocument` .
* Per modificare una esistente `JsonDocument` , usarla per scrivere testo JSON, apportare modifiche durante la scrittura e analizzare l'output da tale per creare un nuovo `JsonDocument` .
* Per unire i documenti JSON esistenti, equivalenti `JObject.Merge` alle `JContainer.Merge` API o da `Newtonsoft.Json` , vedere [questo problema di GitHub](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).

### <a name="jsonelement-is-a-union-struct"></a>Jsonelement è uno struct Unione

`JsonDocument`espone l'oggetto `RootElement` come una proprietà di tipo <xref:System.Text.Json.JsonElement> , che è un tipo di struct Unione che comprende qualsiasi elemento JSON. `Newtonsoft.Json`USA tipi gerarchici dedicati come `JObject` , `JArray` , `JToken` e così via. `JsonElement`è ciò che è possibile ricercare ed enumerare ed è possibile usare `JsonElement` per materializzare gli elementi JSON in tipi .NET.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>Come eseguire una ricerca in JsonDocument e Jsonelement per sottoelementi

Cerca i token JSON usando `JObject` o `JArray` da `Newtonsoft.Json` tendono a essere relativamente veloci perché sono ricerche in un dizionario. Per confronto, le ricerche in `JsonElement` richiedono una ricerca sequenziale delle proprietà e pertanto sono relativamente lente, ad esempio quando si usa `TryGetProperty` . <xref:System.Text.Json>è progettato per ridurre al minimo il tempo di analisi iniziale anziché il tempo di ricerca. Pertanto, utilizzare gli approcci seguenti per ottimizzare le prestazioni durante la ricerca in un `JsonDocument` oggetto:

* Usare gli enumeratori predefiniti ( <xref:System.Text.Json.JsonElement.EnumerateArray%2A> e <xref:System.Text.Json.JsonElement.EnumerateObject%2A> ) invece di eseguire l'indicizzazione o i cicli.
* Non eseguire una ricerca sequenziale interamente `JsonDocument` attraverso ogni proprietà tramite `RootElement` . Cercare invece oggetti JSON annidati in base alla struttura nota dei dati JSON. Se, ad esempio, si sta cercando una `Grade` proprietà negli `Student` oggetti, eseguire il ciclo degli `Student` oggetti e ottenere il valore di `Grade` per ognuno, invece di cercare tutti `JsonElement` gli oggetti che cercano `Grade` Proprietà. Se si esegue quest'ultimo, il passaggio non è necessario per gli stessi dati.

Per un esempio di codice, vedere [usare JsonDocument per l'accesso ai dati](system-text-json-how-to.md#use-jsondocument-for-access-to-data).

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Utf8JsonReader rispetto a JsonTextReader

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>è un reader ad alte prestazioni, a bassa allocazione e di solo invio per testo JSON con codifica UTF-8, letto da [un \<byte> ReadOnlySpan](xref:System.ReadOnlySpan%601) o [ReadOnlySequence \<byte> ](xref:System.Buffers.ReadOnlySequence%601). `Utf8JsonReader`È un tipo di basso livello che può essere utilizzato per compilare parser e deserializzatori personalizzati.

Le sezioni seguenti illustrano i modelli di programmazione consigliati per l'uso di `Utf8JsonReader` .

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader è uno struct di riferimento

Poiché il `Utf8JsonReader` tipo è uno *struct Ref*, presenta [alcune limitazioni](../../csharp/language-reference/builtin-types/struct.md#ref-struct). Ad esempio, non può essere archiviato come campo in una classe o uno struct diverso da uno struct Ref. Per ottenere prestazioni elevate, questo tipo deve essere un dato che deve `ref struct` memorizzare nella cache [il \<byte> ReadOnlySpan](xref:System.ReadOnlySpan%601)di input, che a sua volta è uno struct Ref. Inoltre, questo tipo è modificabile perché include lo stato. Quindi, **passarlo per Ref** anziché per valore. Il passaggio per valore comporterebbe una copia dello struct e le modifiche dello stato non sarebbero visibili al chiamante. Questo comportamento è diverso da `Newtonsoft.Json` perché `Newtonsoft.Json` `JsonTextReader` è una classe. Per altre informazioni su come usare gli struct di riferimento, vedere [scrivere codice C# sicuro ed efficiente](../../csharp/write-safe-efficient-code.md).

### <a name="read-utf-8-text"></a>Leggi testo UTF-8

Per ottenere le migliori prestazioni possibili durante l'uso di `Utf8JsonReader` , leggere i payload JSON già codificati come testo UTF-8 anziché come stringhe UTF-16. Per un esempio di codice, vedere [filtrare i dati usando Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).

### <a name="read-with-a-stream-or-pipereader"></a>Lettura con un flusso o PipeReader

`Utf8JsonReader`Supporta la lettura da un [ReadOnlySpan \<byte> ](xref:System.ReadOnlySpan%601) o [ReadOnlySequence \<byte> ](xref:System.Buffers.ReadOnlySequence%601) con codifica UTF-8 (che è il risultato della lettura da un <xref:System.IO.Pipelines.PipeReader> ).

Per la lettura sincrona, è possibile leggere il payload JSON fino alla fine del flusso in una matrice di byte e passarlo al lettore. Per la lettura da una stringa (codificata come UTF-16), chiamare <xref:System.Text.Encoding.UTF8> .<xref:System.Text.Encoding.GetBytes%2A> per innanzitutto transcodificare la stringa in una matrice di byte con codifica UTF-8. Passare quindi a `Utf8JsonReader` .

Poiché `Utf8JsonReader` considera l'input come testo JSON, un byte order mark (BOM) UTF-8 viene considerato JSON non valido. Il chiamante deve filtrare il timeout prima di passare i dati al lettore.

Per esempi di codice, vedere [usare Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).

### <a name="read-with-multi-segment-readonlysequence"></a>Leggi con ReadOnlySequence multisegmento

Se l'input JSON è un [ReadOnlySpan \<byte> ](xref:System.ReadOnlySpan%601), è possibile accedere a ogni elemento JSON dalla `ValueSpan` proprietà nel lettore mentre si passa attraverso il ciclo di lettura. Tuttavia, se l'input è un [ReadOnlySequence \<byte> ](xref:System.Buffers.ReadOnlySequence%601) (che è il risultato della lettura da un <xref:System.IO.Pipelines.PipeReader> ), alcuni elementi JSON potrebbero risiedere in più segmenti dell' `ReadOnlySequence<byte>` oggetto. Questi elementi non saranno accessibili da <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> in un blocco di memoria contigua. Al contrario, ogni volta che si dispone di un multisegmento `ReadOnlySequence<byte>` come input, eseguire il polling della <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> proprietà sul Reader per capire come accedere all'elemento JSON corrente. Ecco un modello consigliato:

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

Non usare <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> per eseguire confronti byte per byte chiamando per le <xref:System.MemoryExtensions.SequenceEqual%2A> ricerche del nome di proprietà. Chiamare <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> invece, perché il metodo esegue l'escape di tutti i caratteri di escape in JSON. Ecco un esempio che illustra come cercare una proprietà denominata "Name":

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>Lettura di valori null in tipi di valore Nullable

`Newtonsoft.Json`fornisce le API che restituiscono <xref:System.Nullable%601> , ad esempio `ReadAsBoolean` , che gestisce un oggetto `Null` `TokenType` per l'utente restituendo `bool?` . Le `System.Text.Json` API predefinite restituiscono solo tipi di valore non nullable. Ad esempio, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> restituisce `bool` . Genera un'eccezione se trova `Null` in JSON. Negli esempi seguenti vengono illustrati due modi per gestire i valori null, uno restituendo un tipo di valore nullable e l'altro restituendo il valore predefinito:

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

Se è necessario continuare a usare `Newtonsoft.Json` per determinati Framework di destinazione, è possibile usare più destinazioni e due implementazioni. Tuttavia, questo non è semplice e richiede una `#ifdefs` duplicazione del codice sorgente. Un modo per condividere il maggior quantità possibile di codice consiste nel creare un `ref struct` wrapper per `Utf8JsonReader` e `Newtonsoft.Json` `JsonTextReader` . Questo wrapper unifica la superficie pubblica, isolando le differenze di comportamento. In questo modo è possibile isolare le modifiche principalmente alla costruzione del tipo, insieme al passaggio del nuovo tipo in base al riferimento. Questo è il modello che segue la libreria [Microsoft. Extensions. DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) :

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Utf8JsonWriter rispetto a JsonTextWriter

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>è un modo a prestazioni elevate per scrivere testo JSON con codifica UTF-8 da tipi .NET comuni come `String` , `Int32` e `DateTime` . Il writer è un tipo di basso livello che può essere utilizzato per compilare serializzatori personalizzati.

Le sezioni seguenti illustrano i modelli di programmazione consigliati per l'uso di `Utf8JsonWriter` .

### <a name="write-with-utf-8-text"></a>Scrivi con testo UTF-8

Per ottenere le migliori prestazioni possibili durante l'uso di `Utf8JsonWriter` , scrivere payload JSON già codificati come testo UTF-8 anziché come stringhe UTF-16. Usare <xref:System.Text.Json.JsonEncodedText> per memorizzare nella cache e pre-codificare i nomi e i valori delle proprietà delle stringhe note come statici e passarli al writer, anziché usare valori letterali stringa UTF-16. Questa operazione è più veloce rispetto alla memorizzazione nella cache e all'utilizzo di matrici di byte UTF-8.

Questo approccio funziona anche se è necessario eseguire l'escape personalizzato. `System.Text.Json`non consente di disabilitare l'escape durante la scrittura di una stringa. Tuttavia, è possibile passare il proprio oggetto personalizzato <xref:System.Text.Encodings.Web.JavaScriptEncoder> come opzione al writer oppure creare un oggetto personalizzato `JsonEncodedText` che usi `JavascriptEncoder` per eseguire l'escape, quindi scrivere il `JsonEncodedText` anziché la stringa. Per altre informazioni, vedere [personalizzare la codifica dei caratteri](system-text-json-how-to.md#customize-character-encoding).

### <a name="write-raw-values"></a>Scrivi valori non elaborati

Il `Newtonsoft.Json` `WriteRawValue` metodo scrive codice JSON non elaborato in cui è previsto un valore. <xref:System.Text.Json>non ha un equivalente diretto, ma ecco una soluzione alternativa che garantisce che venga scritto solo JSON valido:

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>Personalizzare l'escape di caratteri

L'impostazione [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) di `JsonTextWriter` offre opzioni che consentono di eseguire l'escape di tutti i caratteri non ASCII **o** HTML. Per impostazione predefinita, viene preceduto da `Utf8JsonWriter` caratteri di escape per tutti i caratteri non ASCII **e** HTML. Questa operazione di escape viene eseguita per motivi di sicurezza della difesa in profondità. Per specificare criteri di escape diversi, creare un oggetto <xref:System.Text.Encodings.Web.JavaScriptEncoder> e impostare <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType> . Per altre informazioni, vedere [personalizzare la codifica dei caratteri](system-text-json-how-to.md#customize-character-encoding).

### <a name="customize-json-format"></a>Personalizzare il formato JSON

`JsonTextWriter`include le impostazioni seguenti, per le quali `Utf8JsonWriter` non è presente alcun equivalente:

* [Rientro](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) : specifica il numero di caratteri da rientrare. `Utf8JsonWriter`esegue sempre il rientro a 2 caratteri.
* [IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) -specifica il carattere da utilizzare per il rientro.  `Utf8JsonWriter`Usa sempre gli spazi vuoti.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) : specifica il carattere da usare per racchiudere i valori di stringa.  `Utf8JsonWriter`Usa sempre le virgolette doppie.
* [QUOTENAME](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) -specifica se racchiudere o meno i nomi delle proprietà con virgolette.  `Utf8JsonWriter`racchiuderle sempre tra virgolette.

Non esistono soluzioni alternative che consentono di personalizzare il codice JSON prodotto da `Utf8JsonWriter` in questi modi.

### <a name="write-null-values"></a>Scrivi valori null

Per scrivere valori null usando `Utf8JsonWriter` , chiamare:

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A>per scrivere una coppia chiave-valore con null come valore.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A>per scrivere null come elemento di una matrice JSON.

Per una proprietà di stringa, se la stringa è null, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> e <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> sono equivalenti a `WriteNull` e `WriteNullValue` .

### <a name="write-timespan-uri-or-char-values"></a>Scrivere valori TimeSpan, URI o char

`JsonTextWriter`fornisce `WriteValue` metodi per i valori [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [URI](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)e [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) . `Utf8JsonWriter`non ha metodi equivalenti. Formattare invece questi valori come stringhe (chiamando `ToString()` , ad esempio,) e chiamare <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> .

### <a name="multi-targeting"></a>Multitargeting

Se è necessario continuare a usare `Newtonsoft.Json` per determinati Framework di destinazione, è possibile usare più destinazioni e due implementazioni. Tuttavia, questo non è semplice e richiede una `#ifdefs` duplicazione del codice sorgente. Un modo per condividere il maggior quantità possibile di codice consiste nel creare un wrapper per `Utf8JsonWriter` e `Newtonsoft` `JsonTextWriter` . Questo wrapper unifica la superficie pubblica, isolando le differenze di comportamento. In questo modo è possibile isolare le modifiche principalmente alla costruzione del tipo. La libreria [Microsoft. Extensions. DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) segue:

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>Risorse aggiuntive

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [System.Text.JsonPanoramica](system-text-json-overview.md)
* [Come usareSystem.Text.Json](system-text-json-how-to.md)
* [Come scrivere convertitori personalizzati](system-text-json-converters-how-to.md)
* [Supporto di DateTime e DateTimeOffset inSystem.Text.Json](../datetime/system-text-json-support.md)
* [System.Text.JsonRiferimento API](xref:System.Text.Json)
* [System.Text.Json. Riferimento all'API di serializzazione](xref:System.Text.Json.Serialization)
