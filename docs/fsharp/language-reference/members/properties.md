---
title: Properties
description: Informazioni sulle F# proprietà, che sono membri che rappresentano i valori associati a un oggetto.
ms.date: 05/16/2016
ms.openlocfilehash: c202927fd0022e042703640cd55fb632c7e36068
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627421"
---
# <a name="properties"></a><span data-ttu-id="29fe4-103">Properties</span><span class="sxs-lookup"><span data-stu-id="29fe4-103">Properties</span></span>

<span data-ttu-id="29fe4-104">Le *Proprietà* sono membri che rappresentano i valori associati a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="29fe4-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="29fe4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29fe4-105">Syntax</span></span>

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a><span data-ttu-id="29fe4-106">Note</span><span class="sxs-lookup"><span data-stu-id="29fe4-106">Remarks</span></span>

<span data-ttu-id="29fe4-107">Le proprietà rappresentano la relazione "has a" nella programmazione orientata a oggetti, che rappresenta i dati associati alle istanze degli oggetti o, per le proprietà statiche, con il tipo.</span><span class="sxs-lookup"><span data-stu-id="29fe4-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="29fe4-108">È possibile dichiarare le proprietà in due modi, a seconda che si desideri specificare in modo esplicito il valore sottostante (anche detto archivio di backup) per la proprietà o se si desidera consentire al compilatore di generare automaticamente l'archivio di backup.</span><span class="sxs-lookup"><span data-stu-id="29fe4-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="29fe4-109">In genere, è consigliabile usare il modo più esplicito se la proprietà ha un'implementazione non semplice e il modo automatico quando la proprietà è semplicemente un semplice wrapper per un valore o una variabile.</span><span class="sxs-lookup"><span data-stu-id="29fe4-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="29fe4-110">Per dichiarare in modo esplicito una proprietà, `member` usare la parola chiave.</span><span class="sxs-lookup"><span data-stu-id="29fe4-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="29fe4-111">Questa sintassi dichiarativa è seguita dalla sintassi che specifica `get` i `set` metodi e, anche *funzioni di accesso*denominate.</span><span class="sxs-lookup"><span data-stu-id="29fe4-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="29fe4-112">Le varie forme della sintassi esplicita illustrata nella sezione relativa alla sintassi vengono usate per le proprietà di sola lettura e scrittura, di sola lettura e di sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="29fe4-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="29fe4-113">Per le proprietà di sola lettura, si definisce solo `get` un metodo; per le proprietà di sola scrittura, definire `set` solo un metodo.</span><span class="sxs-lookup"><span data-stu-id="29fe4-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="29fe4-114">Si noti che quando una proprietà ha `get` entrambe `set` le funzioni di accesso e, la sintassi alternativa consente di specificare attributi e modificatori di accessibilità diversi per ogni funzione di accesso, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="29fe4-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="29fe4-115">Per le proprietà di lettura/scrittura, che hanno `get` sia `set` un metodo che, l' `get` ordine `set` di e può essere annullato.</span><span class="sxs-lookup"><span data-stu-id="29fe4-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="29fe4-116">In alternativa, è possibile fornire la sintassi mostrata `get` solo per e la sintassi illustrata solo per `set` anziché utilizzare la sintassi combinata.</span><span class="sxs-lookup"><span data-stu-id="29fe4-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="29fe4-117">In questo modo è più semplice impostare come commento il `get` singolo `set` metodo o il metodo, se si tratta di un'operazione che potrebbe essere necessario eseguire.</span><span class="sxs-lookup"><span data-stu-id="29fe4-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="29fe4-118">Questa alternativa all'uso della sintassi combinata è illustrata nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="29fe4-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="29fe4-119">I valori privati che contengono i dati per le proprietà sono denominati *archivi di backup*.</span><span class="sxs-lookup"><span data-stu-id="29fe4-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="29fe4-120">Per fare in modo che il compilatore crei automaticamente l'archivio di backup, `member val`usare le parole chiave, omettere l'identificatore autonomo, quindi fornire un'espressione per inizializzare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="29fe4-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="29fe4-121">Se la proprietà deve essere modificabile, includere `with get, set`.</span><span class="sxs-lookup"><span data-stu-id="29fe4-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="29fe4-122">Il tipo di classe seguente, ad esempio, include due proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="29fe4-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="29fe4-123">`Property1`è di sola lettura e viene inizializzato nell'argomento fornito al costruttore primario e `Property2` è una proprietà impostabile inizializzata su una stringa vuota:</span><span class="sxs-lookup"><span data-stu-id="29fe4-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="29fe4-124">Le proprietà implementate automaticamente fanno parte dell'inizializzazione di un tipo, pertanto devono essere incluse prima di qualsiasi altra definizione di membro `let` , proprio come `do` le associazioni e le associazioni in una definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="29fe4-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="29fe4-125">Si noti che l'espressione che Inizializza una proprietà implementata automaticamente viene valutata solo durante l'inizializzazione e non ogni volta che viene eseguito l'accesso alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="29fe4-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="29fe4-126">Questo comportamento è a differenza del comportamento di una proprietà implementata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="29fe4-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="29fe4-127">Ciò significa che il codice per inizializzare queste proprietà viene aggiunto al costruttore di una classe.</span><span class="sxs-lookup"><span data-stu-id="29fe4-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="29fe4-128">Si consideri il codice seguente che Mostra questa differenza:</span><span class="sxs-lookup"><span data-stu-id="29fe4-128">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

