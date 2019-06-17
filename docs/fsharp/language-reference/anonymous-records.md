---
title: Record anonimi
description: Informazioni su come usare costrutto e utilizzare record anonimi, una funzionalità del linguaggio che consente la manipolazione dei dati.
ms.date: 06/12/2019
ms.openlocfilehash: e576210d4fb76ccfd09f8feb157ef4542aa94ccf
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041805"
---
# <a name="anonymous-records"></a>Record anonimi

I record anonimi sono aggregazioni semplici di valori denominati che non devono essere dichiarati prima dell'uso. È possibile dichiararli come tipi di struct o riferimento. Si tratta di tipi di riferimento per impostazione predefinita.

## <a name="syntax"></a>Sintassi

Gli esempi seguenti illustrano la sintassi di record anonimi. Elementi delimitato come `[item]` sono facoltativi.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>Utilizzo di base

Record anonimi sono meglio pensare a come F# registrare i tipi che non devono essere dichiarati prima della creazione dell'istanza.

Ad esempio, qui come è possibile interagire con una funzione che genera un record anonimo:

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

Nell'esempio seguente si basa su quello precedente con un `printCircleStats` funzione che accetta un record anonimo come input:

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

La chiamata `printCircleStats` con qualsiasi tipo di record anonimo che non ha la stessa "forma" come tipo di input. compilazione non verrà completata:

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>Struct anonimi record

Record anonimi può anche essere definito come uno struct con l'opzione facoltativa `struct` (parola chiave). Nell'esempio seguente aumenta quello precedente dal producono e usano un record di uno struct anonimo:

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

### <a name="structness-inference"></a>Inferenza Structness

Struct anonimi record consente inoltre di utilizzare "structness inferenza" in cui non è necessario specificare il `struct` (parola chiave) nel sito di chiamata. In questo esempio, elide il `struct` parola chiave quando si chiama `printCircleStats`:

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

L'operazione inversa modello - specificando `struct` quando il tipo di input non è un record di uno struct anonimo - compilazione non verrà completata.

## <a name="embedding-anonymous-records-within-other-types"></a>Incorporamento anonimo record all'interno di altri tipi

È utile dichiarare [unioni discriminate](discriminated-unions.md) cui casi sono i record. Tuttavia, se i dati in record sono dello stesso tipo di unione discriminata, è necessario definire tutti i tipi come ricorsive reciproche. Utilizzo dei record anonimi consente di evitare questa limitazione. Di seguito è riportato un esempio tipo e funzione corrisponde a tale modello su di esso:

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

## <a name="copy-and-update-expressions"></a>Copiare e aggiornare le espressioni

Supportare la costruzione con record anonimi [copiare e aggiornare espressioni](copy-and-update-record-expressions.md). Ad esempio, ecco come è possibile costruire una nuova istanza di un record di tipo anonimo che copia esistente di dati:

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

Tuttavia, a differenza dei record denominato, record anonimi consentono di costruire forme completamente diverse con copia e aggiornare le espressioni. L'esempio seguente accetta lo stesso record anonimi dall'esempio precedente e si espande in un nuovo record anonimi:

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

È anche possibile costruire record anonimi da istanze di record denominato:

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

È anche possibile copiare dati da e verso i record di riferimento e struct anonimi:

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

Record anonimi hanno un numero di caratteristiche essenziali per comprenderne a fondo come possono essere usate.

### <a name="anonymous-records-are-nominal"></a>I record anonimi sono nominali

Record anonimi siano [tipi nominali](https://en.wikipedia.org/wiki/Nominal_type_system). Come denominato rappresentano considerato [record](records.md) tipi, che sono anche nominali, che non richiedono una dichiarazione di anticipo.

Si consideri l'esempio seguente con le dichiarazioni di due record anonimi:

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

Il `x` e `y` valori hanno tipi diversi e non sono compatibili tra loro. Non sono uguaglianza e non sono confrontabili. Per illustrare questo concetto, si consideri un record denominato equivalente:

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

Non c'è nulla differenze sostanziali tra i record anonimi quando vengono confrontati con i relativi equivalenti denominati record quando relativa equivalenza di tipo o il confronto.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>Record anonimi utilizzare confronto e uguaglianza strutturale

Quali tipi di record, record anonimi sono strutturalmente uguaglianza e simili. Questo vale solo se tutti i tipi che costituiscono supportano uguaglianza e confronto, ad esempio con i tipi di record. Per supportare l'uguaglianza o confronto, due record anonimo deve avere la stessa "forma".

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>Record anonimi sono serializzabili

È possibile serializzare i record anonimi proprio come con i record denominati. Di seguito è riportato un esempio con [newtonsoft. JSON](https://www.nuget.org/packages/Newtonsoft.Json/):

```fsharp
open Newtonsoft.Json

let phillip = {| name="Phillip"; age=28 |}
JsonConvert.SerializeObject(phillip)

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(str)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

Record anonimi sono utili per l'invio di dati lightweight in una rete senza la necessità di definire un dominio per i tipi serializzati/deserializzati, fin dall'inizio.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>Record anonimi interoperare con C# tipi anonimi

È possibile usare un'API .NET che richiede l'uso di [ C# tipi anonimi](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). C#i tipi anonimi sono semplici per l'interoperabilità con utilizzando i record anonimi. Nell'esempio seguente viene illustrato come utilizzare i record anonimi di chiamare un [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload che richiede un tipo anonimo:

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

Esistono una vasta gamma di altre API usata in tutto .NET che richiedono l'uso di passaggio di un tipo anonimo. I record anonimi sono lo strumento ideale per lavorare con loro.

## <a name="limitations"></a>Limitazioni

Record anonimi presentano alcune restrizioni nella loro utilizzo. Alcuni sono inerenti alla progettazione, ma gli altri sono soggette a modifica.

### <a name="limitations-with-pattern-matching"></a>Limitazioni relative ai criteri di ricerca

Record anonimi non supportano criteri di ricerca, a differenza dei record denominato. Esistono tre motivi:

1. Un modello necessario tenere conto per ogni campo di un record anonimo, a differenza dei tipi di record denominato. Questo avviene perché i record anonimi non supportano la sottotipizzazione strutturale: si tratta di tipi nominali.
2. A causa di (1), non è possibile avere altri modelli in un'espressione di corrispondenza, poiché ogni modello distinto comporterebbe per un tipo di record anonimi diversi.
3. A causa di (3), qualsiasi modello di record anonimi sarebbe più dettagliato rispetto all'utilizzo della notazione "punto".

È presente un suggerimento su linguaggio open [consentire criteri di ricerca limitate in contesti](https://github.com/fsharp/fslang-suggestions/issues/713).

### <a name="limitations-with-mutability"></a>Limitazioni della modificabilità

Non è attualmente possibile definire un record anonimo con `mutable` dei dati. È presente un' [aprire il suggerimento del linguaggio](https://github.com/fsharp/fslang-suggestions/issues/732) per consentire dati modificabili.

### <a name="limitations-with-struct-anonymous-records"></a>Limitazioni con struct anonimi record

Non è possibile dichiarare uno struct anonimo record sarà `IsByRefLike` o `IsReadOnly`. È presente un' [aprire suggerimento language](https://github.com/fsharp/fslang-suggestions/issues/712) a per `IsByRefLike` e `IsReadOnly` record anonimi.
