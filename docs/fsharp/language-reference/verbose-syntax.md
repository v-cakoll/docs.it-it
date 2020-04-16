---
title: Sintassi dettagliata
description: Informazioni sulla differenza tra sintassi dettagliata e leggera nel linguaggio di programmazione F.
ms.date: 05/16/2016
ms.openlocfilehash: 722807695c56beb0d681b95a78ed8cb8c1df3ddf
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463911"
---
# <a name="verbose-syntax"></a><span data-ttu-id="7bf9a-103">Sintassi dettagliata</span><span class="sxs-lookup"><span data-stu-id="7bf9a-103">Verbose Syntax</span></span>

<span data-ttu-id="7bf9a-104">Sono disponibili due forme di sintassi per molti costrutti nel linguaggio F: *sintassi dettagliata* e *sintassi leggera*.</span><span class="sxs-lookup"><span data-stu-id="7bf9a-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="7bf9a-105">La sintassi dettagliata non è così comunemente usata, ma ha il vantaggio di essere meno sensibile al rientro.</span><span class="sxs-lookup"><span data-stu-id="7bf9a-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="7bf9a-106">La sintassi leggera è più breve e utilizza il rientro per segnalare `begin` `end`l'inizio e la fine dei costrutti, anziché parole chiave aggiuntive come , , `in`e così via.</span><span class="sxs-lookup"><span data-stu-id="7bf9a-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="7bf9a-107">La sintassi predefinita è la sintassi leggera.</span><span class="sxs-lookup"><span data-stu-id="7bf9a-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="7bf9a-108">In questo argomento viene descritta la sintassi per i costrutti F , quando la sintassi leggera non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="7bf9a-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="7bf9a-109">La sintassi dettagliata è sempre abilitata, pertanto anche se si abilita la sintassi leggera, è comunque possibile usare la sintassi dettagliata per alcuni costrutti.</span><span class="sxs-lookup"><span data-stu-id="7bf9a-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="7bf9a-110">È possibile disabilitare la `#light "off"` sintassi leggera utilizzando la direttiva .</span><span class="sxs-lookup"><span data-stu-id="7bf9a-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="7bf9a-111">Tabella dei costrutti</span><span class="sxs-lookup"><span data-stu-id="7bf9a-111">Table of Constructs</span></span>

<span data-ttu-id="7bf9a-112">Nella tabella seguente viene illustrata la sintassi leggera e dettagliata per i costrutti di linguaggio F , in contesti in cui esiste una differenza tra i due formati.</span><span class="sxs-lookup"><span data-stu-id="7bf9a-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="7bf9a-113">In questa tabella, le&lt;&gt;parentesi angolari ( ) racchiudono gli elementi di sintassi forniti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7bf9a-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="7bf9a-114">Fare riferimento alla documentazione per ogni costrutto di linguaggio per informazioni più dettagliate sulla sintassi utilizzata all'interno di questi costrutti.</span><span class="sxs-lookup"><span data-stu-id="7bf9a-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="7bf9a-115">Costrutto di linguaggio</span><span class="sxs-lookup"><span data-stu-id="7bf9a-115">Language construct</span></span></th>
<th><span data-ttu-id="7bf9a-116">Sintassi leggera</span><span class="sxs-lookup"><span data-stu-id="7bf9a-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="7bf9a-117">Sintassi dettagliata</span><span class="sxs-lookup"><span data-stu-id="7bf9a-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="7bf9a-118">espressioni composte</span><span class="sxs-lookup"><span data-stu-id="7bf9a-118">compound expressions</span></span>
</td>
<td>

```xml
<expression1 />
<expression2 />
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

<span data-ttu-id="7bf9a-119">associazioni `let` annidate</span><span class="sxs-lookup"><span data-stu-id="7bf9a-119">nested `let` bindings</span></span>

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
<span data-ttu-id="7bf9a-120">blocco di codice</span><span class="sxs-lookup"><span data-stu-id="7bf9a-120">code block</span></span>
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
<tr><td><span data-ttu-id="7bf9a-121">record</span><span class="sxs-lookup"><span data-stu-id="7bf9a-121">record</span></span>
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
<tr><td><span data-ttu-id="7bf9a-122">classe</span><span class="sxs-lookup"><span data-stu-id="7bf9a-122">class</span></span>
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
<tr><td><span data-ttu-id="7bf9a-123">structure</span><span class="sxs-lookup"><span data-stu-id="7bf9a-123">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="7bf9a-124">sindacato discriminato</span><span class="sxs-lookup"><span data-stu-id="7bf9a-124">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="7bf9a-125">interfaccia</span><span class="sxs-lookup"><span data-stu-id="7bf9a-125">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="7bf9a-126">espressione oggetto</span><span class="sxs-lookup"><span data-stu-id="7bf9a-126">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="7bf9a-127">implementazione dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="7bf9a-127">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="7bf9a-128">tipo estensione</span><span class="sxs-lookup"><span data-stu-id="7bf9a-128">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="7bf9a-129">modulo</span><span class="sxs-lookup"><span data-stu-id="7bf9a-129">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="7bf9a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bf9a-130">See also</span></span>

- [<span data-ttu-id="7bf9a-131">Guida di riferimento al linguaggio F</span><span class="sxs-lookup"><span data-stu-id="7bf9a-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7bf9a-132">Direttive per il compilatore</span><span class="sxs-lookup"><span data-stu-id="7bf9a-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="7bf9a-133">Linee guida per la formattazione del codice</span><span class="sxs-lookup"><span data-stu-id="7bf9a-133">Code Formatting Guidelines</span></span>](../style-guide/formatting.md)
