---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21cea76f31bdf2ac5fcf434ee759f874f917617b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-refout-visual-basic"></a>-refout (Visual Basic)

L'opzione **-refout** specifica un percorso file in cui l'assembly di riferimento deve essere restituito come output.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sintassi

```console
-refout:filepath
```

## <a name="arguments"></a>Argomenti

 `filepath` Il percorso e il nome dell'assembly di riferimento. In genere deve essere in una sottocartella dell'assembly principale. La convenzione consigliata (usata da MSBuild) consiste nell'inserire l'assembly di riferimento in una sottocartella "ref /" relativa all'assembly primario. Tutte le cartelle `filepath` deve esistere; il compilatore non vengono create. 

## <a name="remarks"></a>Note

Visual Basic supporta i `-refout` passare a partire dalla versione 15.3.

Gli assembly di riferimento sono solo di metadati che contengono metadati ma nessun codice di implementazione. È incluso il tipo e membro informazioni per tutte le funzioni ad eccezione dei tipi anonimi. I corpi dei metodi vengono sostituiti con un singolo `throw null` istruzione. Il motivo per usare `throw null` corpi di metodo (in contrapposizione a nessun corpi) è in modo che PEVerify possibile vengono eseguiti e superati (pertanto la convalida la completezza dei metadati).

Gli assembly di riferimento includono un livello di assembly [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attributo. Questo attributo può essere specificato nell'origine, quindi non è necessaria la sintesi da parte del compilatore. A causa di questo attributo, il rifiutano di runtime caricare gli assembly di riferimento per l'esecuzione (ma possono comunque essere caricati in un contesto reflection-only). Strumenti che riflettono sugli assembly necessario verificare che vengano caricati gli assembly di riferimento come ReflectionOnly; in caso contrario, il runtime genera un <xref:System.BadImageFormatException>.

Le opzioni `-refout` e [`-refonly`](refonly-compiler-option.md) si escludono reciprocamente.

## <a name="see-also"></a>Vedere anche
[-refonly](refonly-compiler-option.md)   
[Compilatore della riga di comando di Visual Basic](index.md)  
[Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)  

