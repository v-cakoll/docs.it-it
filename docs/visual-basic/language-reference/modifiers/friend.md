---
title: Friend (Visual Basic)
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
ms.openlocfilehash: 1e6dbaa9201d5c9cd902412797b2427ec488d014
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371411"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="a6c19-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6c19-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="a6c19-103">Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dall'interno dell'assembly che contiene la dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="a6c19-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6c19-104">Note</span><span class="sxs-lookup"><span data-stu-id="a6c19-104">Remarks</span></span>  
 <span data-ttu-id="a6c19-105">In molti casi, consigliabile elementi di programmazione quali classi e strutture da utilizzare per l'intero assembly, non solo dal componente che li dichiara.</span><span class="sxs-lookup"><span data-stu-id="a6c19-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="a6c19-106">Tuttavia, è possibile evitare siano accessibili dal codice all'esterno dell'assembly (ad esempio, se l'applicazione è proprietario).</span><span class="sxs-lookup"><span data-stu-id="a6c19-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="a6c19-107">Se si desidera limitare l'accesso a un elemento in questo modo, è possibile dichiararlo tramite il `Friend` modificatore.</span><span class="sxs-lookup"><span data-stu-id="a6c19-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="a6c19-108">Codice in altre classi, strutture e i moduli compilati nello stesso assembly possono accedere a tutte le `Friend` elementi in tale assembly.</span><span class="sxs-lookup"><span data-stu-id="a6c19-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="a6c19-109">`Friend` l'accesso è spesso il livello preferito per gli elementi di programmazione di un'applicazione, e `Friend` è l'accesso predefinito a livello di un'interfaccia, un modulo, una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="a6c19-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="a6c19-110">È possibile usare `Friend` solo a livello di modulo, interfaccia o dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a6c19-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="a6c19-111">Pertanto, il contesto della dichiarazione per un `Friend` elemento deve essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una classe o una struttura; non può essere una procedura.</span><span class="sxs-lookup"><span data-stu-id="a6c19-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="a6c19-112">È anche possibile usare la [Protected Friend](protected-friend.md) modificatore di accesso, che rende accessibili da all'interno di tale classe, dalle classi derivate e dallo stesso assembly in cui è definita la classe un membro di classe.</span><span class="sxs-lookup"><span data-stu-id="a6c19-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="a6c19-113">Per limitare l'accesso a un membro dalla relativa classe e dalle classi derivate nello stesso assembly, si utilizza il [Private Protected](private-protected.md) modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="a6c19-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="a6c19-114">Per un confronto delle `Friend` e l'altro modificatori di accesso, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a6c19-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6c19-115">È possibile specificare che un altro assembly sia un assembly friend, che consente di accedere a tutti i tipi e membri contrassegnati come `Friend`.</span><span class="sxs-lookup"><span data-stu-id="a6c19-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="a6c19-116">Per altre informazioni, vedere [Friend Assemblies](../../../standard/assembly/friend-assemblies.md) (Assembly friend).</span><span class="sxs-lookup"><span data-stu-id="a6c19-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6c19-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6c19-117">Example</span></span>  
 <span data-ttu-id="a6c19-118">La classe seguente usa il `Friend` modificatore per consentire altri elementi di programmazione all'interno dell'assembly stesso di accedere a determinati membri.</span><span class="sxs-lookup"><span data-stu-id="a6c19-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="a6c19-119">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="a6c19-119">Usage</span></span>  
 <span data-ttu-id="a6c19-120">È possibile usare il `Friend` modificatore nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6c19-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="a6c19-121">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="a6c19-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="a6c19-122">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="a6c19-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="a6c19-123">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="a6c19-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="a6c19-124">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="a6c19-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="a6c19-125">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="a6c19-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="a6c19-126">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="a6c19-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="a6c19-127">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="a6c19-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="a6c19-128">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="a6c19-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="a6c19-129">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="a6c19-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="a6c19-130">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="a6c19-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="a6c19-131">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="a6c19-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="a6c19-132">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="a6c19-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="a6c19-133">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="a6c19-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a6c19-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6c19-134">See also</span></span>
- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="a6c19-135">Public</span><span class="sxs-lookup"><span data-stu-id="a6c19-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="a6c19-136">Protected</span><span class="sxs-lookup"><span data-stu-id="a6c19-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="a6c19-137">Private</span><span class="sxs-lookup"><span data-stu-id="a6c19-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="a6c19-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="a6c19-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="a6c19-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="a6c19-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="a6c19-140">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a6c19-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="a6c19-141">Routine</span><span class="sxs-lookup"><span data-stu-id="a6c19-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="a6c19-142">Strutture</span><span class="sxs-lookup"><span data-stu-id="a6c19-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a6c19-143">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="a6c19-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
