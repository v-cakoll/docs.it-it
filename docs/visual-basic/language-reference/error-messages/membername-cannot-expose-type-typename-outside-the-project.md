---
title: '&#39; &lt;membername&gt;&#39; non può esporre il tipo &#39;&lt; TypeName&gt;&#39; di fuori del progetto mediante &lt;containertype&gt; &#39;&lt; containertypename&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd64c815286a5ffec111bcf1f68674a8e3558403
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a><span data-ttu-id="afc72-102">&#39; &lt;membername&gt;&#39; non può esporre il tipo &#39;&lt; TypeName&gt;&#39; di fuori del progetto mediante &lt;containertype&gt; &#39;&lt; containertypename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="afc72-102">&#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;</span></span>
<span data-ttu-id="afc72-103">Una variabile, parametro di routine o restituito dalla funzione viene esposto all'esterno del relativo contenitore, ma è dichiarato come un tipo che non deve essere esposti di fuori del contenitore.</span><span class="sxs-lookup"><span data-stu-id="afc72-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="afc72-104">La struttura del codice seguente viene illustrata una situazione che genera l'errore.</span><span class="sxs-lookup"><span data-stu-id="afc72-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="afc72-105">Un tipo dichiarato `Protected`, `Friend`, `Protected Friend`, o `Private` deve avere accesso all'esterno del contesto di dichiarazione limitato.</span><span class="sxs-lookup"><span data-stu-id="afc72-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="afc72-106">Utilizzarlo come dati di tipo di una variabile con accesso limitato meno vanificherebbe lo scopo.</span><span class="sxs-lookup"><span data-stu-id="afc72-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="afc72-107">Nel codice precedente, `exposedVar` è `Public` ed espone `privateClass` al codice che non deve avere accesso a esso.</span><span class="sxs-lookup"><span data-stu-id="afc72-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="afc72-108">**ID errore:** BC30909</span><span class="sxs-lookup"><span data-stu-id="afc72-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="afc72-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="afc72-109">To correct this error</span></span>  
  
-   <span data-ttu-id="afc72-110">Modifica il livello di accesso della variabile, parametro di routine o funzione restituito per essere restrittivi almeno quanto il livello di accesso di tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="afc72-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afc72-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afc72-111">See Also</span></span>  
 [<span data-ttu-id="afc72-112">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="afc72-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
