---
title: "'<membername>' non può esporre il tipo '<typename>' all'esterno del progetto mediante <containertype> '<containertypename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 03767501488a395073f925e27adea439751c0de6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265064"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="2ba78-102">'\<nomeMembro >' non può esporre il tipo '\<nomeTipo >' all'esterno del progetto mediante \<containertype > '\<containertypename >'</span><span class="sxs-lookup"><span data-stu-id="2ba78-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="2ba78-103">Una variabile, parametro di routine o restituito dalla funzione viene esposto all'esterno del relativo contenitore, ma viene dichiarato come un tipo che non deve essere esposto all'esterno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="2ba78-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="2ba78-104">Lo scheletro di codice seguente viene illustrata una situazione che genera l'errore.</span><span class="sxs-lookup"><span data-stu-id="2ba78-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="2ba78-105">Un tipo dichiarato `Protected`, `Friend`, `Protected Friend`, o `Private` deve avere accesso all'esterno del contesto di dichiarazione limitato.</span><span class="sxs-lookup"><span data-stu-id="2ba78-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="2ba78-106">Per utilizzarlo come i dati di tipo di una variabile con meno restrizioni accesso vanificherebbe lo scopo.</span><span class="sxs-lookup"><span data-stu-id="2ba78-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="2ba78-107">Nel codice precedente, `exposedVar` viene `Public` e consente di esporre `privateClass` al codice che non dovrebbe avere accesso a esso.</span><span class="sxs-lookup"><span data-stu-id="2ba78-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="2ba78-108">**ID errore:** BC30909</span><span class="sxs-lookup"><span data-stu-id="2ba78-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2ba78-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2ba78-109">To correct this error</span></span>  
  
-   <span data-ttu-id="2ba78-110">Modifica il livello di accesso della variabile, parametro di routine o funzione, tornare a essere restrittivi almeno quanto il livello di accesso del relativo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="2ba78-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba78-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ba78-111">See also</span></span>
- [<span data-ttu-id="2ba78-112">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2ba78-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
