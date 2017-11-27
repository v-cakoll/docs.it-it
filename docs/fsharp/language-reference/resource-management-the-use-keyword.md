---
title: 'Gestione di risorse: parola chiave use (F#)'
description: 'Scopri di F # parola chiave ''use'' e la funzione ''utilizzando'', che consentono di controllare l''inizializzazione e il rilascio delle risorse.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 00c3040e-859f-4dad-a7b5-7b8d44dc232c
ms.openlocfilehash: d4e8626f07f1c77e52e8fabd5ccc07dbf1fa8ddd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="resource-management-the-use-keyword"></a>Gestione di risorse: parola chiave use

In questo argomento descrive la parola chiave `use` e `using` (funzione), che consentono di controllare l'inizializzazione e il rilascio delle risorse.

## <a name="resources"></a>Risorse
Il termine *risorse* viene utilizzato in più modi. Sì, le risorse possono essere dati utilizzati da un'applicazione, ad esempio stringhe, immagini e così via, ma in questo contesto, *risorse* fa riferimento alle risorse del sistema operativo o del software, ad esempio contesti di dispositivo di grafica, gli handle di file di rete e database connessioni, gli oggetti di concorrenza, ad esempio gli handle di attesa e così via. L'utilizzo di queste risorse dalle applicazioni comporta l'acquisizione della risorsa dal sistema operativo o di altri provider di risorse, seguito da nella versione più recente della risorsa per il pool in modo che possa essere fornita a un'altra applicazione. Problemi si verificano quando le applicazioni non rilasciare le risorse al pool più comuni.

## <a name="managing-resources"></a>Gestione di risorse
Per la gestione di risorse in un'applicazione in modo efficiente e all'individuazione, è necessario rilasciare le risorse in modo rapido e prevedibile. .NET Framework consente di effettuare questa operazione fornendo il `System.IDisposable` interfaccia. Un tipo che implementa `System.IDisposable` ha il `System.IDisposable.Dispose` metodo, che libera correttamente le risorse. Le applicazioni scritte ben garantiscono che `System.IDisposable.Dispose` viene chiamato immediatamente quando qualsiasi oggetto che contiene una risorsa limitata non è più necessario. Fortunatamente, la maggior parte dei linguaggi .NET forniscono supporto per semplificare questa operazione e, F # non costituisce un'eccezione. Esistono due utili costrutti di linguaggio che supportano il modello dispose: il `use` associazione e `using` (funzione).

## <a name="use-binding"></a>Utilizzare l'associazione
Il `use` parola chiave ha un formato simile a quella del `let` associazione:

Utilizzare *valore* = *espressione*

Fornisce la stessa funzionalità di un `let` associazione ma aggiunge una chiamata a `Dispose` sul valore quando il valore esce dall'ambito. Si noti che il compilatore inserisce un controllo null sul valore, in modo che se il valore è `null`, la chiamata a `Dispose` non viene eseguito un tentativo.

Nell'esempio seguente viene illustrato come chiudere automaticamente un file utilizzando il `use` (parola chiave).

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

>[!NOTE]
È possibile utilizzare `use` nelle espressioni di calcolo, nel qual caso una versione personalizzata del `use` viene utilizzata l'espressione. Per ulteriori informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di calcolo](computation-expressions.md).


## <a name="using-function"></a>funzione
Il `using` funzione ha il formato seguente:

`using`(*expression1*) *funzione o espressione lambda*

In un `using` espressione *expression1* crea l'oggetto che deve essere eliminato. Il risultato di *expression1* (l'oggetto che deve essere eliminato) diventa un argomento, *valore*a *funzione o lambda*, che è una funzione che prevede un singolo rimanente argomento di tipo che corrisponde al valore prodotto da *expression1*, o un'espressione lambda che prevede un argomento di quel tipo. Al termine dell'esecuzione della funzione, il runtime chiama `Dispose` e libera le risorse (a meno che il valore è `null`, nel qual caso non viene effettuata la chiamata a Dispose).

Nell'esempio seguente viene illustrato il `using` espressione con un'espressione lambda.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

L'esempio seguente mostra il `using` espressione con una funzione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

Si noti che la funzione potrebbe essere una funzione che presenta alcuni argomenti già applicati. Esempio di codice seguente viene illustrato questo. Viene creato un file che contiene la stringa `XYZ`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

Il `using` funzione e `use` associazione sono quasi equivalenti modi per ottenere lo stesso risultato. Il `using` parola chiave consente un maggiore controllo sul momento `Dispose` viene chiamato. Quando si utilizza `using`, `Dispose` viene chiamato alla fine dell'espressione lambda o di funzione; quando si utilizza il `use` (parola chiave), `Dispose` viene chiamato alla fine del blocco di codice che lo contiene. In generale, è preferibile utilizzare `use` anziché il `using` (funzione).


## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)
