---
title: Pubblico
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
# <a name="public-visual-basic"></a><span data-ttu-id="87d87-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87d87-102">Public (Visual Basic)</span></span>
<span data-ttu-id="87d87-103">Specifica che uno o più elementi di programmazione dichiarati non hanno restrizioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="87d87-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87d87-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="87d87-104">Remarks</span></span>  
 <span data-ttu-id="87d87-105">Se si pubblica un componente o un set di componenti, ad esempio una libreria di classi, in genere si vuole che gli elementi di programmazione siano accessibili da qualsiasi codice che interagisce con l'assembly.</span><span class="sxs-lookup"><span data-stu-id="87d87-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="87d87-106">Per conferire l'accesso illimitato a un elemento, è possibile dichiararlo con `Public`.</span><span class="sxs-lookup"><span data-stu-id="87d87-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="87d87-107">L'accesso pubblico è il livello normale per un elemento di programmazione quando non è necessario limitarne l'accesso.</span><span class="sxs-lookup"><span data-stu-id="87d87-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="87d87-108">Si noti che il livello di accesso di un elemento dichiarato all'interno di un'interfaccia, di un modulo, di una classe o di una struttura viene impostato su `Public` se non viene dichiarato in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="87d87-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="87d87-109">Regole</span><span class="sxs-lookup"><span data-stu-id="87d87-109">Rules</span></span>  
  
- <span data-ttu-id="87d87-110">**Contesto di dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="87d87-110">**Declaration Context.**</span></span> <span data-ttu-id="87d87-111">È possibile usare `Public` solo a livello di modulo, interfaccia o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="87d87-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="87d87-112">Ciò significa che il contesto di dichiarazione per un elemento di `Public` deve essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una classe o una struttura e non può essere una routine.</span><span class="sxs-lookup"><span data-stu-id="87d87-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="87d87-113">Comportamento</span><span class="sxs-lookup"><span data-stu-id="87d87-113">Behavior</span></span>  
  
- <span data-ttu-id="87d87-114">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="87d87-114">**Access Level.**</span></span> <span data-ttu-id="87d87-115">Tutto il codice che può accedere a un modulo, una classe o una struttura può accedere ai relativi elementi `Public`.</span><span class="sxs-lookup"><span data-stu-id="87d87-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="87d87-116">**Accesso predefinito.**</span><span class="sxs-lookup"><span data-stu-id="87d87-116">**Default Access.**</span></span> <span data-ttu-id="87d87-117">Per impostazione predefinita, le variabili locali all'interno di una stored procedure non possono usare alcun modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="87d87-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="87d87-118">**Modificatori di accesso.**</span><span class="sxs-lookup"><span data-stu-id="87d87-118">**Access Modifiers.**</span></span> <span data-ttu-id="87d87-119">Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="87d87-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="87d87-120">Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="87d87-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="87d87-121">Il modificatore `Public` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="87d87-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="87d87-122">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="87d87-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="87d87-123">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="87d87-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="87d87-124">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="87d87-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="87d87-125">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="87d87-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="87d87-126">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="87d87-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="87d87-127">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="87d87-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="87d87-128">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="87d87-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="87d87-129">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="87d87-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="87d87-130">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="87d87-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="87d87-131">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="87d87-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="87d87-132">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="87d87-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="87d87-133">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="87d87-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="87d87-134">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="87d87-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="87d87-135">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="87d87-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="87d87-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87d87-136">See also</span></span>

- [<span data-ttu-id="87d87-137">Protected</span><span class="sxs-lookup"><span data-stu-id="87d87-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="87d87-138">Friend</span><span class="sxs-lookup"><span data-stu-id="87d87-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="87d87-139">Private</span><span class="sxs-lookup"><span data-stu-id="87d87-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="87d87-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="87d87-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="87d87-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="87d87-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="87d87-142">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="87d87-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="87d87-143">Routine</span><span class="sxs-lookup"><span data-stu-id="87d87-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="87d87-144">Strutture</span><span class="sxs-lookup"><span data-stu-id="87d87-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="87d87-145">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="87d87-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
