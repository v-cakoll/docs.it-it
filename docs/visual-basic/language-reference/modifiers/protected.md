---
title: Protetto
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
ms.openlocfilehash: 740c998b8a6ccc6798bce37e9b08e408dac7c17d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351308"
---
# <a name="protected-visual-basic"></a><span data-ttu-id="882f3-102">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="882f3-102">Protected (Visual Basic)</span></span>

<span data-ttu-id="882f3-103">Un modificatore di accesso ai membri che specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dall'interno della propria classe o da una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="882f3-103">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>

## <a name="remarks"></a><span data-ttu-id="882f3-104">Note</span><span class="sxs-lookup"><span data-stu-id="882f3-104">Remarks</span></span>

<span data-ttu-id="882f3-105">A volte un elemento di programmazione dichiarato in una classe contiene dati sensibili o codice limitato e si vuole limitare l'accesso all'elemento.</span><span class="sxs-lookup"><span data-stu-id="882f3-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="882f3-106">Tuttavia, se la classe è ereditabile e si prevede una gerarchia di classi derivate, potrebbe essere necessario che queste classi derivate accedano ai dati o al codice.</span><span class="sxs-lookup"><span data-stu-id="882f3-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="882f3-107">In tal caso, è necessario che l'elemento sia accessibile sia dalla classe di base che da tutte le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="882f3-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="882f3-108">Per limitare l'accesso a un elemento in questo modo, è possibile dichiararlo con `Protected`.</span><span class="sxs-lookup"><span data-stu-id="882f3-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>

> [!NOTE]
> <span data-ttu-id="882f3-109">Il modificatore di accesso `Protected` può essere combinato con altri due modificatori:</span><span class="sxs-lookup"><span data-stu-id="882f3-109">The `Protected` access modifier can be combined with two other modifiers:</span></span>
>
> - <span data-ttu-id="882f3-110">Il modificatore [Friend protetto](protected-friend.md) rende accessibile un membro della classe da tale classe, dalle classi derivate e dallo stesso assembly in cui è definita la classe.</span><span class="sxs-lookup"><span data-stu-id="882f3-110">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span>
> - <span data-ttu-id="882f3-111">Il modificatore [protected privato](private-protected.md) rende accessibile a un membro della classe i tipi derivati, ma solo all'interno dell'assembly che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="882f3-111">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="882f3-112">Regole</span><span class="sxs-lookup"><span data-stu-id="882f3-112">Rules</span></span>

<span data-ttu-id="882f3-113">**Contesto di dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="882f3-113">**Declaration Context.**</span></span> <span data-ttu-id="882f3-114">È possibile utilizzare `Protected` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="882f3-114">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="882f3-115">Ciò significa che il contesto di dichiarazione per un elemento di `Protected` deve essere una classe e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una struttura o una procedura.</span><span class="sxs-lookup"><span data-stu-id="882f3-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="882f3-116">Comportamento</span><span class="sxs-lookup"><span data-stu-id="882f3-116">Behavior</span></span>

- <span data-ttu-id="882f3-117">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="882f3-117">**Access Level.**</span></span> <span data-ttu-id="882f3-118">Tutto il codice in una classe può accedere ai relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="882f3-118">All code in a class can access its elements.</span></span> <span data-ttu-id="882f3-119">Il codice in qualsiasi classe che deriva da una classe base può accedere a tutti gli elementi `Protected` della classe di base.</span><span class="sxs-lookup"><span data-stu-id="882f3-119">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="882f3-120">Questo vale per tutte le generazioni di derivazione.</span><span class="sxs-lookup"><span data-stu-id="882f3-120">This is true for all generations of derivation.</span></span> <span data-ttu-id="882f3-121">Ciò significa che una classe può accedere a `Protected` elementi della classe di base della classe di base e così via.</span><span class="sxs-lookup"><span data-stu-id="882f3-121">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>

     <span data-ttu-id="882f3-122">L'accesso protetto non è un superset o un subset di accesso Friend.</span><span class="sxs-lookup"><span data-stu-id="882f3-122">Protected access is not a superset or subset of friend access.</span></span>

- <span data-ttu-id="882f3-123">**Modificatori di accesso.**</span><span class="sxs-lookup"><span data-stu-id="882f3-123">**Access Modifiers.**</span></span> <span data-ttu-id="882f3-124">Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="882f3-124">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="882f3-125">Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="882f3-125">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="882f3-126">Il modificatore `Protected` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="882f3-126">The `Protected` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="882f3-127">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="882f3-127">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)

- [<span data-ttu-id="882f3-128">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="882f3-128">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="882f3-129">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="882f3-129">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- [<span data-ttu-id="882f3-130">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="882f3-130">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [<span data-ttu-id="882f3-131">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="882f3-131">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- [<span data-ttu-id="882f3-132">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="882f3-132">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)

- [<span data-ttu-id="882f3-133">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="882f3-133">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="882f3-134">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="882f3-134">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="882f3-135">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="882f3-135">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)

- [<span data-ttu-id="882f3-136">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="882f3-136">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="882f3-137">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="882f3-137">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

- [<span data-ttu-id="882f3-138">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="882f3-138">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="882f3-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="882f3-139">See also</span></span>

- [<span data-ttu-id="882f3-140">Public</span><span class="sxs-lookup"><span data-stu-id="882f3-140">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="882f3-141">Friend</span><span class="sxs-lookup"><span data-stu-id="882f3-141">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="882f3-142">Private</span><span class="sxs-lookup"><span data-stu-id="882f3-142">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="882f3-143">Private Protected</span><span class="sxs-lookup"><span data-stu-id="882f3-143">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="882f3-144">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="882f3-144">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="882f3-145">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="882f3-145">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="882f3-146">Routine</span><span class="sxs-lookup"><span data-stu-id="882f3-146">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="882f3-147">Strutture</span><span class="sxs-lookup"><span data-stu-id="882f3-147">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="882f3-148">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="882f3-148">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
