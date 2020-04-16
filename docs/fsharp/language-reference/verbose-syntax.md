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
# <a name="verbose-syntax"></a>Sintassi dettagliata

Sono disponibili due forme di sintassi per molti costrutti nel linguaggio F: *sintassi dettagliata* e *sintassi leggera*. La sintassi dettagliata non è così comunemente usata, ma ha il vantaggio di essere meno sensibile al rientro. La sintassi leggera è più breve e utilizza il rientro per segnalare `begin` `end`l'inizio e la fine dei costrutti, anziché parole chiave aggiuntive come , , `in`e così via. La sintassi predefinita è la sintassi leggera. In questo argomento viene descritta la sintassi per i costrutti F , quando la sintassi leggera non è abilitata. La sintassi dettagliata è sempre abilitata, pertanto anche se si abilita la sintassi leggera, è comunque possibile usare la sintassi dettagliata per alcuni costrutti. È possibile disabilitare la `#light "off"` sintassi leggera utilizzando la direttiva .

## <a name="table-of-constructs"></a>Tabella dei costrutti

Nella tabella seguente viene illustrata la sintassi leggera e dettagliata per i costrutti di linguaggio F , in contesti in cui esiste una differenza tra i due formati. In questa tabella, le&lt;&gt;parentesi angolari ( ) racchiudono gli elementi di sintassi forniti dall'utente. Fare riferimento alla documentazione per ogni costrutto di linguaggio per informazioni più dettagliate sulla sintassi utilizzata all'interno di questi costrutti.

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
<tr><td>structure</td><td>

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
<tr><td>sindacato discriminato</td><td>

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
<tr><td>tipo estensione</td><td>

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
<tr><td>modulo</td><td>

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

- [Guida di riferimento al linguaggio F](index.md)
- [Direttive per il compilatore](compiler-directives.md)
- [Linee guida per la formattazione del codice](../style-guide/formatting.md)
