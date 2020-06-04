---
title: "'ReDim' non può modificare il numero di dimensioni"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: b2404927c2faf30d1d058d2163fd5d67e1a52e1e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358167"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="5144b-102">'ReDim' non può modificare il numero di dimensioni</span><span class="sxs-lookup"><span data-stu-id="5144b-102">'ReDim' cannot change the number of dimensions</span></span>
<span data-ttu-id="5144b-103">Un'operazione tenta di usare l'istruzione `ReDim` per modificare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="5144b-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="5144b-104">`ReDim` può modificare la grandezza di una o più dimensioni di una matrice che è già stata dichiarata formalmente, ma non può modificare il numero di dimensioni di una matrice.</span><span class="sxs-lookup"><span data-stu-id="5144b-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5144b-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5144b-105">To correct this error</span></span>  
  
- <span data-ttu-id="5144b-106">Assicurarsi di voler modificare il numero di dimensioni anziché la grandezza delle dimensioni della matrice e, se possibile, usare `Dim` per dichiarare una nuova matrice con il numero di dimensioni desiderato.</span><span class="sxs-lookup"><span data-stu-id="5144b-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5144b-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5144b-107">See also</span></span>

- [<span data-ttu-id="5144b-108">Matrici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5144b-108">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="5144b-109">Dimensioni della matrice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5144b-109">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="5144b-110">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="5144b-110">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="5144b-111">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="5144b-111">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)
