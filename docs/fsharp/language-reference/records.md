---
title: Record (F#)
description: 'Informazioni su come record F # rappresentano aggregazioni semplici di valori denominati, facoltativamente con membri.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3a3701ea-4308-4fa1-9b5c-b955c470f17a
ms.openlocfilehash: f5ade1db39431d99f10eb6967f02335123b83d34
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="records"></a><span data-ttu-id="90fb1-104">Record</span><span class="sxs-lookup"><span data-stu-id="90fb1-104">Records</span></span>

<span data-ttu-id="90fb1-105">I record rappresentano aggregazioni semplici di valori denominati, facoltativamente con membri.</span><span class="sxs-lookup"><span data-stu-id="90fb1-105">Records represent simple aggregates of named values, optionally with members.</span></span>  <span data-ttu-id="90fb1-106">A partire da F # 4.1, essi può essere struct o tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="90fb1-106">Starting with F# 4.1, they can either be structs or reference types.</span></span>  <span data-ttu-id="90fb1-107">Si tratta di tipi di riferimento per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="90fb1-107">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="90fb1-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90fb1-108">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename = {
    [ mutable ] label1 : type1;
    [ mutable ] label2 : type2;
    ...
}
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="90fb1-109">Note</span><span class="sxs-lookup"><span data-stu-id="90fb1-109">Remarks</span></span>
<span data-ttu-id="90fb1-110">Nella sintassi precedente, *typename* è il nome del tipo di record, *label1* e *label2* sono nomi dei valori, detti *etichette*, e *type1* e *type2* sono i tipi di questi valori.</span><span class="sxs-lookup"><span data-stu-id="90fb1-110">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="90fb1-111">*elenco dei membri* elenco facoltativo di membri per il tipo.</span><span class="sxs-lookup"><span data-stu-id="90fb1-111">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="90fb1-112">È possibile utilizzare il `[<Struct>]` attributo per creare un record di struct, anziché un record che è un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="90fb1-112">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="90fb1-113">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="90fb1-113">Following are some examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="90fb1-114">Una volta ogni etichetta in una riga separata, il punto e virgola è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="90fb1-114">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="90fb1-115">È possibile impostare i valori nelle espressioni note come *registrare espressioni*.</span><span class="sxs-lookup"><span data-stu-id="90fb1-115">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="90fb1-116">Il compilatore deduce il tipo dalle etichette utilizzate (se le etichette sono sufficientemente diversi da quelli di altri tipi di record).</span><span class="sxs-lookup"><span data-stu-id="90fb1-116">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="90fb1-117">Le parentesi graffe ({}) racchiudono l'espressione di record.</span><span class="sxs-lookup"><span data-stu-id="90fb1-117">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="90fb1-118">Il codice seguente è illustrata un'espressione di record che inizializza un record con tre elementi float con etichette `x`, `y` e `z`.</span><span class="sxs-lookup"><span data-stu-id="90fb1-118">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="90fb1-119">Non utilizzare la forma abbreviata se potrebbe esserci un altro tipo anche con le stesse etichette.</span><span class="sxs-lookup"><span data-stu-id="90fb1-119">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="90fb1-120">Le etichette del tipo dichiarato più di recente hanno la precedenza rispetto a quelli del tipo dichiarato in precedenza, in tal caso, nell'esempio precedente, `mypoint3D` viene considerato `Point3D`.</span><span class="sxs-lookup"><span data-stu-id="90fb1-120">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="90fb1-121">È possibile specificare in modo esplicito il tipo di record, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="90fb1-121">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="90fb1-122">Metodi possono essere definiti per i tipi di record come per i tipi di classe.</span><span class="sxs-lookup"><span data-stu-id="90fb1-122">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="90fb1-123">La creazione di record utilizzando espressioni di Record</span><span class="sxs-lookup"><span data-stu-id="90fb1-123">Creating Records by Using Record Expressions</span></span>
<span data-ttu-id="90fb1-124">È possibile inizializzare i record utilizzando le etichette che sono definite nel record.</span><span class="sxs-lookup"><span data-stu-id="90fb1-124">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="90fb1-125">Un'espressione che esegue questa operazione è detta un *registrare espressione*.</span><span class="sxs-lookup"><span data-stu-id="90fb1-125">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="90fb1-126">Utilizzare le parentesi graffe per racchiudere l'espressione di record e utilizzare il punto e virgola come delimitatore.</span><span class="sxs-lookup"><span data-stu-id="90fb1-126">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="90fb1-127">Nell'esempio seguente viene illustrato come creare un record.</span><span class="sxs-lookup"><span data-stu-id="90fb1-127">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="90fb1-128">I punti e virgola dopo l'ultimo campo nell'espressione di record e nella definizione del tipo sono facoltativi, indipendentemente dal fatto che i campi sono tutti in una riga.</span><span class="sxs-lookup"><span data-stu-id="90fb1-128">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="90fb1-129">Quando si crea un record, è necessario fornire valori per ogni campo.</span><span class="sxs-lookup"><span data-stu-id="90fb1-129">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="90fb1-130">È possibile fare riferimento ai valori di altri campi nell'espressione di inizializzazione per tutti i campi.</span><span class="sxs-lookup"><span data-stu-id="90fb1-130">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="90fb1-131">Nel codice seguente, il tipo di `myRecord2` è derivato dai nomi dei campi.</span><span class="sxs-lookup"><span data-stu-id="90fb1-131">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="90fb1-132">Facoltativamente, è possibile specificare il nome del tipo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="90fb1-132">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="90fb1-133">Un'altra forma di costruzione di record può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori dei campi.</span><span class="sxs-lookup"><span data-stu-id="90fb1-133">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="90fb1-134">Questa condizione è illustrata la riga di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="90fb1-134">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="90fb1-135">Questa forma di espressione record viene chiamata la *espressione record copia e aggiornamento*.</span><span class="sxs-lookup"><span data-stu-id="90fb1-135">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="90fb1-136">Record non sono modificabili per impostazione predefinita. Tuttavia, è possibile creare facilmente modificati tramite un'espressione di copia e aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="90fb1-136">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="90fb1-137">Anche in modo esplicito, è possibile specificare un campo modificabile.</span><span class="sxs-lookup"><span data-stu-id="90fb1-137">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="90fb1-138">Non utilizzare l'attributo DefaultValue con campi di record.</span><span class="sxs-lookup"><span data-stu-id="90fb1-138">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="90fb1-139">Un approccio migliore consiste nel definire le istanze predefinite di record con campi che vengono inizializzati i valori predefiniti e quindi utilizzare una copia espressione record e aggiornamento per impostare tutti i campi che sono diversi dai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="90fb1-139">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
{
    field1 : int
    field2 : int
}

