---
title: "'ReDim' può modificare solo la prima dimensione a destra"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 8e42e0df7b97fb96f468ce37dd4cfc52fad8c596
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358296"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a>'ReDim' può modificare solo la prima dimensione a destra
Un'istruzione `ReDim` ha tentato di usare la parola chiave `Preserve` per modificare una dimensione di una matrice che non è l'ultima dimensione. Quando si usa `Preserve`, si può ridimensionare solo l'ultima dimensione di una matrice. Per tutte le altre, è necessario specificare le stesse dimensioni di una matrice esistente.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rimuovere la parola chiave `Preserve` .  
  
## <a name="see-also"></a>Vedere anche

- [Matrici in Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Dimensioni della matrice in Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [Istruzione ReDim](../language-reference/statements/redim-statement.md)
- [Istruzione Dim](../language-reference/statements/dim-statement.md)
