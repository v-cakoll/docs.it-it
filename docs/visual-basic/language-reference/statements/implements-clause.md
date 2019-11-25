---
title: Clausola Implements
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
ms.openlocfilehash: f114aee75356e59eafd9d3ba6af9c64402cb374f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345866"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="d8965-102">Clausola Implements (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8965-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="d8965-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span><span class="sxs-lookup"><span data-stu-id="d8965-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8965-104">Note</span><span class="sxs-lookup"><span data-stu-id="d8965-104">Remarks</span></span>  
<span data-ttu-id="d8965-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d8965-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="d8965-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span><span class="sxs-lookup"><span data-stu-id="d8965-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="d8965-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span><span class="sxs-lookup"><span data-stu-id="d8965-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="d8965-108">Reimplementation</span><span class="sxs-lookup"><span data-stu-id="d8965-108">Reimplementation</span></span>  
<span data-ttu-id="d8965-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span><span class="sxs-lookup"><span data-stu-id="d8965-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="d8965-110">This is different from overriding the base class member in the following respects:</span><span class="sxs-lookup"><span data-stu-id="d8965-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="d8965-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span><span class="sxs-lookup"><span data-stu-id="d8965-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="d8965-112">You can reimplement the member with a different name.</span><span class="sxs-lookup"><span data-stu-id="d8965-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="d8965-113">The `Implements` keyword can be used in the following contexts:</span><span class="sxs-lookup"><span data-stu-id="d8965-113">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="d8965-114">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="d8965-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="d8965-115">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="d8965-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="d8965-116">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="d8965-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="d8965-117">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="d8965-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8965-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8965-118">See also</span></span>

- [<span data-ttu-id="d8965-119">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="d8965-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="d8965-120">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="d8965-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="d8965-121">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="d8965-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="d8965-122">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="d8965-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
