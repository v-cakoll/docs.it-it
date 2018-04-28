---
title: Strutture (F#)
description: 'Informazioni su F # struttura, un tipo di oggetto compatto spesso più efficiente rispetto a una classe per i tipi con una piccola quantità di dati e comportamento semplice.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 14a4799b13c40e363dd400f7effd53264acc5614
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="structures"></a>Strutture

Oggetto *struttura* è un tipo di oggetto compatto che può essere più efficiente rispetto a una classe per tipi che dispongono di una piccola quantità di dati e comportamento semplice.

## <a name="syntax"></a>Sintassi

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements
```

## <a name="remarks"></a>Note
Le strutture sono *i tipi di valore*, il che significa che sono archiviati direttamente sullo stack o, quando vengono utilizzati come campi o tipo di elementi di matrice, inline nell'elemento padre. A differenza di record e classi, le strutture hanno una semantica pass-by-value. Ciò significa che sono utili principalmente per piccole aggregazioni di dati accessibili e copiati di frequente.

Nella sintassi precedente sono illustrate due forme. La prima non è la sintassi leggera, ma viene comunque usata frequentemente perché, quando si usano la parole chiave `struct` e `end`, è possibile omettere l'attributo `StructAttribute`, che viene visualizzato nella seconda forma. È possibile abbreviare `StructAttribute` in `Struct`.

Il *gli elementi di definizione del tipo* nella sintassi precedente rappresenta definizioni e dichiarazioni di membri. Le strutture possono disporre di costruttori e campi modificabili e non modificabili e possono dichiarare i membri e le implementazioni dell'interfaccia. Per ulteriori informazioni, vedere [membri](members/index.md).

Le strutture non possono partecipare all'ereditarietà, non possono contenere associazioni `let` o `do` e non possono contenere in modo ricorsivo campi del proprio tipo (nonostante possano contenere celle di riferimento che facciano riferimento al proprio tipo).

Poiché le strutture non consentono associazioni `let`, è necessario dichiarare i campi nelle strutture usando la parola chiave `val`. La parola chiave `val` definisce un campo e il relativo tipo, ma non consente l'inizializzazione. Al contrario, le dichiarazioni `val` sono inizializzate su zero o null. Per questo motivo, le strutture che hanno un costruttore implicito (ovvero, i parametri forniti immediatamente dopo il nome della struttura nella dichiarazione) richiedono di annotare le dichiarazioni `val` con l'attributo `DefaultValue`. Le strutture che hanno un costruttore definito supportano comunque l'inizializzazione su zero. Quindi, l'attributo `DefaultValue` è una dichiarazione che tale valore zero è valido per il campo. I costruttori impliciti per le strutture non eseguono alcuna azione perché le associazioni `let` e `do` non sono consentite per il tipo, ma i valori di parametro di costruttore implicito passati sono disponibili come campi privati.

I costruttori espliciti potrebbero comportare l'inizializzazione dei valori di campo. Quando si ha una struttura con un costruttore esplicito, è comunque supportata l'inizializzazione su zero. Tuttavia, non usare l'attributo `DefaultValue` sulle dichiarazioni `val` perché è in conflitto con il costruttore esplicito. Per ulteriori informazioni su `val` dichiarazioni, vedere [campi espliciti: il `val` parola chiave](members/explicit-fields-the-val-keyword.md).

Gli attributi e modificatori di accessibilità sono consentiti nelle strutture e seguono le stesse regole per gli altri tipi. Per ulteriori informazioni, vedere [attributi](attributes.md) e [controllo di accesso](access-control.md).

Gli esempi di codice seguenti illustrano le definizioni delle strutture.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a>I record di struct e unioni discriminate

A partire da F # 4.1, è possibile rappresentare [record](records.md) e [unioni discriminate](discriminated-unions.md) come struct con il `[<Struct>]` attributo.  Ogni articolo per altre informazioni, vedere.
    
## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Classi](classes.md)

[Record](records.md)

[Membri](members/index.md)
