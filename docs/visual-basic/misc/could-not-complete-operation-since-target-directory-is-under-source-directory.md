---
title: Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: f53ad664b341d4db803dee1f0f008c3918d13d93
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "58039435"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="9b2ba-102">Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine</span><span class="sxs-lookup"><span data-stu-id="9b2ba-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="9b2ba-103">Un'operazione ciclica non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="9b2ba-103">A cyclic operation has failed.</span></span> <span data-ttu-id="9b2ba-104">Queste operazioni sono cicliche e quindi non possono essere completate.</span><span class="sxs-lookup"><span data-stu-id="9b2ba-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="9b2ba-105">Ad esempio, un oggetto A potrebbe provare a ereditare dall'oggetto B, che a sua volta eredita dall'oggetto A.</span><span class="sxs-lookup"><span data-stu-id="9b2ba-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9b2ba-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="9b2ba-106">To correct this error</span></span>  
  
-   <span data-ttu-id="9b2ba-107">Quando si eredita, assicurarsi che non siano presenti riferimenti ciclici.</span><span class="sxs-lookup"><span data-stu-id="9b2ba-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b2ba-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b2ba-108">See also</span></span>

- [<span data-ttu-id="9b2ba-109">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="9b2ba-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="9b2ba-110">Usare i punti di interruzione nel debugger di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9b2ba-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
