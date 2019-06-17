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
# <a name="anonymous-records"></a><span data-ttu-id="11e5f-103">Record anonimi</span><span class="sxs-lookup"><span data-stu-id="11e5f-103">Anonymous Records</span></span>

<span data-ttu-id="11e5f-104">I record anonimi sono aggregazioni semplici di valori denominati che non devono essere dichiarati prima dell'uso.</span><span class="sxs-lookup"><span data-stu-id="11e5f-104">Anonymous records are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="11e5f-105">È possibile dichiararli come tipi di struct o riferimento.</span><span class="sxs-lookup"><span data-stu-id="11e5f-105">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="11e5f-106">Si tratta di tipi di riferimento per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="11e5f-106">They're reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="11e5f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11e5f-107">Syntax</span></span>

<span data-ttu-id="11e5f-108">Gli esempi seguenti illustrano la sintassi di record anonimi.</span><span class="sxs-lookup"><span data-stu-id="11e5f-108">The following examples demonstrate the anonymous record syntax.</span></span> <span data-ttu-id="11e5f-109">Elementi delimitato come `[item]` sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="11e5f-109">Items delimited as `[item]` are optional.</span></span>

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a><span data-ttu-id="11e5f-110">Utilizzo di base</span><span class="sxs-lookup"><span data-stu-id="11e5f-110">Basic usage</span></span>

<span data-ttu-id="11e5f-111">Record anonimi sono meglio pensare a come F# registrare i tipi che non devono essere dichiarati prima della creazione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="11e5f-111">Anonymous records are best thought of as F# record types that don't need to be declared before instantiation.</span></span>

<span data-ttu-id="11e5f-112">Ad esempio, qui come è possibile interagire con una funzione che genera un record anonimo:</span><span class="sxs-lookup"><span data-stu-id="11e5f-112">For example, here how you can interact with a function that produces an anonymous record:</span></span>

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

<span data-ttu-id="11e5f-113">Nell'esempio seguente si basa su quello precedente con un `printCircleStats` funzione che accetta un record anonimo come input:</span><span class="sxs-lookup"><span data-stu-id="11e5f-113">The following example expands on the previous one with a `printCircleStats` function that takes an anonymous record as input:</span></span>

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

<span data-ttu-id="11e5f-114">La chiamata `printCircleStats` con qualsiasi tipo di record anonimo che non ha la stessa "forma" come tipo di input. compilazione non verrà completata:</span><span class="sxs-lookup"><span data-stu-id="11e5f-114">Calling `printCircleStats` with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:</span></span>

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a><span data-ttu-id="11e5f-115">Struct anonimi record</span><span class="sxs-lookup"><span data-stu-id="11e5f-115">Struct anonymous records</span></span>

<span data-ttu-id="11e5f-116">Record anonimi può anche essere definito come uno struct con l'opzione facoltativa `struct` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="11e5f-116">Anonymous records can also be defined as struct with the optional `struct` keyword.</span></span> <span data-ttu-id="11e5f-117">Nell'esempio seguente aumenta quello precedente dal producono e usano un record di uno struct anonimo:</span><span class="sxs-lookup"><span data-stu-id="11e5f-117">The following example augments the previous one by producing and consuming a struct anonymous record:</span></span>

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

### <a name="structness-inference"></a><span data-ttu-id="11e5f-118">Inferenza Structness</span><span class="sxs-lookup"><span data-stu-id="11e5f-118">Structness inference</span></span>

<span data-ttu-id="11e5f-119">Struct anonimi record consente inoltre di utilizzare "structness inferenza" in cui non è necessario specificare il `struct` (parola chiave) nel sito di chiamata.</span><span class="sxs-lookup"><span data-stu-id="11e5f-119">Struct anonymous records also allow for "structness inference" where you do not need to specify the `struct` keyword at the call site.</span></span> <span data-ttu-id="11e5f-120">In questo esempio, elide il `struct` parola chiave quando si chiama `printCircleStats`:</span><span class="sxs-lookup"><span data-stu-id="11e5f-120">In this example, you elide the `struct` keyword when calling `printCircleStats`:</span></span>

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

<span data-ttu-id="11e5f-121">L'operazione inversa modello - specificando `struct` quando il tipo di input non è un record di uno struct anonimo - compilazione non verrà completata.</span><span class="sxs-lookup"><span data-stu-id="11e5f-121">The reverse pattern - specifying `struct` when the input type is not a struct anonymous record - will fail to compile.</span></span>

## <a name="embedding-anonymous-records-within-other-types"></a><span data-ttu-id="11e5f-122">Incorporamento anonimo record all'interno di altri tipi</span><span class="sxs-lookup"><span data-stu-id="11e5f-122">Embedding anonymous records within other types</span></span>

