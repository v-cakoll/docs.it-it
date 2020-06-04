---
title: Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 46ec7ae452d4f8259d0f8ca3a896d1b29151ed61
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84376742"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="ac605-102">Impossibile completare l'operazione. La directory di destinazione è una sottodirectory della directory di origine</span><span class="sxs-lookup"><span data-stu-id="ac605-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="ac605-103">Un'operazione ciclica non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ac605-103">A cyclic operation has failed.</span></span> <span data-ttu-id="ac605-104">Queste operazioni sono cicliche e quindi non possono essere completate.</span><span class="sxs-lookup"><span data-stu-id="ac605-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="ac605-105">Ad esempio, un oggetto A potrebbe provare a ereditare dall'oggetto B, che a sua volta eredita dall'oggetto A.</span><span class="sxs-lookup"><span data-stu-id="ac605-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ac605-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ac605-106">To correct this error</span></span>  
  
- <span data-ttu-id="ac605-107">Quando si eredita, assicurarsi che non siano presenti riferimenti ciclici.</span><span class="sxs-lookup"><span data-stu-id="ac605-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac605-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac605-108">See also</span></span>

- [<span data-ttu-id="ac605-109">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="ac605-109">Error Types</span></span>](../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="ac605-110">Usare i punti di interruzione nel debugger di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ac605-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
