---
title: Proprietà
description: Informazioni su F# proprietà, che sono membri che rappresentano valori associati a un oggetto.
ms.date: 05/16/2016
ms.openlocfilehash: bf605ee1135bd3b3561bde9a8ae66353497931b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666365"
---
# <a name="properties"></a><span data-ttu-id="87ca9-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="87ca9-103">Properties</span></span>

<span data-ttu-id="87ca9-104">*Proprietà* membri che rappresentano valori associati all'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="87ca9-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="87ca9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87ca9-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="87ca9-106">Note</span><span class="sxs-lookup"><span data-stu-id="87ca9-106">Remarks</span></span>

<span data-ttu-id="87ca9-107">Le proprietà rappresentano il "ha un" nella programmazione orientata agli oggetti che rappresentano i dati che sono associato a istanze di oggetti o, per le proprietà statiche, con il tipo di relazione.</span><span class="sxs-lookup"><span data-stu-id="87ca9-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="87ca9-108">È possibile dichiarare le proprietà in due modi, a seconda del fatto che si desidera specificare in modo esplicito il valore sottostante (detto anche l'archivio di backup) per la proprietà o se si vuole consentire al compilatore di generare automaticamente l'archivio di backup per l'utente.</span><span class="sxs-lookup"><span data-stu-id="87ca9-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="87ca9-109">In generale, è necessario utilizzare la modalità automatica e il modo più esplicito se la proprietà ha un'implementazione non semplice quando la proprietà è semplicemente un semplice wrapper per un valore o una variabile.</span><span class="sxs-lookup"><span data-stu-id="87ca9-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="87ca9-110">Per dichiarare una proprietà in modo esplicito, usare il `member` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="87ca9-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="87ca9-111">Questa sintassi dichiarativa è seguita dalla sintassi che specifica la `get` e `set` metodi, denominati anche *funzioni di accesso*.</span><span class="sxs-lookup"><span data-stu-id="87ca9-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="87ca9-112">Le varie forme di sintassi esplicita illustrata nella sezione relativa alla sintassi vengono usate per le proprietà di lettura/scrittura, sola lettura, lettura e scrittura.</span><span class="sxs-lookup"><span data-stu-id="87ca9-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="87ca9-113">Per le proprietà di sola lettura, si definisce solo un `get` metodo; per le proprietà di sola scrittura, definire solo un `set` (metodo).</span><span class="sxs-lookup"><span data-stu-id="87ca9-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="87ca9-114">Si noti che quando una proprietà ha entrambe `get` e `set` funzioni di accesso, la sintassi alternativa consente di specificare gli attributi e i modificatori di accessibilità sono diversi per ogni funzione di accesso, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="87ca9-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="87ca9-115">Per le proprietà di lettura/scrittura, che hanno entrambi un `get` e `set` metodo, l'ordine degli `get` e `set` possano essere annullati.</span><span class="sxs-lookup"><span data-stu-id="87ca9-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="87ca9-116">In alternativa, è possibile fornire la sintassi illustrata per `get` solo e la sintassi illustrata per `set` solo invece di usare la sintassi combinata.</span><span class="sxs-lookup"><span data-stu-id="87ca9-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="87ca9-117">Questa operazione rende più semplice rimuovere i commenti per i singoli `get` o `set` metodo, se questo è un elemento potrebbe essere necessario eseguire operazioni.</span><span class="sxs-lookup"><span data-stu-id="87ca9-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="87ca9-118">Questa alternativa all'utilizzo la sintassi combinata è illustrata nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="87ca9-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="87ca9-119">Esenzione i dati per le proprietà vengono chiamati i valori privati *archivi di backup*.</span><span class="sxs-lookup"><span data-stu-id="87ca9-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="87ca9-120">Affinché il compilatore crea automaticamente l'archivio di backup, usare le parole chiave `member val`, omettere l'identificatore di Self-Service, quindi specificare un'espressione per inizializzare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="87ca9-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="87ca9-121">Se la proprietà è modificabile, includere `with get, set`.</span><span class="sxs-lookup"><span data-stu-id="87ca9-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="87ca9-122">Ad esempio, il seguente tipo di classe include due proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="87ca9-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="87ca9-123">`Property1` è di sola lettura e viene inizializzato all'argomento fornito al costruttore del primario, e `Property2` è una proprietà impostabile inizializzata in una stringa vuota:</span><span class="sxs-lookup"><span data-stu-id="87ca9-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="87ca9-124">Proprietà implementate automaticamente fanno parte dell'inizializzazione di un tipo, quindi devono essere inclusi come prima di qualsiasi altra definizione del membro, `let` associazioni e `do` associazioni in una definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="87ca9-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="87ca9-125">Si noti che l'espressione che consente di inizializzare una proprietà implementata automaticamente viene valutata solo in fase di inizializzazione e non ogni volta che si accede alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="87ca9-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="87ca9-126">Questo comportamento si differenzia dal comportamento di una proprietà implementata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="87ca9-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="87ca9-127">Ciò in modo efficace significa che il codice per inizializzare queste proprietà viene aggiunta al costruttore di una classe.</span><span class="sxs-lookup"><span data-stu-id="87ca9-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="87ca9-128">Si consideri il codice seguente che illustra questa differenza:</span><span class="sxs-lookup"><span data-stu-id="87ca9-128">Consider the following code that shows this difference:</span></span>

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

