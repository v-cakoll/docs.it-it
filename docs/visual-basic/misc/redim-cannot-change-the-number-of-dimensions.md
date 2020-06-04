---
title: "'ReDim' non può modificare il numero di dimensioni"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: b2404927c2faf30d1d058d2163fd5d67e1a52e1e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358167"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>'ReDim' non può modificare il numero di dimensioni
Un'operazione tenta di usare l'istruzione `ReDim` per modificare il numero di dimensioni di una matrice. `ReDim` può modificare la grandezza di una o più dimensioni di una matrice che è già stata dichiarata formalmente, ma non può modificare il numero di dimensioni di una matrice.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Assicurarsi di voler modificare il numero di dimensioni anziché la grandezza delle dimensioni della matrice e, se possibile, usare `Dim` per dichiarare una nuova matrice con il numero di dimensioni desiderato.  
  
## <a name="see-also"></a>Vedere anche

- [Matrici in Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Dimensioni della matrice in Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [Istruzione ReDim](../language-reference/statements/redim-statement.md)
- [Istruzione Dim](../language-reference/statements/dim-statement.md)
