---
title: La prima istruzione di questo oggetto &#39;Sub New&#39; deve essere una chiamata a &#39;MyBase. New&#39; o &#39;MyClass. New&#39; (nessun costruttore accessibile senza parametri)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 75832ae88908094c1cb74ce04ad84c0d2ae91e68
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728895"
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a><span data-ttu-id="db1bb-102">La prima istruzione di questo oggetto &#39;Sub New&#39; deve essere una chiamata a &#39;MyBase. New&#39; o &#39;MyClass. New&#39; (nessun costruttore accessibile senza parametri)</span><span class="sxs-lookup"><span data-stu-id="db1bb-102">First statement of this &#39;Sub New&#39; must be a call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="db1bb-103">La prima istruzione di questo 'Sub New' deve essere una chiamata a 'MyBase. New' o 'MyClass. New' perché classe di base\<basename >' di '\<derivedname >' è privo di un 'Sub New' accessibile che può essere chiamato senza argomenti.</span><span class="sxs-lookup"><span data-stu-id="db1bb-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="db1bb-104">In una classe derivata, ogni costruttore deve chiamare un costruttore di classe di base (`MyBase.New`).</span><span class="sxs-lookup"><span data-stu-id="db1bb-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="db1bb-105">Se la classe di base ha un costruttore senza parametri accessibile alle classi derivate, `MyBase.New` può essere chiamato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="db1bb-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="db1bb-106">In caso contrario, un costruttore di classe di base deve essere chiamato con parametri e questa operazione non può essere eseguita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="db1bb-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="db1bb-107">In questo caso, la prima istruzione di ogni costruttore della classe derivata deve chiamare un costruttore con parametri nella classe base o chiamare un altro costruttore nella classe derivata che consente di chiamare un costruttore di classe di base.</span><span class="sxs-lookup"><span data-stu-id="db1bb-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="db1bb-108">**ID errore:** BC30148</span><span class="sxs-lookup"><span data-stu-id="db1bb-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="db1bb-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="db1bb-109">To correct this error</span></span>  
  
-   <span data-ttu-id="db1bb-110">Chiamare `MyBase.New` specificando i parametri obbligatori o chiamare un costruttore di peer che effettua una chiamata di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="db1bb-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="db1bb-111">Ad esempio, se la classe di base ha un costruttore che viene dichiarato come `Public Sub New(ByVal index as Integer)`, la prima istruzione in derivato costruttore della classe potrebbe essere `MyBase.New(100)`.</span><span class="sxs-lookup"><span data-stu-id="db1bb-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1bb-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db1bb-112">See also</span></span>
- [<span data-ttu-id="db1bb-113">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="db1bb-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
