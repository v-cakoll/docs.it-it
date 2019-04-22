---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: f2cdd228d8ce1912abbbe888c29c42f29299ebba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832736"
---
# <a name="-refout-visual-basic"></a>-refout (Visual Basic)

L'opzione **-refout** specifica un percorso file in cui l'assembly di riferimento deve essere restituito come output.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Sintassi

```console
-refout:filepath
```

## <a name="arguments"></a>Argomenti

 `filepath` Il percorso e nome file dell'assembly di riferimento. In genere deve essere in una sottocartella dell'assembly primario. La convenzione consigliata (usata da MSBuild) consiste nell'inserire l'assembly di riferimento in una sottocartella "ref /" relativa all'assembly primario. Tutte le cartelle in `filepath` deve esistere; il compilatore non vengono create. 

## <a name="remarks"></a>Note

Visual Basic supporta il `-refout` passare a partire dalla versione 15.3.

Gli assembly di riferimento sono solo di metadati che contiene metadati ma nessun codice di implementazione. Includono informazioni su tipo e membro per tutto, tranne i tipi anonimi. I corpi di metodo vengono sostituiti con un singolo `throw null` istruzione. Il motivo per usare `throw null` corpi di metodo (in contrapposizione nessun corpo) è in modo che PEVerify può eseguire e passare (convalidando la completezza dei metadati).

Gli assembly di riferimento includono un livello di assembly [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attributo. Questo attributo può essere specificato nell'origine, quindi non è necessaria la sintesi da parte del compilatore. A causa di questo attributo, i runtime rifiutano di caricare gli assembly di riferimento per l'esecuzione (ma possono comunque essere caricati in un contesto reflection-only). Gli strumenti che riflettono sugli assembly devono garantire che vengano caricati gli assembly di riferimento come sola reflection; in caso contrario, il runtime genera una <xref:System.BadImageFormatException>.

Le opzioni `-refout` e [`-refonly`](refonly-compiler-option.md) si escludono reciprocamente.

## <a name="see-also"></a>Vedere anche

- [/refonly](refonly-compiler-option.md)
- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
