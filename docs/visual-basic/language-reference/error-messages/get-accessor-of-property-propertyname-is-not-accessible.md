---
title: La funzione di accesso 'Get' della proprietà '<propertyname>' non è accessibile
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: cb953671e624d5b9170aa0b3a9dd80c7ba8337e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402914"
---
# <a name="get-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="590b4-102">La funzione di accesso 'Get' della proprietà '\<propertyname>' non è accessibile</span><span class="sxs-lookup"><span data-stu-id="590b4-102">'Get' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="590b4-103">Un'istruzione tenta di recuperare il valore di una proprietà quando non ha accesso alla routine della proprietà `Get` .</span><span class="sxs-lookup"><span data-stu-id="590b4-103">A statement attempts to retrieve the value of a property when it does not have access to the property's `Get` procedure.</span></span>  
  
 <span data-ttu-id="590b4-104">Se l' [istruzione Get](../statements/get-statement.md) è contrassegnata con un livello di accesso più restrittivo rispetto alla relativa [istruzione Property](../statements/property-statement.md), un tentativo di leggere il valore della proprietà potrebbe non riuscire nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="590b4-104">If the [Get Statement](../statements/get-statement.md) is marked with a more restrictive access level than its [Property Statement](../statements/property-statement.md), an attempt to read the property value could fail in the following cases:</span></span>  
  
- <span data-ttu-id="590b4-105">L' `Get` istruzione è contrassegnata come [privata](../modifiers/private.md) e il codice chiamante è all'esterno della classe o della struttura in cui è definita la proprietà.</span><span class="sxs-lookup"><span data-stu-id="590b4-105">The `Get` statement is marked [Private](../modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
- <span data-ttu-id="590b4-106">L' `Get` istruzione è contrassegnata come [protetta](../modifiers/protected.md) e il codice chiamante non si trova nella classe o nella struttura in cui è definita la proprietà, né in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="590b4-106">The `Get` statement is marked [Protected](../modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
- <span data-ttu-id="590b4-107">L' `Get` istruzione è contrassegnata come [Friend](../modifiers/friend.md) e il codice chiamante non si trova nello stesso assembly in cui è definita la proprietà.</span><span class="sxs-lookup"><span data-stu-id="590b4-107">The `Get` statement is marked [Friend](../modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="590b4-108">**ID errore:** BC31103</span><span class="sxs-lookup"><span data-stu-id="590b4-108">**Error ID:** BC31103</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="590b4-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="590b4-109">To correct this error</span></span>  
  
- <span data-ttu-id="590b4-110">Se si ha il controllo del codice sorgente che definisce la proprietà, provare a dichiarare la `Get` routine con lo stesso livello di accesso della proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="590b4-110">If you have control of the source code defining the property, consider declaring the `Get` procedure with the same access level as the property itself.</span></span>  
  
- <span data-ttu-id="590b4-111">Se non si ha il controllo del codice sorgente che definisce la proprietà o se è necessario limitare il `Get` livello di accesso della routine più della proprietà stessa, provare a spostare l'istruzione che legge il valore della proprietà in un'area di codice con un accesso migliore alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="590b4-111">If you do not have control of the source code defining the property, or you must restrict the `Get` procedure access level more than the property itself, try to move the statement that reads the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="590b4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="590b4-112">See also</span></span>

- [<span data-ttu-id="590b4-113">Routine Property</span><span class="sxs-lookup"><span data-stu-id="590b4-113">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="590b4-114">Procedura: dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="590b4-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
