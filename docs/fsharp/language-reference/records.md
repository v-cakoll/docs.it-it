---
title: Record
description: Informazioni sul F# modo in cui i record rappresentano aggregazioni semplici di valori denominati, facoltativamente con i membri.
ms.date: 06/09/2019
ms.openlocfilehash: d92a1a7517e5b05ee687926df29f33fab123b4dd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627291"
---
# <a name="records"></a><span data-ttu-id="caff6-103">Record</span><span class="sxs-lookup"><span data-stu-id="caff6-103">Records</span></span>

<span data-ttu-id="caff6-104">I record rappresentano aggregazioni semplici di valori denominati, facoltativamente con membri.</span><span class="sxs-lookup"><span data-stu-id="caff6-104">Records represent simple aggregates of named values, optionally with members.</span></span> <span data-ttu-id="caff6-105">Possono essere struct o tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="caff6-105">They can either be structs or reference types.</span></span>  <span data-ttu-id="caff6-106">Sono tipi di riferimento per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="caff6-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="caff6-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="caff6-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="caff6-108">Note</span><span class="sxs-lookup"><span data-stu-id="caff6-108">Remarks</span></span>

<span data-ttu-id="caff6-109">Nella sintassi precedente, *typeName* è il nome del tipo di record, *Label1* e *Label2* sono nomi di valori, denominati *labels*e *tipo1* e *tipo2* sono i tipi di questi valori.</span><span class="sxs-lookup"><span data-stu-id="caff6-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="caff6-110">*Member-List* è l'elenco facoltativo di membri per il tipo.</span><span class="sxs-lookup"><span data-stu-id="caff6-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="caff6-111">È possibile utilizzare l' `[<Struct>]` attributo per creare un record struct anziché un record che è un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="caff6-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="caff6-112">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="caff6-112">Following are some examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="caff6-113">Quando ogni etichetta si trova su una riga distinta, il punto e virgola è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="caff6-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="caff6-114">È possibile impostare valori nelle espressioni note come *espressioni di record*.</span><span class="sxs-lookup"><span data-stu-id="caff6-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="caff6-115">Il compilatore deduce il tipo dalle etichette utilizzate (se le etichette sono sufficientemente distinte da quelle di altri tipi di record).</span><span class="sxs-lookup"><span data-stu-id="caff6-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="caff6-116">Racchiudere l'espressione di record tra parentesi graffe ({}).</span><span class="sxs-lookup"><span data-stu-id="caff6-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="caff6-117">Il codice seguente illustra un'espressione di record che Inizializza un record con tre elementi float con `x`etichette `y` , `z`e.</span><span class="sxs-lookup"><span data-stu-id="caff6-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="caff6-118">Non usare il formato abbreviato se può essere presente un altro tipo che ha anche le stesse etichette.</span><span class="sxs-lookup"><span data-stu-id="caff6-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="caff6-119">Le etichette del tipo dichiarato più di recente hanno la precedenza su quelle del tipo dichiarato in precedenza, pertanto nell'esempio precedente, `mypoint3D` viene dedotto `Point3D`come.</span><span class="sxs-lookup"><span data-stu-id="caff6-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="caff6-120">È possibile specificare in modo esplicito il tipo di record, come nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="caff6-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="caff6-121">I metodi possono essere definiti per i tipi di record come per i tipi di classe.</span><span class="sxs-lookup"><span data-stu-id="caff6-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="caff6-122">Creazione di record tramite espressioni di record</span><span class="sxs-lookup"><span data-stu-id="caff6-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="caff6-123">È possibile inizializzare i record usando le etichette definite nel record.</span><span class="sxs-lookup"><span data-stu-id="caff6-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="caff6-124">Un'espressione che esegue questa operazione viene definita espressione di *record*.</span><span class="sxs-lookup"><span data-stu-id="caff6-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="caff6-125">Utilizzare le parentesi graffe per racchiudere l'espressione di record e utilizzare il punto e virgola come delimitatore.</span><span class="sxs-lookup"><span data-stu-id="caff6-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="caff6-126">Nell'esempio seguente viene illustrato come creare un record.</span><span class="sxs-lookup"><span data-stu-id="caff6-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="caff6-127">I punti e virgola dopo l'ultimo campo nell'espressione di record e nella definizione del tipo sono facoltativi, indipendentemente dal fatto che i campi si trovino tutti in una sola riga.</span><span class="sxs-lookup"><span data-stu-id="caff6-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="caff6-128">Quando si crea un record, è necessario specificare i valori per ogni campo.</span><span class="sxs-lookup"><span data-stu-id="caff6-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="caff6-129">Non è possibile fare riferimento ai valori di altri campi nell'espressione di inizializzazione per qualsiasi campo.</span><span class="sxs-lookup"><span data-stu-id="caff6-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="caff6-130">Nel codice seguente, il tipo di `myRecord2` viene dedotto dai nomi dei campi.</span><span class="sxs-lookup"><span data-stu-id="caff6-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="caff6-131">Facoltativamente, è possibile specificare il nome del tipo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="caff6-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="caff6-132">Un altro tipo di costruzione di record può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori di campo.</span><span class="sxs-lookup"><span data-stu-id="caff6-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="caff6-133">Questa operazione viene illustrata nella seguente riga di codice.</span><span class="sxs-lookup"><span data-stu-id="caff6-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="caff6-134">Questa forma dell'espressione di record è denominata *espressione di copia e aggiornamento del record*.</span><span class="sxs-lookup"><span data-stu-id="caff6-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="caff6-135">I record non sono modificabili per impostazione predefinita. Tuttavia, è possibile creare facilmente record modificati usando un'espressione di copia e aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="caff6-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="caff6-136">È anche possibile specificare in modo esplicito un campo modificabile.</span><span class="sxs-lookup"><span data-stu-id="caff6-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="caff6-137">Non usare l'attributo DefaultValue con i campi di record.</span><span class="sxs-lookup"><span data-stu-id="caff6-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="caff6-138">Un approccio migliore consiste nel definire le istanze predefinite dei record con i campi inizializzati sui valori predefiniti e quindi usare un'espressione di copia e aggiornamento del record per impostare i campi che differiscono dai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="caff6-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="creating-mutually-recursive-records"></a><span data-ttu-id="caff6-139">Creazione di record ricorsivi reciproci</span><span class="sxs-lookup"><span data-stu-id="caff6-139">Creating Mutually Recursive Records</span></span>

