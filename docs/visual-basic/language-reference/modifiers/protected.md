---
title: Protected (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 5f279ed0a33840bb1f2321c17a1ffba412837c07
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234757"
---
# <a name="protected-visual-basic"></a><span data-ttu-id="0507b-102">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0507b-102">Protected (Visual Basic)</span></span>
<span data-ttu-id="0507b-103">Un modificatore di accesso di membro che specifica uno o più elementi di programmazione dichiarati sono accessibili solo dalla relativa classe o da una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="0507b-103">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0507b-104">Note</span><span class="sxs-lookup"><span data-stu-id="0507b-104">Remarks</span></span>  
 <span data-ttu-id="0507b-105">Talvolta un elemento di programmazione dichiarato in una classe contiene dati sensibili o codice con restrizioni, e si desidera limitare l'accesso all'elemento.</span><span class="sxs-lookup"><span data-stu-id="0507b-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="0507b-106">Tuttavia, se la classe è ereditabile e si prevede una gerarchia di classi derivate, potrebbe essere necessario per queste classi derivate di accedere ai dati o codice.</span><span class="sxs-lookup"><span data-stu-id="0507b-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="0507b-107">In tal caso, si desidera l'elemento deve essere accessibile dalla classe di base e da tutte le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="0507b-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="0507b-108">Per limitare l'accesso a un elemento in questo modo, è possibile dichiarare con `Protected`.</span><span class="sxs-lookup"><span data-stu-id="0507b-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>  

> [!NOTE]
> <span data-ttu-id="0507b-109">Il `Protected` modificatore di accesso può essere combinato con due altri modificatori:</span><span class="sxs-lookup"><span data-stu-id="0507b-109">The `Protected` access modifier can be combined with two other modifiers:</span></span>
> - <span data-ttu-id="0507b-110">Il [Protected Friend](protected-friend.md) modificatore rende accessibile dall'interno di tale classe, dalle classi derivate e allo stesso assembly in cui è definita la classe un membro di classe.</span><span class="sxs-lookup"><span data-stu-id="0507b-110">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> 
> - <span data-ttu-id="0507b-111">Il [privato protetto](private-protected.md) modificatore rende accessibile un membro di classe da tipi derivati, ma solo all'interno del relativo assembly che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="0507b-111">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>
  
## <a name="rules"></a><span data-ttu-id="0507b-112">Regole</span><span class="sxs-lookup"><span data-stu-id="0507b-112">Rules</span></span>  
  
-   <span data-ttu-id="0507b-113">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="0507b-113">**Declaration Context.**</span></span> <span data-ttu-id="0507b-114">È possibile utilizzare `Protected` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="0507b-114">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="0507b-115">Ciò significa che il contesto della dichiarazione per un `Protected` elemento deve essere una classe e non può essere un file di origine, lo spazio dei nomi, interfaccia, modulo, struttura o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="0507b-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  

## <a name="behavior"></a><span data-ttu-id="0507b-116">Comportamento</span><span class="sxs-lookup"><span data-stu-id="0507b-116">Behavior</span></span>  
  
-   <span data-ttu-id="0507b-117">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="0507b-117">**Access Level.**</span></span> <span data-ttu-id="0507b-118">Tutto il codice in una classe possa accedere ai relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="0507b-118">All code in a class can access its elements.</span></span> <span data-ttu-id="0507b-119">Codice di qualsiasi classe che deriva da una classe di base può accedere a tutti i `Protected` gli elementi della classe di base.</span><span class="sxs-lookup"><span data-stu-id="0507b-119">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="0507b-120">Questo vale per tutte le generazioni di derivazione.</span><span class="sxs-lookup"><span data-stu-id="0507b-120">This is true for all generations of derivation.</span></span> <span data-ttu-id="0507b-121">Ciò significa che possa accedere a una classe `Protected` gli elementi della classe di base della classe base e così via.</span><span class="sxs-lookup"><span data-stu-id="0507b-121">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>  
  
     <span data-ttu-id="0507b-122">Accesso protetto non è un superset o un sottoinsieme di accesso friend.</span><span class="sxs-lookup"><span data-stu-id="0507b-122">Protected access is not a superset or subset of friend access.</span></span>  
  
-   <span data-ttu-id="0507b-123">**Modificatori di accesso.**</span><span class="sxs-lookup"><span data-stu-id="0507b-123">**Access Modifiers.**</span></span> <span data-ttu-id="0507b-124">Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="0507b-124">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="0507b-125">Per un confronto tra i modificatori di accesso, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0507b-125">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="0507b-126">Il modificatore `Protected` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0507b-126">The `Protected` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="0507b-127">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="0507b-127">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="0507b-128">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="0507b-128">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="0507b-129">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="0507b-129">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="0507b-130">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="0507b-130">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="0507b-131">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="0507b-131">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="0507b-132">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="0507b-132">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="0507b-133">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="0507b-133">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="0507b-134">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="0507b-134">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="0507b-135">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="0507b-135">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="0507b-136">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="0507b-136">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="0507b-137">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="0507b-137">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="0507b-138">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="0507b-138">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0507b-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0507b-139">See Also</span></span>  
 [<span data-ttu-id="0507b-140">Public</span><span class="sxs-lookup"><span data-stu-id="0507b-140">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="0507b-141">Friend</span><span class="sxs-lookup"><span data-stu-id="0507b-141">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="0507b-142">Private</span><span class="sxs-lookup"><span data-stu-id="0507b-142">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 <span data-ttu-id="0507b-143">[Protetto privato](private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="0507b-143">[Private Protected](private-protected.md) </span></span>  
 <span data-ttu-id="0507b-144">[Protected Friend](protected-friend.md) </span><span class="sxs-lookup"><span data-stu-id="0507b-144">[Protected Friend](protected-friend.md) </span></span>  
 [<span data-ttu-id="0507b-145">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0507b-145">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="0507b-146">Routine</span><span class="sxs-lookup"><span data-stu-id="0507b-146">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="0507b-147">Strutture</span><span class="sxs-lookup"><span data-stu-id="0507b-147">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="0507b-148">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="0507b-148">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
