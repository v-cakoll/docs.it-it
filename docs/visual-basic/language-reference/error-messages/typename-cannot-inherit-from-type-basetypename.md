---
title: "'<typename>' non può ereditare da <type> '<basetypename>' perché espande l'accesso del <type> base all'esterno dell'assembly"
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: aa04c558abbcc4259c2821cdcbdc1669b91ffee0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402772"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="7d991-102">'\<typename>' non può ereditare da \<type> '\<basetypename>' perché espande l'accesso del \<type> base all'esterno dell'assembly</span><span class="sxs-lookup"><span data-stu-id="7d991-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>
<span data-ttu-id="7d991-103">Una classe o interfaccia eredita da una classe o interfaccia di base ma ha un livello di accesso meno restrittivo.</span><span class="sxs-lookup"><span data-stu-id="7d991-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="7d991-104">Ad esempio, un' `Public` interfaccia eredita da un' `Friend` interfaccia o una `Protected` classe eredita da una `Private` classe.</span><span class="sxs-lookup"><span data-stu-id="7d991-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="7d991-105">Questa operazione espone la classe o l'interfaccia di base per accedere oltre il livello previsto.</span><span class="sxs-lookup"><span data-stu-id="7d991-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="7d991-106">**ID errore:** BC30910</span><span class="sxs-lookup"><span data-stu-id="7d991-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7d991-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7d991-107">To correct this error</span></span>  
  
- <span data-ttu-id="7d991-108">Modificare il livello di accesso della classe o dell'interfaccia derivata in modo che sia almeno quanto restrittivo della classe base o dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7d991-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="7d991-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="7d991-109">-or-</span></span>  
  
- <span data-ttu-id="7d991-110">Se è necessario il livello di accesso meno restrittivo, rimuovere l' `Inherits` istruzione.</span><span class="sxs-lookup"><span data-stu-id="7d991-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="7d991-111">Non è possibile ereditare da una classe o un'interfaccia di base più limitata.</span><span class="sxs-lookup"><span data-stu-id="7d991-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d991-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d991-112">See also</span></span>

- [<span data-ttu-id="7d991-113">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="7d991-113">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="7d991-114">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="7d991-114">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="7d991-115">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="7d991-115">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="7d991-116">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d991-116">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
