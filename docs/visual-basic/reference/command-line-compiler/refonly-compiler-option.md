---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5135ef4d33ddde27416e48c28425aa5b029237b
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2018
---
# <a name="-refonly-visual-basic"></a>-refonly (Visual Basic)

Il **- refonly** opzione indica che l'output primario della compilazione deve essere un assembly di riferimento anziché un'implementazione. Il parametro `-refonly` disabilita automaticamente l'output dei file PDB poiché non è possibile eseguire gli assembly di riferimento.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sintassi

```console
-refonly
```

## <a name="remarks"></a>Note

Visual Basic supporta i `-refout` passare a partire dalla versione 15.3.

Gli assembly di riferimento sono solo di metadati che contengono metadati ma nessun codice di implementazione. È incluso il tipo e membro informazioni per tutte le funzioni ad eccezione dei tipi anonimi. L'utilizzo di corpi `throw null`, a differenza di nessun corpo, è giustificato dal fatto che PEVerify può essere eseguito e avere esito positivo convalidando la completezza dei metadati.

Gli assembly di riferimento includono un livello di assembly [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attributo. Questo attributo può essere specificato nell'origine, quindi non è necessaria la sintesi da parte del compilatore. A causa di questo attributo, il runtime non caricherà gli assembly di riferimento per l'esecuzione (ma possono comunque essere caricati in un contesto reflection-only). Strumenti che riflettono sugli assembly necessario verificare che vengano caricati gli assembly di riferimento come ReflectionOnly; in caso contrario, il runtime genera un <xref:System.BadImageFormatException>.

Le opzioni `-refonly` e [`-refout`](refout-compiler-option.md) si escludono reciprocamente.

## <a name="see-also"></a>Vedere anche
[-refout](refout-compiler-option.md)   
[Compilatore della riga di comando di Visual Basic](index.md)  
[Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)   
