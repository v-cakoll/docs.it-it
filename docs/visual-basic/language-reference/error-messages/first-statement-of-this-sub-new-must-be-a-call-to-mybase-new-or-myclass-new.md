---
title: La prima istruzione di questo 'Sub New' deve essere una chiamata a 'MyBase.New' o a 'MyClass.New' (nessun costruttore accessibile senza parametri)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: debab4e495d05a05801dd11850d0665c8bd6b299
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834322"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="74ae4-102">La prima istruzione di questo 'Sub New' deve essere una chiamata a 'MyBase.New' o a 'MyClass.New' (nessun costruttore accessibile senza parametri)</span><span class="sxs-lookup"><span data-stu-id="74ae4-102">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="74ae4-103">La prima istruzione di questo 'Sub New' deve essere una chiamata a 'MyBase. New' o 'MyClass. New' perché classe di base\<basename >' di '\<derivedname >' è privo di un 'Sub New' accessibile che può essere chiamato senza argomenti.</span><span class="sxs-lookup"><span data-stu-id="74ae4-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="74ae4-104">In una classe derivata, ogni costruttore deve chiamare un costruttore di classe di base (`MyBase.New`).</span><span class="sxs-lookup"><span data-stu-id="74ae4-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="74ae4-105">Se la classe di base ha un costruttore senza parametri accessibile alle classi derivate, `MyBase.New` può essere chiamato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="74ae4-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="74ae4-106">In caso contrario, un costruttore di classe di base deve essere chiamato con parametri e questa operazione non può essere eseguita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="74ae4-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="74ae4-107">In questo caso, la prima istruzione di ogni costruttore della classe derivata deve chiamare un costruttore con parametri nella classe base o chiamare un altro costruttore nella classe derivata che consente di chiamare un costruttore di classe di base.</span><span class="sxs-lookup"><span data-stu-id="74ae4-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="74ae4-108">**ID errore:** BC30148</span><span class="sxs-lookup"><span data-stu-id="74ae4-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="74ae4-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="74ae4-109">To correct this error</span></span>  
  
-   <span data-ttu-id="74ae4-110">Chiamare `MyBase.New` specificando i parametri obbligatori o chiamare un costruttore di peer che effettua una chiamata di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="74ae4-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="74ae4-111">Ad esempio, se la classe di base ha un costruttore che viene dichiarato come `Public Sub New(ByVal index as Integer)`, la prima istruzione in derivato costruttore della classe potrebbe essere `MyBase.New(100)`.</span><span class="sxs-lookup"><span data-stu-id="74ae4-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ae4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74ae4-112">See also</span></span>

- [<span data-ttu-id="74ae4-113">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="74ae4-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
