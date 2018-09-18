---
title: Sintassi dettagliata (F#)
description: 'Informazioni sulla differenza tra la sintassi dettagliata e leggera nel linguaggio di programmazione F #.'
ms.date: 05/16/2016
ms.openlocfilehash: b4f2354738da4692cb444e5e7dd9531d80d26664
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "45972319"
---
# <a name="verbose-syntax"></a>Sintassi dettagliata

Sono disponibili due forme di sintassi per numerosi costrutti del linguaggio F #: *sintassi dettagliata* e *sintassi leggera*. La sintassi dettagliata non è viene comunemente utilizzata, ma offre il vantaggio di essere meno sensibili alla rientro. La sintassi leggera è più breve e utilizza il rientro per indicare l'inizio e alla fine di costrutti, anziché, ad esempio parole chiave aggiuntive `begin`, `end`, `in`e così via. La sintassi di predefinita è la sintassi leggera. Questo argomento viene descritta la sintassi per i costrutti F # sintassi leggera non è abilitata. Sintassi dettagliata è sempre abilitata, in modo che anche se si abilita la sintassi leggera, è comunque possibile usare la sintassi dettagliata per alcuni costrutti. È possibile disabilitare la sintassi leggera, utilizzando il `#light "off"` direttiva.

## <a name="table-of-constructs"></a>Tabella dei costrutti

Nella tabella seguente illustra la sintassi leggera e dettagliata per costrutti del linguaggio F # nei contesti in cui è presente una differenza tra le due forme. In questa tabella, le parentesi acute (&lt;&gt;) racchiudere gli elementi della sintassi fornita dall'utente. Vedere la documentazione per ogni costrutto di linguaggio per informazioni più dettagliate sulla sintassi usata all'interno di questi costrutti.

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

```
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>


nidificata `let` associazioni

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
blocco di codice
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
<tr><td>Record
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
<tr><td>classe
</td><td>
```
type <class-name>(<params>) = ... ```

</td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td>struttura</td><td>

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
<tr><td>unione discriminata</td><td>

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
<tr><td>interfaccia</td><td>

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
<tr><td>espressione di oggetto</td><td>

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
<tr><td>implementazione dell'interfaccia</td><td>

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
<tr><td>estensione del tipo</td><td>

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
<tr><td>module</td><td>

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

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Direttive per il compilatore](compiler-directives.md)
- [Linee guida per la formattazione del codice](code-formatting-guidelines.md)
