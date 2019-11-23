---
title: Friend
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: 98f8ed947c9f4376c5778011a3a91ca8b094f9ec
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351570"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="f1a74-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1a74-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="f1a74-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span><span class="sxs-lookup"><span data-stu-id="f1a74-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1a74-104">Note</span><span class="sxs-lookup"><span data-stu-id="f1a74-104">Remarks</span></span>  
 <span data-ttu-id="f1a74-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span><span class="sxs-lookup"><span data-stu-id="f1a74-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="f1a74-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span><span class="sxs-lookup"><span data-stu-id="f1a74-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="f1a74-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span><span class="sxs-lookup"><span data-stu-id="f1a74-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="f1a74-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span><span class="sxs-lookup"><span data-stu-id="f1a74-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="f1a74-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span><span class="sxs-lookup"><span data-stu-id="f1a74-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="f1a74-110">You can use `Friend` only at the module, interface, or namespace level.</span><span class="sxs-lookup"><span data-stu-id="f1a74-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="f1a74-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span><span class="sxs-lookup"><span data-stu-id="f1a74-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="f1a74-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span><span class="sxs-lookup"><span data-stu-id="f1a74-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="f1a74-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span><span class="sxs-lookup"><span data-stu-id="f1a74-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="f1a74-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f1a74-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1a74-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span><span class="sxs-lookup"><span data-stu-id="f1a74-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="f1a74-116">Per altre informazioni, vedere [Friend Assemblies](../../../standard/assembly/friend.md) (Assembly friend).</span><span class="sxs-lookup"><span data-stu-id="f1a74-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>

## <a name="example"></a><span data-ttu-id="f1a74-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="f1a74-117">Example</span></span>  
 <span data-ttu-id="f1a74-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span><span class="sxs-lookup"><span data-stu-id="f1a74-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="f1a74-119">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="f1a74-119">Usage</span></span>  
 <span data-ttu-id="f1a74-120">You can use the `Friend` modifier in these contexts:</span><span class="sxs-lookup"><span data-stu-id="f1a74-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="f1a74-121">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="f1a74-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="f1a74-122">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="f1a74-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="f1a74-123">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="f1a74-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="f1a74-124">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="f1a74-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="f1a74-125">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="f1a74-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="f1a74-126">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="f1a74-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="f1a74-127">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="f1a74-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="f1a74-128">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="f1a74-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="f1a74-129">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="f1a74-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="f1a74-130">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="f1a74-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="f1a74-131">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="f1a74-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="f1a74-132">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="f1a74-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="f1a74-133">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="f1a74-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="f1a74-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1a74-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="f1a74-135">Public</span><span class="sxs-lookup"><span data-stu-id="f1a74-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="f1a74-136">Protected</span><span class="sxs-lookup"><span data-stu-id="f1a74-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="f1a74-137">Private</span><span class="sxs-lookup"><span data-stu-id="f1a74-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="f1a74-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="f1a74-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="f1a74-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="f1a74-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="f1a74-140">Access levels in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f1a74-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="f1a74-141">Routine</span><span class="sxs-lookup"><span data-stu-id="f1a74-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="f1a74-142">Strutture</span><span class="sxs-lookup"><span data-stu-id="f1a74-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="f1a74-143">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="f1a74-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
