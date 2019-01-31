---
title: La classe delegata '<classname>' non contiene un metodo Invoke. Un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 8339d038f845b8568f31f3068a98ccccf580aeae
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286650"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="469e3-102">Classe delegata\<NomeClasse >' non contiene alcun metodo Invoke, in modo che un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo</span><span class="sxs-lookup"><span data-stu-id="469e3-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="469e3-103">Una chiamata a `Invoke` attraverso un delegato non è riuscita perché `Invoke` non è implementato nella classe delegata.</span><span class="sxs-lookup"><span data-stu-id="469e3-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="469e3-104">**ID errore:** BC30220</span><span class="sxs-lookup"><span data-stu-id="469e3-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="469e3-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="469e3-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="469e3-106">Verificare che sia stata creata un'istanza della classe delegata con un `Dim` istruzione e che una routine è stata assegnata all'istanza del delegato con il `AddressOf` operatore.</span><span class="sxs-lookup"><span data-stu-id="469e3-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="469e3-107">Individuare il codice che implementa la classe delegate e assicurarsi che implementa il `Invoke` procedure.</span><span class="sxs-lookup"><span data-stu-id="469e3-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="469e3-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="469e3-108">See also</span></span>
- [<span data-ttu-id="469e3-109">Delegati</span><span class="sxs-lookup"><span data-stu-id="469e3-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="469e3-110">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="469e3-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="469e3-111">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="469e3-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="469e3-112">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="469e3-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
