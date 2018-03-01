---
title: La prima istruzione di questo &#39; Sub nuovo &#39; deve essere una chiamata a &#39; MyBase. New &#39; o &#39; MyClass. New &#39; (Nessun costruttore accessibile senza parametri)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1065643e1f6c868092fbad839af0dbbd33afaf01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a><span data-ttu-id="f66d4-102">La prima istruzione di questo &#39; Sub nuovo &#39; deve essere una chiamata a &#39; MyBase. New &#39; o &#39; MyClass. New &#39; (Nessun costruttore accessibile senza parametri)</span><span class="sxs-lookup"><span data-stu-id="f66d4-102">First statement of this &#39;Sub New&#39; must be a call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="f66d4-103">La prima istruzione di questo 'Sub New' deve essere una chiamata a 'MyBase. New' o 'MyClass. New' perché classe di base\<basename >' di '\<derivedname >' non dispone di un 'Sub New' accessibile che può essere chiamato senza argomenti.</span><span class="sxs-lookup"><span data-stu-id="f66d4-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="f66d4-104">In una classe derivata, ogni costruttore deve chiamare un costruttore di classe di base (`MyBase.New`).</span><span class="sxs-lookup"><span data-stu-id="f66d4-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="f66d4-105">Se la classe di base ha un costruttore senza parametri accessibile alle classi derivate, `MyBase.New` può essere chiamato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f66d4-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="f66d4-106">In caso contrario, un costruttore di classe di base deve essere chiamato con parametri e questa operazione non può essere eseguita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f66d4-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="f66d4-107">In questo caso, la prima istruzione di ogni costruttore di classe derivata deve chiamare un costruttore con parametri nella classe base o chiamare un altro costruttore nella classe derivata che esegue un costruttore della classe base chiamare.</span><span class="sxs-lookup"><span data-stu-id="f66d4-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="f66d4-108">**ID errore:** BC30148</span><span class="sxs-lookup"><span data-stu-id="f66d4-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f66d4-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f66d4-109">To correct this error</span></span>  
  
-   <span data-ttu-id="f66d4-110">Chiamare `MyBase.New` specificando i parametri obbligatori o chiamare un costruttore peer che effettua una chiamata di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="f66d4-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="f66d4-111">Ad esempio, se la classe di base ha un costruttore che è dichiarato come `Public Sub New(ByVal index as Integer)`la prima istruzione della classe derivata, il costruttore di classe potrebbe essere `MyBase.New(100)`.</span><span class="sxs-lookup"><span data-stu-id="f66d4-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f66d4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f66d4-112">See Also</span></span>  
 [<span data-ttu-id="f66d4-113">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="f66d4-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
