---
title: "'<membername>' non può esporre il tipo '<typename>' all'esterno del progetto mediante <containertype> '<containertypename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 729a9f385d94412469d318cb804d216827eeb0fd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397285"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="64ce8-102">'\<membername>' non può esporre il tipo '\<typename>' all'esterno del progetto mediante \<containertype> '\<containertypename>'</span><span class="sxs-lookup"><span data-stu-id="64ce8-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="64ce8-103">Una variabile, un parametro di routine o un valore restituito dalla funzione viene esposto all'esterno del relativo contenitore, ma viene dichiarato come un tipo che non deve essere esposto all'esterno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="64ce8-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="64ce8-104">Il codice di scheletro seguente mostra una situazione che genera questo errore.</span><span class="sxs-lookup"><span data-stu-id="64ce8-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="64ce8-105">Un tipo dichiarato,, `Protected` `Friend` `Protected Friend` o `Private` è progettato per avere accesso limitato al di fuori del contesto di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="64ce8-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="64ce8-106">Il suo utilizzo come tipo di dati di una variabile con accesso meno limitato comporterebbe la sconfitta di questo scopo.</span><span class="sxs-lookup"><span data-stu-id="64ce8-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="64ce8-107">Nel codice di scheletro precedente, `exposedVar` è `Public` ed esporrebbe `privateClass` a codice che non dovrebbe avere accesso a tale codice.</span><span class="sxs-lookup"><span data-stu-id="64ce8-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="64ce8-108">**ID errore:** BC30909</span><span class="sxs-lookup"><span data-stu-id="64ce8-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="64ce8-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="64ce8-109">To correct this error</span></span>  
  
- <span data-ttu-id="64ce8-110">Modificare il livello di accesso della variabile, il parametro di routine o la funzione Return in modo che sia almeno restrittivo come livello di accesso del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="64ce8-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ce8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64ce8-111">See also</span></span>

- [<span data-ttu-id="64ce8-112">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="64ce8-112">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
