---
title: 'Gestione delle risorse: Parola chiave use'
description: Informazioni sulla F# parola chiave ' use ' e la funzione ' using ', che consente di controllare l'inizializzazione e il rilascio delle risorse.
ms.date: 05/16/2016
ms.openlocfilehash: 5e0838401bee02050343b2f6dcc646a8dc8b4dc0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627266"
---
# <a name="resource-management-the-use-keyword"></a>Gestione delle risorse: Parola chiave use

In questo argomento vengono descritte `use` la parola `using` chiave e la funzione, che consente di controllare l'inizializzazione e il rilascio delle risorse.

## <a name="resources"></a>Risorse

Il termine *risorsa* viene usato in più di un modo. Sì, le risorse possono essere dati utilizzate da un'applicazione, ad esempio stringhe, elementi grafici e simili, ma in questo contesto le *risorse* fanno riferimento a risorse software o del sistema operativo, ad esempio contesti di dispositivi grafici, handle di file, rete e database connessioni, oggetti di concorrenza, ad esempio handle di attesa e così via. L'uso di queste risorse da parte delle applicazioni comporta l'acquisizione della risorsa dal sistema operativo o da un altro provider di risorse, seguito dalla successiva versione della risorsa al pool, in modo che possa essere fornita a un'altra applicazione. Si verificano problemi quando le applicazioni non rilasciano risorse nel pool comune.

## <a name="managing-resources"></a>Gestione di risorse

Per gestire in modo efficiente e responsabile le risorse in un'applicazione, è necessario rilasciare le risorse tempestivamente e in modo prevedibile. Il .NET Framework consente di eseguire questa operazione fornendo l' `System.IDisposable` interfaccia. Un tipo che implementa `System.IDisposable` ha il `System.IDisposable.Dispose` metodo, che libera correttamente le risorse. Le applicazioni ben scritte garantiscono che `System.IDisposable.Dispose` venga chiamato tempestivamente quando un oggetto che include una risorsa limitata non è più necessario. Fortunatamente, la maggior parte dei linguaggi .NET fornisce supporto per semplificare questa F# operazione e non è un'eccezione. Sono disponibili due costrutti di linguaggio utili che supportano il modello Dispose `use` : l'associazione `using` e la funzione.

## <a name="use-binding"></a>USA binding

La `use` parola chiave ha un formato simile a quello `let` dell'associazione:

*espressione* *valore* = use

Fornisce la stessa funzionalità di un' `let` associazione, ma aggiunge una chiamata a `Dispose` sul valore quando il valore esce dall'ambito. Si noti che il compilatore inserisce un controllo null sul valore, in modo che se il valore `null`è, la chiamata `Dispose` a non viene tentata.

Nell'esempio seguente viene illustrato come chiudere automaticamente un file utilizzando la `use` parola chiave.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

> [!NOTE]
> È possibile utilizzare `use` nelle espressioni di calcolo, nel qual caso viene utilizzata una versione `use` personalizzata dell'espressione. Per altre informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md)ed [espressioni di calcolo](computation-expressions.md).

## <a name="using-function"></a>Funzione using

La `using` funzione ha il formato seguente:

`using`(*expression1*) *funzione-or-lambda*

In un' `using` espressione, *expression1* crea l'oggetto che deve essere eliminato. Il risultato di *expression1* , ovvero l'oggetto che deve essere eliminato, diventa un argomento, *valore*, *funzione o lambda*, che è una funzione che prevede un singolo argomento rimanente di un tipo che corrisponde al valore prodotto da  *expression1*o un'espressione lambda che prevede un argomento di quel tipo. Al termine dell'esecuzione della funzione, il runtime chiama `Dispose` e libera le risorse (a meno che il valore non sia `null`, nel qual caso la chiamata a Dispose non viene tentata).

Nell'esempio seguente viene illustrata l' `using` espressione con un'espressione lambda.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

Nell'esempio seguente viene illustrata l' `using` espressione con una funzione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

Si noti che la funzione potrebbe essere una funzione a cui sono già stati applicati alcuni argomenti. Nell'esempio di codice seguente viene illustrata questa possibilità. Viene creato un file che contiene la stringa `XYZ`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

La `using` funzione e l' `use` associazione sono modi quasi equivalenti per eseguire la stessa operazione. La `using` parola chiave offre maggiore controllo su `Dispose` quando viene chiamato il metodo. Quando si usa `using`, `Dispose` viene chiamato alla fine della funzione o dell'espressione lambda. quando si usa la `use` parola chiave, `Dispose` viene chiamato alla fine del blocco di codice contenitore. In generale, è preferibile usare `use` anziché la `using` funzione.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
