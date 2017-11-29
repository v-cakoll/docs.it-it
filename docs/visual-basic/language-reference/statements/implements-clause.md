---
title: Clausola Implements (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ImplementsClause
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73f66eda29e37fda15b4c838da5a0458684131da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="246ac-102">Clausola Implements (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="246ac-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="246ac-103">Indica che un membro di classe o struttura fornisce l'implementazione per un membro definito in un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="246ac-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="246ac-104">Note</span><span class="sxs-lookup"><span data-stu-id="246ac-104">Remarks</span></span>  
<span data-ttu-id="246ac-105">Il `Implements` (parola chiave) non corrisponde la [istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="246ac-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="246ac-106">Utilizzare il `Implements` istruzione per specificare che una classe o struttura implementa una o più interfacce, e quindi per ogni membro il `Implements` (parola chiave) per specificare l'interfaccia e il membro implementa.</span><span class="sxs-lookup"><span data-stu-id="246ac-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="246ac-107">Se una classe o struttura implementa un'interfaccia, è necessario includere il `Implements` istruzione immediatamente dopo il [istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md) o [istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md), e deve implementare tutti i membri definito dall'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="246ac-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="246ac-108">Nuove implementazione</span><span class="sxs-lookup"><span data-stu-id="246ac-108">Reimplementation</span></span>  
<span data-ttu-id="246ac-109">In una classe derivata, si può reimplementare un membro di interfaccia che la classe di base ha già implementato.</span><span class="sxs-lookup"><span data-stu-id="246ac-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="246ac-110">Questo comportamento è diverso da cui si esegue l'override del membro della classe base per i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="246ac-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="246ac-111">Il membro della classe base non è necessario essere [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) per essere reimplementato.</span><span class="sxs-lookup"><span data-stu-id="246ac-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="246ac-112">È possibile reimplementare il membro con un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="246ac-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="246ac-113">Il `Implements` parola chiave può essere utilizzata nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="246ac-113">The `Implements` keyword can be used in the following contexts:</span></span>
- [<span data-ttu-id="246ac-114">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="246ac-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="246ac-115">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="246ac-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="246ac-116">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="246ac-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="246ac-117">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="246ac-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="246ac-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="246ac-118">See Also</span></span>  
 [<span data-ttu-id="246ac-119">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="246ac-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="246ac-120">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="246ac-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="246ac-121">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="246ac-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="246ac-122">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="246ac-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
