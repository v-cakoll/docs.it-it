---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 8e64989ac1410b51991027ffcb33e8dae0c0284b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775559"
---
# <a name="-refonly-visual-basic"></a>-refonly (Visual Basic)

L'opzione **-refonly** indica che l'output primario della compilazione deve essere un assembly di riferimento invece di un assembly di implementazione. Il parametro `-refonly` disabilita automaticamente l'output dei file PDB poiché non è possibile eseguire gli assembly di riferimento.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sintassi

```console
-refonly
```

## <a name="remarks"></a>Note

Visual Basic supporta l'opzione di `-refonly` a partire dalla versione 15,3.

Gli assembly di riferimento sono un tipo speciale di assembly che contiene solo la quantità minima di metadati necessaria per rappresentare la superficie dell'API pubblica della libreria. Sono incluse le dichiarazioni per tutti i membri significativi quando si fa riferimento a un assembly negli strumenti di compilazione, ma si escludono tutte le implementazioni e le dichiarazioni dei membri privati che non hanno alcun impatto osservabile sul contratto API. Per ulteriori informazioni, vedere [assembly di riferimento](../../../standard/assembly/reference-assemblies.md) nella Guida di .NET.

Le opzioni `-refonly` e [`-refout`](refout-compiler-option.md) si escludono reciprocamente.

## <a name="see-also"></a>Vedere anche

- [/refout](refout-compiler-option.md)
- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
