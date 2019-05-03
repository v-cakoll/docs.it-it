---
title: Asserzioni
description: Informazioni su come usare l'espressione 'assert' come una funzionalità di debug per testare le espressioni in di F# linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: c2d97386e87e9b915da490a78fff9aedb9def616
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703218"
---
# <a name="assertions"></a>Asserzioni

Il `assert` espressione è una funzionalità di debug che è possibile usare per testare un'espressione. In caso di errore in modalità Debug, un'asserzione genera una finestra di dialogo di errore di sistema.

## <a name="syntax"></a>Sintassi

```fsharp
assert condition
```

## <a name="remarks"></a>Note

Il `assert` espressione con tipo `bool -> unit`.

Nella sintassi precedente *condizione* rappresenta un'espressione booleana che deve essere testato. Se l'espressione restituisce `true`, esecuzione continua senza interruzioni. Se restituisce `false`, viene generata una finestra di dialogo di errore di sistema. La finestra di dialogo di errore ha una didascalia che contiene la stringa **asserzione non riuscita**. La finestra di dialogo contiene un'analisi dello stack che indica dove si è verificato l'errore di asserzione.

Il controllo delle asserzioni è abilitato solo quando si esegue la compilazione in modalità Debug. vale a dire, se la costante `DEBUG` è definito. Nel sistema del progetto, per impostazione predefinita, il `DEBUG` costante è definita nella configurazione di Debug ma non nella configurazione di rilascio.

Errore di asserzione non può essere intercettato tramite F# gestione delle eccezioni.

> [!NOTE]
> Il `assert` funzione si risolve in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

Esempio di codice seguente viene illustrato l'utilizzo del `assert` espressione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)