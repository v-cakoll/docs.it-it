---
title: Le espressioni lambda non sono valide nella prima espressione di un'istruzione 'Select Case'
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: d56515093020a4c987d132491957ce6db9e21683
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287794"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a><span data-ttu-id="ba4c9-102">Le espressioni lambda non sono valide nella prima espressione di un'istruzione 'Select Case'</span><span class="sxs-lookup"><span data-stu-id="ba4c9-102">Lambda expressions are not valid in the first expression of a 'Select Case' statement</span></span>
<span data-ttu-id="ba4c9-103">È possibile usare un'espressione lambda per l'espressione di test in un `Select Case` istruzione.</span><span class="sxs-lookup"><span data-stu-id="ba4c9-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="ba4c9-104">Le definizioni delle espressioni lambda restituiscono le funzioni e l'espressione di test di un `Select Case` istruzione deve essere un tipo di dati elementare.</span><span class="sxs-lookup"><span data-stu-id="ba4c9-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="ba4c9-105">Il codice seguente causa questo errore:</span><span class="sxs-lookup"><span data-stu-id="ba4c9-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="ba4c9-106">**ID errore:** BC36635</span><span class="sxs-lookup"><span data-stu-id="ba4c9-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ba4c9-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ba4c9-107">To correct this error</span></span>  
  
-   <span data-ttu-id="ba4c9-108">Esaminare il codice per determinare se funziona una costruzione condizionale diversa, ad esempio un'istruzione `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="ba4c9-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
-   <span data-ttu-id="ba4c9-109">Se si intende chiamare la funzione, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ba4c9-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba4c9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba4c9-110">See also</span></span>
- [<span data-ttu-id="ba4c9-111">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="ba4c9-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="ba4c9-112">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="ba4c9-112">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="ba4c9-113">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="ba4c9-113">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
