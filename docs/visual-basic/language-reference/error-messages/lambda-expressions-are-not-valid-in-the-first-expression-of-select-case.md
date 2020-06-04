---
title: Le espressioni lambda non sono valide nella prima espressione di un'istruzione 'Select Case'
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 08f7cd9dd95a10cad0df6539ba43122495347bae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397363"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a><span data-ttu-id="3d829-102">Le espressioni lambda non sono valide nella prima espressione di un'istruzione 'Select Case'</span><span class="sxs-lookup"><span data-stu-id="3d829-102">Lambda expressions are not valid in the first expression of a 'Select Case' statement</span></span>
<span data-ttu-id="3d829-103">Non è possibile usare un'espressione lambda per l'espressione di test in un' `Select Case` istruzione.</span><span class="sxs-lookup"><span data-stu-id="3d829-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="3d829-104">Le definizioni delle espressioni lambda restituiscono funzioni e l'espressione di test di un' `Select Case` istruzione deve essere un tipo di dati elementare.</span><span class="sxs-lookup"><span data-stu-id="3d829-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="3d829-105">Il codice seguente causa questo errore:</span><span class="sxs-lookup"><span data-stu-id="3d829-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="3d829-106">**ID errore:** BC36635</span><span class="sxs-lookup"><span data-stu-id="3d829-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3d829-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3d829-107">To correct this error</span></span>  
  
- <span data-ttu-id="3d829-108">Esaminare il codice per determinare se funziona una costruzione condizionale diversa, ad esempio un'istruzione `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="3d829-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
- <span data-ttu-id="3d829-109">È possibile che si abbia intenzione di chiamare la funzione, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="3d829-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d829-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d829-110">See also</span></span>

- [<span data-ttu-id="3d829-111">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="3d829-111">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="3d829-112">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="3d829-112">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="3d829-113">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="3d829-113">Select...Case Statement</span></span>](../statements/select-case-statement.md)
