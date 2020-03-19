---
title: Strutture
description: Informazioni sulla struttura F , un tipo di oggetto compatto spesso più efficiente di una classe per i tipi con una piccola quantità di dati e un comportamento semplice.
ms.date: 05/16/2016
ms.openlocfilehash: 1e9652cc4776e4d1d52eb20e41b6dd87a6c5ba05
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400281"
---
# <a name="structures"></a>Strutture

Una *struttura* è un tipo di oggetto compatto che può essere più efficiente di una classe per i tipi che dispongono di una piccola quantità di dati e di un comportamento semplice.

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

## <a name="remarks"></a>Osservazioni

Le strutture sono *tipi di valore*, ovvero vengono archiviate direttamente nello stack o, quando vengono utilizzate come campi o elementi della matrice, inline nel tipo padre. A differenza di record e classi, le strutture hanno una semantica pass-by-value. Ciò significa che sono utili principalmente per piccole aggregazioni di dati accessibili e copiati di frequente.

Nella sintassi precedente sono illustrate due forme. La prima non è la sintassi leggera, ma viene comunque usata frequentemente perché, quando si usano la parole chiave  e , è possibile omettere l'attributo , che viene visualizzato nella seconda forma. È possibile abbreviare `StructAttribute` in `Struct`.

Il *type-definition-elements-and-members* nella sintassi precedente rappresenta le dichiarazioni e le definizioni dei membri. Le strutture possono disporre di costruttori e campi modificabili e non modificabili e possono dichiarare i membri e le implementazioni dell'interfaccia. Per ulteriori informazioni, vedere [Membri](./members/index.md).

Le strutture non possono partecipare all'ereditarietà, non possono contenere associazioni `let` o `do` e non possono contenere in modo ricorsivo campi del proprio tipo (nonostante possano contenere celle di riferimento che facciano riferimento al proprio tipo).

Poiché le strutture non consentono associazioni `let`, è necessario dichiarare i campi nelle strutture usando la parola chiave `val`. La parola chiave `val` definisce un campo e il relativo tipo, ma non consente l'inizializzazione. Al contrario, le dichiarazioni `val` sono inizializzate su zero o null. Per questo motivo, le strutture che hanno un costruttore implicito (ovvero, i parametri forniti immediatamente dopo il nome della struttura nella dichiarazione) richiedono di annotare le dichiarazioni `val` con l'attributo `DefaultValue`. Le strutture che hanno un costruttore definito supportano comunque l'inizializzazione su zero. Quindi, l'attributo `DefaultValue` è una dichiarazione che tale valore zero è valido per il campo. I costruttori impliciti per le strutture non eseguono alcuna azione perché le associazioni `let` e `do` non sono consentite per il tipo, ma i valori di parametro di costruttore implicito passati sono disponibili come campi privati.

I costruttori espliciti potrebbero comportare l'inizializzazione dei valori di campo. Quando si ha una struttura con un costruttore esplicito, è comunque supportata l'inizializzazione su zero. Tuttavia, non usare l'attributo `DefaultValue` sulle dichiarazioni `val` perché è in conflitto con il costruttore esplicito. Per ulteriori `val` informazioni sulle dichiarazioni, vedere [Campi espliciti: `val` parola chiave](./members/explicit-fields-the-val-keyword.md).

Gli attributi e modificatori di accessibilità sono consentiti nelle strutture e seguono le stesse regole per gli altri tipi. Per ulteriori informazioni, vedere [Attributi](attributes.md) e [controllo di accesso](access-control.md).

Gli esempi di codice seguenti illustrano le definizioni delle strutture.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a>Struct ByRefLike

È possibile definire struct personalizzati che `byref`possono aderire alla semantica simile: vedere [Byrefs](byrefs.md) per altre informazioni. Questa operazione viene <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> eseguita con l'attributo:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike`non implica `Struct`. Entrambi devono essere presenti nel tipo.

Uno`byref`struct "-like" in F è un tipo di valore associato allo stack. Non viene mai allocato nell'heap gestito. Un `byref`-like struct è utile per la programmazione ad alte prestazioni, in quanto viene applicato con set di controlli sicuri sulla durata e non acquisizione. Le regole sono:

- Possono essere utilizzati come parametri di funzione, parametri di metodo, variabili locali, restituisce il metodo.
- Non possono essere membri statici o di istanza di una classe o di uno struct normale.
- Non possono essere acquisiti`async` da alcun costrutto di chiusura (metodi o espressioni lambda).
- Non possono essere utilizzati come parametro generico.

Anche se queste regole limitano fortemente l'utilizzo, lo fanno per soddisfare la promessa di calcolo ad alte prestazioni in modo sicuro.

## <a name="readonly-structs"></a>Strutture ReadOnly

È possibile annotare <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> gli struct con l'attributo. Ad esempio:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsReadOnly`non implica `Struct`. È necessario aggiungere entrambi `IsReadOnly` per avere uno struct.

L'utilizzo di questo attributo genera metadati che `inref<'T>` consentono `in ref`a F e C' di considerarlo rispettivamente come e , in modo da essere in grado di considerarlo come e , in modo cogiurio .

La definizione di un valore modificabile all'interno di uno struct readonly genera un errore.

## <a name="struct-records-and-discriminated-unions"></a>Record struct e unioni discriminate

È possibile rappresentare [i record](records.md) e le [unioni discriminate](discriminated-unions.md) come struct con l'attributo `[<Struct>]` .  Per ulteriori informazioni, consulta ogni articolo.

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento al linguaggio F](index.md)
- [Classi](classes.md)
- [Record](records.md)
- [Membri](./members/index.md)
