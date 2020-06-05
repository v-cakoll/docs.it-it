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
ms.openlocfilehash: 4ac8e5942cf6097642ec111992ebfcdb91e8d7c1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392171"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="67af9-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67af9-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="67af9-103">Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo all'interno dell'assembly che contiene la relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="67af9-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67af9-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="67af9-104">Remarks</span></span>  
 <span data-ttu-id="67af9-105">In molti casi, si desidera che gli elementi di programmazione come classi e strutture siano utilizzati dall'intero assembly, non solo dal componente che li dichiara.</span><span class="sxs-lookup"><span data-stu-id="67af9-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="67af9-106">Tuttavia, è possibile che non si desideri che siano accessibili dal codice all'esterno dell'assembly (ad esempio, se l'applicazione è proprietaria).</span><span class="sxs-lookup"><span data-stu-id="67af9-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="67af9-107">Se si vuole limitare l'accesso a un elemento in questo modo, è possibile dichiararlo usando il `Friend` modificatore.</span><span class="sxs-lookup"><span data-stu-id="67af9-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="67af9-108">Il codice in altre classi, strutture e moduli compilati nello stesso assembly può accedere a tutti gli `Friend` elementi in tale assembly.</span><span class="sxs-lookup"><span data-stu-id="67af9-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="67af9-109">`Friend`l'accesso è spesso il livello preferenziale per gli elementi di programmazione di un'applicazione e `Friend` rappresenta il livello di accesso predefinito di un'interfaccia, un modulo, una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="67af9-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="67af9-110">È possibile usare `Friend` solo a livello di modulo, interfaccia o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="67af9-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="67af9-111">Il contesto di dichiarazione per un `Friend` elemento deve pertanto essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una classe o una struttura e non può essere una routine.</span><span class="sxs-lookup"><span data-stu-id="67af9-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="67af9-112">È anche possibile usare il modificatore di accesso [Friend protetto](protected-friend.md) , che rende accessibile un membro della classe da tale classe, dalle classi derivate e dallo stesso assembly in cui è definita la classe.</span><span class="sxs-lookup"><span data-stu-id="67af9-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="67af9-113">Per limitare l'accesso a un membro dall'interno della relativa classe e dalle classi derivate nello stesso assembly, usare il modificatore di accesso [privato protetto](private-protected.md) .</span><span class="sxs-lookup"><span data-stu-id="67af9-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="67af9-114">Per un confronto tra `Friend` e gli altri modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="67af9-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67af9-115">È possibile specificare che un altro assembly è un assembly Friend, che consente di accedere a tutti i tipi e membri contrassegnati come `Friend` .</span><span class="sxs-lookup"><span data-stu-id="67af9-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="67af9-116">Per ulteriori informazioni, vedere [assembly Friend](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="67af9-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>

## <a name="example"></a><span data-ttu-id="67af9-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="67af9-117">Example</span></span>  
 <span data-ttu-id="67af9-118">La classe seguente usa il `Friend` modificatore per consentire ad altri elementi di programmazione all'interno dello stesso assembly di accedere a determinati membri.</span><span class="sxs-lookup"><span data-stu-id="67af9-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="67af9-119">Uso</span><span class="sxs-lookup"><span data-stu-id="67af9-119">Usage</span></span>  
 <span data-ttu-id="67af9-120">È possibile usare il `Friend` modificatore in questi contesti:</span><span class="sxs-lookup"><span data-stu-id="67af9-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="67af9-121">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="67af9-121">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="67af9-122">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="67af9-122">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="67af9-123">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="67af9-123">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="67af9-124">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="67af9-124">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="67af9-125">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="67af9-125">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="67af9-126">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="67af9-126">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="67af9-127">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="67af9-127">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="67af9-128">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="67af9-128">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="67af9-129">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="67af9-129">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="67af9-130">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="67af9-130">Module Statement</span></span>](../statements/module-statement.md)  
  
 [<span data-ttu-id="67af9-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="67af9-131">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="67af9-132">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="67af9-132">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="67af9-133">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="67af9-133">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="67af9-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67af9-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="67af9-135">Pubblica</span><span class="sxs-lookup"><span data-stu-id="67af9-135">Public</span></span>](public.md)
- [<span data-ttu-id="67af9-136">Protetto</span><span class="sxs-lookup"><span data-stu-id="67af9-136">Protected</span></span>](protected.md)
- [<span data-ttu-id="67af9-137">Privata</span><span class="sxs-lookup"><span data-stu-id="67af9-137">Private</span></span>](private.md)
- [<span data-ttu-id="67af9-138">Privato protetto</span><span class="sxs-lookup"><span data-stu-id="67af9-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="67af9-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="67af9-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="67af9-140">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67af9-140">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="67af9-141">Procedure</span><span class="sxs-lookup"><span data-stu-id="67af9-141">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="67af9-142">Strutture</span><span class="sxs-lookup"><span data-stu-id="67af9-142">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="67af9-143">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="67af9-143">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