<span data-ttu-id="87ca9-129">**Output**</span><span class="sxs-lookup"><span data-stu-id="87ca9-129">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="87ca9-130">L'output del codice precedente mostra che il valore di AutoProperty rimane invariato quando viene chiamato più volte, mentre il ExplicitProperty cambia ogni volta che viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="87ca9-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="87ca9-131">Ciò dimostra che l'espressione per una proprietà implementata automaticamente non viene valutata ogni volta, perché è il metodo di richiamo della proprietà esplicite.</span><span class="sxs-lookup"><span data-stu-id="87ca9-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
><span data-ttu-id="87ca9-132">Esistono alcune librerie, ad esempio Entity Framework (`System.Data.Entity`) che eseguono operazioni personalizzate nei costruttori di classe di base che non funzionano correttamente con l'inizializzazione di proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="87ca9-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="87ca9-133">In questi casi, provare a usare le proprietà esplicite.</span><span class="sxs-lookup"><span data-stu-id="87ca9-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="87ca9-134">Le proprietà possono essere membri di classi, strutture, unioni discriminate, record, interfacce e le estensioni di tipo e possono anche essere definite nelle espressioni di oggetto.</span><span class="sxs-lookup"><span data-stu-id="87ca9-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="87ca9-135">Gli attributi possono essere applicati alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="87ca9-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="87ca9-136">Per applicare un attributo a una proprietà, scrivere l'attributo su una riga separata prima che la proprietà.</span><span class="sxs-lookup"><span data-stu-id="87ca9-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="87ca9-137">Per altre informazioni, vedere [Attributi](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="87ca9-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="87ca9-138">Per impostazione predefinita, le proprietà sono pubbliche.</span><span class="sxs-lookup"><span data-stu-id="87ca9-138">By default, properties are public.</span></span> <span data-ttu-id="87ca9-139">I modificatori di accessibilità possono anche essere applicati alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="87ca9-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="87ca9-140">Per applicare un modificatore di accessibilità, aggiungerlo immediatamente prima del nome della proprietà, se lo scopo è quello di si applicano a entrambe le `get` e `set` metodi; aggiungerlo prima il `get` e `set` parole chiave se è un'accessibilità diversa obbligatorio per ogni funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="87ca9-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="87ca9-141">Il *modificatore di accessibilità* può essere uno dei seguenti: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="87ca9-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="87ca9-142">Per altre informazioni, vedere [Controllo di accesso](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="87ca9-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="87ca9-143">Le implementazioni di proprietà vengono eseguite ogni volta che si accede a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="87ca9-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="87ca9-144">Statiche e proprietà dell'istanza</span><span class="sxs-lookup"><span data-stu-id="87ca9-144">Static and Instance Properties</span></span>

