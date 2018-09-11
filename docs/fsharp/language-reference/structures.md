---
title: Strutture (F#)
description: 'Informazioni sulla struttura F #, un tipo di oggetto compatto spesso più efficiente rispetto a una classe per i tipi con una piccola quantità di dati e comportamento semplice.'
ms.date: 05/16/2016
ms.openlocfilehash: 08af88132dda28883e246b94585ff4ed8bd2f16a
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44337955"
---
# <a name="structures"></a>Strutture

Oggetto *struttura* è un tipo di oggetto compatto che può essere più efficiente rispetto a una classe per tipi che dispongono di una piccola quantità di dati e comportamento semplice.

## <a name="syntax"></a>Sintassi

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a>Note

Le strutture sono *i tipi di valore*, che indica che essi vengono archiviate direttamente sullo stack o, quando vengono utilizzati come campi o tipo di elementi di matrice, inline nell'elemento padre. A differenza di record e classi, le strutture hanno una semantica pass-by-value. Ciò significa che sono utili principalmente per piccole aggregazioni di dati accessibili e copiati di frequente.

Nella sintassi precedente sono illustrate due forme. La prima non è la sintassi leggera, ma viene comunque usata frequentemente perché, quando si usano la parole chiave `struct` e `end`, è possibile omettere l'attributo `StructAttribute`, che viene visualizzato nella seconda forma. È possibile abbreviare `StructAttribute` in `Struct`.

Il *-definition-elementi-e-membri di tipo* nella sintassi precedente rappresenta definizioni e dichiarazioni di membri. Le strutture possono disporre di costruttori e campi modificabili e non modificabili e possono dichiarare i membri e le implementazioni dell'interfaccia. Per altre informazioni, vedere [membri](members/index.md).

Le strutture non possono partecipare all'ereditarietà, non possono contenere associazioni `let` o `do` e non possono contenere in modo ricorsivo campi del proprio tipo (nonostante possano contenere celle di riferimento che facciano riferimento al proprio tipo).

Poiché le strutture non consentono associazioni `let`, è necessario dichiarare i campi nelle strutture usando la parola chiave `val`. La parola chiave `val` definisce un campo e il relativo tipo, ma non consente l'inizializzazione. Al contrario, le dichiarazioni `val` sono inizializzate su zero o null. Per questo motivo, le strutture che hanno un costruttore implicito (ovvero, i parametri forniti immediatamente dopo il nome della struttura nella dichiarazione) richiedono di annotare le dichiarazioni `val` con l'attributo `DefaultValue`. Le strutture che hanno un costruttore definito supportano comunque l'inizializzazione su zero. Quindi, l'attributo `DefaultValue` è una dichiarazione che tale valore zero è valido per il campo. I costruttori impliciti per le strutture non eseguono alcuna azione perché le associazioni `let` e `do` non sono consentite per il tipo, ma i valori di parametro di costruttore implicito passati sono disponibili come campi privati.

I costruttori espliciti potrebbero comportare l'inizializzazione dei valori di campo. Quando si ha una struttura con un costruttore esplicito, è comunque supportata l'inizializzazione su zero. Tuttavia, non usare l'attributo `DefaultValue` sulle dichiarazioni `val` perché è in conflitto con il costruttore esplicito. Per altre informazioni sulle `val` dichiarazioni, vedere [i campi espliciti: il `val` parola chiave](members/explicit-fields-the-val-keyword.md).

Gli attributi e modificatori di accessibilità sono consentiti nelle strutture e seguono le stesse regole per gli altri tipi. Per altre informazioni, vedere [attributi](attributes.md) e [Access Control](access-control.md).

Gli esempi di codice seguenti illustrano le definizioni delle strutture.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a>Struct ByRefLike

È possibile definire struct che possono rispettare `byref`-come semantica: vedere [Zkratka](byrefs.md) per altre informazioni. Questa operazione viene eseguita con il <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attributo:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` non implica `Struct`. Entrambi devono essere presenti nel tipo.

Un "`byref`-ad esempio" struct in F # è un tipo di valore con associazione dello stack. Non viene allocato nell'heap gestito. Oggetto `byref`-come struct è utile per la programmazione ad alte prestazioni, come viene applicato con set di controlli accurati su durata e di non acquisizione. Le regole sono:

* Possono essere utilizzati come parametri di funzione, i parametri dei metodi, variabili locali, metodo viene restituito.
* Essi non può essere statico o istanza i membri di una classe o struct normali.
* Non è possibile acquisire da qualsiasi costrutto di chiusura (`async` metodi o espressioni lambda).
* Non possono essere utilizzati come un parametro generico.

Anche se queste regole limitano molto fortemente utilizzo, a tale scopo per soddisfare la promessa di high performance computing in modo sicuro.

## <a name="readonly-structs"></a>Struct di sola lettura

È possibile aggiungere annotazioni di struct con il <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> attributo. Ad esempio:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsReadOnly` non implica `Struct`. È necessario aggiungere entrambi disporre un `IsReadOnly` struct.

Utilizzo di questo attributo genera metadati consentendo F # e c# sa di considerarla `inref<'T>` e `in ref`, rispettivamente.

Definizione di un valore modificabile all'interno di uno struct di sola lettura, viene generato un errore.

## <a name="struct-records-and-discriminated-unions"></a>I record di struct e unioni discriminate

È possibile rappresentare [record](records.md) e [unioni discriminate](discriminated-unions.md) come struct con il `[<Struct>]` attributo.  Vedere ogni articolo per altre informazioni.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Classi](classes.md)
- [Record](records.md)
- [Membri](members/index.md)
