---
title: La classe delegata '<classname>' non contiene un metodo Invoke. Un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 27be97ba2930791bcb9012c824bc418a0089b037
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409712"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="1116c-102">La classe delegata '\<classname>' non contiene un metodo Invoke. Un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo</span><span class="sxs-lookup"><span data-stu-id="1116c-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="1116c-103">Una chiamata a `Invoke` tramite un delegato non è riuscita perché `Invoke` non è implementato nella classe delegata.</span><span class="sxs-lookup"><span data-stu-id="1116c-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="1116c-104">**ID errore:** BC30220</span><span class="sxs-lookup"><span data-stu-id="1116c-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1116c-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="1116c-105">To correct this error</span></span>  
  
1. <span data-ttu-id="1116c-106">Assicurarsi che un'istanza della classe delegata sia stata creata con un' `Dim` istruzione e che una routine sia stata assegnata all'istanza del delegato con l' `AddressOf` operatore.</span><span class="sxs-lookup"><span data-stu-id="1116c-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2. <span data-ttu-id="1116c-107">Individuare il codice che implementa la classe delegata e assicurarsi che implementi la `Invoke` procedura.</span><span class="sxs-lookup"><span data-stu-id="1116c-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1116c-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1116c-108">See also</span></span>

- [<span data-ttu-id="1116c-109">Delegati</span><span class="sxs-lookup"><span data-stu-id="1116c-109">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="1116c-110">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="1116c-110">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="1116c-111">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="1116c-111">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="1116c-112">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="1116c-112">Dim Statement</span></span>](../statements/dim-statement.md)
