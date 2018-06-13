---
title: Funzione annidata non dispone di una firma compatibile con il delegato &#39; &lt;NomeDelegato&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 94c53d30ad9aea9386fbb1be3e65fa31719f7a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594471"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a><span data-ttu-id="e4330-102">Funzione annidata non dispone di una firma compatibile con il delegato &#39; &lt;NomeDelegato&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="e4330-102">Nested function does not have a signature that is compatible with delegate &#39;&lt;delegatename&gt;&#39;</span></span>
<span data-ttu-id="e4330-103">Un'espressione lambda è stata assegnata a un delegato che ha una firma compatibile.</span><span class="sxs-lookup"><span data-stu-id="e4330-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="e4330-104">Nel codice seguente, ad esempio, è consigliabile delegare `Del` presenta due parametri di tipo integer.</span><span class="sxs-lookup"><span data-stu-id="e4330-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 <span data-ttu-id="e4330-105">Se un'espressione lambda con un argomento è dichiarata come tipo, viene generato l'errore `Del`:</span><span class="sxs-lookup"><span data-stu-id="e4330-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 <span data-ttu-id="e4330-106">**ID errore:** BC36532</span><span class="sxs-lookup"><span data-stu-id="e4330-106">**Error ID:** BC36532</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e4330-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e4330-107">To correct this error</span></span>  
  
-   <span data-ttu-id="e4330-108">Modificare la definizione del delegato o l'espressione lambda assegnata in modo che le firme compatibili.</span><span class="sxs-lookup"><span data-stu-id="e4330-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4330-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4330-109">See Also</span></span>  
 [<span data-ttu-id="e4330-110">Conversione di tipo relaxed del delegato</span><span class="sxs-lookup"><span data-stu-id="e4330-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [<span data-ttu-id="e4330-111">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="e4330-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
