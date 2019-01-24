---
title: Il numero di indici è superiore al numero di dimensioni della matrice indicizzata
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: b113860366ccbe47fed8ef13abb90a540dc88b33
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710651"
---
# <a name="number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a>Il numero di indici è superiore al numero di dimensioni della matrice indicizzata
Il numero di indici usati per accedere a un elemento di matrice deve essere esattamente uguale all'ordine di priorità della matrice, vale a dire al numero di dimensioni dichiarate per la matrice.  
  
 **ID errore:** BC30106  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere gli indici da riferimento della matrice fino a quando il numero totale di indici è pari all'ordine della matrice. Ad esempio:  
  
    ```vb  
    Dim gameBoard(3, 3) As String  
  
    ' Incorrect code. The array has two dimensions.  
    gameBoard(1, 1, 1) = "X"  
    gameBoard(2, 1, 1) = "O"  
  
    ' Correct code.  
    gameBoard(0, 0) = "X"  
    gameBoard(1, 0) = "O"  
    ```  
  
## <a name="see-also"></a>Vedere anche
- [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md)