<span data-ttu-id="11e5f-123">È utile dichiarare [unioni discriminate](discriminated-unions.md) cui casi sono i record.</span><span class="sxs-lookup"><span data-stu-id="11e5f-123">It's useful to declare [discriminated unions](discriminated-unions.md) whose cases are records.</span></span> <span data-ttu-id="11e5f-124">Tuttavia, se i dati in record sono dello stesso tipo di unione discriminata, è necessario definire tutti i tipi come ricorsive reciproche.</span><span class="sxs-lookup"><span data-stu-id="11e5f-124">But if the data in the records is the same type as the discriminated union, you must define all types as mutually recursive.</span></span> <span data-ttu-id="11e5f-125">Utilizzo dei record anonimi consente di evitare questa limitazione.</span><span class="sxs-lookup"><span data-stu-id="11e5f-125">Using anonymous records avoids this restriction.</span></span> <span data-ttu-id="11e5f-126">Di seguito è riportato un esempio tipo e funzione corrisponde a tale modello su di esso:</span><span class="sxs-lookup"><span data-stu-id="11e5f-126">What follows is an example type and function that pattern matches over it:</span></span>

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

## <a name="copy-and-update-expressions"></a><span data-ttu-id="11e5f-127">Copiare e aggiornare le espressioni</span><span class="sxs-lookup"><span data-stu-id="11e5f-127">Copy and update expressions</span></span>

