---
title: Attributi
description: Informazioni su come F# attributi abilitano i metadati da applicare a un costrutto di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: 6e80bc4e32ee4ff5ff132270bde8e2fd018369e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703205"
---
# <a name="attributes"></a><span data-ttu-id="4f43b-103">Attributi</span><span class="sxs-lookup"><span data-stu-id="4f43b-103">Attributes</span></span>

<span data-ttu-id="4f43b-104">Gli attributi abilitano i metadati da applicare a un costrutto di programmazione.</span><span class="sxs-lookup"><span data-stu-id="4f43b-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="4f43b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f43b-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="4f43b-106">Note</span><span class="sxs-lookup"><span data-stu-id="4f43b-106">Remarks</span></span>

<span data-ttu-id="4f43b-107">Nella sintassi precedente, il *destinazione* è facoltativo e, se presente, specifica il tipo di entità del programma a cui si applica l'attributo.</span><span class="sxs-lookup"><span data-stu-id="4f43b-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="4f43b-108">I valori validi per *destinazione* vengono visualizzati nella tabella riportata più avanti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="4f43b-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="4f43b-109">Il *-nome dell'attributo* fa riferimento al nome (possibilmente qualificato con spazi dei nomi) di un tipo di attributo valido, con o senza il suffisso `Attribute` che in genere viene usato nei nomi di tipo di attributo.</span><span class="sxs-lookup"><span data-stu-id="4f43b-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="4f43b-110">Ad esempio, il tipo `ObsoleteAttribute` può essere abbreviato semplicemente `Obsolete` in questo contesto.</span><span class="sxs-lookup"><span data-stu-id="4f43b-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="4f43b-111">Il *argomenti* include gli argomenti del costruttore per il tipo di attributo.</span><span class="sxs-lookup"><span data-stu-id="4f43b-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="4f43b-112">Se un attributo ha un costruttore predefinito, è possono omettere l'elenco di argomenti e le parentesi.</span><span class="sxs-lookup"><span data-stu-id="4f43b-112">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="4f43b-113">Gli attributi supportano entrambi gli argomenti posizionali e gli argomenti denominati.</span><span class="sxs-lookup"><span data-stu-id="4f43b-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="4f43b-114">*Gli argomenti posizionali* sono argomenti che vengono usati nell'ordine in cui vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="4f43b-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="4f43b-115">Argomenti denominati possono essere utilizzati se l'attributo ha le proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="4f43b-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="4f43b-116">È possibile impostare tali informazioni tramite la sintassi seguente nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="4f43b-116">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="4f43b-117">Le inizializzazioni tali proprietà possono essere in qualsiasi ordine, ma devono seguire gli argomenti posizionali.</span><span class="sxs-lookup"><span data-stu-id="4f43b-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="4f43b-118">Ecco un esempio di un attributo che usa argomenti posizionali e inizializzazioni delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="4f43b-118">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="4f43b-119">In questo esempio, l'attributo è `DllImportAttribute`, qui utilizzato nella sua forma abbreviata.</span><span class="sxs-lookup"><span data-stu-id="4f43b-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="4f43b-120">Il primo argomento è un parametro posizionale e la seconda è una proprietà.</span><span class="sxs-lookup"><span data-stu-id="4f43b-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="4f43b-121">Gli attributi sono un costrutto di programmazione .NET che consente a un oggetto noto come un *attributo* da associare a un tipo o altro elemento del programma.</span><span class="sxs-lookup"><span data-stu-id="4f43b-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="4f43b-122">L'elemento del programma a cui viene applicato un attributo è noto come il *destinazione dell'attributo*.</span><span class="sxs-lookup"><span data-stu-id="4f43b-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="4f43b-123">L'attributo contiene in genere i metadati relativi al valore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4f43b-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="4f43b-124">In questo contesto, i metadati può essere tutti i dati sul tipo diverso da relativi campi e i membri.</span><span class="sxs-lookup"><span data-stu-id="4f43b-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="4f43b-125">Gli attributi F# può essere applicato a costrutti di programmazione seguenti: funzioni, metodi, assembly, moduli, tipi (classi, record, strutture, interfacce, delegati, enumerazioni, unioni e così via), costruttori, proprietà, campi, i parametri, parametri di tipo e i valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="4f43b-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="4f43b-126">Atributy nejsou povolené. su `let` associazioni all'interno di classi, le espressioni o espressioni del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4f43b-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="4f43b-127">In genere, la dichiarazione di attributo viene visualizzata direttamente prima della dichiarazione dell'attributo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4f43b-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="4f43b-128">Più dichiarazioni di attributo sono utilizzabile tra loro, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4f43b-128">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="4f43b-129">È possibile eseguire una query degli attributi in fase di esecuzione usando la reflection .NET.</span><span class="sxs-lookup"><span data-stu-id="4f43b-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="4f43b-130">È possibile dichiarare più attributi singolarmente, come nell'esempio di codice precedente, oppure è possibile dichiararli in un set di parentesi, se si usa un punto e virgola per separare i singoli attributi e i costruttori, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4f43b-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="4f43b-131">In genere, gli attributi includono il `Obsolete` attributo, gli attributi per considerazioni sulla sicurezza, gli attributi per il supporto COM, gli attributi relativi alla proprietà del codice e gli attributi che indica se un tipo può essere serializzato.</span><span class="sxs-lookup"><span data-stu-id="4f43b-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="4f43b-132">Nell'esempio seguente viene illustrato l'utilizzo del `Obsolete` attributo.</span><span class="sxs-lookup"><span data-stu-id="4f43b-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="4f43b-133">Per le destinazioni degli attributi `assembly` e `module`, applicare gli attributi a un livello superiore `do` binding dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4f43b-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="4f43b-134">È possibile includere la parola `assembly` o `module` nella dichiarazione di attributo, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4f43b-134">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="4f43b-135">Se si omette l'attributo di destinazione per un attributo applicato a un `do` binding, il F# compilatore prova a determinare l'attributo di destinazione appropriato per quell'attributo.</span><span class="sxs-lookup"><span data-stu-id="4f43b-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="4f43b-136">Molte classi di attributo dispongono di un attributo di tipo `System.AttributeUsageAttribute` che include informazioni sulle possibili destinazioni supportate per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="4f43b-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="4f43b-137">Se il `System.AttributeUsageAttribute` indica che l'attributo supporta le funzioni come destinazione, l'attributo proviene da applicare al punto di ingresso principale del programma.</span><span class="sxs-lookup"><span data-stu-id="4f43b-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="4f43b-138">Se il `System.AttributeUsageAttribute` indica che l'attributo supporta gli assembly come destinazioni, il compilatore prende l'attributo da applicare all'assembly.</span><span class="sxs-lookup"><span data-stu-id="4f43b-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="4f43b-139">La maggior parte degli attributi non si applicano a entrambe le funzioni e assembly, ma in casi in cui avviene l'attributo non viene eseguito da applicare alla funzione principale del programma.</span><span class="sxs-lookup"><span data-stu-id="4f43b-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="4f43b-140">Se l'attributo di destinazione viene specificato in modo esplicito, l'attributo viene applicato alla destinazione specificata.</span><span class="sxs-lookup"><span data-stu-id="4f43b-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="4f43b-141">Sebbene non sia in genere necessario specificare l'attributo di destinazione in modo esplicito, i valori validi per *destinazione* in un attributo vengono visualizzate nella tabella seguente, insieme a esempi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="4f43b-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="4f43b-142">Attributo di destinazione</span><span class="sxs-lookup"><span data-stu-id="4f43b-142">Attribute target</span></span></td>
    <th><span data-ttu-id="4f43b-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f43b-143">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4f43b-144">assembly</span><span class="sxs-lookup"><span data-stu-id="4f43b-144">assembly</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4f43b-145">return</span><span class="sxs-lookup"><span data-stu-id="4f43b-145">return</span></span></td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4f43b-146">campo</span><span class="sxs-lookup"><span data-stu-id="4f43b-146">field</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4f43b-147">proprietà</span><span class="sxs-lookup"><span data-stu-id="4f43b-147">property</span></span></td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4f43b-148">param</span><span class="sxs-lookup"><span data-stu-id="4f43b-148">param</span></span></td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10<code></pre></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4f43b-149">tipo</span><span class="sxs-lookup"><span data-stu-id="4f43b-149">type</span></span></td>
    <td>
        <pre lang="fsharp"><code>
        [&lt;type: StructLayout(Sequential)&gt;] 
        type MyStruct = 
        struct 
        x : byte
        y : int
        end
        <code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="4f43b-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f43b-150">See also</span></span>

- [<span data-ttu-id="4f43b-151">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="4f43b-151">F# Language Reference</span></span>](index.md)