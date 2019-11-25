---
title: Public
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 35bf1a65e0b8f24a1263adc480719c69b95dff9b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351287"
---
# <a name="public-visual-basic"></a><span data-ttu-id="b15cb-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b15cb-102">Public (Visual Basic)</span></span>
<span data-ttu-id="b15cb-103">Specifies that one or more declared programming elements have no access restrictions.</span><span class="sxs-lookup"><span data-stu-id="b15cb-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b15cb-104">Note</span><span class="sxs-lookup"><span data-stu-id="b15cb-104">Remarks</span></span>  
 <span data-ttu-id="b15cb-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span><span class="sxs-lookup"><span data-stu-id="b15cb-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="b15cb-106">To confer such unlimited access on an element, you can declare it with `Public`.</span><span class="sxs-lookup"><span data-stu-id="b15cb-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="b15cb-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span><span class="sxs-lookup"><span data-stu-id="b15cb-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="b15cb-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span><span class="sxs-lookup"><span data-stu-id="b15cb-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b15cb-109">Regole</span><span class="sxs-lookup"><span data-stu-id="b15cb-109">Rules</span></span>  
  
- <span data-ttu-id="b15cb-110">**Declaration Context.**</span><span class="sxs-lookup"><span data-stu-id="b15cb-110">**Declaration Context.**</span></span> <span data-ttu-id="b15cb-111">You can use `Public` only at module, interface, or namespace level.</span><span class="sxs-lookup"><span data-stu-id="b15cb-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="b15cb-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span><span class="sxs-lookup"><span data-stu-id="b15cb-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="b15cb-113">Comportamento</span><span class="sxs-lookup"><span data-stu-id="b15cb-113">Behavior</span></span>  
  
- <span data-ttu-id="b15cb-114">**Access Level.**</span><span class="sxs-lookup"><span data-stu-id="b15cb-114">**Access Level.**</span></span> <span data-ttu-id="b15cb-115">All code that can access a module, class, or structure can access its `Public` elements.</span><span class="sxs-lookup"><span data-stu-id="b15cb-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="b15cb-116">**Default Access.**</span><span class="sxs-lookup"><span data-stu-id="b15cb-116">**Default Access.**</span></span> <span data-ttu-id="b15cb-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span><span class="sxs-lookup"><span data-stu-id="b15cb-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="b15cb-118">**Access Modifiers.**</span><span class="sxs-lookup"><span data-stu-id="b15cb-118">**Access Modifiers.**</span></span> <span data-ttu-id="b15cb-119">The keywords that specify access level are called *access modifiers*.</span><span class="sxs-lookup"><span data-stu-id="b15cb-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="b15cb-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b15cb-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="b15cb-121">Il modificatore `Public` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b15cb-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="b15cb-122">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="b15cb-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="b15cb-123">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="b15cb-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="b15cb-124">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="b15cb-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="b15cb-125">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="b15cb-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="b15cb-126">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="b15cb-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="b15cb-127">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="b15cb-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="b15cb-128">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="b15cb-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="b15cb-129">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="b15cb-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="b15cb-130">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="b15cb-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="b15cb-131">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="b15cb-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="b15cb-132">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="b15cb-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="b15cb-133">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="b15cb-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="b15cb-134">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="b15cb-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="b15cb-135">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="b15cb-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="b15cb-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b15cb-136">See also</span></span>

- [<span data-ttu-id="b15cb-137">Protected</span><span class="sxs-lookup"><span data-stu-id="b15cb-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="b15cb-138">Friend</span><span class="sxs-lookup"><span data-stu-id="b15cb-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="b15cb-139">Private</span><span class="sxs-lookup"><span data-stu-id="b15cb-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="b15cb-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="b15cb-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="b15cb-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="b15cb-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="b15cb-142">Access levels in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b15cb-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="b15cb-143">Routine</span><span class="sxs-lookup"><span data-stu-id="b15cb-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="b15cb-144">Strutture</span><span class="sxs-lookup"><span data-stu-id="b15cb-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="b15cb-145">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="b15cb-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
