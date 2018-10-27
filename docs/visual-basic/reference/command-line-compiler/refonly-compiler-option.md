---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: b22fb9ae24a04d9fe530811bf764352199c31813
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50036060"
---
# <a name="-refonly-visual-basic"></a>-refonly (Visual Basic)

Il **- refonly** opzione indica che l'output primario della compilazione deve essere un assembly di riferimento invece di un assembly di implementazione. Il parametro `-refonly` disabilita automaticamente l'output dei file PDB poiché non è possibile eseguire gli assembly di riferimento.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sintassi

```console
-refonly
```

## <a name="remarks"></a>Note

Visual Basic supporta il `-refout` passare a partire dalla versione 15.3.

Gli assembly di riferimento sono solo di metadati che contiene metadati ma nessun codice di implementazione. Includono informazioni su tipo e membro per tutto, tranne i tipi anonimi. L'utilizzo di corpi `throw null`, a differenza di nessun corpo, è giustificato dal fatto che PEVerify può essere eseguito e avere esito positivo convalidando la completezza dei metadati.

Gli assembly di riferimento includono un livello di assembly [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attributo. Questo attributo può essere specificato nell'origine, quindi non è necessaria la sintesi da parte del compilatore. A causa di questo attributo, i runtime non caricheranno caricare gli assembly di riferimento per l'esecuzione (ma possono comunque essere caricati in un contesto reflection-only). Gli strumenti che riflettono sugli assembly devono garantire che vengano caricati gli assembly di riferimento come sola reflection; in caso contrario, il runtime genera una <xref:System.BadImageFormatException>.

Le opzioni `-refonly` e [`-refout`](refout-compiler-option.md) si escludono reciprocamente.

## <a name="see-also"></a>Vedere anche
[-refout](refout-compiler-option.md)   
[Compilatore della riga di comando di Visual Basic](index.md)  
[Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)   
