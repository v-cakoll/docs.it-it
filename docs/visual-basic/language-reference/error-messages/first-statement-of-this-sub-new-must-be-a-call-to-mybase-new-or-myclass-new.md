---
title: La prima istruzione di questo 'Sub New' deve essere una chiamata a 'MyBase.New' o a 'MyClass.New' (nessun costruttore accessibile senza parametri)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 2b9d2568fb64e4af72733ad1f3dee58aaee650e5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402979"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="39d0d-102">La prima istruzione di questo 'Sub New' deve essere una chiamata a 'MyBase.New' o a 'MyClass.New' (nessun costruttore accessibile senza parametri)</span><span class="sxs-lookup"><span data-stu-id="39d0d-102">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="39d0d-103">La prima istruzione di questo ' Sub New ' deve essere una chiamata a' MyBase. New ' o a' MyClass. New ' perché la classe base ' \<basename> ' di ' \<derivedname> ' non ha un'Sub New ' accessibile che può essere chiamato senza argomenti.</span><span class="sxs-lookup"><span data-stu-id="39d0d-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="39d0d-104">In una classe derivata ogni costruttore deve chiamare un costruttore della classe base ( `MyBase.New` ).</span><span class="sxs-lookup"><span data-stu-id="39d0d-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="39d0d-105">Se la classe base dispone di un costruttore senza parametri accessibile alle classi derivate, `MyBase.New` può essere chiamato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="39d0d-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="39d0d-106">In caso contrario, è necessario chiamare un costruttore della classe base con parametri e questa operazione non può essere eseguita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="39d0d-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="39d0d-107">In questo caso, la prima istruzione di ogni costruttore della classe derivata deve chiamare un costruttore con parametri sulla classe di base o chiamare un altro costruttore nella classe derivata che effettua una chiamata al costruttore della classe base.</span><span class="sxs-lookup"><span data-stu-id="39d0d-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="39d0d-108">**ID errore:** BC30148</span><span class="sxs-lookup"><span data-stu-id="39d0d-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="39d0d-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="39d0d-109">To correct this error</span></span>  
  
- <span data-ttu-id="39d0d-110">Chiamare `MyBase.New` la fornitura dei parametri obbligatori o chiamare un costruttore peer che esegue tale chiamata.</span><span class="sxs-lookup"><span data-stu-id="39d0d-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="39d0d-111">Se, ad esempio, la classe base ha un costruttore dichiarato come `Public Sub New(ByVal index as Integer)` , la prima istruzione nel costruttore della classe derivata potrebbe essere `MyBase.New(100)` .</span><span class="sxs-lookup"><span data-stu-id="39d0d-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d0d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39d0d-112">See also</span></span>

- [<span data-ttu-id="39d0d-113">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="39d0d-113">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
