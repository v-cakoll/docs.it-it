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
ms.openlocfilehash: d906fc8ada19f22059da44acbd76dd07dacd4801
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234589"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="76fea-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76fea-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="76fea-103">Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dall'interno dell'assembly che contiene la dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="76fea-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76fea-104">Note</span><span class="sxs-lookup"><span data-stu-id="76fea-104">Remarks</span></span>  
 <span data-ttu-id="76fea-105">In molti casi, si desidera elementi, ad esempio le classi e da usare con l'intero assembly, non solo tramite il componente che li dichiara delle strutture di programmazione.</span><span class="sxs-lookup"><span data-stu-id="76fea-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="76fea-106">Tuttavia, potrebbe non desiderati siano accessibili dal codice all'esterno dell'assembly (ad esempio, se l'applicazione è proprietario).</span><span class="sxs-lookup"><span data-stu-id="76fea-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="76fea-107">Se si desidera limitare l'accesso a un elemento in questo modo, è possibile dichiarare utilizzando il `Friend` modificatore.</span><span class="sxs-lookup"><span data-stu-id="76fea-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="76fea-108">Codice in altre classi, strutture e i moduli compilati nello stesso assembly possono accedere a tutti i `Friend` elementi in tale assembly.</span><span class="sxs-lookup"><span data-stu-id="76fea-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="76fea-109">`Friend` l'accesso è spesso il livello preferito per gli elementi di programmazione dell'applicazione, e `Friend` è l'accesso predefinito a livello di un'interfaccia, un modulo, una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="76fea-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="76fea-110">È possibile utilizzare `Friend` solo a livello di modulo, interfaccia o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="76fea-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="76fea-111">Pertanto, il contesto della dichiarazione per un `Friend` elemento deve essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una classe o una struttura, non può essere una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="76fea-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="76fea-112">È anche possibile usare il [Protected Friend](protected-friend.md) modificatore di accesso, che rende accessibile dall'interno di tale classe, dalle classi derivate e allo stesso assembly in cui è definita la classe un membro di classe.</span><span class="sxs-lookup"><span data-stu-id="76fea-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="76fea-113">Per limitare l'accesso a un membro all'interno di classe e dalle classi derivate nello stesso assembly, utilizzare il [privato protetto](private-protected.md) modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="76fea-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="76fea-114">Per un confronto tra `Friend` e l'altro modificatori di accesso, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="76fea-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76fea-115">È possibile specificare che un altro assembly sia un assembly friend, che consente di accedere a tutti i tipi e membri contrassegnati come `Friend`.</span><span class="sxs-lookup"><span data-stu-id="76fea-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="76fea-116">Per altre informazioni, vedere [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md) (Assembly friend).</span><span class="sxs-lookup"><span data-stu-id="76fea-116">For more information, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="76fea-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="76fea-117">Example</span></span>  
 <span data-ttu-id="76fea-118">La classe seguente usa il `Friend` modificatore per consentire altri elementi di programmazione all'interno dell'assembly stesso per accedere a determinati membri.</span><span class="sxs-lookup"><span data-stu-id="76fea-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a><span data-ttu-id="76fea-119">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="76fea-119">Usage</span></span>  
 <span data-ttu-id="76fea-120">È possibile utilizzare il `Friend` modificatore nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="76fea-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="76fea-121">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="76fea-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="76fea-122">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="76fea-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="76fea-123">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="76fea-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="76fea-124">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="76fea-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="76fea-125">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="76fea-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="76fea-126">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="76fea-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="76fea-127">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="76fea-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="76fea-128">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="76fea-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="76fea-129">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="76fea-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="76fea-130">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="76fea-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="76fea-131">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="76fea-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="76fea-132">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="76fea-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="76fea-133">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="76fea-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="76fea-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76fea-134">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="76fea-135">Public</span><span class="sxs-lookup"><span data-stu-id="76fea-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="76fea-136">Protected</span><span class="sxs-lookup"><span data-stu-id="76fea-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="76fea-137">Private</span><span class="sxs-lookup"><span data-stu-id="76fea-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 <span data-ttu-id="76fea-138">[Protetto privato](./private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="76fea-138">[Private Protected](./private-protected.md) </span></span>  
 <span data-ttu-id="76fea-139">[Protected Friend](./protected-friend.md) </span><span class="sxs-lookup"><span data-stu-id="76fea-139">[Protected Friend](./protected-friend.md) </span></span>  
 [<span data-ttu-id="76fea-140">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="76fea-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="76fea-141">Routine</span><span class="sxs-lookup"><span data-stu-id="76fea-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="76fea-142">Strutture</span><span class="sxs-lookup"><span data-stu-id="76fea-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="76fea-143">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="76fea-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