<span data-ttu-id="87ca9-145">Le proprietà possono essere statici o delle proprietà dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="87ca9-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="87ca9-146">Proprietà statica possono essere richiamate senza un'istanza e vengono usate per i valori associati al tipo, non a singoli oggetti.</span><span class="sxs-lookup"><span data-stu-id="87ca9-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="87ca9-147">Per le proprietà statiche, omettere l'identificatore di Self-Service.</span><span class="sxs-lookup"><span data-stu-id="87ca9-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="87ca9-148">L'identificatore di Self-Service è necessario per le proprietà dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="87ca9-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="87ca9-149">La seguente definizione di proprietà statica si basa su uno scenario in cui è presente un campo statico `myStaticValue` vale a dire l'archivio di backup per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="87ca9-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="87ca9-150">Le proprietà possono anche essere di tipo matrice, nel qual caso vengono chiamati *proprietà indicizzate*.</span><span class="sxs-lookup"><span data-stu-id="87ca9-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="87ca9-151">Per altre informazioni, vedere [Indexed Properties](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="87ca9-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="87ca9-152">Annotazione del tipo di proprietà</span><span class="sxs-lookup"><span data-stu-id="87ca9-152">Type Annotation for Properties</span></span>

<span data-ttu-id="87ca9-153">In molti casi, il compilatore ha informazioni sufficienti per dedurre il tipo di una proprietà dal tipo dell'archivio di backup, ma è possibile impostare il tipo in modo esplicito mediante l'aggiunta di un'annotazione di tipo.</span><span class="sxs-lookup"><span data-stu-id="87ca9-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="87ca9-154">Utilizzo proprietà set di funzioni di accesso</span><span class="sxs-lookup"><span data-stu-id="87ca9-154">Using Property set Accessors</span></span>

<span data-ttu-id="87ca9-155">È possibile impostare proprietà che forniscono `set` funzioni di accesso usando il `<-` operatore.</span><span class="sxs-lookup"><span data-stu-id="87ca9-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="87ca9-156">L'output viene **20**.</span><span class="sxs-lookup"><span data-stu-id="87ca9-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="87ca9-157">Proprietà astratte</span><span class="sxs-lookup"><span data-stu-id="87ca9-157">Abstract Properties</span></span>

<span data-ttu-id="87ca9-158">Proprietà possono essere astratte.</span><span class="sxs-lookup"><span data-stu-id="87ca9-158">Properties can be abstract.</span></span> <span data-ttu-id="87ca9-159">Come con i metodi, `abstract` significa semplicemente che è una dispatch virtuale associato alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="87ca9-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="87ca9-160">Le proprietà astratte possono essere davvero astratte, vale a dire senza una definizione della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="87ca9-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="87ca9-161">La classe che contiene tale proprietà è pertanto una classe astratta.</span><span class="sxs-lookup"><span data-stu-id="87ca9-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="87ca9-162">In alternativa, abstract può significare semplicemente che una proprietà è virtuale e in tal caso, una definizione deve essere presente nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="87ca9-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="87ca9-163">Si noti che le proprietà astratte non devono essere private e se una funzione di accesso è astratto, l'altra deve anche essere astratta.</span><span class="sxs-lookup"><span data-stu-id="87ca9-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="87ca9-164">Per altre informazioni sulle classi astratte, vedere [classi astratte](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="87ca9-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="87ca9-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87ca9-165">See also</span></span>

- [<span data-ttu-id="87ca9-166">Membri</span><span class="sxs-lookup"><span data-stu-id="87ca9-166">Members</span></span>](index.md)
- [<span data-ttu-id="87ca9-167">Metodi</span><span class="sxs-lookup"><span data-stu-id="87ca9-167">Methods</span></span>](methods.md)
