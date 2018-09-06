---
title: Costruttori (F#)
description: 'Informazioni su come definire e usare i costruttori in F # per creare e inizializzare gli oggetti di classe e struttura.'
ms.date: 05/16/2016
ms.openlocfilehash: ff2463f890034cce0bbaa85d9a5c93e50427cd03
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43803941"
---
# <a name="constructors"></a>Costruttori

Questo argomento descrive come definire e usare i costruttori per creare e inizializzare gli oggetti di classe e struttura.

## <a name="construction-of-class-objects"></a>Costruzione di oggetti classe

Oggetti di tipo classe hanno costruttori. Esistono due tipi di costruttori. Uno è il costruttore principale, i cui parametri sono inclusi tra parentesi subito dopo il nome del tipo. Specificare gli altri costruttori aggiuntivi facoltativi usando la `new` (parola chiave). Tutti questi costruttori aggiuntivi devono chiamare il costruttore primario.

Il costruttore principale non contiene `let` e `do` associazioni che vengono visualizzati all'inizio della definizione di classe. Oggetto `let` associazione dichiara i campi privati e i metodi della classe; un `do` associazione esegue il codice. Per altre informazioni sulle `let` sulle associazioni nei costruttori di classe, vedere [ `let` associazioni nelle classi](let-bindings-in-classes.md). Per altre informazioni sulle `do` sulle associazioni nei costruttori, vedere [ `do` associazioni nelle classi](do-bindings-in-classes.md).

Indipendentemente dal fatto che il costruttore da chiamare è un costruttore primario o un costruttore aggiuntivo, è possibile creare oggetti usando un `new` espressione, con o senza l'opzione facoltativa `new` (parola chiave). Inizializzare gli oggetti con gli argomenti del costruttore, elencando gli argomenti nell'ordine e separati da virgole e racchiusi tra parentesi o utilizzando gli argomenti denominati e i valori tra parentesi. È possibile anche impostare le proprietà su un oggetto durante la costruzione dell'oggetto usando i nomi delle proprietà e come si utilizzano l'assegnazione di valori denominati argomenti del costruttore.

Il codice seguente illustra una classe che ha un costruttore e sui vari modi di creare oggetti.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

L'output è indicato di seguito.

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a>Costruzione di strutture

Le strutture seguono tutte le regole delle classi. Pertanto, è possibile avere un costruttore primario ed è possibile fornire costruttori aggiuntivi utilizzando `new`. Tuttavia, c'è una differenza importante tra classi e strutture: le strutture possono disporre di un costruttore predefinito (vale a dire, uno senza argomenti) anche se è definito alcun costruttore primario. Il costruttore predefinito inizializza tutti i campi per il valore predefinito per tale tipo, in genere zero o equivalente. I costruttori definiti per le strutture devono avere almeno un argomento in modo che non entrino in conflitto con il costruttore predefinito.

Inoltre, le strutture hanno spesso i campi che vengono creati utilizzando il `val` (parola chiave); le classi possono anche avere questi campi. Strutture e classi che dispongono di campi definiti tramite la `val` (parola chiave) possono essere inizializzati anche nei costruttori aggiuntivi utilizzando espressioni di record, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

Per altre informazioni, vedere [i campi espliciti: il `val` parola chiave](explicit-fields-the-val-keyword.md).

## <a name="executing-side-effects-in-constructors"></a>L'esecuzione di effetti collaterali nei costruttori

Un costruttore primario in una classe può eseguire codice in un `do` associazione. Tuttavia, cosa accade se è necessario eseguire il codice in un costruttore aggiuntivo, senza un `do` associazione? A tale scopo, si utilizza il `then` (parola chiave).

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

Eseguire comunque gli effetti collaterali di costruttore primario. Pertanto, l'output è come indicato di seguito.

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a>Autoidentificatori nei costruttori

In altri membri, è fornire un nome per l'oggetto corrente nella definizione di ogni membro. È anche possibile inserire l'autoidentificatore sulla prima riga della definizione di classe utilizzando il `as` parola chiave immediatamente dopo i parametri del costruttore. Nell'esempio seguente viene illustrata questa sintassi.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

In costruttori aggiuntivi, è possibile definire anche un identificatore automatico inserendo la `as` clausola subito dopo i parametri del costruttore. Nell'esempio seguente viene illustrata questa sintassi.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

Possono verificarsi problemi quando si prova a usare un oggetto prima che sia definita completamente. Pertanto, Usa dello stesso identificatore può causare il compilatore genera un avviso e inserimento di controlli aggiuntivi per assicurarsi che i membri di un oggetto non sono accessibili prima che venga inizializzato l'oggetto. Usare solo l'autoidentificatore nel `do` associazioni del costruttore primario, o dopo il `then` parola chiave in costruttori aggiuntivi.

Il nome dell'identificatore utente non dovrà essere `this`. Può trattarsi di qualsiasi identificatore valido.

## <a name="assigning-values-to-properties-at-initialization"></a>Assegnazione di valori alle proprietà in fase di inizializzazione

È possibile assegnare valori alle proprietà di un oggetto di classe nel codice di inizializzazione mediante l'aggiunta di un elenco di assegnazioni del form `property = value` all'elenco di argomenti per un costruttore. Queste operazioni sono illustrate nell'esempio di codice riportato di seguito.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

La versione seguente di codice precedente illustra la combinazione di argomenti normali, gli argomenti facoltativi e le impostazioni delle proprietà nella chiamata di un costruttore.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a>Costruttori nelle classi ereditate

Quando si eredita da una classe base che ha un costruttore, è necessario specificare gli argomenti nella clausola eredita. Per altre informazioni, vedere [costruttori ed ereditarietà](../inheritance.md#constructors-and-inheritance).

## <a name="static-constructors-or-type-constructors"></a>I costruttori di tipi o i costruttori statici

Oltre a specificare il codice per la creazione di oggetti, statici `let` e `do` associazioni possono essere create nei tipi di classe da eseguire prima che il tipo viene utilizzato innanzitutto per eseguire l'inizializzazione a livello di tipo. Per altre informazioni, vedere [ `let` associazioni nelle classi](let-bindings-in-classes.md) e [ `do` associazioni nelle classi](do-bindings-in-classes.md).

## <a name="see-also"></a>Vedere anche

- [Membri](index.md)
