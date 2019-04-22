---
title: Il numero di indici è superiore al numero di dimensioni della matrice indicizzata
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: 01659205f271b089fe4e8aa87cf7a8c44e7a4000
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837989"
---
# <a name="number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a><span data-ttu-id="e16f4-102">Il numero di indici è superiore al numero di dimensioni della matrice indicizzata</span><span class="sxs-lookup"><span data-stu-id="e16f4-102">Number of indices exceeds the number of dimensions of the indexed array</span></span>
<span data-ttu-id="e16f4-103">Il numero di indici usati per accedere a un elemento di matrice deve essere esattamente uguale all'ordine di priorità della matrice, vale a dire al numero di dimensioni dichiarate per la matrice.</span><span class="sxs-lookup"><span data-stu-id="e16f4-103">The number of indices used to access an array element must be exactly the same as the rank of the array, that is, the number of dimensions declared for it.</span></span>  
  
 <span data-ttu-id="e16f4-104">**ID errore:** BC30106</span><span class="sxs-lookup"><span data-stu-id="e16f4-104">**Error ID:** BC30106</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e16f4-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e16f4-105">To correct this error</span></span>  
  
-   <span data-ttu-id="e16f4-106">Rimuovere gli indici da riferimento della matrice fino a quando il numero totale di indici è pari all'ordine della matrice.</span><span class="sxs-lookup"><span data-stu-id="e16f4-106">Remove subscripts from the array reference until the total number of subscripts equals the rank of the array.</span></span> <span data-ttu-id="e16f4-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e16f4-107">For example:</span></span>  
  
    ```vb  
    Dim gameBoard(3, 3) As String  
  
    ' Incorrect code. The array has two dimensions.  
    gameBoard(1, 1, 1) = "X"  
    gameBoard(2, 1, 1) = "O"  
  
    ' Correct code.  
    gameBoard(0, 0) = "X"  
    gameBoard(1, 0) = "O"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e16f4-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e16f4-108">See also</span></span>

- [<span data-ttu-id="e16f4-109">Matrici</span><span class="sxs-lookup"><span data-stu-id="e16f4-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
