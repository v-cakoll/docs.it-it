---
title: '#Direttiva ExternalSource (Visual Basic)'
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
ms.openlocfilehash: ac7096e998dd8d2a416dc739e1d7625e1abff7a6
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696829"
---
# <a name="externalsource-directive"></a>Direttiva #ExternalSource
Indica un mapping tra le righe specifiche del codice sorgente e il testo esterno all'origine.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a>Parti  
 `StringLiteral`  
 Percorso dell'origine esterna.  
  
 `IntLiteral`  
 Il numero di riga della prima riga dell'origine esterna.  
  
 `LogicalLine`  
 Riga in cui si è verificato l'errore nell'origine esterna.  
  
 `#End ExternalSource`  
 Termina il blocco `#ExternalSource`.  
  
## <a name="remarks"></a>Note  
 Questa direttiva viene utilizzata solo dal compilatore e dal debugger.  
  
 Un file di origine può includere direttive di origine esterne, che indicano un mapping tra righe specifiche di codice nel file di origine e testo esterno all'origine, ad esempio un file aspx. Se durante la compilazione vengono rilevati errori nel codice sorgente designato, vengono identificati come provenienti dall'origine esterna.  
  
 Le direttive external source non hanno alcun effetto sulla compilazione e non possono essere annidate. Sono destinate esclusivamente all'uso interno da parte dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
