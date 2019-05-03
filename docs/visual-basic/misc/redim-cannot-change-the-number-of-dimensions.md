---
title: "'ReDim' non può modificare il numero di dimensioni"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: b6bb78c3f1d7224e6e4b432fd3aef4589f2f1cd4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964892"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>'ReDim' non può modificare il numero di dimensioni
Un'operazione tenta di usare l'istruzione `ReDim` per modificare il numero di dimensioni di una matrice. `ReDim` può modificare la grandezza di una o più dimensioni di una matrice che è già stata dichiarata formalmente, ma non può modificare il numero di dimensioni di una matrice.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Assicurarsi di voler modificare il numero di dimensioni anziché la grandezza delle dimensioni della matrice e, se possibile, usare `Dim` per dichiarare una nuova matrice con il numero di dimensioni desiderato.  
  
## <a name="see-also"></a>Vedere anche

- [Matrici in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [Dimensioni di matrice in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [Istruzione ReDim](../../visual-basic/language-reference/statements/redim-statement.md)
- [Istruzione Dim](../../visual-basic/language-reference/statements/dim-statement.md)
