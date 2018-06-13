---
title: L'oggetto o la classe non supporta il set di eventi
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: 4a6f1f59f43cdb351d49fbcbfd18362db888586e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593204"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="72f0c-102">L'oggetto o la classe non supporta il set di eventi</span><span class="sxs-lookup"><span data-stu-id="72f0c-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="72f0c-103">Si è tentato di utilizzare un `WithEvents` variabile con un componente che non può fungere da un'origine evento per il set specificato di eventi.</span><span class="sxs-lookup"><span data-stu-id="72f0c-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="72f0c-104">Ad esempio, si desidera elaborare gli eventi di un oggetto, quindi creare un altro oggetto che `Implements` il primo oggetto.</span><span class="sxs-lookup"><span data-stu-id="72f0c-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="72f0c-105">Sebbene si pensi che è stato possibile sink degli eventi dall'oggetto implementato, questo non è sempre il caso.</span><span class="sxs-lookup"><span data-stu-id="72f0c-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="72f0c-106">`Implements` implementa solo un'interfaccia per i metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="72f0c-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="72f0c-107">`WithEvents` non è supportata per private `UserControls`, perché le informazioni sul tipo necessarie generare il `ObjectEvent` non è disponibile in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="72f0c-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72f0c-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="72f0c-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="72f0c-109">È Impossibile sink di eventi per un componente che non sia l'origine eventi.</span><span class="sxs-lookup"><span data-stu-id="72f0c-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f0c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72f0c-110">See Also</span></span>  
 [<span data-ttu-id="72f0c-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="72f0c-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [<span data-ttu-id="72f0c-112">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="72f0c-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
