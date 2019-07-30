---
title: Properties
description: Informazioni sulle F# proprietà, che sono membri che rappresentano i valori associati a un oggetto.
ms.date: 05/16/2016
ms.openlocfilehash: c202927fd0022e042703640cd55fb632c7e36068
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627421"
---
# <a name="properties"></a>Properties

Le *Proprietà* sono membri che rappresentano i valori associati a un oggetto.

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

Le proprietà rappresentano la relazione "has a" nella programmazione orientata a oggetti, che rappresenta i dati associati alle istanze degli oggetti o, per le proprietà statiche, con il tipo.

È possibile dichiarare le proprietà in due modi, a seconda che si desideri specificare in modo esplicito il valore sottostante (anche detto archivio di backup) per la proprietà o se si desidera consentire al compilatore di generare automaticamente l'archivio di backup. In genere, è consigliabile usare il modo più esplicito se la proprietà ha un'implementazione non semplice e il modo automatico quando la proprietà è semplicemente un semplice wrapper per un valore o una variabile. Per dichiarare in modo esplicito una proprietà, `member` usare la parola chiave. Questa sintassi dichiarativa è seguita dalla sintassi che specifica `get` i `set` metodi e, anche *funzioni di accesso*denominate. Le varie forme della sintassi esplicita illustrata nella sezione relativa alla sintassi vengono usate per le proprietà di sola lettura e scrittura, di sola lettura e di sola scrittura. Per le proprietà di sola lettura, si definisce solo `get` un metodo; per le proprietà di sola scrittura, definire `set` solo un metodo. Si noti che quando una proprietà ha `get` entrambe `set` le funzioni di accesso e, la sintassi alternativa consente di specificare attributi e modificatori di accessibilità diversi per ogni funzione di accesso, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

Per le proprietà di lettura/scrittura, che hanno `get` sia `set` un metodo che, l' `get` ordine `set` di e può essere annullato. In alternativa, è possibile fornire la sintassi mostrata `get` solo per e la sintassi illustrata solo per `set` anziché utilizzare la sintassi combinata. In questo modo è più semplice impostare come commento il `get` singolo `set` metodo o il metodo, se si tratta di un'operazione che potrebbe essere necessario eseguire. Questa alternativa all'uso della sintassi combinata è illustrata nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

I valori privati che contengono i dati per le proprietà sono denominati *archivi di backup*. Per fare in modo che il compilatore crei automaticamente l'archivio di backup, `member val`usare le parole chiave, omettere l'identificatore autonomo, quindi fornire un'espressione per inizializzare la proprietà. Se la proprietà deve essere modificabile, includere `with get, set`. Il tipo di classe seguente, ad esempio, include due proprietà implementate automaticamente. `Property1`è di sola lettura e viene inizializzato nell'argomento fornito al costruttore primario e `Property2` è una proprietà impostabile inizializzata su una stringa vuota:

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

Le proprietà implementate automaticamente fanno parte dell'inizializzazione di un tipo, pertanto devono essere incluse prima di qualsiasi altra definizione di membro `let` , proprio come `do` le associazioni e le associazioni in una definizione di tipo. Si noti che l'espressione che Inizializza una proprietà implementata automaticamente viene valutata solo durante l'inizializzazione e non ogni volta che viene eseguito l'accesso alla proprietà. Questo comportamento è a differenza del comportamento di una proprietà implementata in modo esplicito. Ciò significa che il codice per inizializzare queste proprietà viene aggiunto al costruttore di una classe. Si consideri il codice seguente che Mostra questa differenza:

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

L'output del codice precedente mostra che il valore di autoproperty è invariato quando viene chiamato ripetutamente, mentre ExplicitProperty viene modificato ogni volta che viene chiamato. Ciò dimostra che l'espressione per una proprietà implementata automaticamente non viene valutata ogni volta, così come il metodo Get per la proprietà Explicit.

>[!WARNING]
>Sono disponibili alcune librerie, ad esempio la Entity Framework (`System.Data.Entity`) che eseguono operazioni personalizzate nei costruttori della classe di base che non funzionano correttamente con l'inizializzazione delle proprietà implementate automaticamente. In questi casi, provare a usare proprietà esplicite.

Le proprietà possono essere membri di classi, strutture, unioni discriminate, record, interfacce ed estensioni di tipo e possono essere definite anche nelle espressioni di oggetto.

Gli attributi possono essere applicati alle proprietà. Per applicare un attributo a una proprietà, scrivere l'attributo su una riga distinta prima della proprietà. Per altre informazioni, vedere [Attributi](../attributes.md).

Per impostazione predefinita, le proprietà sono pubbliche. I modificatori di accessibilità possono anche essere applicati alle proprietà. Per applicare un modificatore di accessibilità, aggiungerlo immediatamente prima del nome della proprietà se `get` è destinato a entrambi i metodi e `set` . aggiungerlo prima delle `get` parole chiave `set` e se l'accessibilità è diversa obbligatorio per ogni funzione di accesso. Il *modificatore* di accessibilità può essere uno dei seguenti `public`: `private`, `internal`,. Per altre informazioni, vedere [Controllo di accesso](../access-control.md).

Le implementazioni delle proprietà vengono eseguite ogni volta che si accede a una proprietà.

## <a name="static-and-instance-properties"></a>Proprietà statiche e di istanza

Le proprietà possono essere proprietà statiche o di istanza. Le proprietà statiche possono essere richiamate senza un'istanza di e vengono utilizzate per i valori associati al tipo, non con singoli oggetti. Per le proprietà statiche, omettere l'identificatore automatico. Il self-identifier è obbligatorio per le proprietà dell'istanza.

La definizione di proprietà statica seguente si basa su uno scenario in cui è presente un campo `myStaticValue` statico che rappresenta l'archivio di backup per la proprietà.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

Le proprietà possono anche essere di tipo matrice, nel qual caso sono denominate *proprietà indicizzate*. Per ulteriori informazioni, vedere [proprietà indicizzate](indexed-properties.md).

## <a name="type-annotation-for-properties"></a>Annotazione del tipo per le proprietà

In molti casi, il compilatore dispone di informazioni sufficienti per dedurre il tipo di una proprietà dal tipo di archivio di backup, ma è possibile impostare il tipo in modo esplicito aggiungendo un'annotazione di tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a>Uso delle funzioni di accesso del set di proprietà

È possibile impostare proprietà che forniscono `set` funzioni di accesso tramite l' `<-` operatore.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

L'output è **20**.

## <a name="abstract-properties"></a>Proprietà astratte

Le proprietà possono essere astratte. Come per i metodi `abstract` , significa solo che è presente un dispatch virtuale associato alla proprietà. Le proprietà astratte possono essere effettivamente astratte, ovvero senza una definizione nella stessa classe. La classe che contiene tale proprietà è quindi una classe astratta. In alternativa, abstract può semplicemente significare che una proprietà è virtuale e, in tal caso, deve essere presente una definizione nella stessa classe. Si noti che le proprietà astratte non devono essere private e se una funzione di accesso è astratta, anche l'altra deve essere astratta. Per ulteriori informazioni sulle classi astratte, vedere [classi astratte](../abstract-classes.md).

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a>Vedere anche

- [Membri](index.md)
- [Metodi](methods.md)
