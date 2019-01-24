---
title: L'oggetto o la classe non supporta il set di eventi
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: 82f3acff1730b4b31b0118a46376825c8807e1da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552151"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="bd4de-102">L'oggetto o la classe non supporta il set di eventi</span><span class="sxs-lookup"><span data-stu-id="bd4de-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="bd4de-103">Si è provato a usare un `WithEvents` variabile con un componente che non può fungere da un'origine evento per il set specificato di eventi.</span><span class="sxs-lookup"><span data-stu-id="bd4de-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="bd4de-104">Ad esempio, si voleva il sink degli eventi di un oggetto, quindi creare un altro oggetto che `Implements` il primo oggetto.</span><span class="sxs-lookup"><span data-stu-id="bd4de-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="bd4de-105">Anche se si potrebbe pensare che è possibile effettuare il sink gli eventi dall'oggetto implementato, questo non è sempre il caso.</span><span class="sxs-lookup"><span data-stu-id="bd4de-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="bd4de-106">`Implements` implementa solo un'interfaccia per i metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="bd4de-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="bd4de-107">`WithEvents` non è supportata per privati `UserControls`, perché le informazioni sul tipo necessarie generare il `ObjectEvent` non è disponibile in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bd4de-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bd4de-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="bd4de-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="bd4de-109">È possibile effettuare il sink degli eventi per un componente che non sia l'origine eventi.</span><span class="sxs-lookup"><span data-stu-id="bd4de-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd4de-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd4de-110">See also</span></span>
- [<span data-ttu-id="bd4de-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="bd4de-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="bd4de-112">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="bd4de-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
