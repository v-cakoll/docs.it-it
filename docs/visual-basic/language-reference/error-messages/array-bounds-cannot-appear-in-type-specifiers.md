---
title: I limiti di matrice non possono trovarsi negli identificatori di tipo
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: f31aea5a98233c8f262a77ba5c99eea389bc33ee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715439"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="ecee2-102">I limiti di matrice non possono trovarsi negli identificatori di tipo</span><span class="sxs-lookup"><span data-stu-id="ecee2-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="ecee2-103">Le dimensioni di matrice non possono essere dichiarate come parte di un identificatore di tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="ecee2-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="ecee2-104">**ID errore:** BC30638</span><span class="sxs-lookup"><span data-stu-id="ecee2-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ecee2-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ecee2-105">To correct this error</span></span>  
  
-   <span data-ttu-id="ecee2-106">Specificare le dimensioni della matrice subito dopo il nome della variabile anziché inserire la dimensione della matrice dopo il tipo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ecee2-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="ecee2-107">Definire una matrice e inizializzarlo con il numero desiderato di elementi, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ecee2-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ecee2-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecee2-108">See also</span></span>
- [<span data-ttu-id="ecee2-109">Matrici</span><span class="sxs-lookup"><span data-stu-id="ecee2-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
