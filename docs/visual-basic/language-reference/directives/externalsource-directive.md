---
title: '#<a name="externalsource-directive"></a>Direttiva ExternalSource'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "160"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f90b838e50b65b8652cd9cf6f6ee084e9552f025
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="externalsource-directive"></a>Direttiva #ExternalSource
Indica un mapping tra righe specifiche del codice sorgente e testo esterno al codice sorgente.  
  
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
  
 Un file di origine può includere le direttive origine esterna, che indicano un mapping tra righe specifiche di codice nel file di origine e testo esterno per l'origine, ad esempio un file con estensione aspx. Se vengono rilevati errori nel codice sorgente designato durante la compilazione, vengono identificati come provenienti dall'origine esterna.  
  
 Direttive origine esterna non hanno alcun effetto sulla compilazione e non possono essere annidate. Questi sono solo per uso interno da parte dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Compilazione condizionale](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
