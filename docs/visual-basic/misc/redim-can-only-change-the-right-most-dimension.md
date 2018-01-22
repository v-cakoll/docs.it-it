---
title: "&#39; ReDim &#39; può modificare solo la dimensione più a destra"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 752e0e54c48b3b348a477787e5e911f1b1777667
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a><span data-ttu-id="47772-102">&#39; ReDim &#39; può modificare solo la dimensione più a destra</span><span class="sxs-lookup"><span data-stu-id="47772-102">&#39;ReDim&#39; can only change the right-most dimension</span></span>
<span data-ttu-id="47772-103">Un'istruzione `ReDim` ha tentato di usare la parola chiave `Preserve` per modificare una dimensione di una matrice che non è l'ultima dimensione.</span><span class="sxs-lookup"><span data-stu-id="47772-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="47772-104">Quando si usa `Preserve`, si può ridimensionare solo l'ultima dimensione di una matrice.</span><span class="sxs-lookup"><span data-stu-id="47772-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="47772-105">Per tutte le altre, è necessario specificare le stesse dimensioni di una matrice esistente.</span><span class="sxs-lookup"><span data-stu-id="47772-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="47772-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="47772-106">To correct this error</span></span>  
  
-   <span data-ttu-id="47772-107">Rimuovere la parola chiave `Preserve` .</span><span class="sxs-lookup"><span data-stu-id="47772-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47772-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47772-108">See Also</span></span>  
 [<span data-ttu-id="47772-109">Matrici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47772-109">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="47772-110">Dimensioni di matrice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47772-110">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="47772-111">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="47772-111">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="47772-112">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="47772-112">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="47772-113">Preserve - eliminazione</span><span class="sxs-lookup"><span data-stu-id="47772-113">Preserve - delete</span></span>](http://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
