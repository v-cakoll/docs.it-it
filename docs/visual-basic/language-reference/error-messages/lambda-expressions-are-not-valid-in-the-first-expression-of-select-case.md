---
title: Espressioni lambda non sono valide nella prima espressione di un &#39; Selezionare i Case &#39; istruzione
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e91401d6891d4e38014bb716a337560885cf73a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a><span data-ttu-id="2d7bf-102">Espressioni lambda non sono valide nella prima espressione di un &#39; Selezionare i Case &#39; istruzione</span><span class="sxs-lookup"><span data-stu-id="2d7bf-102">Lambda expressions are not valid in the first expression of a &#39;Select Case&#39; statement</span></span>
<span data-ttu-id="2d7bf-103">Non è possibile utilizzare un'espressione lambda dell'espressione di test in un `Select Case` istruzione.</span><span class="sxs-lookup"><span data-stu-id="2d7bf-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="2d7bf-104">Le definizioni delle espressioni lambda restituiscono funzioni e l'espressione di test di un `Select Case` istruzione deve essere un tipo di dati elementare.</span><span class="sxs-lookup"><span data-stu-id="2d7bf-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="2d7bf-105">Il codice seguente causa questo errore:</span><span class="sxs-lookup"><span data-stu-id="2d7bf-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="2d7bf-106">**ID errore:** BC36635</span><span class="sxs-lookup"><span data-stu-id="2d7bf-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2d7bf-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2d7bf-107">To correct this error</span></span>  
  
-   <span data-ttu-id="2d7bf-108">Esaminare il codice per determinare se funziona una costruzione condizionale diversa, ad esempio un'istruzione `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="2d7bf-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
-   <span data-ttu-id="2d7bf-109">Se si intende chiamare la funzione, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2d7bf-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d7bf-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d7bf-110">See Also</span></span>  
 [<span data-ttu-id="2d7bf-111">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="2d7bf-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="2d7bf-112">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="2d7bf-112">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="2d7bf-113">Istruzione Select...Case</span><span class="sxs-lookup"><span data-stu-id="2d7bf-113">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
