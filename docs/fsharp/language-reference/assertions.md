---
title: Asserzioni (F#)
description: Informazioni su come utilizzare l'espressione 'assert' come una funzionalità di debug per il test di espressioni in linguaggio di programmazione c#.
ms.date: 05/16/2016
ms.openlocfilehash: 83e6cd77bbbb2c32e9b778e5bf6dd9d2e9c8fe32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="assertions"></a>Asserzioni

Il `assert` espressione è una funzionalità di debug che è possibile utilizzare per testare un'espressione. In caso di errore in modalità Debug, un'asserzione genera una finestra di dialogo di errore di sistema.

## <a name="syntax"></a>Sintassi

```fsharp
assert condition
```

## <a name="remarks"></a>Note

Il `assert` tipo dell'espressione è `bool -> unit`.

Nella sintassi precedente, *condizione* rappresenta un'espressione booleana da testare. Se l'espressione restituisce `true`, esecuzione continua. Se restituisce `false`, viene generata una finestra di dialogo Errore di sistema. La finestra di dialogo di errore ha una didascalia che contiene la stringa **asserzione non riuscita**. Nella finestra di dialogo contiene una traccia dello stack che indica dove si è verificato l'errore di asserzione.

Il controllo delle asserzioni è abilitato solo quando si esegue la compilazione in modalità Debug. ovvero, se la costante `DEBUG` è definito. Nel sistema del progetto, per impostazione predefinita, il `DEBUG` costante è definita nella configurazione di Debug, ma non nella configurazione di rilascio.

Errore di asserzione non può essere intercettato tramite la gestione delle eccezioni di F #.

>[!NOTE]
Il `assert` funzione si risolve in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

Esempio di codice seguente viene illustrato l'utilizzo del `assert` espressione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a>Vedere anche

[Riferimenti per il linguaggio F#](index.md)
