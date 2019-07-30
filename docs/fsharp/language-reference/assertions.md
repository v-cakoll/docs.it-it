---
title: Asserzioni
description: Informazioni su come usare l'espressione "Assert" come funzionalità di debug per il F# test delle espressioni nel linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: b8b7e9662143b432d650f87515d4af31cced4149
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630033"
---
# <a name="assertions"></a>Asserzioni

L' `assert` espressione è una funzionalità di debug che è possibile utilizzare per testare un'espressione. In caso di errore in modalità Debug, un'asserzione genera una finestra di dialogo di errore di sistema.

## <a name="syntax"></a>Sintassi

```fsharp
assert condition
```

## <a name="remarks"></a>Note

L' `assert` espressione è di `bool -> unit`tipo.

Nella sintassi precedente, *Condition* rappresenta un'espressione booleana che deve essere testata. Se l'espressione restituisce `true`, l'esecuzione continua senza effetti. Se restituisce, viene generata `false`una finestra di dialogo di errore di sistema. Nella finestra di dialogo di errore è presente una didascalia che contiene l'asserzione di stringa **non riuscita**. La finestra di dialogo contiene una traccia dello stack che indica dove si è verificato l'errore di asserzione.

Il controllo dell'asserzione è abilitato solo quando si esegue la compilazione in modalità di debug; ovvero se la costante `DEBUG` è definita. Nel sistema del progetto, per impostazione predefinita, `DEBUG` la costante è definita nella configurazione di debug, ma non nella configurazione di rilascio.

L'errore di asserzione non può essere rilevato F# tramite la gestione delle eccezioni.

> [!NOTE]
> La `assert` funzione viene risolta in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

Nell'esempio di codice riportato di seguito viene illustrato l' `assert` utilizzo dell'espressione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
