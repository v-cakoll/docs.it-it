---
title: '&#39;ReDim&#39; non è possibile modificare il numero di dimensioni'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: bfd4096141833b85a2126340ef549e1e1d1f8e3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33640381"
---
# <a name="39redim39-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="ae2dd-102">&#39;ReDim&#39; non è possibile modificare il numero di dimensioni</span><span class="sxs-lookup"><span data-stu-id="ae2dd-102">&#39;ReDim&#39; cannot change the number of dimensions</span></span>
<span data-ttu-id="ae2dd-103">Un'operazione tenta di usare l'istruzione `ReDim` per modificare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="ae2dd-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="ae2dd-104">`ReDim` può modificare la grandezza di una o più dimensioni di una matrice che è già stata dichiarata formalmente, ma non può modificare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="ae2dd-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ae2dd-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ae2dd-105">To correct this error</span></span>  
  
-   <span data-ttu-id="ae2dd-106">Assicurarsi di voler modificare il numero di dimensioni anziché la grandezza delle dimensioni della matrice e, se possibile, usare `Dim` per dichiarare una nuova matrice con il numero di dimensioni desiderato.</span><span class="sxs-lookup"><span data-stu-id="ae2dd-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae2dd-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae2dd-107">See Also</span></span>  
 [<span data-ttu-id="ae2dd-108">Matrici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae2dd-108">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="ae2dd-109">Dimensioni della matrice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae2dd-109">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="ae2dd-110">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="ae2dd-110">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="ae2dd-111">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="ae2dd-111">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
