---
title: Identificatori di riga, file e percorso di origine (F#)
description: "Informazioni sull'utilizzo di F # identificatore valori incorporati che consentono di accedere il numero di riga di origine, directory e nome file del codice."
ms.date: 05/16/2016
ms.openlocfilehash: 76b705fec0d951b12655edbe69e7c9212f50779d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="source-line-file-and-path-identifiers"></a>Identificatori di riga, di file e di percorso di origine

Gli identificatori `__LINE__`, `__SOURCE_DIRECTORY__` e `__SOURCE_FILE__` sono valori incorporati che consentono di accedere al origine riga numero, directory e file di nome nel codice.


## <a name="syntax"></a>Sintassi

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>Note
Ognuno di questi valori è di tipo `string`.

Nella tabella seguente vengono riepilogati la riga di codice sorgente, file e identificatori del percorso che sono disponibili in F #. Questi identificatori non sono macro del preprocessore. sono valori predefiniti che sono riconosciuti dal compilatore.

|Identificatore predefinito|Descrizione|
|---------------------|-----------|
|`__LINE__`|Restituisce il numero di riga corrente, prendere in considerazione `#line` direttive.|
|`__SOURCE_DIRECTORY__`|Restituisce il percorso corrente completo della directory di origine, prendere in considerazione `#line` direttive.|
|`__SOURCE_FILE__`|Restituisce il nome di file di origine corrente e il relativo percorso, prendere in considerazione `#line` direttive.|
Per ulteriori informazioni sul `#line` direttiva, vedere [direttive del compilatore](compiler-directives.md).

## <a name="example"></a>Esempio

Esempio di codice seguente viene illustrato l'utilizzo di questi valori.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

Output:

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a>Vedere anche
[Direttive per il compilatore](compiler-directives.md)

[Riferimenti per il linguaggio F#](index.md)
