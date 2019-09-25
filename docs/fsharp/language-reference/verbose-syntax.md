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
# <a name="verbose-syntax"></a>Sintassi dettagliata

Esistono due forme di sintassi disponibili per molti costrutti nel F# linguaggio: *sintassi dettagliata* e *sintassi leggera*. La sintassi dettagliata non è comunemente utilizzata, ma presenta il vantaggio di essere meno sensibile ai rientri. La sintassi leggera è più breve e utilizza il rientro per segnalare l'inizio e la fine dei costrutti, anziché parole chiave `begin`aggiuntive `end`come `in`,, e così via. La sintassi predefinita è la sintassi semplificata. In questo argomento viene descritta la F# sintassi dei costrutti quando la sintassi Lightweight non è abilitata. La sintassi verbose è sempre abilitata, quindi anche se si Abilita la sintassi leggera, è comunque possibile usare la sintassi dettagliata per alcuni costrutti. È possibile disabilitare la sintassi Lightweight usando la `#light "off"` direttiva.

## <a name="table-of-constructs"></a>Tabella dei costrutti

La tabella seguente illustra la sintassi semplificata e dettagliata per F# i costrutti di linguaggio in contesti in cui esiste una differenza tra le due forme. In questa tabella, le parentesi angolari (&lt;&gt;) racchiudono gli elementi della sintassi specificati dall'utente. Per informazioni più dettagliate sulla sintassi usata all'interno di questi costrutti, vedere la documentazione relativa a ogni costrutto di linguaggio.

<table>
<tr>
<th>Costrutto di linguaggio</th>
<th>Sintassi leggera</th>
<th>Sintassi dettagliata</th>
</tr>
<tr>
<td>
espressioni composte
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

associazioni `let` annidate

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
blocco di codice
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
<tr><td>record
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
<tr><td>classe
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
<tr><td>struttura</td><td>

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
<tr><td>unione discriminata</td><td>

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
<tr><td>interfaccia</td><td>

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
<tr><td>espressione oggetto</td><td>

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
<tr><td>implementazione dell'interfaccia</td><td>

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
<tr><td>estensione del tipo</td><td>

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
<tr><td>module</td><td>

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

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Direttive per il compilatore](compiler-directives.md)
- [Linee guida per la formattazione del codice](code-formatting-guidelines.md)
