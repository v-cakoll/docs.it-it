---
title: '#Direttiva ExternalSource'
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
ms.openlocfilehash: e4c7704c32c3a6c73e069d0b7129d5386696b438
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402992"
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
  
## <a name="remarks"></a>Commenti  

 Questa direttiva viene utilizzata solo dal compilatore e dal debugger.  
  
 Un file di origine può includere direttive di origine esterne, che indicano un mapping tra righe specifiche di codice nel file di origine e testo esterno all'origine, ad esempio un file aspx. Se durante la compilazione vengono rilevati errori nel codice sorgente designato, vengono identificati come provenienti dall'origine esterna.  
  
 Le direttive external source non hanno alcun effetto sulla compilazione e non possono essere annidate. Sono destinate esclusivamente all'uso interno da parte dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Compilazione condizionale](../../programming-guide/program-structure/conditional-compilation.md)