<span data-ttu-id="11e5f-128">Supportare la costruzione con record anonimi [copiare e aggiornare espressioni](copy-and-update-record-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="11e5f-128">Anonymous records support construction with [copy and update expressions](copy-and-update-record-expressions.md).</span></span> <span data-ttu-id="11e5f-129">Ad esempio, ecco come è possibile costruire una nuova istanza di un record di tipo anonimo che copia esistente di dati:</span><span class="sxs-lookup"><span data-stu-id="11e5f-129">For example, here's how you can construct a new instance of an anonymous record that copies an existing one's data:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

<span data-ttu-id="11e5f-130">Tuttavia, a differenza dei record denominato, record anonimi consentono di costruire forme completamente diverse con copia e aggiornare le espressioni.</span><span class="sxs-lookup"><span data-stu-id="11e5f-130">However, unlike named records, anonymous records allow you to construct entirely different forms with copy and update expressions.</span></span> <span data-ttu-id="11e5f-131">L'esempio seguente accetta lo stesso record anonimi dall'esempio precedente e si espande in un nuovo record anonimi:</span><span class="sxs-lookup"><span data-stu-id="11e5f-131">The follow example takes the same anonymous record from the previous example and expands it into a new anonymous record:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

<span data-ttu-id="11e5f-132">È anche possibile costruire record anonimi da istanze di record denominato:</span><span class="sxs-lookup"><span data-stu-id="11e5f-132">It is also possible to construct anonymous records from instances of named records:</span></span>

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

<span data-ttu-id="11e5f-133">È anche possibile copiare dati da e verso i record di riferimento e struct anonimi:</span><span class="sxs-lookup"><span data-stu-id="11e5f-133">You can also copy data to and from reference and struct anonymous records:</span></span>

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

## <a name="properties-of-anonymous-records"></a><span data-ttu-id="11e5f-134">Proprietà dei record anonimi</span><span class="sxs-lookup"><span data-stu-id="11e5f-134">Properties of anonymous records</span></span>

<span data-ttu-id="11e5f-135">Record anonimi hanno un numero di caratteristiche essenziali per comprenderne a fondo come possono essere usate.</span><span class="sxs-lookup"><span data-stu-id="11e5f-135">Anonymous records have a number of characteristics that are essential to fully understanding how they can be used.</span></span>

### <a name="anonymous-records-are-nominal"></a><span data-ttu-id="11e5f-136">I record anonimi sono nominali</span><span class="sxs-lookup"><span data-stu-id="11e5f-136">Anonymous records are nominal</span></span>

<span data-ttu-id="11e5f-137">Record anonimi siano [tipi nominali](https://en.wikipedia.org/wiki/Nominal_type_system).</span><span class="sxs-lookup"><span data-stu-id="11e5f-137">Anonymous records are [nominal types](https://en.wikipedia.org/wiki/Nominal_type_system).</span></span> <span data-ttu-id="11e5f-138">Come denominato rappresentano considerato [record](records.md) tipi, che sono anche nominali, che non richiedono una dichiarazione di anticipo.</span><span class="sxs-lookup"><span data-stu-id="11e5f-138">They are best thought as named [record](records.md) types (which are also nominal) that do not require an up-front declaration.</span></span>

<span data-ttu-id="11e5f-139">Si consideri l'esempio seguente con le dichiarazioni di due record anonimi:</span><span class="sxs-lookup"><span data-stu-id="11e5f-139">Consider the following example with two anonymous record declarations:</span></span>

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

<span data-ttu-id="11e5f-140">Il `x` e `y` valori hanno tipi diversi e non sono compatibili tra loro.</span><span class="sxs-lookup"><span data-stu-id="11e5f-140">The `x` and `y` values have different types and are not compatible with one another.</span></span> <span data-ttu-id="11e5f-141">Non sono uguaglianza e non sono confrontabili.</span><span class="sxs-lookup"><span data-stu-id="11e5f-141">They are not equatable and they are not comparable.</span></span> <span data-ttu-id="11e5f-142">Per illustrare questo concetto, si consideri un record denominato equivalente:</span><span class="sxs-lookup"><span data-stu-id="11e5f-142">To illustrate this, consider a named record equivalent:</span></span>

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

<span data-ttu-id="11e5f-143">Non c'è nulla differenze sostanziali tra i record anonimi quando vengono confrontati con i relativi equivalenti denominati record quando relativa equivalenza di tipo o il confronto.</span><span class="sxs-lookup"><span data-stu-id="11e5f-143">There isn't anything inherently different about anonymous records when compared with their named record equivalents when concerning type equivalency or comparison.</span></span>

### <a name="anonymous-records-use-structural-equality-and-comparison"></a><span data-ttu-id="11e5f-144">Record anonimi utilizzare confronto e uguaglianza strutturale</span><span class="sxs-lookup"><span data-stu-id="11e5f-144">Anonymous records use structural equality and comparison</span></span>

<span data-ttu-id="11e5f-145">Quali tipi di record, record anonimi sono strutturalmente uguaglianza e simili.</span><span class="sxs-lookup"><span data-stu-id="11e5f-145">Like record types, anonymous records are structurally equatable and comparable.</span></span> <span data-ttu-id="11e5f-146">Questo vale solo se tutti i tipi che costituiscono supportano uguaglianza e confronto, ad esempio con i tipi di record.</span><span class="sxs-lookup"><span data-stu-id="11e5f-146">This is only true if all constituent types support equality and comparison, like with record types.</span></span> <span data-ttu-id="11e5f-147">Per supportare l'uguaglianza o confronto, due record anonimo deve avere la stessa "forma".</span><span class="sxs-lookup"><span data-stu-id="11e5f-147">To support equality or comparison, two anonymous records must have the same "shape".</span></span>

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a><span data-ttu-id="11e5f-148">Record anonimi sono serializzabili</span><span class="sxs-lookup"><span data-stu-id="11e5f-148">Anonymous records are serializable</span></span>

<span data-ttu-id="11e5f-149">È possibile serializzare i record anonimi proprio come con i record denominati.</span><span class="sxs-lookup"><span data-stu-id="11e5f-149">You can serialize anonymous records just as you can with named records.</span></span> <span data-ttu-id="11e5f-150">Di seguito è riportato un esempio con [newtonsoft. JSON](https://www.nuget.org/packages/Newtonsoft.Json/):</span><span class="sxs-lookup"><span data-stu-id="11e5f-150">Here is an example using [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span></span>

```fsharp
open Newtonsoft.Json

let phillip = {| name="Phillip"; age=28 |}
JsonConvert.SerializeObject(phillip)

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(str)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

<span data-ttu-id="11e5f-151">Record anonimi sono utili per l'invio di dati lightweight in una rete senza la necessità di definire un dominio per i tipi serializzati/deserializzati, fin dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="11e5f-151">Anonymous records are useful for sending lightweight data over a network without the need to define a domain for your serialized/deserialized types up front.</span></span>

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a><span data-ttu-id="11e5f-152">Record anonimi interoperare con C# tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="11e5f-152">Anonymous records interoperate with C# anonymous types</span></span>

<span data-ttu-id="11e5f-153">È possibile usare un'API .NET che richiede l'uso di [ C# tipi anonimi](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="11e5f-153">It is possible to use a .NET API that requires the use of [C# anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="11e5f-154">C#i tipi anonimi sono semplici per l'interoperabilità con utilizzando i record anonimi.</span><span class="sxs-lookup"><span data-stu-id="11e5f-154">C# anonymous types are trivial to interoperate with by using anonymous records.</span></span> <span data-ttu-id="11e5f-155">Nell'esempio seguente viene illustrato come utilizzare i record anonimi di chiamare un [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload che richiede un tipo anonimo:</span><span class="sxs-lookup"><span data-stu-id="11e5f-155">The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:</span></span>

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

<span data-ttu-id="11e5f-156">Esistono una vasta gamma di altre API usata in tutto .NET che richiedono l'uso di passaggio di un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="11e5f-156">There are a multitude of other APIs used throughout .NET that require the use of passing in an anonymous type.</span></span> <span data-ttu-id="11e5f-157">I record anonimi sono lo strumento ideale per lavorare con loro.</span><span class="sxs-lookup"><span data-stu-id="11e5f-157">Anonymous records are your tool for working with them.</span></span>

## <a name="limitations"></a><span data-ttu-id="11e5f-158">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="11e5f-158">Limitations</span></span>

<span data-ttu-id="11e5f-159">Record anonimi presentano alcune restrizioni nella loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="11e5f-159">Anonymous records have some restrictions in their usage.</span></span> <span data-ttu-id="11e5f-160">Alcuni sono inerenti alla progettazione, ma gli altri sono soggette a modifica.</span><span class="sxs-lookup"><span data-stu-id="11e5f-160">Some are inherent to their design, but others are amenable to change.</span></span>

### <a name="limitations-with-pattern-matching"></a><span data-ttu-id="11e5f-161">Limitazioni relative ai criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="11e5f-161">Limitations with pattern matching</span></span>

<span data-ttu-id="11e5f-162">Record anonimi non supportano criteri di ricerca, a differenza dei record denominato.</span><span class="sxs-lookup"><span data-stu-id="11e5f-162">Anonymous records do not support pattern matching, unlike named records.</span></span> <span data-ttu-id="11e5f-163">Esistono tre motivi:</span><span class="sxs-lookup"><span data-stu-id="11e5f-163">There are three reasons:</span></span>

1. <span data-ttu-id="11e5f-164">Un modello necessario tenere conto per ogni campo di un record anonimo, a differenza dei tipi di record denominato.</span><span class="sxs-lookup"><span data-stu-id="11e5f-164">A pattern would have to account for every field of an anonymous record, unlike named record types.</span></span> <span data-ttu-id="11e5f-165">Questo avviene perché i record anonimi non supportano la sottotipizzazione strutturale: si tratta di tipi nominali.</span><span class="sxs-lookup"><span data-stu-id="11e5f-165">This is because anonymous records do not support structural subtyping – they are nominal types.</span></span>
2. <span data-ttu-id="11e5f-166">A causa di (1), non è possibile avere altri modelli in un'espressione di corrispondenza, poiché ogni modello distinto comporterebbe per un tipo di record anonimi diversi.</span><span class="sxs-lookup"><span data-stu-id="11e5f-166">Because of (1), there is no ability to have additional patterns in a pattern match expression, as each distinct pattern would imply a different anonymous record type.</span></span>
3. <span data-ttu-id="11e5f-167">A causa di (3), qualsiasi modello di record anonimi sarebbe più dettagliato rispetto all'utilizzo della notazione "punto".</span><span class="sxs-lookup"><span data-stu-id="11e5f-167">Because of (3), any anonymous record pattern would be more verbose than the use of “dot” notation.</span></span>

<span data-ttu-id="11e5f-168">È presente un suggerimento su linguaggio open [consentire criteri di ricerca limitate in contesti](https://github.com/fsharp/fslang-suggestions/issues/713).</span><span class="sxs-lookup"><span data-stu-id="11e5f-168">There is an open language suggestion to [allow pattern matching in limited contexts](https://github.com/fsharp/fslang-suggestions/issues/713).</span></span>

### <a name="limitations-with-mutability"></a><span data-ttu-id="11e5f-169">Limitazioni della modificabilità</span><span class="sxs-lookup"><span data-stu-id="11e5f-169">Limitations with mutability</span></span>

<span data-ttu-id="11e5f-170">Non è attualmente possibile definire un record anonimo con `mutable` dei dati.</span><span class="sxs-lookup"><span data-stu-id="11e5f-170">It is not currently possible to define an anonymous record with `mutable` data.</span></span> <span data-ttu-id="11e5f-171">È presente un' [aprire il suggerimento del linguaggio](https://github.com/fsharp/fslang-suggestions/issues/732) per consentire dati modificabili.</span><span class="sxs-lookup"><span data-stu-id="11e5f-171">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/732) to allow mutable data.</span></span>

### <a name="limitations-with-struct-anonymous-records"></a><span data-ttu-id="11e5f-172">Limitazioni con struct anonimi record</span><span class="sxs-lookup"><span data-stu-id="11e5f-172">Limitations with struct anonymous records</span></span>

<span data-ttu-id="11e5f-173">Non è possibile dichiarare uno struct anonimo record sarà `IsByRefLike` o `IsReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="11e5f-173">It is not possible to declare struct anonymous records as `IsByRefLike` or `IsReadOnly`.</span></span> <span data-ttu-id="11e5f-174">È presente un' [aprire suggerimento language](https://github.com/fsharp/fslang-suggestions/issues/712) a per `IsByRefLike` e `IsReadOnly` record anonimi.</span><span class="sxs-lookup"><span data-stu-id="11e5f-174">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/712) to for `IsByRefLike` and `IsReadOnly` anonymous records.</span></span>
