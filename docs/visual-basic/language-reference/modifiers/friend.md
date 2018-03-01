---
title: Friend (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: df0e8ad1990fe7a1aa495e1794c942813cffb5bc
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="friend-visual-basic"></a><span data-ttu-id="08c73-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08c73-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="08c73-103">Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dall'interno dell'assembly che contiene la dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="08c73-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08c73-104">Note</span><span class="sxs-lookup"><span data-stu-id="08c73-104">Remarks</span></span>  
 <span data-ttu-id="08c73-105">In molti casi, si desidera elementi, ad esempio le classi e da usare con l'intero assembly, non solo tramite il componente che li dichiara delle strutture di programmazione.</span><span class="sxs-lookup"><span data-stu-id="08c73-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="08c73-106">Tuttavia, potrebbe non desiderati siano accessibili dal codice all'esterno dell'assembly (ad esempio, se l'applicazione è proprietario).</span><span class="sxs-lookup"><span data-stu-id="08c73-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="08c73-107">Se si desidera limitare l'accesso a un elemento in questo modo, è possibile dichiarare utilizzando il `Friend` modificatore.</span><span class="sxs-lookup"><span data-stu-id="08c73-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="08c73-108">Codice in altre classi, strutture e i moduli compilati nello stesso assembly possono accedere a tutti i `Friend` elementi in tale assembly.</span><span class="sxs-lookup"><span data-stu-id="08c73-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="08c73-109">`Friend`l'accesso è spesso il livello preferito per gli elementi di programmazione dell'applicazione, e `Friend` è l'accesso predefinito di un'interfaccia, un modulo, una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="08c73-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="08c73-110">È possibile utilizzare `Friend` solo a livello di modulo, interfaccia o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="08c73-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="08c73-111">Pertanto, il contesto della dichiarazione per un `Friend` elemento deve essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una classe o una struttura, non può essere una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="08c73-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  
  
 <span data-ttu-id="08c73-112">È possibile utilizzare il `Friend` modificatore in combinazione con il [Protected](../../../visual-basic/language-reference/modifiers/protected.md) modificatore nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="08c73-112">You can use the `Friend` modifier in conjunction with the [Protected](../../../visual-basic/language-reference/modifiers/protected.md) modifier in the same declaration.</span></span> <span data-ttu-id="08c73-113">Questa combinazione conferisce entrambi `Friend` accesso e l'accesso protetto per gli elementi dichiarati, in modo che siano accessibili da un punto qualsiasi nello stesso assembly, dalla rispettiva classe e dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="08c73-113">This combination confers both `Friend` access and protected access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="08c73-114">È possibile specificare `Protected Friend` solo in membri di classi.</span><span class="sxs-lookup"><span data-stu-id="08c73-114">You can specify `Protected Friend` only on members of classes.</span></span>  
  
 <span data-ttu-id="08c73-115">Per un confronto tra `Friend` e l'altro modificatori di accesso, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="08c73-115">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08c73-116">È possibile specificare che un altro assembly sia un assembly friend, che consente di accedere a tutti i tipi e membri contrassegnati come `Friend`.</span><span class="sxs-lookup"><span data-stu-id="08c73-116">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="08c73-117">Per altre informazioni, vedere [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md) (Assembly friend).</span><span class="sxs-lookup"><span data-stu-id="08c73-117">For more information, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="08c73-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="08c73-118">Example</span></span>  
 <span data-ttu-id="08c73-119">La classe seguente usa il `Friend` modificatore per consentire altri elementi di programmazione all'interno dell'assembly stesso per accedere a determinati membri.</span><span class="sxs-lookup"><span data-stu-id="08c73-119">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a><span data-ttu-id="08c73-120">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="08c73-120">Usage</span></span>  
 <span data-ttu-id="08c73-121">È possibile utilizzare il `Friend` modificatore nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="08c73-121">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="08c73-122">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="08c73-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="08c73-123">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="08c73-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="08c73-124">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="08c73-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="08c73-125">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="08c73-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="08c73-126">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="08c73-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="08c73-127">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="08c73-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="08c73-128">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="08c73-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="08c73-129">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="08c73-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="08c73-130">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="08c73-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="08c73-131">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="08c73-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="08c73-132">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="08c73-132">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="08c73-133">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="08c73-133">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="08c73-134">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="08c73-134">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="08c73-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08c73-135">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="08c73-136">Public</span><span class="sxs-lookup"><span data-stu-id="08c73-136">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="08c73-137">Protected</span><span class="sxs-lookup"><span data-stu-id="08c73-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="08c73-138">Private</span><span class="sxs-lookup"><span data-stu-id="08c73-138">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="08c73-139">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="08c73-139">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="08c73-140">Routine</span><span class="sxs-lookup"><span data-stu-id="08c73-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="08c73-141">Strutture</span><span class="sxs-lookup"><span data-stu-id="08c73-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="08c73-142">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="08c73-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
