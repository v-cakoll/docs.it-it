---
title: La funzione di accesso 'Set' della proprietà '<propertyname>' non è accessibile
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 3bc50d6762998ca5d8f445d84c8b698c9f46436f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055147"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="b26ae-102">'Set' della funzione di accesso della proprietà '\<NomeProprietà >' non è accessibile</span><span class="sxs-lookup"><span data-stu-id="b26ae-102">'Set' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="b26ae-103">Un'istruzione tenta di archiviare il valore di una proprietà quando non ha accesso alla proprietà `Set` procedure.</span><span class="sxs-lookup"><span data-stu-id="b26ae-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="b26ae-104">Se il [impostare l'istruzione](../../../visual-basic/language-reference/statements/set-statement.md) è contrassegnata con un accesso più restrittivo livello relativo [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), un tentativo di impostare il valore della proprietà potrebbe non riuscire nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b26ae-104">If the [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
- <span data-ttu-id="b26ae-105">Il `Set` istruzione è contrassegnata [Private](../../../visual-basic/language-reference/modifiers/private.md) e il codice chiamante è di fuori della classe o struttura in cui la proprietà è definita.</span><span class="sxs-lookup"><span data-stu-id="b26ae-105">The `Set` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
- <span data-ttu-id="b26ae-106">Il `Set` istruzione è contrassegnata [Protected](../../../visual-basic/language-reference/modifiers/protected.md) e il codice chiamante non nella classe o struttura in cui la proprietà è definita, né in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="b26ae-106">The `Set` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
- <span data-ttu-id="b26ae-107">Il `Set` istruzione è contrassegnata [Friend](../../../visual-basic/language-reference/modifiers/friend.md) e il codice chiamante non è presente nello stesso assembly in cui la proprietà è definita.</span><span class="sxs-lookup"><span data-stu-id="b26ae-107">The `Set` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="b26ae-108">**ID errore:** BC31102</span><span class="sxs-lookup"><span data-stu-id="b26ae-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b26ae-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b26ae-109">To correct this error</span></span>  
  
- <span data-ttu-id="b26ae-110">Se si ha il controllo del codice sorgente che definisce la proprietà, si consideri la dichiarazione di `Set` procedure con lo stesso livello di accesso della proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="b26ae-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
- <span data-ttu-id="b26ae-111">Se non si ha il controllo del codice sorgente che definisce la proprietà o se è necessario limitare il `Set` procedure più la proprietà stessa, provare a spostare l'istruzione che imposta il valore della proprietà in un'area di codice che ha un accesso migliore a livello di accesso di proprietà.</span><span class="sxs-lookup"><span data-stu-id="b26ae-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b26ae-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b26ae-112">See also</span></span>

- [<span data-ttu-id="b26ae-113">Routine Property</span><span class="sxs-lookup"><span data-stu-id="b26ae-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="b26ae-114">Procedura: Dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="b26ae-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
