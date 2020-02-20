---
title: Record anonimi
description: Informazioni su come usare il costrutto e l'uso di record anonimi, una funzionalità del linguaggio che consente di manipolare i dati.
ms.date: 06/12/2019
ms.openlocfilehash: 061fd3279c84b9a3161c687d9392947ee7ce9c83
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453026"
---
# <a name="anonymous-records"></a>Record anonimi

I record anonimi sono aggregazioni semplici di valori denominati che non devono essere dichiarati prima dell'uso. È possibile dichiararli come struct o tipi di riferimento. Si tratta di tipi di riferimento per impostazione predefinita.

## <a name="syntax"></a>Sintassi

Negli esempi seguenti viene illustrata la sintassi dei record anonimi. Gli elementi delimitati come `[item]` sono facoltativi.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>Utilizzo di base

I record anonimi sono considerati i F# tipi di record che non devono essere dichiarati prima della creazione dell'istanza.

Ad esempio, ecco come è possibile interagire con una funzione che produce un record anonimo:

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

Nell'esempio seguente viene espansa in quella precedente con una funzione `printCircleStats` che accetta un record anonimo come input:

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

La chiamata di `printCircleStats` con qualsiasi tipo di record anonimo che non ha la stessa "forma" perché il tipo di input non verrà compilato:

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>Record anonimi struct

I record anonimi possono essere definiti anche come struct con la parola chiave `struct` facoltativa. Nell'esempio seguente viene migliorato quello precedente generando e utilizzando un record anonimo struct:

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

### <a name="structness-inference"></a>Inferenza di struct

I record anonimi struct consentono anche di "inferenza di struct", in cui non è necessario specificare la parola chiave `struct` nel sito di chiamata. In questo esempio si elide la parola chiave `struct` durante la chiamata `printCircleStats`:

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

Il criterio inverso, che specifica `struct` quando il tipo di input non è un record anonimo struct, non verrà compilato.

## <a name="embedding-anonymous-records-within-other-types"></a>Incorporamento di record anonimi all'interno di altri tipi

È utile dichiarare [unioni discriminate](discriminated-unions.md) i cui casi sono record. Tuttavia, se i dati nei record sono dello stesso tipo dell'unione discriminata, è necessario definire tutti i tipi come ricorsivamente ricorsivi. L'utilizzo di record anonimi evita questa restrizione. Di seguito è riportato un tipo di esempio e una funzione a cui corrisponde il modello:

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

## <a name="copy-and-update-expressions"></a>Espressioni di copia e aggiornamento

I record anonimi supportano la costruzione con [espressioni di copia e aggiornamento](copy-and-update-record-expressions.md). Ad esempio, ecco come è possibile costruire una nuova istanza di un record anonimo che copia i dati di uno esistente:

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

Tuttavia, a differenza dei record denominati, i record anonimi consentono di costruire forme completamente diverse con espressioni di copia e aggiornamento. L'esempio seguente accetta lo stesso record anonimo dell'esempio precedente e lo espande in un nuovo record anonimo:

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

È anche possibile costruire record anonimi da istanze di record denominati:

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

È anche possibile copiare dati da e verso record anonimi di riferimento e struct:

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

I record anonimi hanno una serie di caratteristiche essenziali per comprendere completamente come possono essere usate.

### <a name="anonymous-records-are-nominal"></a>I record anonimi sono nominali

I record anonimi sono [tipi nominali](https://en.wikipedia.org/wiki/Nominal_type_system). Sono considerati i tipi di [record](records.md) denominati (che sono anche nominali) che non richiedono una dichiarazione iniziale.

Si consideri l'esempio seguente con due dichiarazioni di record anonime:

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

I valori `x` e `y` hanno tipi diversi e non sono compatibili tra loro. Non sono equivalenti e non sono confrontabili. Per illustrare questo problema, prendere in considerazione un record denominato equivalente:

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

Non esiste alcuna differenza intrinseca sui record anonimi rispetto ai record denominati equivalenti quando riguarda l'equivalenza del tipo o il confronto.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>I record anonimi usano l'uguaglianza strutturale e il confronto

Analogamente ai tipi di record, i record anonimi sono strutturalmente equivalenti e confrontabili. Questa operazione è valida solo se tutti i tipi costitutivi supportano l'uguaglianza e il confronto, ad esempio con i tipi di record. Per supportare l'uguaglianza o il confronto, due record anonimi devono avere la stessa forma.

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>I record anonimi sono serializzabili

È possibile serializzare i record anonimi esattamente come si può fare con i record denominati. Di seguito è riportato un esempio di uso di [Newtonsoft. JSON](https://www.nuget.org/packages/Newtonsoft.Json/):

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip') 

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

I record anonimi sono utili per l'invio di dati semplici in una rete senza la necessità di definire un dominio per i tipi serializzati o deserializzati.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>I record anonimi interagiscono con C# i tipi anonimi

È possibile usare un'API .NET che richiede l'uso di [ C# tipi anonimi](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). C#i tipi anonimi sono semplici da usare con i record anonimi. Nell'esempio seguente viene illustrato come utilizzare record anonimi per chiamare un overload [LINQ](../../csharp/programming-guide/concepts/linq/index.md) che richiede un tipo anonimo:

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

Esistono numerose altre API usate in .NET che richiedono l'uso di un tipo anonimo. I record anonimi rappresentano lo strumento per l'utilizzo.

## <a name="limitations"></a>Limitazioni

I record anonimi presentano alcune restrizioni per l'utilizzo. Alcune sono intrinseche alla loro progettazione, ma altre sono suscettibili di modificarle.

### <a name="limitations-with-pattern-matching"></a>Limitazioni con criteri di ricerca

I record anonimi non supportano i criteri di ricerca, a differenza dei record denominati. Esistono tre motivi:

1. Un modello deve tenere conto di ogni campo di un record Anonimo, a differenza dei tipi di record denominati. Ciò è dovuto al fatto che i record anonimi non supportano la Sottotipizzazione strutturale, ovvero tipi nominali.
2. A causa di (1), non è possibile avere modelli aggiuntivi in un'espressione di ricerca di criteri di ricerca, perché ogni modello distinto implica un tipo di record anonimo diverso.
3. A causa di (3), qualsiasi modello di record anonimo sarebbe più dettagliato dell'uso della notazione "punto".

È disponibile un suggerimento per il linguaggio aperto che consente di individuare i criteri di ricerca [nei contesti limitati](https://github.com/fsharp/fslang-suggestions/issues/713).

### <a name="limitations-with-mutability"></a>Limitazioni con mutabilità

Non è attualmente possibile definire un record anonimo con dati `mutable`. È disponibile un [suggerimento sul linguaggio aperto](https://github.com/fsharp/fslang-suggestions/issues/732) per consentire i dati modificabili.

### <a name="limitations-with-struct-anonymous-records"></a>Limitazioni con i record anonimi struct

Non è possibile dichiarare i record anonimi struct come `IsByRefLike` o `IsReadOnly`. Per `IsByRefLike` e `IsReadOnly` record anonimi è disponibile un [suggerimento sul linguaggio aperto](https://github.com/fsharp/fslang-suggestions/issues/712) .
