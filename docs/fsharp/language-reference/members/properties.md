---
title: Proprietà (F#)
description: 'Informazioni sulle proprietà, F # che sono membri che rappresentano i valori associati a un oggetto.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 6cad5d0e32958374e080f9b8046f7eb73b6bf615
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="properties"></a>Proprietà

*Proprietà* sono membri che rappresentano i valori associati a un oggetto.


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
Le proprietà rappresentano il "ha un" nella programmazione orientata agli oggetti che rappresentano i dati associati alle istanze di oggetto o, per le proprietà statiche, con il tipo di relazione.

È possibile dichiarare una proprietà in due modi, a seconda se si desidera specificare in modo esplicito il valore sottostante (detto anche l'archivio di backup) per la proprietà o se si desidera consentire al compilatore di generare automaticamente l'archivio di backup per l'utente. In genere, è necessario utilizzare il modo più esplicito se la proprietà è un'implementazione non semplice e la modalità automatica quando la proprietà è un semplice wrapper per un valore o una variabile. Per dichiarare una proprietà in modo esplicito, utilizzare il `member` (parola chiave). Questa sintassi dichiarativa è seguita dalla sintassi che specifica il `get` e `set` metodi, denominati anche *funzioni di accesso*. Le varie forme di sintassi illustrato nella sezione relativa alla sintassi esplicita vengono utilizzate per le proprietà di sola lettura, lettura e scrittura di lettura/scrittura. Per le proprietà di sola lettura, definire solo un `get` metodo; per le proprietà di sola scrittura, definire solo un `set` metodo. Si noti che quando una proprietà ha entrambi `get` e `set` funzioni di accesso, la sintassi alternativa consente di specificare gli attributi e modificatori di accessibilità che sono diversi per ogni funzione di accesso, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

Per le proprietà di lettura/scrittura, che hanno entrambi un `get` e `set` (metodo), l'ordine di `get` e `set` possano essere annullati. In alternativa, è possibile fornire la sintassi illustrata per `get` solo e la sintassi illustrata per `set` solo anziché utilizzare la sintassi combinata. Ciò rende più semplice per impostare come commento i singoli `get` o `set` (metodo), in caso di un elemento potrebbe essere necessario eseguire. Questa procedura alternativa per utilizzare la sintassi combinata è illustrata nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

Private i valori che vengono chiamati i dati per le proprietà di attesa *archivi di backup*. Se il compilatore crea automaticamente l'archivio di backup, utilizzare le parole chiave `member val`, omettere l'identificatore di Self-Service, quindi specificare un'espressione per inizializzare la proprietà. Se la proprietà è modificabile, includere `with get, set`. Ad esempio, il seguente tipo di classe include due proprietà implementate automaticamente. `Property1` è di sola lettura e viene inizializzato all'argomento fornito per il costruttore primario, e `Property2` è una proprietà impostabile inizializzata su una stringa vuota:

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

Proprietà implementate automaticamente sono parte dell'inizializzazione di un tipo, pertanto devono essere inclusi come prima di qualsiasi altra definizione del membro, `let` associazioni e `do` binding in una definizione di tipo. Si noti che l'espressione che consente di inizializzare una proprietà implementata automaticamente viene valutato solo al momento dell'inizializzazione e non ogni volta che si accede alla proprietà. Questo comportamento si differenzia dal comportamento di una proprietà implementata in modo esplicito. Ciò in modo efficace significa che il codice per inizializzare le proprietà viene aggiunta al costruttore di una classe. Si consideri il codice seguente viene illustrata questa differenza:

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

L'output del codice precedente mostra che il valore di AutoProperty è invariato quando viene chiamato più volte, mentre il ExplicitProperty cambia ogni volta che viene chiamato. Ciò dimostra che l'espressione per una proprietà implementata automaticamente non viene valutata ogni volta, come il metodo di richiamo della proprietà esplicita.


>[!WARNING]
Esistono alcune librerie, ad esempio Entity Framework (`System.Data.Entity`) che eseguono operazioni personalizzate nei costruttori di classe di base che non funzionano correttamente con l'inizializzazione di proprietà implementate automaticamente. In questi casi, provare a utilizzare la proprietà esplicita.

Le proprietà possono essere membri di classi, strutture, unioni discriminate, record, interfacce e le estensioni di tipo e possono essere definite anche nelle espressioni di oggetto.

Gli attributi possono essere applicati alle proprietà. Per applicare un attributo a una proprietà, scrivere l'attributo su una riga separata prima che la proprietà. Per altre informazioni, vedere [Attributi](../attributes.md).

Per impostazione predefinita, le proprietà sono pubbliche. I modificatori di accessibilità possono inoltre essere applicati alle proprietà. Per applicare un modificatore di accessibilità, aggiungerlo immediatamente prima del nome della proprietà, se deve essere applicato a entrambi il `get` e `set` metodi; aggiungerlo prima di `get` e `set` parole chiave se è diverso di accessibilità obbligatorio per ogni funzione di accesso. Il *modificatore di accessibilità* può essere uno dei seguenti: `public`, `private`, `internal`. Per altre informazioni, vedere [Controllo di accesso](../access-control.md).

Le implementazioni di proprietà vengono eseguite ogni volta che accede a una proprietà.


## <a name="static-and-instance-properties"></a>Statico e delle proprietà dell'istanza
Proprietà possono essere statici o delle proprietà dell'istanza. Proprietà statica possono essere richiamate senza un'istanza e permettono i valori associati al tipo, non a singoli oggetti. Per le proprietà statiche, omettere l'identificatore di Self-Service. L'autoidentificatore è obbligatorio per le proprietà dell'istanza.

La seguente definizione di proprietà statica è basata su uno scenario in cui è presente un campo statico `myStaticValue` che rappresenta l'archivio di backup per la proprietà.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

Proprietà possono anche essere tipo matrice, nel qual caso vengono chiamati *proprietà indicizzate*. Per ulteriori informazioni, vedere [le proprietà indicizzate](indexed-properties.md).


## <a name="type-annotation-for-properties"></a>Annotazione del tipo di proprietà
In molti casi, il compilatore ha informazioni sufficienti per dedurre il tipo di una proprietà dal tipo di archivio di backup, ma è possibile impostare il tipo in modo esplicito mediante l'aggiunta di un'annotazione di tipo.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a>Utilizzo di proprietà set di funzioni di accesso
È possibile impostare proprietà che forniscono `set` funzioni di accesso tramite il `<-` operatore.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

L'output è **20**.


## <a name="abstract-properties"></a>Proprietà astratte
Proprietà possono essere astratte. Come con i metodi, `abstract` significa semplicemente che è un invio virtuale associato alla proprietà. Le proprietà astratte possono essere effettivamente astratte, ovvero senza una definizione nella stessa classe. Pertanto, la classe che contiene tale proprietà è una classe astratta. In alternativa, astratta può significare semplicemente che una proprietà è virtuale e in tal caso, una definizione deve trovarsi nella stessa classe. Si noti che le proprietà astratte non devono essere private, e se una funzione di accesso è astratto, anche l'altra deve essere astratta. Per ulteriori informazioni sulle classi astratte, vedere [classi astratte](../abstract-classes.md).

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a>Vedere anche
[Membri](index.md)

[Metodi](methods.md)
