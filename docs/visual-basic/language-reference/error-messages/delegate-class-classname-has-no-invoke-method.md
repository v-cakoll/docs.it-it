---
title: La classe delegata &#39; &lt;classname&gt; &#39; non contiene alcun metodo Invoke, un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: cc1abba46224772e733780800dd104dfc7ebe9ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588830"
---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="f9200-102">La classe delegata &#39; &lt;classname&gt; &#39; non contiene alcun metodo Invoke, un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo</span><span class="sxs-lookup"><span data-stu-id="f9200-102">Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="f9200-103">Una chiamata a `Invoke` tramite un delegato non è riuscita perché `Invoke` non è implementata nella classe delegata.</span><span class="sxs-lookup"><span data-stu-id="f9200-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="f9200-104">**ID errore:** BC30220</span><span class="sxs-lookup"><span data-stu-id="f9200-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f9200-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f9200-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="f9200-106">Verificare che sia stata creata un'istanza della classe delegato con un `Dim` istruzione e una stored procedure è stata assegnata all'istanza del delegato con il `AddressOf` operatore.</span><span class="sxs-lookup"><span data-stu-id="f9200-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="f9200-107">Individuare il codice che implementa la classe delegata e assicurarsi che implementa il `Invoke` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f9200-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9200-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9200-108">See Also</span></span>  
 [<span data-ttu-id="f9200-109">Delegati</span><span class="sxs-lookup"><span data-stu-id="f9200-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="f9200-110">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="f9200-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="f9200-111">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="f9200-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="f9200-112">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="f9200-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
