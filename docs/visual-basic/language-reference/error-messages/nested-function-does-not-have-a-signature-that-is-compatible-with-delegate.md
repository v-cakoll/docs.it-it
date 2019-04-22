---
title: La funzione annidata non dispone di una firma compatibile con il delegato '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 04eae6d2c6d64e8a0f46ae3c2801a7eb6d893dca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58822288"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="b792d-102">Funzione annidata non ha una firma compatibile con il delegato '\<NomeDelegato >'</span><span class="sxs-lookup"><span data-stu-id="b792d-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>
<span data-ttu-id="b792d-103">Un'espressione lambda assegnata a un delegato che ha una firma compatibile.</span><span class="sxs-lookup"><span data-stu-id="b792d-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="b792d-104">Nel codice seguente, ad esempio, è consigliabile delegare `Del` ha due parametri di tipo integer.</span><span class="sxs-lookup"><span data-stu-id="b792d-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 <span data-ttu-id="b792d-105">L'errore viene generato se un'espressione lambda con un argomento è dichiarata come tipo `Del`:</span><span class="sxs-lookup"><span data-stu-id="b792d-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 <span data-ttu-id="b792d-106">**ID errore:** BC36532</span><span class="sxs-lookup"><span data-stu-id="b792d-106">**Error ID:** BC36532</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b792d-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b792d-107">To correct this error</span></span>  
  
-   <span data-ttu-id="b792d-108">Modificare la definizione del delegato o l'espressione lambda assegnata in modo che le firme sono compatibili.</span><span class="sxs-lookup"><span data-stu-id="b792d-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b792d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b792d-109">See also</span></span>

- [<span data-ttu-id="b792d-110">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="b792d-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="b792d-111">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="b792d-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
