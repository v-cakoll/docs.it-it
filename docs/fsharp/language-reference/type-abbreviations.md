---
title: Abbreviazioni dei tipi
description: Informazioni sulle F# abbreviazioni di tipo per assegnare a un tipo un nome più significativo allo scopo di semplificare la lettura del codice.
ms.date: 05/16/2016
ms.openlocfilehash: 339b22a675e3f1ad8a3da207053e611942b55a22
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630207"
---
# <a name="type-abbreviations"></a>Abbreviazioni dei tipi

Un'abbreviazione di *tipo* è un alias o un nome alternativo per un tipo.

## <a name="syntax"></a>Sintassi

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a>Note

È possibile usare le abbreviazioni di tipo per assegnare a un tipo un nome più significativo, in modo da semplificare la lettura del codice. È anche possibile usarli per creare un nome facile da usare per un tipo altrimenti complesso da scrivere. Inoltre, è possibile usare le abbreviazioni di tipo per semplificare la modifica di un tipo sottostante senza modificare tutto il codice che usa il tipo. Di seguito è riportata un'abbreviazione di tipo semplice.

Per `public`impostazione predefinita, l'accessibilità delle abbreviazioni di tipo è.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

Le abbreviazioni di tipo possono includere parametri generici, come nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

Nel codice precedente, `Transform` è un'abbreviazione di tipo che rappresenta una funzione che accetta un solo argomento di qualsiasi tipo e che restituisce un singolo valore dello stesso tipo.

Le abbreviazioni di tipo non vengono mantenute nel codice MSIL .NET Framework. Pertanto, quando si usa un F# assembly da un altro linguaggio .NET Framework, è necessario usare il nome del tipo sottostante per un'abbreviazione di tipo.

Le abbreviazioni di tipo possono essere usate anche in unità di misura. Per ulteriori informazioni, vedere [unità di misura](units-of-measure.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
