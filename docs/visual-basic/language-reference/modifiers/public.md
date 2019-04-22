---
title: Public (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 0c85564503f3c83e436044cd92ee3014945f1ef3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818384"
---
# <a name="public-visual-basic"></a><span data-ttu-id="9d67a-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d67a-102">Public (Visual Basic)</span></span>
<span data-ttu-id="9d67a-103">Specifica che uno o più elementi di programmazione dichiarati non sono restrizioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="9d67a-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d67a-104">Note</span><span class="sxs-lookup"><span data-stu-id="9d67a-104">Remarks</span></span>  
 <span data-ttu-id="9d67a-105">Se si sta pubblicando un componente o un set di componenti, ad esempio una libreria di classi, è consigliabile in genere gli elementi di programmazione sia accessibile da qualsiasi codice che interagisce con l'assembly.</span><span class="sxs-lookup"><span data-stu-id="9d67a-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="9d67a-106">Per conferire tale accesso illimitato a un elemento, è possibile dichiararla con `Public`.</span><span class="sxs-lookup"><span data-stu-id="9d67a-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="9d67a-107">L'accesso pubblico è il livello normale per un elemento di programmazione quando non è necessario limitare l'accesso a esso.</span><span class="sxs-lookup"><span data-stu-id="9d67a-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="9d67a-108">Si noti che il livello di accesso di un elemento dichiarato all'interno di un'interfaccia, modulo, classe o struttura per impostazione predefinita `Public` se non si dichiara in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="9d67a-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9d67a-109">Regole</span><span class="sxs-lookup"><span data-stu-id="9d67a-109">Rules</span></span>  
  
-   <span data-ttu-id="9d67a-110">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="9d67a-110">**Declaration Context.**</span></span> <span data-ttu-id="9d67a-111">È possibile usare `Public` solo a livello di modulo, interfaccia o dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9d67a-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="9d67a-112">Ciò significa che il contesto della dichiarazione per un `Public` elemento deve essere un file di origine, lo spazio dei nomi, interfaccia, modulo, classe o struttura e non può essere una procedura.</span><span class="sxs-lookup"><span data-stu-id="9d67a-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="9d67a-113">Comportamento</span><span class="sxs-lookup"><span data-stu-id="9d67a-113">Behavior</span></span>  
  
-   <span data-ttu-id="9d67a-114">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="9d67a-114">**Access Level.**</span></span> <span data-ttu-id="9d67a-115">Tutto il codice che può accedere a un modulo, classe o struttura può accedere ai relativi `Public` elementi.</span><span class="sxs-lookup"><span data-stu-id="9d67a-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
-   <span data-ttu-id="9d67a-116">**Accesso predefinito.**</span><span class="sxs-lookup"><span data-stu-id="9d67a-116">**Default Access.**</span></span> <span data-ttu-id="9d67a-117">Le variabili locali all'interno di una routine per impostazione predefinita per l'accesso pubblico ed è possono usare modificatori di accesso su di essi.</span><span class="sxs-lookup"><span data-stu-id="9d67a-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
-   <span data-ttu-id="9d67a-118">**Modificatori di accesso.**</span><span class="sxs-lookup"><span data-stu-id="9d67a-118">**Access Modifiers.**</span></span> <span data-ttu-id="9d67a-119">Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="9d67a-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="9d67a-120">Per un confronto tra i modificatori di accesso, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9d67a-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="9d67a-121">Il modificatore `Public` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d67a-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="9d67a-122">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="9d67a-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="9d67a-123">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="9d67a-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="9d67a-124">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="9d67a-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="9d67a-125">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="9d67a-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="9d67a-126">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="9d67a-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="9d67a-127">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="9d67a-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="9d67a-128">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="9d67a-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="9d67a-129">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="9d67a-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="9d67a-130">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="9d67a-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="9d67a-131">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="9d67a-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="9d67a-132">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="9d67a-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="9d67a-133">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="9d67a-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="9d67a-134">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="9d67a-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="9d67a-135">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="9d67a-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="9d67a-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d67a-136">See also</span></span>

- [<span data-ttu-id="9d67a-137">Protected</span><span class="sxs-lookup"><span data-stu-id="9d67a-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="9d67a-138">Friend</span><span class="sxs-lookup"><span data-stu-id="9d67a-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="9d67a-139">Private</span><span class="sxs-lookup"><span data-stu-id="9d67a-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="9d67a-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="9d67a-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="9d67a-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="9d67a-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="9d67a-142">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9d67a-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="9d67a-143">Routine</span><span class="sxs-lookup"><span data-stu-id="9d67a-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="9d67a-144">Strutture</span><span class="sxs-lookup"><span data-stu-id="9d67a-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="9d67a-145">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="9d67a-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
