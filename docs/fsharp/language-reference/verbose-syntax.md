---
title: Sintassi dettagliata (F#)
description: 'Informazioni sulla differenza tra la sintassi dettagliata e leggera nel linguaggio di programmazione F #.'
ms.date: 05/16/2016
ms.openlocfilehash: b4f2354738da4692cb444e5e7dd9531d80d26664
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45589313"
---
# <a name="verbose-syntax"></a><span data-ttu-id="c2781-103">Sintassi dettagliata</span><span class="sxs-lookup"><span data-stu-id="c2781-103">Verbose Syntax</span></span>

<span data-ttu-id="c2781-104">Sono disponibili due forme di sintassi per numerosi costrutti del linguaggio F #: *sintassi dettagliata* e *sintassi leggera*.</span><span class="sxs-lookup"><span data-stu-id="c2781-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="c2781-105">La sintassi dettagliata non è viene comunemente utilizzata, ma offre il vantaggio di essere meno sensibili alla rientro.</span><span class="sxs-lookup"><span data-stu-id="c2781-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="c2781-106">La sintassi leggera è più breve e utilizza il rientro per indicare l'inizio e alla fine di costrutti, anziché, ad esempio parole chiave aggiuntive `begin`, `end`, `in`e così via.</span><span class="sxs-lookup"><span data-stu-id="c2781-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="c2781-107">La sintassi di predefinita è la sintassi leggera.</span><span class="sxs-lookup"><span data-stu-id="c2781-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="c2781-108">Questo argomento viene descritta la sintassi per i costrutti F # sintassi leggera non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="c2781-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="c2781-109">Sintassi dettagliata è sempre abilitata, in modo che anche se si abilita la sintassi leggera, è comunque possibile usare la sintassi dettagliata per alcuni costrutti.</span><span class="sxs-lookup"><span data-stu-id="c2781-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="c2781-110">È possibile disabilitare la sintassi leggera, utilizzando il `#light "off"` direttiva.</span><span class="sxs-lookup"><span data-stu-id="c2781-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="c2781-111">Tabella dei costrutti</span><span class="sxs-lookup"><span data-stu-id="c2781-111">Table of Constructs</span></span>

<span data-ttu-id="c2781-112">Nella tabella seguente illustra la sintassi leggera e dettagliata per costrutti del linguaggio F # nei contesti in cui è presente una differenza tra le due forme.</span><span class="sxs-lookup"><span data-stu-id="c2781-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="c2781-113">In questa tabella, le parentesi acute (&lt;&gt;) racchiudere gli elementi della sintassi fornita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c2781-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="c2781-114">Vedere la documentazione per ogni costrutto di linguaggio per informazioni più dettagliate sulla sintassi usata all'interno di questi costrutti.</span><span class="sxs-lookup"><span data-stu-id="c2781-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="c2781-115">Costrutto di linguaggio</span><span class="sxs-lookup"><span data-stu-id="c2781-115">Language construct</span></span></th>
<th><span data-ttu-id="c2781-116">Sintassi leggera</span><span class="sxs-lookup"><span data-stu-id="c2781-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="c2781-117">Sintassi dettagliata</span><span class="sxs-lookup"><span data-stu-id="c2781-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="c2781-118">espressioni composte</span><span class="sxs-lookup"><span data-stu-id="c2781-118">compound expressions</span></span>
</td>
<td>

```xml
<expression1>
<expression2>
```
</td><td>

```
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>


<span data-ttu-id="c2781-119">nidificata `let` associazioni</span><span class="sxs-lookup"><span data-stu-id="c2781-119">nested `let` bindings</span></span>

</td><td>
```
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
<span data-ttu-id="c2781-120">blocco di codice</span><span class="sxs-lookup"><span data-stu-id="c2781-120">code block</span></span>
</td><td>

```
(
    <expression1>
    <expression2>
)
```

</td><td>

```
begin
    <expression1>;
    <expression2>;
end
```
</td>
</tr>
<tr><td>
`for...do`
</td><td>

```
for counter = start to finish do
    ...
```

</td><td>

```
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```
while <condition> do
    ...
```

</td><td>

```
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```
for var in start .. finish do
    ...
```

</td><td>

```
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```
do
    ...
```

</td><td>

```
do
    ...
in
```

</td>
</tr>
<tr><td><span data-ttu-id="c2781-121">Record</span><span class="sxs-lookup"><span data-stu-id="c2781-121">record</span></span>
</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="c2781-122">classe</span><span class="sxs-lookup"><span data-stu-id="c2781-122">class</span></span>
</td><td><span data-ttu-id="c2781-123">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="c2781-123">
```
type <class-name>(<params>) = ... ```

</span></span></td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td><span data-ttu-id="c2781-124">struttura</span><span class="sxs-lookup"><span data-stu-id="c2781-124">structure</span></span></td><td>

```
[<StructAttribute>]
type <structure-name> =
    ...
```
</td><td>

```
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="c2781-125">unione discriminata</span><span class="sxs-lookup"><span data-stu-id="c2781-125">discriminated union</span></span></td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```
</td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end    
```

</td>
</tr>
<tr><td><span data-ttu-id="c2781-126">interfaccia</span><span class="sxs-lookup"><span data-stu-id="c2781-126">interface</span></span></td><td>

```
type <interface-name> =
    ...
```
</td><td>

```
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="c2781-127">espressione di oggetto</span><span class="sxs-lookup"><span data-stu-id="c2781-127">object expression</span></span></td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td><span data-ttu-id="c2781-128">implementazione dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="c2781-128">interface implementation</span></span></td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="c2781-129">estensione del tipo</span><span class="sxs-lookup"><span data-stu-id="c2781-129">type extension</span></span></td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="c2781-130">module</span><span class="sxs-lookup"><span data-stu-id="c2781-130">module</span></span></td><td>

```
module <module-name> =
    ...
```

</td><td>

```
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>

## <a name="see-also"></a><span data-ttu-id="c2781-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2781-131">See also</span></span>

- [<span data-ttu-id="c2781-132">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="c2781-132">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="c2781-133">Direttive per il compilatore</span><span class="sxs-lookup"><span data-stu-id="c2781-133">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="c2781-134">Linee guida per la formattazione del codice</span><span class="sxs-lookup"><span data-stu-id="c2781-134">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
