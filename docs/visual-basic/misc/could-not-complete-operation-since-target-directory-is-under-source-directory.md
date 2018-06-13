---
title: Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 68217023a980891200c18b5536ef902574d36257
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33638512"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="c8e1b-102">Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine</span><span class="sxs-lookup"><span data-stu-id="c8e1b-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="c8e1b-103">Un'operazione ciclica non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c8e1b-103">A cyclic operation has failed.</span></span> <span data-ttu-id="c8e1b-104">Queste operazioni sono cicliche e quindi non possono essere completate.</span><span class="sxs-lookup"><span data-stu-id="c8e1b-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="c8e1b-105">Ad esempio, un oggetto A potrebbe provare a ereditare dall'oggetto B, che a sua volta eredita dall'oggetto A.</span><span class="sxs-lookup"><span data-stu-id="c8e1b-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c8e1b-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c8e1b-106">To correct this error</span></span>  
  
-   <span data-ttu-id="c8e1b-107">Quando si eredita, assicurarsi che non siano presenti riferimenti ciclici.</span><span class="sxs-lookup"><span data-stu-id="c8e1b-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e1b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8e1b-108">See Also</span></span>  
 [<span data-ttu-id="c8e1b-109">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="c8e1b-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="c8e1b-110">Nozioni fondamentali di debug: i punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="c8e1b-110">Debugging Basics: Breakpoints</span></span>](http://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
