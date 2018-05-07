---
title: Costruttori (F#)
description: 'Informazioni su come definire e utilizzare i costruttori in F # per creare e inizializzare gli oggetti di classe e struttura.'
ms.date: 05/16/2016
ms.openlocfilehash: 1773c111e0398aa83951afe14979d8a4ebc4907f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="constructors"></a>Costruttori

In questo argomento viene descritto come definire e utilizzare i costruttori per creare e inizializzare gli oggetti di classe e struttura.


## <a name="construction-of-class-objects"></a>Costruzione di oggetti classe
Gli oggetti di tipi di classe hanno costruttori. Esistono due tipi di costruttori. Uno è il costruttore primario, i cui parametri sono inclusi tra parentesi subito dopo il nome del tipo. Specificare gli altri costruttori aggiuntivi facoltativi utilizzando il `new` (parola chiave). Qualsiasi costruttore aggiuntivo devono chiamare il costruttore primario.

Il costruttore primario contiene `let` e `do` associazioni che vengono visualizzati all'inizio della definizione della classe. Oggetto `let` binding dichiara i campi privati e i metodi della classe; un `do` associazione esegue il codice. Per ulteriori informazioni su `let` associazioni nei costruttori di classe, vedere [ `let` associazioni nelle classi](let-bindings-in-classes.md). Per ulteriori informazioni su `do` associazioni nei costruttori, vedere [ `do` associazioni nelle classi](do-bindings-in-classes.md).

Indipendentemente dal fatto che il costruttore da chiamare sia un costruttore primario o un costruttore aggiuntivo, è possibile creare oggetti usando una `new` espressione, con o senza l'opzione facoltativa `new` (parola chiave). Inizializzare gli oggetti con gli argomenti del costruttore, elencando gli argomenti nell'ordine e separati da virgole e racchiuso tra parentesi o utilizzando gli argomenti denominati e i valori tra parentesi. È inoltre possibile impostare proprietà su un oggetto durante la costruzione dell'oggetto usando i nomi delle proprietà e l'assegnazione di valori come si utilizzano denominato gli argomenti del costruttore.

Il codice seguente viene illustrata una classe che ha un costruttore e diverse modalità di creazione di oggetti.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

L'output è indicato di seguito.

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a>Costruzione di strutture
Le strutture seguono tutte le regole delle classi. Pertanto, è possibile avere un costruttore primario e fornire costruttori aggiuntivi utilizzando `new`. Tuttavia, è una differenza importante tra classi e strutture: le strutture possono disporre di un costruttore predefinito (vale a dire uno senza argomenti) anche se è definito alcun costruttore primario. Il costruttore predefinito inizializza tutti i campi per il valore predefinito per tale tipo, generalmente zero o equivalente. Costruttori definiti per le strutture devono avere almeno un argomento in modo che non entrino in conflitto con il costruttore predefinito.

Strutture, inoltre, hanno spesso i campi che vengono creati utilizzando il `val` (parola chiave); le classi possono disporre anche di questi campi. Strutture e classi che dispongono di campi definiti tramite il `val` parola chiave può inoltre essere inizializzati in costruttori aggiuntivi utilizzando espressioni di record, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

Per ulteriori informazioni, vedere [campi espliciti: il `val` parola chiave](explicit-fields-the-val-keyword.md).


## <a name="executing-side-effects-in-constructors"></a>L'esecuzione di effetti collaterali nei costruttori
Un costruttore primario in una classe può eseguire codice in un `do` associazione. Tuttavia, se è necessario eseguire codice in un costruttore aggiuntivo, senza un `do` associazione? A tale scopo, utilizzare il `then` (parola chiave).

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

Eseguire comunque gli effetti collaterali del costruttore primario. Di conseguenza, l'output è il seguente.

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a>Autoidentificatori nei costruttori
Negli altri membri, fornire un nome per l'oggetto corrente nella definizione di ogni membro. È anche possibile inserire l'autoidentificatore nella prima riga della definizione della classe utilizzando il `as` parola chiave immediatamente dopo i parametri del costruttore. Nell'esempio seguente viene illustrata questa sintassi.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

Nei costruttori aggiuntivi, è anche possibile definire un autoidentificatore inserendo il `as` clausola subito dopo i parametri del costruttore. Nell'esempio seguente viene illustrata questa sintassi.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

Problemi possono verificarsi quando si tenta di utilizzare un oggetto prima che sia definita completamente. Pertanto, Usa dello stesso identificatore può causare al compilatore di generare un avviso e l'inserimento di controlli aggiuntivi per assicurarsi che i membri di un oggetto non si accede prima l'oggetto viene inizializzato. Utilizzare solo l'autoidentificatore nella `do` associazioni del costruttore primario o dopo il `then` (parola chiave) nei costruttori aggiuntivi.

Il nome dello stesso identificatore non deve essere `this`. Può essere qualsiasi identificatore valido.


## <a name="assigning-values-to-properties-at-initialization"></a>L'assegnazione di valori alle proprietà in fase di inizializzazione
È possibile assegnare valori alle proprietà di un oggetto di classe nel codice di inizializzazione aggiungendo un elenco di assegnazioni nel formato `property = value` all'elenco di argomenti per un costruttore. Queste operazioni sono illustrate nell'esempio di codice riportato di seguito.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

La seguente versione del codice precedente viene illustrata la combinazione di argomenti normali, gli argomenti facoltativi e le impostazioni delle proprietà nella chiamata di un costruttore.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]
    
## <a name="constructors-in-inherited-class"></a>Costruttori di classe ereditata
Quando si eredita da una classe di base che ha un costruttore, è necessario specificare gli argomenti nella clausola eredita. Per ulteriori informazioni, vedere [costruttori ed ereditarietà](../inheritance.md#constructors-and-inheritance).

## <a name="static-constructors-or-type-constructors"></a>Costruttori statici o costruttori di tipo
Oltre a specificare il codice per la creazione di oggetti, statici `let` e `do` associazioni possono essere create in tipi di classe da eseguire prima che il tipo viene innanzitutto utilizzato per eseguire l'inizializzazione a livello di tipo. Per ulteriori informazioni, vedere [ `let` associazioni nelle classi](let-bindings-in-classes.md) e [ `do` associazioni nelle classi](do-bindings-in-classes.md).

## <a name="see-also"></a>Vedere anche
[Membri](index.md)
