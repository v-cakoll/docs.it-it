---
title: La funzione di accesso 'Set' della proprietà '<propertyname>' non è accessibile
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 077533a5b1fe241b61ded9516ad8f450d7dbbf5e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400344"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="5f910-102">La funzione di accesso 'Set' della proprietà '\<propertyname>' non è accessibile</span><span class="sxs-lookup"><span data-stu-id="5f910-102">'Set' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="5f910-103">Un'istruzione tenta di archiviare il valore di una proprietà quando non ha accesso alla routine della proprietà `Set` .</span><span class="sxs-lookup"><span data-stu-id="5f910-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="5f910-104">Se l' [istruzione set](../statements/set-statement.md) è contrassegnata con un livello di accesso più restrittivo rispetto alla relativa [istruzione Property](../statements/property-statement.md), un tentativo di impostare il valore della proprietà potrebbe non riuscire nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f910-104">If the [Set Statement](../statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
- <span data-ttu-id="5f910-105">L' `Set` istruzione è contrassegnata come [privata](../modifiers/private.md) e il codice chiamante è all'esterno della classe o della struttura in cui è definita la proprietà.</span><span class="sxs-lookup"><span data-stu-id="5f910-105">The `Set` statement is marked [Private](../modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
- <span data-ttu-id="5f910-106">L' `Set` istruzione è contrassegnata come [protetta](../modifiers/protected.md) e il codice chiamante non si trova nella classe o nella struttura in cui è definita la proprietà, né in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="5f910-106">The `Set` statement is marked [Protected](../modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
- <span data-ttu-id="5f910-107">L' `Set` istruzione è contrassegnata come [Friend](../modifiers/friend.md) e il codice chiamante non si trova nello stesso assembly in cui è definita la proprietà.</span><span class="sxs-lookup"><span data-stu-id="5f910-107">The `Set` statement is marked [Friend](../modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="5f910-108">**ID errore:** BC31102</span><span class="sxs-lookup"><span data-stu-id="5f910-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5f910-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5f910-109">To correct this error</span></span>  
  
- <span data-ttu-id="5f910-110">Se si ha il controllo del codice sorgente che definisce la proprietà, provare a dichiarare la `Set` routine con lo stesso livello di accesso della proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="5f910-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
- <span data-ttu-id="5f910-111">Se non si ha il controllo del codice sorgente che definisce la proprietà o se è necessario limitare il `Set` livello di accesso della routine più della proprietà stessa, provare a spostare l'istruzione che imposta il valore della proprietà su un'area di codice che dispone di un accesso migliore alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="5f910-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f910-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f910-112">See also</span></span>

- [<span data-ttu-id="5f910-113">Routine Property</span><span class="sxs-lookup"><span data-stu-id="5f910-113">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="5f910-114">Procedura: dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="5f910-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
