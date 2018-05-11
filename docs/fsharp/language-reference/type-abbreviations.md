---
title: Abbreviazioni dei tipi (F#)
description: 'Informazioni su F # le abbreviazioni di tipo per assegnare un nome più significativo di un tipo per rendere il codice più facile da leggere.'
ms.date: 05/16/2016
ms.openlocfilehash: e222caa41a20a64071c94cffea6ea7b2bec8eb22
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2018
---
# <a name="type-abbreviations"></a>Abbreviazioni dei tipi

Oggetto *abbreviazione di tipo* è un alias o nome alternativo per un tipo.

## <a name="syntax"></a>Sintassi

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a>Note
È possibile utilizzare le abbreviazioni di tipo per assegnare un tipo di un nome più significativo, per rendere il codice più facile da leggere. È possibile utilizzare tali per creare un nome facile da usare per un tipo che è altrimenti difficili da scrivere. Inoltre, è possibile utilizzare le abbreviazioni di tipo per renderne più semplice modificare un tipo sottostante senza modificare tutto il codice che utilizza il tipo. Di seguito è un'abbreviazione di tipo semplice.

Per impostazione predefinita accessibilità di abbreviazioni dei tipi `public`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

Abbreviazioni dei tipi possono includere parametri generici, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

Nel codice precedente, `Transform` è un'abbreviazione di tipo che rappresenta una funzione che accetta un singolo argomento di qualsiasi tipo e restituisce un singolo valore dello stesso tipo.

Le abbreviazioni di tipo non vengono mantenute nel codice MSIL di .NET Framework. Pertanto, quando si utilizza un assembly F # da un altro linguaggio .NET Framework, è necessario utilizzare il nome del tipo sottostante di un'abbreviazione di tipo.

Le abbreviazioni di tipo consente inoltre alle unità di misura. Per ulteriori informazioni, vedere [unità di misura](units-of-measure.md).


## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

