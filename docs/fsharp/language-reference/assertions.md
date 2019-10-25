---
title: Asserzioni
description: Informazioni su come usare l'espressione "Assert" come funzionalità di debug per il F# test delle espressioni nel linguaggio di programmazione.
ms.date: 10/22/2019
ms.openlocfilehash: 430db20e5ca307ba43a72e678a0424e03b0ac381
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799070"
---
# <a name="assertions"></a>Asserzioni

L'espressione `assert` è una funzionalità di debug che è possibile utilizzare per testare un'espressione. In caso di errore in modalità Debug, un'asserzione genera una finestra di dialogo di errore di sistema.

## <a name="syntax"></a>Sintassi

```fsharp
assert condition
```

## <a name="remarks"></a>Note

Il tipo dell'espressione `assert` è `bool -> unit`.

La funzione `assert` viene risolta <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Questo significa che il comportamento è identico a chiamare direttamente <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.

Il controllo dell'asserzione è abilitato solo quando si esegue la compilazione in modalità di debug; ovvero se viene definita la costante `DEBUG`. Nel sistema del progetto, per impostazione predefinita, la costante `DEBUG` è definita nella configurazione di debug, ma non nella configurazione di rilascio.

L'errore di asserzione non può essere rilevato F# tramite la gestione delle eccezioni.

## <a name="example"></a>Esempio

Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo dell'espressione `assert`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
