---
title: "'<typename>' non può ereditare da <type> '<basetypename>' perché espande l'accesso del <type> base all'esterno dell'assembly"
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 226c85f887ecc706a5cb554c2163742f10896141
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269822"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="b417e-102">'\<nomeTipo >' non può ereditare \<tipo > '\<nomeTipoBase >' perché espande l'accesso della base \<tipo > all'esterno dell'assembly</span><span class="sxs-lookup"><span data-stu-id="b417e-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>
<span data-ttu-id="b417e-103">Una classe o interfaccia eredita da una classe di base o interfaccia ma ha un livello di accesso meno restrittivo.</span><span class="sxs-lookup"><span data-stu-id="b417e-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="b417e-104">Ad esempio, un `Public` interfaccia eredita da un `Friend` interfaccia o una `Protected` classe eredita da un `Private` classe.</span><span class="sxs-lookup"><span data-stu-id="b417e-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="b417e-105">Ciò espone la classe di base o l'interfaccia per accedere a oltre il livello desiderato.</span><span class="sxs-lookup"><span data-stu-id="b417e-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="b417e-106">**ID errore:** BC30910</span><span class="sxs-lookup"><span data-stu-id="b417e-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b417e-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b417e-107">To correct this error</span></span>  
  
-   <span data-ttu-id="b417e-108">Modificare il livello di accesso della classe derivata o dell'interfaccia sia restrittiva almeno quanto quella della classe di base o dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b417e-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="b417e-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b417e-109">-or-</span></span>  
  
-   <span data-ttu-id="b417e-110">Se è necessario il livello di accesso meno restrittivo, rimuovere il `Inherits` istruzione.</span><span class="sxs-lookup"><span data-stu-id="b417e-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="b417e-111">È possibile ereditare da una classe di base con maggiori restrizioni o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b417e-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b417e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b417e-112">See also</span></span>
- [<span data-ttu-id="b417e-113">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="b417e-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="b417e-114">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="b417e-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="b417e-115">Istruzione Inherits</span><span class="sxs-lookup"><span data-stu-id="b417e-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="b417e-116">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b417e-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
