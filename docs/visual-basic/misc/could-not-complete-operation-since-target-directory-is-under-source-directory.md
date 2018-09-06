---
title: Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: b821034731514362a3725c390e02542b536f0a59
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43890804"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="3e090-102">Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine</span><span class="sxs-lookup"><span data-stu-id="3e090-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="3e090-103">Un'operazione ciclica non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3e090-103">A cyclic operation has failed.</span></span> <span data-ttu-id="3e090-104">Queste operazioni sono cicliche e quindi non possono essere completate.</span><span class="sxs-lookup"><span data-stu-id="3e090-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="3e090-105">Ad esempio, un oggetto A potrebbe provare a ereditare dall'oggetto B, che a sua volta eredita dall'oggetto A.</span><span class="sxs-lookup"><span data-stu-id="3e090-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3e090-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3e090-106">To correct this error</span></span>  
  
-   <span data-ttu-id="3e090-107">Quando si eredita, assicurarsi che non siano presenti riferimenti ciclici.</span><span class="sxs-lookup"><span data-stu-id="3e090-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e090-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e090-108">See Also</span></span>  
 [<span data-ttu-id="3e090-109">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="3e090-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="3e090-110">Nozioni fondamentali di debug: punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="3e090-110">Debugging Basics: Breakpoints</span></span>](https://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
