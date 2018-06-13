---
title: '&#39;ReDim&#39; può modificare solo la dimensione più a destra'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: efb98df13a7e3e378347b30b6fc00b90030ec194
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641183"
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="50ba0-102">&#39;ReDim&#39; può modificare solo la dimensione più a destra</span><span class="sxs-lookup"><span data-stu-id="50ba0-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="50ba0-103">Un'istruzione `ReDim` ha tentato di usare la parola chiave `Preserve` per modificare una dimensione di una matrice che non è l'ultima dimensione.</span><span class="sxs-lookup"><span data-stu-id="50ba0-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="50ba0-104">Quando si usa `Preserve`, si può ridimensionare solo l'ultima dimensione di una matrice.</span><span class="sxs-lookup"><span data-stu-id="50ba0-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="50ba0-105">Per tutte le altre, è necessario specificare le stesse dimensioni di una matrice esistente.</span><span class="sxs-lookup"><span data-stu-id="50ba0-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="50ba0-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="50ba0-106">To correct this error</span></span>  
  
-   <span data-ttu-id="50ba0-107">Rimuovere la parola chiave `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="50ba0-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50ba0-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50ba0-108">See Also</span></span>  
 [<span data-ttu-id="50ba0-109">Matrici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50ba0-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="50ba0-110">Dimensioni della matrice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50ba0-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="50ba0-111">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="50ba0-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="50ba0-112">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="50ba0-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="50ba0-113">Preserve - eliminazione</span><span class="sxs-lookup"><span data-stu-id="50ba0-113">Preserve - delete</span></span>](http://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
