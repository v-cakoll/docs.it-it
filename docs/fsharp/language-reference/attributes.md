---
title: Attributes
description: Informazioni su F# come gli attributi consentono l'applicazione dei metadati a un costrutto di programmazione.
ms.date: 02/19/2020
ms.openlocfilehash: 77b84713ab9360166b3634d406993cf209c8a623
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543638"
---
# <a name="attributes"></a><span data-ttu-id="56f9a-103">Attributes</span><span class="sxs-lookup"><span data-stu-id="56f9a-103">Attributes</span></span>

<span data-ttu-id="56f9a-104">Gli attributi consentono di applicare i metadati a un costrutto di programmazione.</span><span class="sxs-lookup"><span data-stu-id="56f9a-104">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="56f9a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56f9a-105">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="56f9a-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="56f9a-106">Remarks</span></span>

<span data-ttu-id="56f9a-107">Nella sintassi precedente, la *destinazione* è facoltativa e, se presente, specifica il tipo di entità programma a cui si applica l'attributo.</span><span class="sxs-lookup"><span data-stu-id="56f9a-107">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="56f9a-108">I valori validi per la *destinazione* sono illustrati nella tabella riportata più avanti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="56f9a-108">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="56f9a-109">Il *nome dell'attributo* fa riferimento al nome (possibilmente qualificato con gli spazi dei nomi) di un tipo di attributo valido, con o senza il suffisso `Attribute` usato in genere nei nomi dei tipi di attributo.</span><span class="sxs-lookup"><span data-stu-id="56f9a-109">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="56f9a-110">Il tipo `ObsoleteAttribute`, ad esempio, può essere abbreviato in modo da `Obsolete` solo in questo contesto.</span><span class="sxs-lookup"><span data-stu-id="56f9a-110">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="56f9a-111">Gli *argomenti* sono gli argomenti del costruttore per il tipo di attributo.</span><span class="sxs-lookup"><span data-stu-id="56f9a-111">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="56f9a-112">Se un attributo ha un costruttore senza parametri, è possibile omettere l'elenco di argomenti e le parentesi.</span><span class="sxs-lookup"><span data-stu-id="56f9a-112">If an attribute has a parameterless constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="56f9a-113">Gli attributi supportano sia gli argomenti posizionali che gli argomenti denominati.</span><span class="sxs-lookup"><span data-stu-id="56f9a-113">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="56f9a-114">Gli *argomenti posizionali* sono argomenti utilizzati nell'ordine in cui sono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="56f9a-114">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="56f9a-115">Gli argomenti denominati possono essere utilizzati se l'attributo dispone di proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="56f9a-115">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="56f9a-116">È possibile impostarle usando la sintassi seguente nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="56f9a-116">You can set these by using the following syntax in the argument list.</span></span>

```fsharp
property-name = property-value
```

