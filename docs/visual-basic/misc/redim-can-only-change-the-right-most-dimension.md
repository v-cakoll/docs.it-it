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
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="81de6-102">'ReDim' può modificare solo la prima dimensione a destra</span><span class="sxs-lookup"><span data-stu-id="81de6-102">'ReDim' can only change the right-most dimension</span></span>
<span data-ttu-id="81de6-103">Un'istruzione `ReDim` ha tentato di usare la parola chiave `Preserve` per modificare una dimensione di una matrice che non è l'ultima dimensione.</span><span class="sxs-lookup"><span data-stu-id="81de6-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="81de6-104">Quando si usa `Preserve`, si può ridimensionare solo l'ultima dimensione di una matrice.</span><span class="sxs-lookup"><span data-stu-id="81de6-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="81de6-105">Per tutte le altre, è necessario specificare le stesse dimensioni di una matrice esistente.</span><span class="sxs-lookup"><span data-stu-id="81de6-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="81de6-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="81de6-106">To correct this error</span></span>  
  
-   <span data-ttu-id="81de6-107">Rimuovere la parola chiave `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="81de6-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81de6-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81de6-108">See also</span></span>
- [<span data-ttu-id="81de6-109">Matrici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="81de6-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="81de6-110">Dimensioni di matrice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="81de6-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="81de6-111">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="81de6-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="81de6-112">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="81de6-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="81de6-113">Preserve - eliminazione</span><span class="sxs-lookup"><span data-stu-id="81de6-113">Preserve - delete</span></span>](https://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
