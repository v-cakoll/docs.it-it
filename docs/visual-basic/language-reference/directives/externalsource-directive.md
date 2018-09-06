---
title: '#ExternalSource (direttiva) (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: dcde8507eb033d0a47d5c5d3fa36176cd63b0856
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861787"
---
# <a name="externalsource-directive"></a>Direttiva #ExternalSource
Indica un mapping tra le righe specifiche del codice sorgente e testo esterno al codice sorgente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>Parti  
 `StringLiteral`  
 Il percorso all'origine esterna.  
  
 `IntLiteral`  
 Il numero di riga della prima riga dell'origine esterna.  
  
 `LogicalLine`  
 La riga in cui l'errore si verifica nell'origine esterna.  
  
 `#End ExternalSource`  
 Termina il blocco `#ExternalSource`.  
  
## <a name="remarks"></a>Note  
 Questa direttiva viene usata solo dal compilatore e il debugger.  
  
 Un file di origine può includere le direttive origine esterna, che indicano un mapping tra righe di codice nel file di origine specifiche e testo esterno per l'origine, ad esempio un file con estensione aspx. Se si verificano errori nel codice sorgente designata durante la compilazione, sono identificate come provenienti dall'origine esterna.  
  
 Direttive origine esterna non hanno alcun effetto sulla compilazione e non possono essere annidate. Essi sono destinati all'utilizzo interno da parte dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
