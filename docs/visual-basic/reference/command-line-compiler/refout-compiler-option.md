---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: c11d83ff37da41faa3dc6b66a87e2c52c5f6c7ac
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582864"
---
# <a name="-refout-visual-basic"></a>-refout (Visual Basic)

L'opzione **-refout** specifica un percorso file in cui l'assembly di riferimento deve essere restituito come output.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sintassi

```console
-refout:filepath
```

## <a name="arguments"></a>argomenti

`filepath`  
Percorso e nome del file dell'assembly di riferimento. In genere dovrebbe trovarsi in una sottocartella dell'assembly primario. La convenzione consigliata (usata da MSBuild) consiste nell'inserire l'assembly di riferimento in una sottocartella "ref /" relativa all'assembly primario. Tutte le cartelle nel `filepath` devono esistere; il compilatore non li crea.

## <a name="remarks"></a>Note

Visual Basic supporta l'opzione di `-refout` a partire dalla versione 15,3.

Gli assembly di riferimento sono assembly di soli metadati che contengono metadati ma nessun codice di implementazione. Includono informazioni sul tipo e sui membri per tutti gli elementi eccetto i tipi anonimi. I corpi dei metodi vengono sostituiti con una singola istruzione `throw null`. Il motivo per cui si usano i corpi del metodo `throw null` (in contrapposizione a nessun corpo) è in modo che PEVerify possa essere eseguito e superato (convalidando quindi la completezza dei metadati).

Gli assembly di riferimento includono un attributo [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) a livello di assembly. Questo attributo può essere specificato nell'origine, quindi non è necessaria la sintesi da parte del compilatore. A causa di questo attributo, i runtime rifiutano di caricare gli assembly di riferimento per l'esecuzione, ma possono comunque essere caricati in un contesto di sola reflection. Gli strumenti che riflettono gli assembly devono assicurarsi di caricare gli assembly di riferimento come solo reflection; in caso contrario, il runtime genera un'<xref:System.BadImageFormatException>.

Le opzioni `-refout` e [`-refonly`](refonly-compiler-option.md) si escludono reciprocamente.

## <a name="see-also"></a>Vedere anche

- [/refonly](refonly-compiler-option.md)
- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
