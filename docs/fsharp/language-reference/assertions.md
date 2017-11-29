---
title: Asserzioni (F#)
description: "Informazioni su come utilizzare l'espressione 'assert' come una funzionalità di debug per il test di espressioni in linguaggio di programmazione c#."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2badaad7-f086-47e7-99c1-91f35117da83
ms.openlocfilehash: 56891769602afaa765ebfe7e7822a179c7a22968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
