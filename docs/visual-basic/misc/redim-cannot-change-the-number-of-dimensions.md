---
title: "'ReDim' non può modificare il numero di dimensioni"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: b6bb78c3f1d7224e6e4b432fd3aef4589f2f1cd4
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "58019399"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="e2a68-102">'ReDim' non può modificare il numero di dimensioni</span><span class="sxs-lookup"><span data-stu-id="e2a68-102">'ReDim' cannot change the number of dimensions</span></span>
<span data-ttu-id="e2a68-103">Un'operazione tenta di usare l'istruzione `ReDim` per modificare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="e2a68-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="e2a68-104">`ReDim` può modificare la grandezza di una o più dimensioni di una matrice che è già stata dichiarata formalmente, ma non può modificare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="e2a68-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e2a68-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e2a68-105">To correct this error</span></span>  
  
-   <span data-ttu-id="e2a68-106">Assicurarsi di voler modificare il numero di dimensioni anziché la grandezza delle dimensioni della matrice e, se possibile, usare `Dim` per dichiarare una nuova matrice con il numero di dimensioni desiderato.</span><span class="sxs-lookup"><span data-stu-id="e2a68-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2a68-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2a68-107">See also</span></span>

- [<span data-ttu-id="e2a68-108">Matrici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2a68-108">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="e2a68-109">Dimensioni di matrice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2a68-109">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="e2a68-110">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="e2a68-110">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="e2a68-111">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="e2a68-111">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
