---
title: Sintassi dettagliata (F#)
description: 'Informazioni sulla differenza tra la sintassi dettagliata e leggera nel linguaggio di programmazione F #.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0a6792b3-b312-4453-a025-21d9760eee5d
ms.openlocfilehash: 2cef359a879897825733a3186be97b38896f5953
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="verbose-syntax"></a><span data-ttu-id="4fa8e-104">Sintassi dettagliata</span><span class="sxs-lookup"><span data-stu-id="4fa8e-104">Verbose Syntax</span></span>

<span data-ttu-id="4fa8e-105">Sono disponibili due forme di sintassi per numerosi costrutti di linguaggio F #: *sintassi dettagliata* e *sintassi leggera*.</span><span class="sxs-lookup"><span data-stu-id="4fa8e-105">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="4fa8e-106">La sintassi dettagliata non viene usata di frequente, ma ha il vantaggio di essere meno sensibile rientro.</span><span class="sxs-lookup"><span data-stu-id="4fa8e-106">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="4fa8e-107">La sintassi leggera è più breve e utilizza il rientro per segnalare l'inizio e fine dei costrutti, anziché come parole chiave aggiuntive `begin`, `end`, `in`e così via.</span><span class="sxs-lookup"><span data-stu-id="4fa8e-107">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="4fa8e-108">La sintassi predefinita è la sintassi leggera.</span><span class="sxs-lookup"><span data-stu-id="4fa8e-108">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="4fa8e-109">In questo argomento viene descritta la sintassi per i costrutti F # quando non è abilitata la sintassi leggera.</span><span class="sxs-lookup"><span data-stu-id="4fa8e-109">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="4fa8e-110">Sintassi dettagliata è sempre abilitata, pertanto anche se si abilita la sintassi leggera, è comunque possibile usare la sintassi dettagliata per alcuni costrutti.</span><span class="sxs-lookup"><span data-stu-id="4fa8e-110">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="4fa8e-111">È possibile disabilitare la sintassi leggera utilizzando il `#light "off"` direttiva.</span><span class="sxs-lookup"><span data-stu-id="4fa8e-111">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>


## <a name="table-of-constructs"></a><span data-ttu-id="4fa8e-112">Tabella dei costrutti</span><span class="sxs-lookup"><span data-stu-id="4fa8e-112">Table of Constructs</span></span>
<span data-ttu-id="4fa8e-113">Nella tabella seguente viene mostrata la sintassi leggera e dettagliata per i costrutti di linguaggio F # in contesti in cui è presente una differenza tra le due forme.</span><span class="sxs-lookup"><span data-stu-id="4fa8e-113">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="4fa8e-114">In questa tabella, le parentesi acute (&lt;&gt;) racchiudere gli elementi della sintassi fornito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4fa8e-114">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="4fa8e-115">Consultare la documentazione per ogni costrutto di linguaggio per informazioni più dettagliate sulla sintassi utilizzata all'interno di questi costrutti.</span><span class="sxs-lookup"><span data-stu-id="4fa8e-115">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>



<table>
<tr>
<th><span data-ttu-id="4fa8e-116">Costrutto di linguaggio</span><span class="sxs-lookup"><span data-stu-id="4fa8e-116">Language construct</span></span></th>
<th><span data-ttu-id="4fa8e-117">Sintassi leggera</span><span class="sxs-lookup"><span data-stu-id="4fa8e-117">Lightweight syntax</span></span></th>
<th><span data-ttu-id="4fa8e-118">Sintassi dettagliata</span><span class="sxs-lookup"><span data-stu-id="4fa8e-118">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="4fa8e-119">espressioni composte</span><span class="sxs-lookup"><span data-stu-id="4fa8e-119">compound expressions</span></span>
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


<span data-ttu-id="4fa8e-120">nidificata `let` associazioni</span><span class="sxs-lookup"><span data-stu-id="4fa8e-120">nested `let` bindings</span></span>

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
<span data-ttu-id="4fa8e-121">blocco di codice</span><span class="sxs-lookup"><span data-stu-id="4fa8e-121">code block</span></span>
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
<tr><td><span data-ttu-id="4fa8e-122">Record</span><span class="sxs-lookup"><span data-stu-id="4fa8e-122">record</span></span>
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
<tr><td><span data-ttu-id="4fa8e-123">classe</span><span class="sxs-lookup"><span data-stu-id="4fa8e-123">class</span></span>
</td><td><span data-ttu-id="4fa8e-124">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="4fa8e-124">
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
<tr><td><span data-ttu-id="4fa8e-125">struttura</span><span class="sxs-lookup"><span data-stu-id="4fa8e-125">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="4fa8e-126">unione discriminata</span><span class="sxs-lookup"><span data-stu-id="4fa8e-126">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="4fa8e-127">interfaccia</span><span class="sxs-lookup"><span data-stu-id="4fa8e-127">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="4fa8e-128">espressione di oggetto</span><span class="sxs-lookup"><span data-stu-id="4fa8e-128">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="4fa8e-129">implementazione dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="4fa8e-129">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="4fa8e-130">estensione del tipo</span><span class="sxs-lookup"><span data-stu-id="4fa8e-130">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="4fa8e-131">module</span><span class="sxs-lookup"><span data-stu-id="4fa8e-131">module</span></span></td><td>

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



## <a name="see-also"></a><span data-ttu-id="4fa8e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fa8e-132">See Also</span></span>
[<span data-ttu-id="4fa8e-133">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="4fa8e-133">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="4fa8e-134">Direttive per il compilatore</span><span class="sxs-lookup"><span data-stu-id="4fa8e-134">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="4fa8e-135">Linee guida per la formattazione del codice</span><span class="sxs-lookup"><span data-stu-id="4fa8e-135">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
