---
title: L'oggetto o la classe non supporta il set di eventi
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: bc75e031c2d05bea3aa64774a9d3817756e51e8b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409361"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="6c712-102">L'oggetto o la classe non supporta il set di eventi</span><span class="sxs-lookup"><span data-stu-id="6c712-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="6c712-103">Si è provato a usare una `WithEvents` variabile con un componente che non può funzionare come origine evento per il set di eventi specificato.</span><span class="sxs-lookup"><span data-stu-id="6c712-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="6c712-104">Si desidera, ad esempio, affondare gli eventi di un oggetto, quindi creare un altro oggetto che `Implements` il primo oggetto.</span><span class="sxs-lookup"><span data-stu-id="6c712-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="6c712-105">Sebbene si possa pensare che è possibile affondare gli eventi dall'oggetto implementato, questo non è sempre il caso.</span><span class="sxs-lookup"><span data-stu-id="6c712-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="6c712-106">`Implements`implementa solo un'interfaccia per metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="6c712-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="6c712-107">`WithEvents`non è supportato per private `UserControls` , perché le informazioni sul tipo necessarie per generare l'oggetto `ObjectEvent` non sono disponibili in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6c712-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6c712-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="6c712-108">To correct this error</span></span>  
  
1. <span data-ttu-id="6c712-109">Non è possibile eseguire il sink di eventi per un componente che non è un evento di origine.</span><span class="sxs-lookup"><span data-stu-id="6c712-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c712-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c712-110">See also</span></span>

- [<span data-ttu-id="6c712-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="6c712-111">WithEvents</span></span>](../modifiers/withevents.md)
- [<span data-ttu-id="6c712-112">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="6c712-112">Implements Statement</span></span>](../statements/implements-statement.md)