let defaultRecord1 = { field1 = 0; field2 = 0 }
let defaultRecord2 = { field1 = 1; field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with field2 = 42 }
```

## <a name="pattern-matching-with-records"></a><span data-ttu-id="90fb1-140">Criteri di ricerca con i record</span><span class="sxs-lookup"><span data-stu-id="90fb1-140">Pattern Matching with Records</span></span>
<span data-ttu-id="90fb1-141">I record sono utilizzabili con criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="90fb1-141">Records can be used with pattern matching.</span></span> <span data-ttu-id="90fb1-142">È possibile specificare in modo esplicito alcuni campi e fornire le variabili per gli altri campi che verranno assegnati quando si verifica una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="90fb1-142">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="90fb1-143">Questo aspetto è illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="90fb1-143">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="90fb1-144">L'output di questo codice è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="90fb1-144">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="90fb1-145">Differenze tra i record e classi</span><span class="sxs-lookup"><span data-stu-id="90fb1-145">Differences Between Records and Classes</span></span>
<span data-ttu-id="90fb1-146">I campi del record differiscono dalle classi in automaticamente sono esposti come proprietà e sono utilizzate per la creazione e la copia di record.</span><span class="sxs-lookup"><span data-stu-id="90fb1-146">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="90fb1-147">La costruzione di record è diversa anche dalla costruzione di classi.</span><span class="sxs-lookup"><span data-stu-id="90fb1-147">Record construction also differs from class construction.</span></span> <span data-ttu-id="90fb1-148">In un tipo di record, è possibile definire un costruttore.</span><span class="sxs-lookup"><span data-stu-id="90fb1-148">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="90fb1-149">Al contrario, la sintassi di costruzione descritta in questo argomento si applica.</span><span class="sxs-lookup"><span data-stu-id="90fb1-149">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="90fb1-150">Le classi non dispongono di alcuna relazione diretta tra i parametri del costruttore, campi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="90fb1-150">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="90fb1-151">Come tipi di unione e struttura, record hanno una semantica di uguaglianza strutturale.</span><span class="sxs-lookup"><span data-stu-id="90fb1-151">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="90fb1-152">Le classi dispongono di riferimento semantica di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="90fb1-152">Classes have reference equality semantics.</span></span> <span data-ttu-id="90fb1-153">Esempio di codice seguente viene illustrato questo.</span><span class="sxs-lookup"><span data-stu-id="90fb1-153">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="90fb1-154">Se si scrive lo stesso codice con le classi, i due oggetti di classe sarebbero uguali perché i due valori rappresenterebbero due oggetti sull'heap e verrebbero confrontati solo gli indirizzi (a meno che il tipo di classe esegue l'override di `System.Object.Equals` (metodo)).</span><span class="sxs-lookup"><span data-stu-id="90fb1-154">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="90fb1-155">Se è necessario fare riferimento l'uguaglianza per i record, aggiungere l'attributo `[<ReferenceEquality>]` sopra il record.</span><span class="sxs-lookup"><span data-stu-id="90fb1-155">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="90fb1-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90fb1-156">See Also</span></span>
[<span data-ttu-id="90fb1-157">Tipi F#</span><span class="sxs-lookup"><span data-stu-id="90fb1-157">F# Types</span></span>](fsharp-types.md)

[<span data-ttu-id="90fb1-158">Classi</span><span class="sxs-lookup"><span data-stu-id="90fb1-158">Classes</span></span>](classes.md)

[<span data-ttu-id="90fb1-159">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="90fb1-159">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="90fb1-160">Uguaglianza di riferimento</span><span class="sxs-lookup"><span data-stu-id="90fb1-160">Reference-Equality</span></span>](https://msdn.microsoft.com/en-us/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)

[<span data-ttu-id="90fb1-161">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="90fb1-161">Pattern Matching</span></span>](pattern-matching.md)
