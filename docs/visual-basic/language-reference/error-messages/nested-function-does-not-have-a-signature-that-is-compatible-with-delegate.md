---
title: Funzione annidata non ha una firma compatibile con il delegato &#39; &lt;NomeDelegato&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: abfda4ee6064ec9ea54b8a3c383d10f8263a1458
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506407"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a><span data-ttu-id="be052-102">Funzione annidata non ha una firma compatibile con il delegato &#39; &lt;NomeDelegato&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="be052-102">Nested function does not have a signature that is compatible with delegate &#39;&lt;delegatename&gt;&#39;</span></span>
<span data-ttu-id="be052-103">Un'espressione lambda assegnata a un delegato che ha una firma compatibile.</span><span class="sxs-lookup"><span data-stu-id="be052-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="be052-104">Nel codice seguente, ad esempio, è consigliabile delegare `Del` ha due parametri di tipo integer.</span><span class="sxs-lookup"><span data-stu-id="be052-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 <span data-ttu-id="be052-105">L'errore viene generato se un'espressione lambda con un argomento è dichiarata come tipo `Del`:</span><span class="sxs-lookup"><span data-stu-id="be052-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 <span data-ttu-id="be052-106">**ID errore:** BC36532</span><span class="sxs-lookup"><span data-stu-id="be052-106">**Error ID:** BC36532</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="be052-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="be052-107">To correct this error</span></span>  
  
-   <span data-ttu-id="be052-108">Modificare la definizione del delegato o l'espressione lambda assegnata in modo che le firme sono compatibili.</span><span class="sxs-lookup"><span data-stu-id="be052-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be052-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be052-109">See also</span></span>
- [<span data-ttu-id="be052-110">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="be052-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="be052-111">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="be052-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
