---
title: Asserzioni (F#)
description: "Informazioni su come usare l'espressione 'assert' come una funzionalità di debug per testare le espressioni nel linguaggio di programmazione F #."
ms.date: 05/16/2016
ms.openlocfilehash: 85b1e839bfd19bada48b7f1821d15ddd8fa77754
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44206419"
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

Errore di asserzione non può essere intercettato tramite la gestione delle eccezioni di F #.

>[!NOTE]
Il `assert` funzione si risolve in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

Esempio di codice seguente viene illustrato l'utilizzo del `assert` espressione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