<span data-ttu-id="56f9a-117">Tali inizializzazioni di proprietà possono essere in qualsiasi ordine, ma devono seguire qualsiasi argomento posizionale.</span><span class="sxs-lookup"><span data-stu-id="56f9a-117">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="56f9a-118">Di seguito è riportato un esempio di un attributo che usa gli argomenti posizionali e le inizializzazioni delle proprietà:</span><span class="sxs-lookup"><span data-stu-id="56f9a-118">The following is an example of an attribute that uses positional arguments and property initializations:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="56f9a-119">In questo esempio l'attributo è `DllImportAttribute`, in questo caso viene usato in formato abbreviato.</span><span class="sxs-lookup"><span data-stu-id="56f9a-119">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="56f9a-120">Il primo argomento è un parametro posizionale e il secondo è una proprietà.</span><span class="sxs-lookup"><span data-stu-id="56f9a-120">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="56f9a-121">Gli attributi sono un costrutto di programmazione .NET che consente a un oggetto noto come *attributo* di essere associato a un tipo o a un altro elemento del programma.</span><span class="sxs-lookup"><span data-stu-id="56f9a-121">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="56f9a-122">L'elemento Program a cui è applicato un attributo è noto come *destinazione dell'attributo*.</span><span class="sxs-lookup"><span data-stu-id="56f9a-122">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="56f9a-123">L'attributo contiene in genere i metadati sulla relativa destinazione.</span><span class="sxs-lookup"><span data-stu-id="56f9a-123">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="56f9a-124">In questo contesto, i metadati possono essere di qualsiasi tipo, ad eccezione dei relativi campi e membri.</span><span class="sxs-lookup"><span data-stu-id="56f9a-124">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="56f9a-125">Gli attributi F# in possono essere applicati ai seguenti costrutti di programmazione: funzioni, metodi, assembly, moduli, tipi (classi, record, strutture, interfacce, delegati, enumerazioni, unioni e così via), costruttori, proprietà, campi, parametri, parametri di tipo e valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="56f9a-125">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="56f9a-126">Gli attributi non sono consentiti nelle associazioni `let` all'interno di classi, espressioni o espressioni del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="56f9a-126">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="56f9a-127">In genere, la dichiarazione di attributo viene visualizzata direttamente prima della dichiarazione della destinazione dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="56f9a-127">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="56f9a-128">È possibile utilizzare contemporaneamente più dichiarazioni di attributo, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="56f9a-128">Multiple attribute declarations can be used together, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="56f9a-129">È possibile eseguire query sugli attributi in fase di esecuzione usando la reflection .NET.</span><span class="sxs-lookup"><span data-stu-id="56f9a-129">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="56f9a-130">È possibile dichiarare più attributi singolarmente, come nell'esempio di codice precedente, oppure è possibile dichiararli in un set di parentesi quadre se si usa un punto e virgola per separare i singoli attributi e costruttori, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="56f9a-130">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="56f9a-131">Gli attributi rilevati in genere includono l'attributo `Obsolete`, gli attributi per considerazioni sulla sicurezza, gli attributi per il supporto COM, gli attributi correlati alla proprietà del codice e gli attributi che indicano se un tipo può essere serializzato.</span><span class="sxs-lookup"><span data-stu-id="56f9a-131">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="56f9a-132">Nell'esempio seguente viene illustrato l'utilizzo dell'attributo `Obsolete`.</span><span class="sxs-lookup"><span data-stu-id="56f9a-132">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="56f9a-133">Per le destinazioni degli attributi `assembly` e `module`, applicare gli attributi a un'associazione di `do` di primo livello nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="56f9a-133">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="56f9a-134">È possibile includere la parola `assembly` o `module` nella dichiarazione dell'attributo, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="56f9a-134">You can include the word `assembly` or `module` in the attribute declaration, as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="56f9a-135">Se si omette la destinazione dell'attributo per un attributo applicato a un `do` binding, F# il compilatore tenta di determinare la destinazione dell'attributo che ha senso per tale attributo.</span><span class="sxs-lookup"><span data-stu-id="56f9a-135">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="56f9a-136">Molte classi Attribute hanno un attributo di tipo `System.AttributeUsageAttribute` che include informazioni sulle possibili destinazioni supportate per tale attributo.</span><span class="sxs-lookup"><span data-stu-id="56f9a-136">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="56f9a-137">Se il `System.AttributeUsageAttribute` indica che l'attributo supporta funzioni come destinazioni, l'attributo viene accettato per essere applicato al punto di ingresso principale del programma.</span><span class="sxs-lookup"><span data-stu-id="56f9a-137">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="56f9a-138">Se il `System.AttributeUsageAttribute` indica che l'attributo supporta gli assembly come destinazioni, il compilatore accetta l'attributo da applicare all'assembly.</span><span class="sxs-lookup"><span data-stu-id="56f9a-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="56f9a-139">La maggior parte degli attributi non si applica sia alle funzioni che agli assembly, ma nei casi in cui lo fanno, l'attributo viene accettato per essere applicato alla funzione principale del programma.</span><span class="sxs-lookup"><span data-stu-id="56f9a-139">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="56f9a-140">Se la destinazione dell'attributo viene specificata in modo esplicito, l'attributo viene applicato alla destinazione specificata.</span><span class="sxs-lookup"><span data-stu-id="56f9a-140">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="56f9a-141">Anche se in genere non è necessario specificare la destinazione dell'attributo in modo esplicito, i valori validi per la *destinazione* in un attributo insieme ad esempi di utilizzo sono illustrati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="56f9a-141">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute along with examples of usage are shown in the following table:</span></span>

<table>
  <tr>
    <th><span data-ttu-id="56f9a-142">Destinazione attributo</span><span class="sxs-lookup"><span data-stu-id="56f9a-142">Attribute target</span></span></td>
    <th><span data-ttu-id="56f9a-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="56f9a-143">Example</span></span></td>
  </tr>
  <tr>
    <td><span data-ttu-id="56f9a-144">assembly</span><span class="sxs-lookup"><span data-stu-id="56f9a-144">assembly</span></span></td>
    <td><pre><code class="lang-fsharp">[&lt;assembly: AssemblyVersion("1.0.0.0")&gt;]</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="56f9a-145">return</span><span class="sxs-lookup"><span data-stu-id="56f9a-145">return</span></span></td>
    <td><pre><code class="lang-fsharp">let function1 x : [&lt;return: MyCustomAttributeThatWorksOnReturns&gt;] int = x + 1</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="56f9a-146">campo</span><span class="sxs-lookup"><span data-stu-id="56f9a-146">field</span></span></td>
    <td><pre><code class="lang-fsharp">[&lt;DefaultValue&gt;] val mutable x: int</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="56f9a-147">proprietà</span><span class="sxs-lookup"><span data-stu-id="56f9a-147">property</span></span></td>
    <td><pre><code class="lang-fsharp">[&lt;Obsolete&gt;] this.MyProperty = x</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="56f9a-148">param</span><span class="sxs-lookup"><span data-stu-id="56f9a-148">param</span></span></td>
    <td><pre><code class="lang-fsharp">member this.MyMethod([&lt;Out&gt;] x : ref&lt;int&gt;) = x := 10</code></pre></td>
  </tr>
  <tr>
    <td><span data-ttu-id="56f9a-149">type</span><span class="sxs-lookup"><span data-stu-id="56f9a-149">type</span></span></td>
    <td>
        <pre><code class="lang-fsharp">
[&lt;type: StructLayout(LayoutKind.Sequential)&gt;]
type MyStruct =
  struct
    val x : byte
    val y : int
  end</code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="56f9a-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56f9a-150">See also</span></span>

- [<span data-ttu-id="56f9a-151">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="56f9a-151">F# Language Reference</span></span>](index.md)