<span data-ttu-id="29fe4-129">**Output**</span><span class="sxs-lookup"><span data-stu-id="29fe4-129">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="29fe4-130">L'output del codice precedente mostra che il valore di autoproperty è invariato quando viene chiamato ripetutamente, mentre ExplicitProperty viene modificato ogni volta che viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="29fe4-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="29fe4-131">Ciò dimostra che l'espressione per una proprietà implementata automaticamente non viene valutata ogni volta, così come il metodo Get per la proprietà Explicit.</span><span class="sxs-lookup"><span data-stu-id="29fe4-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
><span data-ttu-id="29fe4-132">Sono disponibili alcune librerie, ad esempio la Entity Framework (`System.Data.Entity`) che eseguono operazioni personalizzate nei costruttori della classe di base che non funzionano correttamente con l'inizializzazione delle proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="29fe4-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="29fe4-133">In questi casi, provare a usare proprietà esplicite.</span><span class="sxs-lookup"><span data-stu-id="29fe4-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="29fe4-134">Le proprietà possono essere membri di classi, strutture, unioni discriminate, record, interfacce ed estensioni di tipo e possono essere definite anche nelle espressioni di oggetto.</span><span class="sxs-lookup"><span data-stu-id="29fe4-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="29fe4-135">Gli attributi possono essere applicati alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="29fe4-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="29fe4-136">Per applicare un attributo a una proprietà, scrivere l'attributo su una riga distinta prima della proprietà.</span><span class="sxs-lookup"><span data-stu-id="29fe4-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="29fe4-137">Per altre informazioni, vedere [Attributi](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="29fe4-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="29fe4-138">Per impostazione predefinita, le proprietà sono pubbliche.</span><span class="sxs-lookup"><span data-stu-id="29fe4-138">By default, properties are public.</span></span> <span data-ttu-id="29fe4-139">I modificatori di accessibilità possono anche essere applicati alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="29fe4-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="29fe4-140">Per applicare un modificatore di accessibilità, aggiungerlo immediatamente prima del nome della proprietà se `get` è destinato a entrambi i metodi e `set` . aggiungerlo prima delle `get` parole chiave `set` e se l'accessibilità è diversa obbligatorio per ogni funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="29fe4-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="29fe4-141">Il *modificatore* di accessibilità può essere uno dei seguenti `public`: `private`, `internal`,.</span><span class="sxs-lookup"><span data-stu-id="29fe4-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="29fe4-142">Per altre informazioni, vedere [Controllo di accesso](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="29fe4-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="29fe4-143">Le implementazioni delle proprietà vengono eseguite ogni volta che si accede a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="29fe4-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="29fe4-144">Proprietà statiche e di istanza</span><span class="sxs-lookup"><span data-stu-id="29fe4-144">Static and Instance Properties</span></span>

