---
title: Proprietà (F#)
description: "Informazioni su F # le proprietà, che sono membri che rappresentano valori associati all'oggetto specificato."
ms.date: 05/16/2016
ms.openlocfilehash: 75d21415b44ccc1c26ef5f478d5f5de20c3412e8
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197925"
---
# <a name="properties"></a>Proprietà

*Proprietà* membri che rappresentano valori associati all'oggetto specificato.

## <a name="syntax"></a>Sintassi

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a>Note

Le proprietà rappresentano il "ha un" nella programmazione orientata agli oggetti che rappresentano i dati che sono associato a istanze di oggetti o, per le proprietà statiche, con il tipo di relazione.

È possibile dichiarare le proprietà in due modi, a seconda del fatto che si desidera specificare in modo esplicito il valore sottostante (detto anche l'archivio di backup) per la proprietà o se si vuole consentire al compilatore di generare automaticamente l'archivio di backup per l'utente. In generale, è necessario utilizzare la modalità automatica e il modo più esplicito se la proprietà ha un'implementazione non semplice quando la proprietà è semplicemente un semplice wrapper per un valore o una variabile. Per dichiarare una proprietà in modo esplicito, usare il `member` (parola chiave). Questa sintassi dichiarativa è seguita dalla sintassi che specifica la `get` e `set` metodi, denominati anche *funzioni di accesso*. Le varie forme di sintassi esplicita illustrata nella sezione relativa alla sintassi vengono usate per le proprietà di lettura/scrittura, sola lettura, lettura e scrittura. Per le proprietà di sola lettura, si definisce solo un `get` metodo; per le proprietà di sola scrittura, definire solo un `set` (metodo). Si noti che quando una proprietà ha entrambe `get` e `set` funzioni di accesso, la sintassi alternativa consente di specificare gli attributi e i modificatori di accessibilità sono diversi per ogni funzione di accesso, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

Per le proprietà di lettura/scrittura, che hanno entrambi un `get` e `set` metodo, l'ordine degli `get` e `set` possano essere annullati. In alternativa, è possibile fornire la sintassi illustrata per `get` solo e la sintassi illustrata per `set` solo invece di usare la sintassi combinata. Questa operazione rende più semplice rimuovere i commenti per i singoli `get` o `set` metodo, se questo è un elemento potrebbe essere necessario eseguire operazioni. Questa alternativa all'utilizzo la sintassi combinata è illustrata nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

Esenzione i dati per le proprietà vengono chiamati i valori privati *archivi di backup*. Affinché il compilatore crea automaticamente l'archivio di backup, usare le parole chiave `member val`, omettere l'identificatore di Self-Service, quindi specificare un'espressione per inizializzare la proprietà. Se la proprietà è modificabile, includere `with get, set`. Ad esempio, il seguente tipo di classe include due proprietà implementate automaticamente. `Property1` è di sola lettura e viene inizializzato all'argomento fornito al costruttore del primario, e `Property2` è una proprietà impostabile inizializzata in una stringa vuota:

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

Proprietà implementate automaticamente fanno parte dell'inizializzazione di un tipo, quindi devono essere inclusi come prima di qualsiasi altra definizione del membro, `let` associazioni e `do` associazioni in una definizione di tipo. Si noti che l'espressione che consente di inizializzare una proprietà implementata automaticamente viene valutata solo in fase di inizializzazione e non ogni volta che si accede alla proprietà. Questo comportamento si differenzia dal comportamento di una proprietà implementata in modo esplicito. Ciò in modo efficace significa che il codice per inizializzare queste proprietà viene aggiunta al costruttore di una classe. Si consideri il codice seguente che illustra questa differenza:

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

**Output**

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

L'output del codice precedente mostra che il valore di AutoProperty rimane invariato quando viene chiamato più volte, mentre il ExplicitProperty cambia ogni volta che viene chiamato. Ciò dimostra che l'espressione per una proprietà implementata automaticamente non viene valutata ogni volta, perché è il metodo di richiamo della proprietà esplicite.

>[!WARNING]
Esistono alcune librerie, ad esempio Entity Framework (`System.Data.Entity`) che eseguono operazioni personalizzate nei costruttori di classe di base che non funzionano correttamente con l'inizializzazione di proprietà implementate automaticamente. In questi casi, provare a usare le proprietà esplicite.

Le proprietà possono essere membri di classi, strutture, unioni discriminate, record, interfacce e le estensioni di tipo e possono anche essere definite nelle espressioni di oggetto.

Gli attributi possono essere applicati alle proprietà. Per applicare un attributo a una proprietà, scrivere l'attributo su una riga separata prima che la proprietà. Per altre informazioni, vedere [Attributi](../attributes.md).

Per impostazione predefinita, le proprietà sono pubbliche. I modificatori di accessibilità possono anche essere applicati alle proprietà. Per applicare un modificatore di accessibilità, aggiungerlo immediatamente prima del nome della proprietà, se lo scopo è quello di si applicano a entrambe le `get` e `set` metodi; aggiungerlo prima il `get` e `set` parole chiave se è un'accessibilità diversa obbligatorio per ogni funzione di accesso. Il *modificatore di accessibilità* può essere uno dei seguenti: `public`, `private`, `internal`. Per altre informazioni, vedere [Controllo di accesso](../access-control.md).

Le implementazioni di proprietà vengono eseguite ogni volta che si accede a una proprietà.

## <a name="static-and-instance-properties"></a>Statiche e proprietà dell'istanza

Le proprietà possono essere statici o delle proprietà dell'istanza. Proprietà statica possono essere richiamate senza un'istanza e vengono usate per i valori associati al tipo, non a singoli oggetti. Per le proprietà statiche, omettere l'identificatore di Self-Service. L'identificatore di Self-Service è necessario per le proprietà dell'istanza.

La seguente definizione di proprietà statica si basa su uno scenario in cui è presente un campo statico `myStaticValue` vale a dire l'archivio di backup per la proprietà.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

Le proprietà possono anche essere di tipo matrice, nel qual caso vengono chiamati *proprietà indicizzate*. Per altre informazioni, vedere [Indexed Properties](indexed-properties.md).

## <a name="type-annotation-for-properties"></a>Annotazione del tipo di proprietà

In molti casi, il compilatore ha informazioni sufficienti per dedurre il tipo di una proprietà dal tipo dell'archivio di backup, ma è possibile impostare il tipo in modo esplicito mediante l'aggiunta di un'annotazione di tipo.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a>Utilizzo proprietà set di funzioni di accesso

È possibile impostare proprietà che forniscono `set` funzioni di accesso usando il `<-` operatore.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

L'output viene **20**.

## <a name="abstract-properties"></a>Proprietà astratte

Proprietà possono essere astratte. Come con i metodi, `abstract` significa semplicemente che è una dispatch virtuale associato alla proprietà. Le proprietà astratte possono essere davvero astratte, vale a dire senza una definizione della stessa classe. La classe che contiene tale proprietà è pertanto una classe astratta. In alternativa, abstract può significare semplicemente che una proprietà è virtuale e in tal caso, una definizione deve essere presente nella stessa classe. Si noti che le proprietà astratte non devono essere private e se una funzione di accesso è astratto, l'altra deve anche essere astratta. Per altre informazioni sulle classi astratte, vedere [classi astratte](../abstract-classes.md).

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a>Vedere anche

- [Membri](index.md)
- [Metodi](methods.md)
