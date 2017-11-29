---
title: "Proprietà (F#)"
description: "Informazioni sulle proprietà, F # che sono membri che rappresentano i valori associati a un oggetto."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 98b363a5-ee6a-4b7b-b8ae-b244f2a0b316
ms.openlocfilehash: 53b93b20310c557ad9c30226bc08f85cbf2f3010
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="properties"></a><span data-ttu-id="f7a99-104">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f7a99-104">Properties</span></span>

<span data-ttu-id="f7a99-105">*Proprietà* sono membri che rappresentano i valori associati a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f7a99-105">*Properties* are members that represent values associated with an object.</span></span>


## <a name="syntax"></a><span data-ttu-id="f7a99-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7a99-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="f7a99-107">Note</span><span class="sxs-lookup"><span data-stu-id="f7a99-107">Remarks</span></span>
<span data-ttu-id="f7a99-108">Le proprietà rappresentano il "ha un" nella programmazione orientata agli oggetti che rappresentano i dati associati alle istanze di oggetto o, per le proprietà statiche, con il tipo di relazione.</span><span class="sxs-lookup"><span data-stu-id="f7a99-108">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="f7a99-109">È possibile dichiarare una proprietà in due modi, a seconda se si desidera specificare in modo esplicito il valore sottostante (detto anche l'archivio di backup) per la proprietà o se si desidera consentire al compilatore di generare automaticamente l'archivio di backup per l'utente.</span><span class="sxs-lookup"><span data-stu-id="f7a99-109">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="f7a99-110">In genere, è necessario utilizzare il modo più esplicito se la proprietà è un'implementazione non semplice e la modalità automatica quando la proprietà è un semplice wrapper per un valore o una variabile.</span><span class="sxs-lookup"><span data-stu-id="f7a99-110">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="f7a99-111">Per dichiarare una proprietà in modo esplicito, utilizzare il `member` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="f7a99-111">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="f7a99-112">Questa sintassi dichiarativa è seguita dalla sintassi che specifica il `get` e `set` metodi, denominati anche *funzioni di accesso*.</span><span class="sxs-lookup"><span data-stu-id="f7a99-112">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="f7a99-113">Le varie forme di sintassi illustrato nella sezione relativa alla sintassi esplicita vengono utilizzate per le proprietà di sola lettura, lettura e scrittura di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="f7a99-113">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="f7a99-114">Per le proprietà di sola lettura, definire solo un `get` metodo; per le proprietà di sola scrittura, definire solo un `set` metodo.</span><span class="sxs-lookup"><span data-stu-id="f7a99-114">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="f7a99-115">Si noti che quando una proprietà ha entrambi `get` e `set` funzioni di accesso, la sintassi alternativa consente di specificare gli attributi e modificatori di accessibilità che sono diversi per ogni funzione di accesso, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f7a99-115">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="f7a99-116">Per le proprietà di lettura/scrittura, che hanno entrambi un `get` e `set` (metodo), l'ordine di `get` e `set` possano essere annullati.</span><span class="sxs-lookup"><span data-stu-id="f7a99-116">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="f7a99-117">In alternativa, è possibile fornire la sintassi illustrata per `get` solo e la sintassi illustrata per `set` solo anziché utilizzare la sintassi combinata.</span><span class="sxs-lookup"><span data-stu-id="f7a99-117">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="f7a99-118">Ciò rende più semplice per impostare come commento i singoli `get` o `set` (metodo), in caso di un elemento potrebbe essere necessario eseguire.</span><span class="sxs-lookup"><span data-stu-id="f7a99-118">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="f7a99-119">Questa procedura alternativa per utilizzare la sintassi combinata è illustrata nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f7a99-119">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="f7a99-120">Private i valori che vengono chiamati i dati per le proprietà di attesa *archivi di backup*.</span><span class="sxs-lookup"><span data-stu-id="f7a99-120">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="f7a99-121">Se il compilatore crea automaticamente l'archivio di backup, utilizzare le parole chiave `member val`, omettere l'identificatore di Self-Service, quindi specificare un'espressione per inizializzare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7a99-121">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="f7a99-122">Se la proprietà è modificabile, includere `with get, set`.</span><span class="sxs-lookup"><span data-stu-id="f7a99-122">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="f7a99-123">Ad esempio, il seguente tipo di classe include due proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f7a99-123">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="f7a99-124">`Property1`è di sola lettura e viene inizializzato per l'argomento fornito al costruttore primario, e `Property2` è una proprietà impostabile inizializzata in una stringa vuota:</span><span class="sxs-lookup"><span data-stu-id="f7a99-124">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="f7a99-125">Proprietà implementate automaticamente sono parte dell'inizializzazione di un tipo, pertanto devono essere inclusi come prima di qualsiasi altra definizione del membro, `let` associazioni e `do` binding in una definizione di tipo.</span><span class="sxs-lookup"><span data-stu-id="f7a99-125">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="f7a99-126">Si noti che l'espressione che consente di inizializzare una proprietà implementata automaticamente viene valutato solo al momento dell'inizializzazione e non ogni volta che si accede alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7a99-126">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="f7a99-127">Questo comportamento si differenzia dal comportamento di una proprietà implementata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="f7a99-127">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="f7a99-128">Ciò in modo efficace significa che il codice per inizializzare le proprietà viene aggiunta al costruttore di una classe.</span><span class="sxs-lookup"><span data-stu-id="f7a99-128">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="f7a99-129">Si consideri il codice seguente viene illustrata questa differenza:</span><span class="sxs-lookup"><span data-stu-id="f7a99-129">Consider the following code that shows this difference:</span></span>

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

<span data-ttu-id="f7a99-130">**Output**</span><span class="sxs-lookup"><span data-stu-id="f7a99-130">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="f7a99-131">L'output del codice precedente mostra che il valore di AutoProperty è invariato quando viene chiamato più volte, mentre il ExplicitProperty cambia ogni volta che viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="f7a99-131">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="f7a99-132">Ciò dimostra che l'espressione per una proprietà implementata automaticamente non viene valutata ogni volta, come il metodo di richiamo della proprietà esplicita.</span><span class="sxs-lookup"><span data-stu-id="f7a99-132">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>


>[!WARNING]
<span data-ttu-id="f7a99-133">Esistono alcune librerie, ad esempio Entity Framework (`System.Data.Entity`) che eseguono operazioni personalizzate nei costruttori di classe di base che non funzionano correttamente con l'inizializzazione di proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f7a99-133">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="f7a99-134">In questi casi, provare a utilizzare la proprietà esplicita.</span><span class="sxs-lookup"><span data-stu-id="f7a99-134">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="f7a99-135">Le proprietà possono essere membri di classi, strutture, unioni discriminate, record, interfacce e le estensioni di tipo e possono essere definite anche nelle espressioni di oggetto.</span><span class="sxs-lookup"><span data-stu-id="f7a99-135">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="f7a99-136">Gli attributi possono essere applicati alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7a99-136">Attributes can be applied to properties.</span></span> <span data-ttu-id="f7a99-137">Per applicare un attributo a una proprietà, scrivere l'attributo su una riga separata prima che la proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7a99-137">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="f7a99-138">Per altre informazioni, vedere [Attributi](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="f7a99-138">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="f7a99-139">Per impostazione predefinita, le proprietà sono pubbliche.</span><span class="sxs-lookup"><span data-stu-id="f7a99-139">By default, properties are public.</span></span> <span data-ttu-id="f7a99-140">I modificatori di accessibilità possono inoltre essere applicati alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7a99-140">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="f7a99-141">Per applicare un modificatore di accessibilità, aggiungerlo immediatamente prima del nome della proprietà, se deve essere applicato a entrambi il `get` e `set` metodi; aggiungerlo prima di `get` e `set` parole chiave se è diverso di accessibilità obbligatorio per ogni funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="f7a99-141">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="f7a99-142">Il *modificatore di accessibilità* può essere uno dei seguenti: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="f7a99-142">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="f7a99-143">Per altre informazioni, vedere [Controllo di accesso](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="f7a99-143">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="f7a99-144">Le implementazioni di proprietà vengono eseguite ogni volta che accede a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7a99-144">Property implementations are executed each time a property is accessed.</span></span>


## <a name="static-and-instance-properties"></a><span data-ttu-id="f7a99-145">Statico e delle proprietà dell'istanza</span><span class="sxs-lookup"><span data-stu-id="f7a99-145">Static and Instance Properties</span></span>
<span data-ttu-id="f7a99-146">Proprietà possono essere statici o delle proprietà dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="f7a99-146">Properties can be static or instance properties.</span></span> <span data-ttu-id="f7a99-147">Proprietà statica possono essere richiamate senza un'istanza e permettono i valori associati al tipo, non a singoli oggetti.</span><span class="sxs-lookup"><span data-stu-id="f7a99-147">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="f7a99-148">Per le proprietà statiche, omettere l'identificatore di Self-Service.</span><span class="sxs-lookup"><span data-stu-id="f7a99-148">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="f7a99-149">L'autoidentificatore è obbligatorio per le proprietà dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="f7a99-149">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="f7a99-150">La seguente definizione di proprietà statica è basata su uno scenario in cui è presente un campo statico `myStaticValue` che rappresenta l'archivio di backup per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7a99-150">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="f7a99-151">Proprietà possono anche essere tipo matrice, nel qual caso vengono chiamati *proprietà indicizzate*.</span><span class="sxs-lookup"><span data-stu-id="f7a99-151">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="f7a99-152">Per ulteriori informazioni, vedere [le proprietà indicizzate](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f7a99-152">For more information, see [Indexed Properties](indexed-properties.md).</span></span>


## <a name="type-annotation-for-properties"></a><span data-ttu-id="f7a99-153">Annotazione del tipo di proprietà</span><span class="sxs-lookup"><span data-stu-id="f7a99-153">Type Annotation for Properties</span></span>
<span data-ttu-id="f7a99-154">In molti casi, il compilatore ha informazioni sufficienti per dedurre il tipo di una proprietà dal tipo di archivio di backup, ma è possibile impostare il tipo in modo esplicito mediante l'aggiunta di un'annotazione di tipo.</span><span class="sxs-lookup"><span data-stu-id="f7a99-154">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="f7a99-155">Utilizzo di proprietà set di funzioni di accesso</span><span class="sxs-lookup"><span data-stu-id="f7a99-155">Using Property set Accessors</span></span>
<span data-ttu-id="f7a99-156">È possibile impostare proprietà che forniscono `set` funzioni di accesso tramite il `<-` operatore.</span><span class="sxs-lookup"><span data-stu-id="f7a99-156">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="f7a99-157">L'output è **20**.</span><span class="sxs-lookup"><span data-stu-id="f7a99-157">The output is **20**.</span></span>


## <a name="abstract-properties"></a><span data-ttu-id="f7a99-158">Proprietà astratte</span><span class="sxs-lookup"><span data-stu-id="f7a99-158">Abstract Properties</span></span>
<span data-ttu-id="f7a99-159">Proprietà possono essere astratte.</span><span class="sxs-lookup"><span data-stu-id="f7a99-159">Properties can be abstract.</span></span> <span data-ttu-id="f7a99-160">Come con i metodi, `abstract` significa semplicemente che è un invio virtuale associato alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7a99-160">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="f7a99-161">Le proprietà astratte possono essere effettivamente astratte, ovvero senza una definizione nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="f7a99-161">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="f7a99-162">Pertanto, la classe che contiene tale proprietà è una classe astratta.</span><span class="sxs-lookup"><span data-stu-id="f7a99-162">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="f7a99-163">In alternativa, astratta può significare semplicemente che una proprietà è virtuale e in tal caso, una definizione deve trovarsi nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="f7a99-163">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="f7a99-164">Si noti che le proprietà astratte non devono essere private, e se una funzione di accesso è astratto, anche l'altra deve essere astratta.</span><span class="sxs-lookup"><span data-stu-id="f7a99-164">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="f7a99-165">Per ulteriori informazioni sulle classi astratte, vedere [classi astratte](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="f7a99-165">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="f7a99-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7a99-166">See Also</span></span>
[<span data-ttu-id="f7a99-167">Membri</span><span class="sxs-lookup"><span data-stu-id="f7a99-167">Members</span></span>](index.md)

[<span data-ttu-id="f7a99-168">Metodi</span><span class="sxs-lookup"><span data-stu-id="f7a99-168">Methods</span></span>](methods.md)
