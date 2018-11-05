---
title: 'Gestione di risorse: parola chiave use (F#)'
description: Informazioni su di F# parola chiave 'use' e la funzione 'using', che è possibile controllare l'inizializzazione e il rilascio delle risorse.
ms.date: 05/16/2016
ms.openlocfilehash: ffa1cb515139a3705920d9d9f79be1a69602f7d8
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "45616068"
---
# <a name="resource-management-the-use-keyword"></a>Gestione di risorse: parola chiave use

In questo argomento descrive la parola chiave `use` e il `using` (funzione), che consentono di controllare l'inizializzazione e il rilascio delle risorse.

## <a name="resources"></a>Risorse

Il termine *risorsa* viene usato in diversi modi. Sì, è possibile i dati utilizzati da un'applicazione, ad esempio stringhe, grafica e simili, ma in questo contesto, le risorse *risorse* fa riferimento alle risorse di sistema operativo o software, ad esempio i contesti di dispositivo di grafica, gli handle di file, rete e oggetti di concorrenza, ad esempio gli handle di attesa e così via, le connessioni di database. L'uso di queste risorse dalle applicazioni comporta l'acquisizione della risorsa di sistema operativo o altri provider di risorse, seguita da nella versione più recente della risorsa per il pool in modo che può essere fornito a un'altra applicazione. Si verificano problemi quando le applicazioni non rilasciano le risorse al pool comuni.

## <a name="managing-resources"></a>Gestione di risorse

Per Gestione risorse di un'applicazione efficiente e responsabilmente la risorsa, è necessario rilasciare le risorse in modo rapido e prevedibile. .NET Framework consente di eseguire questa operazione fornendo il `System.IDisposable` interfaccia. Un tipo che implementa `System.IDisposable` ha il `System.IDisposable.Dispose` metodo, che libera correttamente le risorse. Garantiscono che per le applicazioni ben scritte `System.IDisposable.Dispose` viene chiamato immediatamente quando qualsiasi oggetto che contiene una risorsa limitata non è più necessario. Fortunatamente, la maggior parte dei linguaggi .NET specificano il supporto per semplificare questa operazione, e F# non fa eccezione. Esistono due utili costrutti di linguaggio che supportano il modello dispose: il `use` binding e il `using` (funzione).

## <a name="use-binding"></a>Usare l'associazione

Il `use` parola chiave ha un formato simile a quella del `let` associazione:

usare *valore* = *espressione*

Fornisce la stessa funzionalità di un `let` associazione ma aggiunge una chiamata a `Dispose` sul valore quando il valore esce dall'ambito. Si noti che il compilatore inserisce un controllo null per il valore in modo che, se il valore è `null`, la chiamata a `Dispose` non viene effettuato un tentativo.

Nell'esempio seguente viene illustrato come chiudere un file automaticamente tramite la `use` (parola chiave).

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

>[!NOTE]
È possibile usare `use` nelle espressioni di calcolo, nel qual caso una versione personalizzata del `use` espressione viene usata. Per altre informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di calcolo](computation-expressions.md).

## <a name="using-function"></a>utilizzo (funzione)

Il `using` funzione ha il formato seguente:

`using` (*expression1*) *funzione o espressione lambda*

In un `using` espressione *expression1* crea l'oggetto che deve essere eliminato. Il risultato del *expression1* (l'oggetto che deve essere eliminato) diventa un argomento *valore*, alla *funzione o espressione lambda*, che è una funzione che prevede un singolo argomento di un tipo che corrisponde al valore restante prodotta da *expression1*, o un'espressione lambda che prevede un argomento di quel tipo. Al termine dell'esecuzione della funzione, il runtime chiama `Dispose` e libera le risorse (a meno che il valore è `null`, nel qual caso non viene effettuata la chiamata a Dispose).

Nell'esempio seguente viene illustrato il `using` espressione con un'espressione lambda.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

L'esempio seguente mostra il `using` espressione con una funzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

Si noti che la funzione potrebbe essere una funzione che presenta alcuni argomenti già applicati. Nell'esempio di codice seguente viene illustrata questa possibilità. Viene creato un file che contiene la stringa `XYZ`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

Il `using` funzione e `use` associazione sono quasi equivalenti modi per ottenere lo stesso risultato. Il `using` parola chiave offre un maggiore controllo sul momento `Dispose` viene chiamato. Quando si usa `using`, `Dispose` viene chiamato alla fine dell'espressione lambda o funzione; quando usano le `use` parola chiave, `Dispose` viene chiamato alla fine del blocco di codice che lo contiene. In generale, è preferibile usare `use` anziché il `using` (funzione).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
