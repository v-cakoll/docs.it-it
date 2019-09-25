---
title: Sintassi dettagliata
description: Informazioni sulla differenza tra sintassi dettagliata e leggera nel linguaggio di F# programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: d2459da60bba5d88bd23615c8bf09ba64f7c22c4
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214044"
---
# <a name="verbose-syntax"></a><span data-ttu-id="2af0d-103">Sintassi dettagliata</span><span class="sxs-lookup"><span data-stu-id="2af0d-103">Verbose Syntax</span></span>

<span data-ttu-id="2af0d-104">Esistono due forme di sintassi disponibili per molti costrutti nel F# linguaggio: *sintassi dettagliata* e *sintassi leggera*.</span><span class="sxs-lookup"><span data-stu-id="2af0d-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="2af0d-105">La sintassi dettagliata non è comunemente utilizzata, ma presenta il vantaggio di essere meno sensibile ai rientri.</span><span class="sxs-lookup"><span data-stu-id="2af0d-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="2af0d-106">La sintassi leggera è più breve e utilizza il rientro per segnalare l'inizio e la fine dei costrutti, anziché parole chiave `begin`aggiuntive `end`come `in`,, e così via.</span><span class="sxs-lookup"><span data-stu-id="2af0d-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="2af0d-107">La sintassi predefinita è la sintassi semplificata.</span><span class="sxs-lookup"><span data-stu-id="2af0d-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="2af0d-108">In questo argomento viene descritta la F# sintassi dei costrutti quando la sintassi Lightweight non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="2af0d-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="2af0d-109">La sintassi verbose è sempre abilitata, quindi anche se si Abilita la sintassi leggera, è comunque possibile usare la sintassi dettagliata per alcuni costrutti.</span><span class="sxs-lookup"><span data-stu-id="2af0d-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="2af0d-110">È possibile disabilitare la sintassi Lightweight usando la `#light "off"` direttiva.</span><span class="sxs-lookup"><span data-stu-id="2af0d-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="2af0d-111">Tabella dei costrutti</span><span class="sxs-lookup"><span data-stu-id="2af0d-111">Table of Constructs</span></span>

<span data-ttu-id="2af0d-112">La tabella seguente illustra la sintassi semplificata e dettagliata per F# i costrutti di linguaggio in contesti in cui esiste una differenza tra le due forme.</span><span class="sxs-lookup"><span data-stu-id="2af0d-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="2af0d-113">In questa tabella, le parentesi angolari (&lt;&gt;) racchiudono gli elementi della sintassi specificati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2af0d-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="2af0d-114">Per informazioni più dettagliate sulla sintassi usata all'interno di questi costrutti, vedere la documentazione relativa a ogni costrutto di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="2af0d-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="2af0d-115">Costrutto di linguaggio</span><span class="sxs-lookup"><span data-stu-id="2af0d-115">Language construct</span></span></th>
<th><span data-ttu-id="2af0d-116">Sintassi leggera</span><span class="sxs-lookup"><span data-stu-id="2af0d-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="2af0d-117">Sintassi dettagliata</span><span class="sxs-lookup"><span data-stu-id="2af0d-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="2af0d-118">espressioni composte</span><span class="sxs-lookup"><span data-stu-id="2af0d-118">compound expressions</span></span>
</td>
<td>

```xml
<expression1>
<expression2>
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

<span data-ttu-id="2af0d-119">associazioni `let` annidate</span><span class="sxs-lookup"><span data-stu-id="2af0d-119">nested `let` bindings</span></span>

</td><td>

```fsharp
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```fsharp
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
<span data-ttu-id="2af0d-120">blocco di codice</span><span class="sxs-lookup"><span data-stu-id="2af0d-120">code block</span></span>
</td><td>

```fsharp
(
    <expression1>
    <expression2>
)
```

</td><td>

```fsharp
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

```fsharp
for counter = start to finish do
    ...
```

</td><td>

```fsharp
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```fsharp
while <condition> do
    ...
```

</td><td>

```fsharp
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```fsharp
for var in start .. finish do
    ...
```

</td><td>

```fsharp
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```fsharp
do
    ...
```

</td><td>

```fsharp
do
    ...
in
```

</td>
</tr>
<tr><td><span data-ttu-id="2af0d-121">record</span><span class="sxs-lookup"><span data-stu-id="2af0d-121">record</span></span>
</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```fsharp
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
<tr><td><span data-ttu-id="2af0d-122">classe</span><span class="sxs-lookup"><span data-stu-id="2af0d-122">class</span></span>
</td><td>

```fsharp
type <class-name>(<params>) =
    ...
```

</td><td>

```fsharp
type <class-name>(<params>) =
    class
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="2af0d-123">struttura</span><span class="sxs-lookup"><span data-stu-id="2af0d-123">structure</span></span></td><td>

```fsharp
[<StructAttribute>]
type <structure-name> =
    ...
```

</td><td>

```fsharp
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="2af0d-124">unione discriminata</span><span class="sxs-lookup"><span data-stu-id="2af0d-124">discriminated union</span></span></td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```

</td><td>

```fsharp
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
<tr><td><span data-ttu-id="2af0d-125">interfaccia</span><span class="sxs-lookup"><span data-stu-id="2af0d-125">interface</span></span></td><td>

```fsharp
type <interface-name> =
    ...
```

</td><td>

```fsharp
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="2af0d-126">espressione oggetto</span><span class="sxs-lookup"><span data-stu-id="2af0d-126">object expression</span></span></td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td><span data-ttu-id="2af0d-127">implementazione dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="2af0d-127">interface implementation</span></span></td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="2af0d-128">estensione del tipo</span><span class="sxs-lookup"><span data-stu-id="2af0d-128">type extension</span></span></td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="2af0d-129">module</span><span class="sxs-lookup"><span data-stu-id="2af0d-129">module</span></span></td><td>

```fsharp
module <module-name> =
    ...
```

</td><td>

```fsharp
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>

## <a name="see-also"></a><span data-ttu-id="2af0d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2af0d-130">See also</span></span>

- [<span data-ttu-id="2af0d-131">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="2af0d-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2af0d-132">Direttive per il compilatore</span><span class="sxs-lookup"><span data-stu-id="2af0d-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="2af0d-133">Linee guida per la formattazione del codice</span><span class="sxs-lookup"><span data-stu-id="2af0d-133">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
