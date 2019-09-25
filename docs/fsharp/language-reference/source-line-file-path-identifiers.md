---
title: Identificatori di riga, di file e di percorso di origine
description: Informazioni su come usare i valori di F# identificatore predefiniti che consentono di accedere al numero di riga, alla directory e al nome file del codice sorgente.
ms.date: 05/16/2016
ms.openlocfilehash: f22c3dfb3cb106fbe45883ffd7de01feac30db00
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216755"
---
# <a name="source-line-file-and-path-identifiers"></a>Identificatori di riga, di file e di percorso di origine

Gli identificatori `__LINE__` `__SOURCE_DIRECTORY__` e`__SOURCE_FILE__` sono valori predefiniti che consentono di accedere al numero di riga, alla directory e al nome file del codice sorgente.

## <a name="syntax"></a>Sintassi

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>Note

Ognuno di questi valori è di `string`tipo.

Nella tabella seguente sono riepilogati gli identificatori di riga, file e percorso di origine disponibili in F#. Questi identificatori non sono macro del preprocessore; si tratta di valori predefiniti riconosciuti dal compilatore.

|Identificatore predefinito|Descrizione|
|---------------------|-----------|
|`__LINE__`|Restituisce il numero di riga corrente, considerando `#line` le direttive.|
|`__SOURCE_DIRECTORY__`|Restituisce il percorso completo corrente della directory di origine, considerando `#line` le direttive.|
|`__SOURCE_FILE__`|Restituisce il nome del file di origine corrente, senza il relativo percorso, `#line` considerando le direttive.|

Per ulteriori informazioni sulla `#line` direttiva, vedere [direttive del compilatore](compiler-directives.md).

## <a name="example"></a>Esempio

Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo di questi valori.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

Output:

```console
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a>Vedere anche

- [Direttive per il compilatore](compiler-directives.md)
- [Riferimenti per il linguaggio F#](index.md)
