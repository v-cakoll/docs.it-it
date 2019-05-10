---
title: "'ReDim' non può modificare il numero di dimensioni"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 1e9695bbc7f104aa741de232f1f6d3c76df2cebf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591736"
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