<span data-ttu-id="29fe4-145">Le proprietà possono essere proprietà statiche o di istanza.</span><span class="sxs-lookup"><span data-stu-id="29fe4-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="29fe4-146">Le proprietà statiche possono essere richiamate senza un'istanza di e vengono utilizzate per i valori associati al tipo, non con singoli oggetti.</span><span class="sxs-lookup"><span data-stu-id="29fe4-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="29fe4-147">Per le proprietà statiche, omettere l'identificatore automatico.</span><span class="sxs-lookup"><span data-stu-id="29fe4-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="29fe4-148">Il self-identifier è obbligatorio per le proprietà dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="29fe4-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="29fe4-149">La definizione di proprietà statica seguente si basa su uno scenario in cui è presente un campo `myStaticValue` statico che rappresenta l'archivio di backup per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="29fe4-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="29fe4-150">Le proprietà possono anche essere di tipo matrice, nel qual caso sono denominate *proprietà indicizzate*.</span><span class="sxs-lookup"><span data-stu-id="29fe4-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="29fe4-151">Per ulteriori informazioni, vedere [proprietà indicizzate](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="29fe4-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="29fe4-152">Annotazione del tipo per le proprietà</span><span class="sxs-lookup"><span data-stu-id="29fe4-152">Type Annotation for Properties</span></span>

<span data-ttu-id="29fe4-153">In molti casi, il compilatore dispone di informazioni sufficienti per dedurre il tipo di una proprietà dal tipo di archivio di backup, ma è possibile impostare il tipo in modo esplicito aggiungendo un'annotazione di tipo.</span><span class="sxs-lookup"><span data-stu-id="29fe4-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="29fe4-154">Uso delle funzioni di accesso del set di proprietà</span><span class="sxs-lookup"><span data-stu-id="29fe4-154">Using Property set Accessors</span></span>

<span data-ttu-id="29fe4-155">È possibile impostare proprietà che forniscono `set` funzioni di accesso tramite l' `<-` operatore.</span><span class="sxs-lookup"><span data-stu-id="29fe4-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="29fe4-156">L'output è **20**.</span><span class="sxs-lookup"><span data-stu-id="29fe4-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="29fe4-157">Proprietà astratte</span><span class="sxs-lookup"><span data-stu-id="29fe4-157">Abstract Properties</span></span>

<span data-ttu-id="29fe4-158">Le proprietà possono essere astratte.</span><span class="sxs-lookup"><span data-stu-id="29fe4-158">Properties can be abstract.</span></span> <span data-ttu-id="29fe4-159">Come per i metodi `abstract` , significa solo che è presente un dispatch virtuale associato alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="29fe4-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="29fe4-160">Le proprietà astratte possono essere effettivamente astratte, ovvero senza una definizione nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="29fe4-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="29fe4-161">La classe che contiene tale proprietà è quindi una classe astratta.</span><span class="sxs-lookup"><span data-stu-id="29fe4-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="29fe4-162">In alternativa, abstract può semplicemente significare che una proprietà è virtuale e, in tal caso, deve essere presente una definizione nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="29fe4-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="29fe4-163">Si noti che le proprietà astratte non devono essere private e se una funzione di accesso è astratta, anche l'altra deve essere astratta.</span><span class="sxs-lookup"><span data-stu-id="29fe4-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="29fe4-164">Per ulteriori informazioni sulle classi astratte, vedere [classi astratte](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="29fe4-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="29fe4-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29fe4-165">See also</span></span>

- [<span data-ttu-id="29fe4-166">Membri</span><span class="sxs-lookup"><span data-stu-id="29fe4-166">Members</span></span>](index.md)
- [<span data-ttu-id="29fe4-167">Metodi</span><span class="sxs-lookup"><span data-stu-id="29fe4-167">Methods</span></span>](methods.md)
