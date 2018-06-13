---
title: Clausola Implements (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 1e34245ac528e9e2463afbfd07dff91bf693830b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603405"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="e31c8-102">Clausola Implements (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e31c8-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="e31c8-103">Indica che un membro di classe o struttura fornisce l'implementazione per un membro definito in un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e31c8-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e31c8-104">Note</span><span class="sxs-lookup"><span data-stu-id="e31c8-104">Remarks</span></span>  
<span data-ttu-id="e31c8-105">Il `Implements` (parola chiave) non corrisponde la [istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e31c8-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="e31c8-106">Utilizzare il `Implements` istruzione per specificare che una classe o struttura implementa una o più interfacce, e quindi per ogni membro il `Implements` (parola chiave) per specificare l'interfaccia e il membro implementa.</span><span class="sxs-lookup"><span data-stu-id="e31c8-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="e31c8-107">Se una classe o struttura implementa un'interfaccia, è necessario includere il `Implements` istruzione immediatamente dopo il [istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md) o [istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md), e deve implementare tutti i membri definito dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e31c8-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="e31c8-108">Nuove implementazione</span><span class="sxs-lookup"><span data-stu-id="e31c8-108">Reimplementation</span></span>  
<span data-ttu-id="e31c8-109">In una classe derivata, si può reimplementare un membro di interfaccia che la classe di base ha già implementato.</span><span class="sxs-lookup"><span data-stu-id="e31c8-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="e31c8-110">Questo comportamento è diverso da cui si esegue l'override del membro della classe base per i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="e31c8-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="e31c8-111">Il membro della classe base non è necessario essere [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) per essere reimplementato.</span><span class="sxs-lookup"><span data-stu-id="e31c8-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="e31c8-112">È possibile reimplementare il membro con un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="e31c8-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="e31c8-113">Il `Implements` parola chiave può essere utilizzata nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e31c8-113">The `Implements` keyword can be used in the following contexts:</span></span>
- [<span data-ttu-id="e31c8-114">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="e31c8-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="e31c8-115">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="e31c8-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="e31c8-116">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="e31c8-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="e31c8-117">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="e31c8-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e31c8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e31c8-118">See Also</span></span>  
 [<span data-ttu-id="e31c8-119">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="e31c8-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="e31c8-120">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="e31c8-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="e31c8-121">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="e31c8-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="e31c8-122">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="e31c8-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
