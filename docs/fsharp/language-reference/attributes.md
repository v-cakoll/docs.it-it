---
title: Attributi (F#)
description: 'Informazioni su come gli attributi di F # Abilita i metadati da applicare a un costrutto di programmazione.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 95c001e6-3708-4d04-a850-d855f78eb51e
ms.openlocfilehash: 88098e51d19a86f501c35abe3408524378f147b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="attributes"></a><span data-ttu-id="4c61e-104">Attributi</span><span class="sxs-lookup"><span data-stu-id="4c61e-104">Attributes</span></span>

<span data-ttu-id="4c61e-105">Attributi Abilita i metadati da applicare a un costrutto di programmazione.</span><span class="sxs-lookup"><span data-stu-id="4c61e-105">Attributes enable metadata to be applied to a programming construct.</span></span>

## <a name="syntax"></a><span data-ttu-id="4c61e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c61e-106">Syntax</span></span>

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a><span data-ttu-id="4c61e-107">Note</span><span class="sxs-lookup"><span data-stu-id="4c61e-107">Remarks</span></span>

<span data-ttu-id="4c61e-108">Nella sintassi precedente, il *destinazione* è facoltativo e, se presente, specifica il tipo di entità del programma a cui si applica l'attributo.</span><span class="sxs-lookup"><span data-stu-id="4c61e-108">In the previous syntax, the *target* is optional and, if present, specifies the kind of program entity that the attribute applies to.</span></span> <span data-ttu-id="4c61e-109">I valori validi per *destinazione* vengono visualizzati nella tabella riportata più avanti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="4c61e-109">Valid values for *target* are shown in the table that appears later in this document.</span></span>

<span data-ttu-id="4c61e-110">Il *-nome dell'attributo* fa riferimento al nome (eventualmente qualificato con spazi dei nomi) di un tipo di attributo valido, con o senza il suffisso `Attribute` in genere utilizzato nei nomi di tipi di attributo.</span><span class="sxs-lookup"><span data-stu-id="4c61e-110">The *attribute-name* refers to the name (possibly qualified with namespaces) of a valid attribute type, with or without the suffix `Attribute` that is usually used in attribute type names.</span></span> <span data-ttu-id="4c61e-111">Ad esempio, il tipo `ObsoleteAttribute` può essere abbreviato semplicemente `Obsolete` in questo contesto.</span><span class="sxs-lookup"><span data-stu-id="4c61e-111">For example, the type `ObsoleteAttribute` can be shortened to just `Obsolete` in this context.</span></span>

<span data-ttu-id="4c61e-112">Il *argomenti* sono gli argomenti del costruttore del tipo di attributo.</span><span class="sxs-lookup"><span data-stu-id="4c61e-112">The *arguments* are the arguments to the constructor for the attribute type.</span></span> <span data-ttu-id="4c61e-113">Se un attributo ha un costruttore predefinito, è possibile omettere l'elenco di argomenti e le parentesi.</span><span class="sxs-lookup"><span data-stu-id="4c61e-113">If an attribute has a default constructor, the argument list and parentheses can be omitted.</span></span> <span data-ttu-id="4c61e-114">Gli attributi supportano sia gli argomenti posizionali e argomenti denominati.</span><span class="sxs-lookup"><span data-stu-id="4c61e-114">Attributes support both positional arguments and named arguments.</span></span> <span data-ttu-id="4c61e-115">*Gli argomenti posizionali* sono argomenti utilizzati nell'ordine in cui appaiono.</span><span class="sxs-lookup"><span data-stu-id="4c61e-115">*Positional arguments* are arguments that are used in the order in which they appear.</span></span> <span data-ttu-id="4c61e-116">Se l'attributo dispone di proprietà pubbliche, è possono utilizzare argomenti denominati.</span><span class="sxs-lookup"><span data-stu-id="4c61e-116">Named arguments can be used if the attribute has public properties.</span></span> <span data-ttu-id="4c61e-117">È possibile impostare questi eventi utilizzando la sintassi seguente nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="4c61e-117">You can set these by using the following syntax in the argument list.</span></span>

```
*property-name* = *property-value*
```

<span data-ttu-id="4c61e-118">Tali inizializzazioni delle proprietà possono essere in qualsiasi ordine, ma devono seguire tutti gli argomenti posizionali.</span><span class="sxs-lookup"><span data-stu-id="4c61e-118">Such property initializations can be in any order, but they must follow any positional arguments.</span></span> <span data-ttu-id="4c61e-119">Ecco un esempio di un attributo che usa argomenti posizionali e inizializzazioni delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c61e-119">Following is an example of an attribute that uses positional arguments and property initializations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

<span data-ttu-id="4c61e-120">In questo esempio, l'attributo è `DllImportAttribute`, utilizzato nella forma abbreviata.</span><span class="sxs-lookup"><span data-stu-id="4c61e-120">In this example, the attribute is `DllImportAttribute`, here used in shortened form.</span></span> <span data-ttu-id="4c61e-121">Il primo argomento è un parametro posizionale e la seconda è una proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c61e-121">The first argument is a positional parameter and the second is a property.</span></span>

<span data-ttu-id="4c61e-122">Gli attributi sono un costrutto di programmazione .NET che consente a un oggetto noto come un *attributo* da associare a un tipo o altro elemento del programma.</span><span class="sxs-lookup"><span data-stu-id="4c61e-122">Attributes are a .NET programming construct that enables an object known as an *attribute* to be associated with a type or other program element.</span></span> <span data-ttu-id="4c61e-123">L'elemento di programma a cui viene applicato un attributo è noto come il *la destinazione dell'attributo*.</span><span class="sxs-lookup"><span data-stu-id="4c61e-123">The program element to which an attribute is applied is known as the *attribute target*.</span></span> <span data-ttu-id="4c61e-124">L'attributo è in genere contiene i metadati relativi alla sua destinazione.</span><span class="sxs-lookup"><span data-stu-id="4c61e-124">The attribute usually contains metadata about its target.</span></span> <span data-ttu-id="4c61e-125">In questo contesto, i metadati potrebbe essere tutti i dati sul tipo diverso di campi e membri.</span><span class="sxs-lookup"><span data-stu-id="4c61e-125">In this context, metadata could be any data about the type other than its fields and members.</span></span>

<span data-ttu-id="4c61e-126">Attributi in F # possono essere applicati per i costrutti di programmazione seguenti: funzioni, metodi, assembly, moduli, tipi (classi, record, strutture, interfacce, delegati, enumerazioni, unioni e così via), costruttori, proprietà, campi, parametri, parametri di tipo e valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="4c61e-126">Attributes in F# can be applied to the following programming constructs: functions, methods, assemblies, modules, types (classes, records, structures, interfaces, delegates, enumerations, unions, and so on), constructors, properties, fields, parameters, type parameters, and return values.</span></span> <span data-ttu-id="4c61e-127">Gli attributi non consentiti su `let` associazioni all'interno di classi, espressioni o espressioni del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4c61e-127">Attributes are not allowed on `let` bindings inside classes, expressions, or workflow expressions.</span></span>

<span data-ttu-id="4c61e-128">In genere, la dichiarazione di attributo viene visualizzato direttamente prima della dichiarazione dell'attributo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4c61e-128">Typically, the attribute declaration appears directly before the declaration of the attribute target.</span></span> <span data-ttu-id="4c61e-129">Insieme, come indicato di seguito, è possono utilizzare più dichiarazioni di attributo.</span><span class="sxs-lookup"><span data-stu-id="4c61e-129">Multiple attribute declarations can be used together, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

<span data-ttu-id="4c61e-130">È possibile eseguire query di attributi in fase di esecuzione tramite la reflection .NET.</span><span class="sxs-lookup"><span data-stu-id="4c61e-130">You can query attributes at run time by using .NET reflection.</span></span>

<span data-ttu-id="4c61e-131">È possibile dichiarare più attributi singoli, come nell'esempio di codice precedente, oppure è possibile dichiararli in un set di parentesi, se si utilizza un punto e virgola per separare i singoli attributi e i costruttori, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4c61e-131">You can declare multiple attributes individually, as in the previous code example, or you can declare them in one set of brackets if you use a semicolon to separate the individual attributes and constructors, as shown here.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

<span data-ttu-id="4c61e-132">In genere, gli attributi includono il `Obsolete` attributi, gli attributi per motivi di sicurezza, gli attributi per il supporto COM, gli attributi relativi alla proprietà del codice e gli attributi che indica se un tipo può essere serializzato.</span><span class="sxs-lookup"><span data-stu-id="4c61e-132">Typically encountered attributes include the `Obsolete` attribute, attributes for security considerations, attributes for COM support, attributes that relate to ownership of code, and attributes indicating whether a type can be serialized.</span></span> <span data-ttu-id="4c61e-133">Nell'esempio seguente viene illustrato l'utilizzo del `Obsolete` attributo.</span><span class="sxs-lookup"><span data-stu-id="4c61e-133">The following example demonstrates the use of the `Obsolete` attribute.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

<span data-ttu-id="4c61e-134">Per le destinazioni degli attributi `assembly` e `module`, applicare gli attributi di un livello principale `do` associazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4c61e-134">For the attribute targets `assembly` and `module`, you apply the attributes to a top-level `do` binding in your assembly.</span></span> <span data-ttu-id="4c61e-135">È possibile includere la parola `assembly` o `module` nella dichiarazione di attributo, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="4c61e-135">You can include the word `assembly` or `module` in the attribute declaration, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

<span data-ttu-id="4c61e-136">Se si omette l'attributo di destinazione per un attributo applicato a un `do` associazione, il compilatore F # tenta di determinare l'attributo di destinazione appropriato per tale attributo.</span><span class="sxs-lookup"><span data-stu-id="4c61e-136">If you omit the attribute target for an attribute applied to a `do` binding, the F# compiler attempts to determine the attribute target that makes sense for that attribute.</span></span> <span data-ttu-id="4c61e-137">Molte classi di attributo dispongono di un attributo di tipo `System.AttributeUsageAttribute` che include informazioni sulle possibili destinazioni per l'attributo è supportato.</span><span class="sxs-lookup"><span data-stu-id="4c61e-137">Many attribute classes have an attribute of type `System.AttributeUsageAttribute` that includes information about the possible targets supported for that attribute.</span></span> <span data-ttu-id="4c61e-138">Se il `System.AttributeUsageAttribute` indica che l'attributo supporta le funzioni come destinazione, l'attributo viene applicato al punto di ingresso principale del programma.</span><span class="sxs-lookup"><span data-stu-id="4c61e-138">If the `System.AttributeUsageAttribute` indicates that the attribute supports functions as targets, the attribute is taken to apply to the main entry point of the program.</span></span> <span data-ttu-id="4c61e-139">Se il `System.AttributeUsageAttribute` indica che l'attributo supporta gli assembly come destinazione, il compilatore prende l'attributo da applicare all'assembly.</span><span class="sxs-lookup"><span data-stu-id="4c61e-139">If the `System.AttributeUsageAttribute` indicates that the attribute supports assemblies as targets, the compiler takes the attribute to apply to the assembly.</span></span> <span data-ttu-id="4c61e-140">La maggior parte degli attributi non sono applicano per le funzioni e gli assembly, ma nei casi in cui avviene, è necessario l'attributo si applica alla funzione principale del programma.</span><span class="sxs-lookup"><span data-stu-id="4c61e-140">Most attributes do not apply to both functions and assemblies, but in cases where they do, the attribute is taken to apply to the program's main function.</span></span> <span data-ttu-id="4c61e-141">Se l'attributo di destinazione è specificato in modo esplicito, l'attributo viene applicato alla destinazione specificata.</span><span class="sxs-lookup"><span data-stu-id="4c61e-141">If the attribute target is specified explicitly, the attribute is applied to the specified target.</span></span>

<span data-ttu-id="4c61e-142">Anche se in genere è necessario specificare l'attributo di destinazione in modo esplicito, i valori validi per *destinazione* in un attributo sono illustrati nella tabella seguente, insieme a esempi di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="4c61e-142">Although you do not usually need to specify the attribute target explicitly, valid values for *target* in an attribute are shown in the following table, along with examples of usage.</span></span>

<table>
  <tr>
    <th><span data-ttu-id="4c61e-143">Attributo di destinazione</span><span class="sxs-lookup"><span data-stu-id="4c61e-143">Attribute target</span></span></td>
    <th><span data-ttu-id="4c61e-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c61e-144">Example</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4c61e-145">assembly</span><span class="sxs-lookup"><span data-stu-id="4c61e-145">assembly</span></span></td>
    <td><span data-ttu-id="4c61e-146">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span><span class="sxs-lookup"><span data-stu-id="4c61e-146">`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4c61e-147">return</span><span class="sxs-lookup"><span data-stu-id="4c61e-147">return</span></span></td>
    <td><span data-ttu-id="4c61e-148">' function1 let x: [<return: Obsolete>] int = x + 1'</span><span class="sxs-lookup"><span data-stu-id="4c61e-148">`let function1 x : [<return: Obsolete>] int = x + 1`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4c61e-149">campo</span><span class="sxs-lookup"><span data-stu-id="4c61e-149">field</span></span></td>
    <td><span data-ttu-id="4c61e-150">' [<field: DefaultValue>] x: int modificabile val'</span><span class="sxs-lookup"><span data-stu-id="4c61e-150">`[<field: DefaultValue>] val mutable x: int`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4c61e-151">proprietà</span><span class="sxs-lookup"><span data-stu-id="4c61e-151">property</span></span></td>
    <td><span data-ttu-id="4c61e-152">' [<property: Obsolete>] questo. MyProperty = x'</span><span class="sxs-lookup"><span data-stu-id="4c61e-152">`[<property: Obsolete>] this.MyProperty = x`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4c61e-153">Param</span><span class="sxs-lookup"><span data-stu-id="4c61e-153">param</span></span></td>
    <td><span data-ttu-id="4c61e-154">' membro questo. MyMethod ([<param: Out>] x: ref<int>) = x: = 10"</span><span class="sxs-lookup"><span data-stu-id="4c61e-154">`member this.MyMethod([<param: Out>] x : ref<int>) = x := 10`</span></span></td> 
  </tr>
  <tr>
    <td><span data-ttu-id="4c61e-155">tipo</span><span class="sxs-lookup"><span data-stu-id="4c61e-155">type</span></span></td>
    <td><span data-ttu-id="4c61e-156">
        ```
        [<type: StructLayout(Sequential)>] digitare MyStruct = struct x: y byte: fine int```
    </span><span class="sxs-lookup"><span data-stu-id="4c61e-156">
        ```
        [<type: StructLayout(Sequential)>] type MyStruct = struct x : byte y : int end ```
    </span></span></td> 
  </tr>
</table>

## <a name="see-also"></a><span data-ttu-id="4c61e-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c61e-157">See Also</span></span>

[<span data-ttu-id="4c61e-158">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="4c61e-158">F# Language Reference</span></span>](index.md)
