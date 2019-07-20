---
title: Costruttori
description: Informazioni su come definire e utilizzare i costruttori in F# per creare e inizializzare oggetti classe e struttura.
ms.date: 05/16/2016
ms.openlocfilehash: ef5dc134ad98179b6a365c4c34a9eca22fe5f7f6
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364366"
---
# <a name="constructors"></a>Costruttori

In questo argomento viene descritto come definire e utilizzare i costruttori per creare e inizializzare oggetti classe e struttura.

## <a name="construction-of-class-objects"></a>Costruzione di oggetti classe

Gli oggetti dei tipi di classe hanno costruttori. Esistono due tipi di costruttori. Uno è il costruttore primario, i cui parametri vengono visualizzati tra parentesi subito dopo il nome del tipo. Per specificare altri costruttori facoltativi aggiuntivi, usare la `new` parola chiave. Tutti questi costruttori aggiuntivi devono chiamare il costruttore primario.

Il costruttore primario contiene `let` le `do` associazioni e visualizzate all'inizio della definizione della classe. Un' `let` associazione dichiara i metodi e i campi privati della classe; un' `do` associazione esegue il codice. Per ulteriori informazioni sulle `let` associazioni nei costruttori di classi, vedere [ `let` binding nelle classi](let-bindings-in-classes.md). Per ulteriori informazioni sulle `do` associazioni nei costruttori, vedere [ `do` binding nelle classi](do-bindings-in-classes.md).

Indipendentemente dal fatto che il costruttore che si vuole chiamare sia un costruttore primario o un costruttore aggiuntivo, è possibile creare oggetti usando un' `new` espressione, con o senza la parola `new` chiave Optional. Gli oggetti vengono inizializzati insieme agli argomenti del costruttore, elencando gli argomenti nell'ordine e separati da virgole e racchiusi tra parentesi o utilizzando argomenti e valori denominati tra parentesi. È inoltre possibile impostare le proprietà di un oggetto durante la costruzione dell'oggetto utilizzando i nomi delle proprietà e assegnando valori analogamente a come si utilizzano gli argomenti del costruttore denominati.

Nel codice seguente viene illustrata una classe che dispone di un costruttore e diversi modi per creare oggetti.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

L'output è indicato di seguito.

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a>Costruzione di strutture

Le strutture seguono tutte le regole delle classi. Pertanto, è possibile avere un costruttore primario ed è possibile fornire costruttori `new`aggiuntivi tramite. Tuttavia, esiste una differenza importante tra le strutture e le classi: le strutture possono avere un costruttore senza parametri, ovvero uno senza argomenti, anche se non è stato definito alcun costruttore primario. Il costruttore senza parametri Inizializza tutti i campi sul valore predefinito per quel tipo, in genere zero o l'equivalente. Tutti i costruttori definiti per le strutture devono avere almeno un argomento in modo che non siano in conflitto con il costruttore predefinito.

Inoltre, le strutture hanno spesso campi creati usando la `val` parola chiave. le classi possono anche avere questi campi. Le strutture e le classi con campi definiti tramite la `val` parola chiave possono essere inizializzate anche in costruttori aggiuntivi tramite espressioni di record, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

Per ulteriori informazioni, vedere [campi espliciti: `val` Parola chiave](explicit-fields-the-val-keyword.md).

## <a name="executing-side-effects-in-constructors"></a>Esecuzione di effetti collaterali nei costruttori

Un costruttore primario in una classe può eseguire codice in un' `do` associazione. Tuttavia, cosa accade se è necessario eseguire codice in un costruttore aggiuntivo, senza un' `do` associazione? A tale scopo, usare la `then` parola chiave.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

Gli effetti collaterali del costruttore primario continuano a essere eseguiti. Di conseguenza, l'output è il seguente.

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a>Identificatori autonomi nei costruttori

Gli altri membri forniscono un nome per l'oggetto corrente nella definizione di ogni membro. È anche possibile inserire l'identificatore automatico nella prima riga della definizione della classe usando la `as` parola chiave immediatamente dopo i parametri del costruttore. Nell'esempio seguente viene illustrata questa sintassi.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

In costruttori aggiuntivi è inoltre possibile definire un identificatore autonomo inserendo la `as` clausola subito dopo i parametri del costruttore. Nell'esempio seguente viene illustrata questa sintassi.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

Possono verificarsi problemi quando si tenta di utilizzare un oggetto prima che sia completamente definito. Pertanto, gli utilizzi dell'identificatore automatico possono causare la generazione di un avviso da parte del compilatore e l'inserimento di controlli aggiuntivi per garantire che i membri di un oggetto non accedano prima che l'oggetto venga inizializzato. È consigliabile usare solo l'identificatore automatico nei `do` binding del costruttore primario o dopo la `then` parola chiave in costruttori aggiuntivi.

Il nome dell'identificatore auto non deve essere `this`. Può essere qualsiasi identificatore valido.

## <a name="assigning-values-to-properties-at-initialization"></a>Assegnazione di valori a proprietà in fase di inizializzazione

È possibile assegnare valori alle proprietà di un oggetto classe nel codice di inizializzazione aggiungendo un elenco di assegnazioni del form `property = value` all'elenco di argomenti per un costruttore. Queste operazioni sono illustrate nell'esempio di codice riportato di seguito.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Nella versione seguente del codice precedente viene illustrata la combinazione di argomenti ordinari, argomenti facoltativi e impostazioni delle proprietà in una chiamata al costruttore.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a>Costruttori nella classe ereditata

Quando si eredita da una classe di base che dispone di un costruttore, è necessario specificare i relativi argomenti nella clausola inherit. Per ulteriori informazioni, vedere [costruttori ed ereditarietà](../inheritance.md#constructors-and-inheritance).

## <a name="static-constructors-or-type-constructors"></a>Costruttori statici o costruttori di tipo

Oltre a specificare il codice per la creazione di oggetti `let` , `do` le associazioni statiche e possono essere create in tipi di classe che vengono eseguite prima che il tipo venga usato per la prima volta per eseguire l'inizializzazione a livello di tipo. Per ulteriori informazioni, vedere [ `let` binding in classi](let-bindings-in-classes.md) e [ `do` associazioni nelle classi](do-bindings-in-classes.md).

## <a name="see-also"></a>Vedere anche

- [Membri](index.md)