<span data-ttu-id="caff6-140">A volte, quando si crea un record, è possibile che dipenda da un altro tipo che si desidera definire in seguito.</span><span class="sxs-lookup"><span data-stu-id="caff6-140">Sometime when creating a record, you may want to have it depend on another type that you would like to define afterwards.</span></span> <span data-ttu-id="caff6-141">Si tratta di un errore di compilazione a meno che non si definiscono i tipi di record per essere ricorsivi reciproci.</span><span class="sxs-lookup"><span data-stu-id="caff6-141">This is a compile error unless you define the record types to be mutually recursive.</span></span>

<span data-ttu-id="caff6-142">La definizione di record ricorsivi reciproci viene `and` eseguita con la parola chiave.</span><span class="sxs-lookup"><span data-stu-id="caff6-142">Defining mutually recursive records is done with the `and` keyword.</span></span> <span data-ttu-id="caff6-143">In questo modo è possibile collegare due o più tipi di record.</span><span class="sxs-lookup"><span data-stu-id="caff6-143">This lets you link 2 or more record types together.</span></span>

<span data-ttu-id="caff6-144">Ad esempio, il codice seguente definisce un `Person` tipo `Address` e come ricorsivamente ricorsivo:</span><span class="sxs-lookup"><span data-stu-id="caff6-144">For example, the following code defines a `Person` and `Address` type as mutually recursive:</span></span>

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string }
```

<span data-ttu-id="caff6-145">Se si definisce l'esempio precedente senza la `and` parola chiave, non verrà compilato.</span><span class="sxs-lookup"><span data-stu-id="caff6-145">If you were to define the previous example without the `and` keyword, then it would not compile.</span></span> <span data-ttu-id="caff6-146">La `and` parola chiave è obbligatoria per le definizioni ricorsive reciproche.</span><span class="sxs-lookup"><span data-stu-id="caff6-146">The `and` keyword is required for mutually recursive definitions.</span></span>

## <a name="pattern-matching-with-records"></a><span data-ttu-id="caff6-147">Criteri di ricerca con record</span><span class="sxs-lookup"><span data-stu-id="caff6-147">Pattern Matching with Records</span></span>

<span data-ttu-id="caff6-148">I record possono essere usati con i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="caff6-148">Records can be used with pattern matching.</span></span> <span data-ttu-id="caff6-149">È possibile specificare in modo esplicito alcuni campi e fornire variabili per altri campi che verranno assegnati quando si verifica una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="caff6-149">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="caff6-150">Questo aspetto è illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="caff6-150">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="caff6-151">L'output di questo codice è il seguente.</span><span class="sxs-lookup"><span data-stu-id="caff6-151">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="caff6-152">Differenze tra record e classi</span><span class="sxs-lookup"><span data-stu-id="caff6-152">Differences Between Records and Classes</span></span>

<span data-ttu-id="caff6-153">I campi di record sono diversi dalle classi perché vengono esposti automaticamente come proprietà e vengono usati nella creazione e nella copia di record.</span><span class="sxs-lookup"><span data-stu-id="caff6-153">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="caff6-154">La costruzione di record differisce anche dalla costruzione delle classi.</span><span class="sxs-lookup"><span data-stu-id="caff6-154">Record construction also differs from class construction.</span></span> <span data-ttu-id="caff6-155">In un tipo di record non è possibile definire un costruttore.</span><span class="sxs-lookup"><span data-stu-id="caff6-155">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="caff6-156">Viene invece applicata la sintassi di costruzione descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="caff6-156">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="caff6-157">Le classi non hanno alcuna relazione diretta tra i parametri del costruttore, i campi e le proprietà.</span><span class="sxs-lookup"><span data-stu-id="caff6-157">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="caff6-158">Analogamente ai tipi unione e struttura, i record hanno una semantica di uguaglianza strutturale.</span><span class="sxs-lookup"><span data-stu-id="caff6-158">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="caff6-159">Le classi hanno una semantica di uguaglianza di riferimento.</span><span class="sxs-lookup"><span data-stu-id="caff6-159">Classes have reference equality semantics.</span></span> <span data-ttu-id="caff6-160">Nell'esempio di codice seguente viene illustrata questa possibilità.</span><span class="sxs-lookup"><span data-stu-id="caff6-160">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="caff6-161">L'output di questo codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="caff6-161">The output of this code is as follows:</span></span>

```
The records are equal.
```

<span data-ttu-id="caff6-162">Se si scrive lo stesso codice con le classi, i due oggetti classe sarebbero diversi perché i due valori rappresenterebbero due oggetti nell'heap e verranno confrontati solo gli indirizzi (a meno che il tipo di classe non esegua l'override del `System.Object.Equals` metodo).</span><span class="sxs-lookup"><span data-stu-id="caff6-162">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="caff6-163">Se è necessaria l'uguaglianza dei riferimenti per i record, `[<ReferenceEquality>]` aggiungere l'attributo sopra il record.</span><span class="sxs-lookup"><span data-stu-id="caff6-163">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="caff6-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="caff6-164">See also</span></span>

- [<span data-ttu-id="caff6-165">Tipi F#</span><span class="sxs-lookup"><span data-stu-id="caff6-165">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="caff6-166">Classi</span><span class="sxs-lookup"><span data-stu-id="caff6-166">Classes</span></span>](classes.md)
- [<span data-ttu-id="caff6-167">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="caff6-167">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="caff6-168">Riferimento-uguaglianza</span><span class="sxs-lookup"><span data-stu-id="caff6-168">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [<span data-ttu-id="caff6-169">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="caff6-169">Pattern Matching</span></span>](pattern-matching.md)
