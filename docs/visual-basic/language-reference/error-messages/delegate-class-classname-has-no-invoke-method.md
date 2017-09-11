---
title: "Classe delegata&lt;classname&gt;&quot; dispone di alcun metodo Invoke, in modo da un&quot;espressione di questo tipo non può essere la destinazione di una chiamata al metodo | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30220
- bc30220
dev_langs:
- VB
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 54cd62bc2b4cafa89873728ba4e5b31c46f1aab1
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="delegate-class-39ltclassnamegt39-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="c4250-102">Classe delegata&lt;classname&gt;' dispone di alcun metodo Invoke, in modo da un'espressione di questo tipo non può essere la destinazione di una chiamata al metodo</span><span class="sxs-lookup"><span data-stu-id="c4250-102">Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="c4250-103">Una chiamata a `Invoke` tramite un delegato non è riuscito perché `Invoke` non è implementata nella classe delegata.</span><span class="sxs-lookup"><span data-stu-id="c4250-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="c4250-104">**ID errore:** BC30220</span><span class="sxs-lookup"><span data-stu-id="c4250-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c4250-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c4250-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="c4250-106">Assicurarsi che sia stata creata un'istanza della classe delegato con un `Dim` istruzione e che sia stata assegnata una routine per l'istanza del delegato con il `AddressOf` operatore.</span><span class="sxs-lookup"><span data-stu-id="c4250-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="c4250-107">Individuare il codice che implementa la classe delegata e controllare che implementi la `Invoke` procedura.</span><span class="sxs-lookup"><span data-stu-id="c4250-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4250-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4250-108">See Also</span></span>  
 <span data-ttu-id="c4250-109">[Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="c4250-109">[Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="c4250-110"> [Delegate (istruzione)](../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c4250-110"> [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="c4250-111"> [AddressOf (operatore)](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="c4250-111"> [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="c4250-112"> [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="c4250-112"> [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>
