---
title: Record anonimi
description: Informazioni su come usare la costruzione e l'utilizzo di record anonimi, una funzionalità del linguaggio che consente di modificare i dati.
ms.date: 06/12/2019
ms.openlocfilehash: ef3aa8fccdb6ff406542932816e4138040845a59
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187485"
---
# <a name="anonymous-records"></a>Record anonimi

I record anonimi sono aggregazioni semplici di valori denominati che non devono essere dichiarati prima dell'uso. È possibile dichiararli come struct o tipi di riferimento. Sono tipi di riferimento per impostazione predefinita.

## <a name="syntax"></a>Sintassi

Negli esempi seguenti viene illustrata la sintassi dei record anonimi. Elementi delimitati `[item]` come sono facoltativi.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>Utilizzo di base

I record anonimi sono meglio considerati come tipi di record F , che non è necessario dichiararsi prima della creazione di un'istanza.

Ad esempio, in questo caso è possibile interagire con una funzione che produce un record anonimo:For example, here how you can interact with a function that produces an anonymous record:

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

L'esempio seguente si espande su `printCircleStats` quello precedente con una funzione che accetta un record anonimo come input:The following example expands on the previous one with a function that takes an anonymous record as input:

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let printCircleStats r (stats: {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

La `printCircleStats` chiamata con qualsiasi tipo di record anonimo che non ha la stessa forma del tipo di input non verrà compilata:Calling with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>Struct record anonimi

I record anonimi possono anche essere `struct` definiti come struct con la parola chiave facoltativa. L'esempio seguente aumenta quello precedente producendo e utilizzando un record anonimo struct:The following example augments the previous by producing and consuming a struct anonymous record:

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    // Note that the keyword comes before the '{| |}' brace pair
    struct {| Area = a; Circumference = c; Diameter = d |}

// the 'struct' keyword also comes before the '{| |}' brace pair when declaring the parameter type
let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

### <a name="structness-inference"></a>Inferenza di struttura

Struct record anonimi consentono anche "inferenza structness" in `struct` cui non è necessario specificare la parola chiave nel sito di chiamata. In questo esempio, si `struct` elide `printCircleStats`la parola chiave quando si chiama :

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

Il modello inverso, che specifica `struct` quando il tipo di input non è un record anonimo struct, non verrà compilato.

## <a name="embedding-anonymous-records-within-other-types"></a>Incorporamento di record anonimi all'interno di altri tipi

È utile dichiarare [le unioni discriminate](discriminated-unions.md) i cui casi sono record. Tuttavia, se i dati nei record sono dello stesso tipo dell'unione discriminata, è necessario definire tutti i tipi come ricorsivi reciprocamente. L'utilizzo di record anonimi evita questa restrizione. Quello che segue è un tipo di esempio e una funzione che il modello corrisponde su di esso:What follows is an example type and function that pattern matches over it:

```fsharp
type FullName = { FirstName: string; LastName: string }

// Note that using a named for Manager and Executive would require mutually recursive definitions.
type Employee =
    | Engineer of FullName
    | Manager of {| Name: FullName; Reports: Employee list |}
    | Executive of {| Name: FullName; Reports: Employee list; Assistant: Employee |}

let getFirstName e =
    match e with
    | Engineer fullName -> fullName.FirstName
    | Manager m -> m.Name.FirstName
    | Executive ex -> ex.Name.FirstName
```

## <a name="copy-and-update-expressions"></a>Copiare e aggiornare espressioni

I record anonimi supportano la costruzione con [espressioni di copia e aggiornamento](copy-and-update-record-expressions.md). Ad esempio, ecco come è possibile costruire una nuova istanza di un record anonimo che copia i dati di uno esistente:For example, here's how you can construct a new instance of an anonymous record that copies an existing's data:

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

Tuttavia, a differenza dei record denominati, i record anonimi consentono di creare moduli completamente diversi con espressioni di copia e aggiornamento. L'esempio seguente accetta lo stesso record anonimo dell'esempio precedente e lo espande in un nuovo record anonimo:

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

È anche possibile creare record anonimi da istanze di record denominati:

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

È inoltre possibile copiare dati da e verso i record anonimi di riferimento e struct:You can also copy data to and from reference and struct anonymous records:

```fsharp
// Copy data from a reference record into a struct anonymous record
type R1 = { X: int }
let r1 = { X = 1 }

let data1 = struct {| r1 with Y = 1 |}

// Copy data from a struct record into a reference anonymous record
[<Struct>]
type R2 = { X: int }
let r2 = { X = 1 }

let data2 = {| r1 with Y = 1 |}

// Copy the reference anonymous record data into a struct anonymous record
let data3 = struct {| data2 with Z = r2.X |}
```

## <a name="properties-of-anonymous-records"></a>Proprietà dei record anonimi

I record anonimi hanno una serie di caratteristiche essenziali per comprendere appieno come possono essere utilizzati.

### <a name="anonymous-records-are-nominal"></a>I record anonimi sono nominali

I record anonimi sono [di tipo nominale](https://en.wikipedia.org/wiki/Nominal_type_system). È meglio che siano considerati come tipi di [record](records.md) denominati (che sono anche nominali) che non richiedono una dichiarazione iniziale.

Si consideri l'esempio seguente con due dichiarazioni di record anonimi:Consider the following example with two anonymous record declarations:

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

I `x` `y` valori e hanno tipi diversi e non sono compatibili tra loro. Non sono equabili e non sono comparabili. Per illustrare questo concetto, si consideri un equivalente record denominato:To illustrate this, consider a named record equivalent:

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

Non c'è nulla di intrinsecamente diverso nei record anonimi rispetto ai rispettivi equivalenti di record denominati per quanto riguarda l'equivalenza o il confronto dei tipi.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>I record anonimi utilizzano l'uguaglianza strutturale e il confronto

Come i tipi di record, i record anonimi sono strutturalmente equabili e comparabili. Questo è vero solo se tutti i tipi costitutivi supportano l'uguaglianza e il confronto, ad esempio con i tipi di record. Per supportare l'uguaglianza o il confronto, due record anonimi devono avere la stessa "forma".

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>I record anonimi sono serializzabili

È possibile serializzare i record anonimi come con i record denominati. Di seguito è riportato un esempio di utilizzo [di Newtonsoft.Json:](https://www.nuget.org/packages/Newtonsoft.Json/)

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip')

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

I record anonimi sono utili per l'invio di dati leggeri in rete senza la necessità di definire un dominio per i tipi serializzati/deserializzati in anticipo.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>I record anonimi interagiscono con i tipi anonimi di C

È possibile utilizzare un'API .NET che richiede l'utilizzo di [tipi anonimi di C.](../../csharp/programming-guide/classes-and-structs/anonymous-types.md) I tipi anonimi di C, sono semplici per interagire con l'utilizzo di record anonimi. Nell'esempio seguente viene illustrato come utilizzare i record anonimi per chiamare un overload LINQ che richiede un tipo anonimo:The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

Esistono una moltitudine di altre API utilizzate in .NET che richiedono l'uso di passaggio in un tipo anonimo. I record anonimi sono il tuo strumento per lavorare con loro.

## <a name="limitations"></a>Limitazioni

I record anonimi hanno alcune restrizioni sul loro utilizzo. Alcuni sono inerenti al loro design, ma altri sono suscettibili di cambiare.

### <a name="limitations-with-pattern-matching"></a>Limitazioni con criteri di ricerca

I record anonimi non supportano i criteri di ricerca, a differenza dei record denominati. Ci sono tre ragioni:

1. Un modello dovrebbe tenere conto di ogni campo di un record anonimo, a differenza dei tipi di record denominati. Ciò è dovuto al fatto che i record anonimi non supportano il sottotipi strutturale, ovvero tipi nominali.
2. A causa di (1), non è possibile avere modelli aggiuntivi in un'espressione di corrispondenza di modello, poiché ogni modello distinto implicherebbe un tipo di record anonimo diverso.
3. A causa di (3), qualsiasi modello di record anonimo sarebbe più dettagliato rispetto all'uso della notazione "punto".

È disponibile un suggerimento linguistico aperto per consentire la [corrispondenza dei modelli in contesti limitati.](https://github.com/fsharp/fslang-suggestions/issues/713)

### <a name="limitations-with-mutability"></a>Limitazioni con mutabilità

Al momento non è possibile definire `mutable` un record anonimo con dati. È disponibile un [suggerimento linguistico aperto](https://github.com/fsharp/fslang-suggestions/issues/732) per consentire i dati modificabili.

### <a name="limitations-with-struct-anonymous-records"></a>Limitazioni con i record anonimi structLimitations with struct anonymous records

Non è possibile dichiarare record `IsByRefLike` anonimi `IsReadOnly`struct come o . C'è un [suggerimento linguistico aperto](https://github.com/fsharp/fslang-suggestions/issues/712) per i record per `IsByRefLike` e `IsReadOnly` anonimi.
