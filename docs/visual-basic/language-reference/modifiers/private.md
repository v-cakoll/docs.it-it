---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 524f03e77e075bef08a1b41b563985de41baacb6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404810"
---
# <a name="private-visual-basic"></a><span data-ttu-id="02f9e-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02f9e-102">Private (Visual Basic)</span></span>
<span data-ttu-id="02f9e-103">Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dall'interno del contesto di dichiarazione, incluso all'interno di qualsiasi tipo contenuto.</span><span class="sxs-lookup"><span data-stu-id="02f9e-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02f9e-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="02f9e-104">Remarks</span></span>  
 <span data-ttu-id="02f9e-105">Se un elemento di programmazione rappresenta una funzionalità proprietaria o contiene dati riservati, in genere si vuole limitarne l'accesso al più possibile.</span><span class="sxs-lookup"><span data-stu-id="02f9e-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="02f9e-106">Si ottiene la massima limitazione consentendo solo il modulo, la classe o la struttura che lo definisce per accedervi.</span><span class="sxs-lookup"><span data-stu-id="02f9e-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="02f9e-107">Per limitare l'accesso a un elemento in questo modo, è possibile dichiararlo con `Private` .</span><span class="sxs-lookup"><span data-stu-id="02f9e-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="02f9e-108">È anche possibile usare il modificatore di accesso [privato protetto](private-protected.md) , che rende accessibile un membro all'interno di tale classe e dalle classi derivate presenti nell'assembly contenitore.</span><span class="sxs-lookup"><span data-stu-id="02f9e-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="02f9e-109">Regole</span><span class="sxs-lookup"><span data-stu-id="02f9e-109">Rules</span></span>  

- <span data-ttu-id="02f9e-110">\*\*Contesto della dichiarazione. \*\*</span><span class="sxs-lookup"><span data-stu-id="02f9e-110">**Declaration Context.**</span></span> <span data-ttu-id="02f9e-111">Si può usare `Private` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="02f9e-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="02f9e-112">Ciò significa che il contesto di dichiarazione per un `Private` elemento deve essere un modulo, una classe o una struttura e non può essere un file di origine, uno spazio dei nomi, un'interfaccia o una routine.</span><span class="sxs-lookup"><span data-stu-id="02f9e-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="02f9e-113">Comportamento</span><span class="sxs-lookup"><span data-stu-id="02f9e-113">Behavior</span></span>  
  
- <span data-ttu-id="02f9e-114">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="02f9e-114">**Access Level.**</span></span> <span data-ttu-id="02f9e-115">Tutto il codice all'interno di un contesto di dichiarazione può accedere ai relativi `Private` elementi.</span><span class="sxs-lookup"><span data-stu-id="02f9e-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="02f9e-116">Incluso il codice all'interno di un tipo contenuto, ad esempio una classe annidata o un'espressione di assegnazione in un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="02f9e-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="02f9e-117">Nessun codice esterno al contesto di dichiarazione può accedere ai relativi `Private` elementi.</span><span class="sxs-lookup"><span data-stu-id="02f9e-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="02f9e-118">**Modificatori di accesso.**</span><span class="sxs-lookup"><span data-stu-id="02f9e-118">**Access Modifiers.**</span></span> <span data-ttu-id="02f9e-119">Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="02f9e-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="02f9e-120">Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="02f9e-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="02f9e-121">Il modificatore `Private` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="02f9e-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="02f9e-122">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="02f9e-122">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="02f9e-123">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="02f9e-123">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="02f9e-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="02f9e-124">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="02f9e-125">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="02f9e-125">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="02f9e-126">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="02f9e-126">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="02f9e-127">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="02f9e-127">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="02f9e-128">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="02f9e-128">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="02f9e-129">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="02f9e-129">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="02f9e-130">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="02f9e-130">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="02f9e-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="02f9e-131">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="02f9e-132">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="02f9e-132">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="02f9e-133">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="02f9e-133">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="02f9e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02f9e-134">See also</span></span>

- [<span data-ttu-id="02f9e-135">Pubblica</span><span class="sxs-lookup"><span data-stu-id="02f9e-135">Public</span></span>](public.md)
- [<span data-ttu-id="02f9e-136">Protetto</span><span class="sxs-lookup"><span data-stu-id="02f9e-136">Protected</span></span>](protected.md)
- [<span data-ttu-id="02f9e-137">Amico</span><span class="sxs-lookup"><span data-stu-id="02f9e-137">Friend</span></span>](friend.md)
- [<span data-ttu-id="02f9e-138">Privato protetto</span><span class="sxs-lookup"><span data-stu-id="02f9e-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="02f9e-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="02f9e-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="02f9e-140">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02f9e-140">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="02f9e-141">Procedure</span><span class="sxs-lookup"><span data-stu-id="02f9e-141">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="02f9e-142">Strutture</span><span class="sxs-lookup"><span data-stu-id="02f9e-142">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="02f9e-143">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="02f9e-143">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
