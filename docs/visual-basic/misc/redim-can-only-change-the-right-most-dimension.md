---
title: "'ReDim' può modificare solo la prima dimensione a destra"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 97eedabd550be397f9cdffc5fd864d7a88c30c31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714204"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a>'ReDim' può modificare solo la prima dimensione a destra
Un'istruzione `ReDim` ha tentato di usare la parola chiave `Preserve` per modificare una dimensione di una matrice che non è l'ultima dimensione. Quando si usa `Preserve`, si può ridimensionare solo l'ultima dimensione di una matrice. Per tutte le altre, è necessario specificare le stesse dimensioni di una matrice esistente.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere la parola chiave `Preserve` .  
  
## <a name="see-also"></a>Vedere anche
- [Matrici in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [Dimensioni di matrice in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [Istruzione ReDim](../../visual-basic/language-reference/statements/redim-statement.md)
- [Istruzione Dim](../../visual-basic/language-reference/statements/dim-statement.md)
- [Preserve - eliminazione](https://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
