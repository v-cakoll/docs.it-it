---
title: Shadows
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: 7aed6bec21bd484cca019b061bd5915de13a9eb8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402707"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="c2383-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2383-102">Shadows (Visual Basic)</span></span>

<span data-ttu-id="c2383-103">Specifica che un elemento di programmazione dichiarato ridichiara e nasconde un elemento con nome identico o un set di elementi in overload in una classe base.</span><span class="sxs-lookup"><span data-stu-id="c2383-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>

## <a name="remarks"></a><span data-ttu-id="c2383-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="c2383-104">Remarks</span></span>

<span data-ttu-id="c2383-105">Lo scopo principale dello shadowing, noto anche come *nascondiglio per nome*, è quello di mantenere la definizione dei membri della classe.</span><span class="sxs-lookup"><span data-stu-id="c2383-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="c2383-106">La classe base può subire una modifica che crea un elemento con lo stesso nome di uno già definito.</span><span class="sxs-lookup"><span data-stu-id="c2383-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="c2383-107">In tal caso, il `Shadows` modificatore impone la risoluzione dei riferimenti attraverso la classe al membro definito, anziché al nuovo elemento della classe di base.</span><span class="sxs-lookup"><span data-stu-id="c2383-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>

<span data-ttu-id="c2383-108">Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali.</span><span class="sxs-lookup"><span data-stu-id="c2383-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="c2383-109">Per ulteriori informazioni, vedere [shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="c2383-109">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>

## <a name="rules"></a><span data-ttu-id="c2383-110">Regole</span><span class="sxs-lookup"><span data-stu-id="c2383-110">Rules</span></span>

- <span data-ttu-id="c2383-111">\*\*Contesto della dichiarazione. \*\*</span><span class="sxs-lookup"><span data-stu-id="c2383-111">**Declaration Context.**</span></span> <span data-ttu-id="c2383-112">È possibile usare `Shadows` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="c2383-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="c2383-113">Ciò significa che il contesto di dichiarazione per un `Shadows` elemento deve essere una classe e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una struttura o una procedura.</span><span class="sxs-lookup"><span data-stu-id="c2383-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

  <span data-ttu-id="c2383-114">In una singola istruzione di dichiarazione è possibile dichiarare un solo elemento shadowing.</span><span class="sxs-lookup"><span data-stu-id="c2383-114">You can declare only one shadowing element in a single declaration statement.</span></span>

- <span data-ttu-id="c2383-115">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="c2383-115">**Combined Modifiers.**</span></span> <span data-ttu-id="c2383-116">Non è possibile specificare `Shadows` insieme a `Overloads` , `Overrides` o `Static` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="c2383-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>

- <span data-ttu-id="c2383-117">**Tipi di elemento.**</span><span class="sxs-lookup"><span data-stu-id="c2383-117">**Element Types.**</span></span> <span data-ttu-id="c2383-118">È possibile nascondere qualsiasi tipo di elemento dichiarato con qualsiasi altro tipo.</span><span class="sxs-lookup"><span data-stu-id="c2383-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="c2383-119">Se si nasconde una proprietà o una routine con un'altra proprietà o routine, i parametri e il tipo restituito non devono corrispondere a quelli della routine o della proprietà della classe base.</span><span class="sxs-lookup"><span data-stu-id="c2383-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>

- <span data-ttu-id="c2383-120">**Accesso.**</span><span class="sxs-lookup"><span data-stu-id="c2383-120">**Accessing.**</span></span> <span data-ttu-id="c2383-121">L'elemento ombreggiato nella classe base non è in genere disponibile all'interno della classe derivata che lo nasconde.</span><span class="sxs-lookup"><span data-stu-id="c2383-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="c2383-122">Tuttavia, si applicano le considerazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c2383-122">However, the following considerations apply.</span></span>

  - <span data-ttu-id="c2383-123">Se l'elemento shadowing non è accessibile dal codice che vi fa riferimento, il riferimento viene risolto nell'elemento ombreggiato.</span><span class="sxs-lookup"><span data-stu-id="c2383-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="c2383-124">Se, ad esempio, un `Private` elemento nasconde un elemento della classe base, il codice che non dispone dell'autorizzazione per accedere all'elemento `Private` accede all'elemento della classe di base.</span><span class="sxs-lookup"><span data-stu-id="c2383-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>

  - <span data-ttu-id="c2383-125">Se si nasconde un elemento, è comunque possibile accedere all'elemento ombreggiato tramite un oggetto dichiarato con il tipo della classe di base.</span><span class="sxs-lookup"><span data-stu-id="c2383-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="c2383-126">È anche possibile accedervi tramite `MyBase` .</span><span class="sxs-lookup"><span data-stu-id="c2383-126">You can also access it through `MyBase`.</span></span>

<span data-ttu-id="c2383-127">Il modificatore `Shadows` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2383-127">The `Shadows` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="c2383-128">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="c2383-128">Class Statement</span></span>](../statements/class-statement.md)

- [<span data-ttu-id="c2383-129">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="c2383-129">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="c2383-130">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="c2383-130">Declare Statement</span></span>](../statements/declare-statement.md)

- [<span data-ttu-id="c2383-131">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="c2383-131">Delegate Statement</span></span>](../statements/delegate-statement.md)

- [<span data-ttu-id="c2383-132">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="c2383-132">Dim Statement</span></span>](../statements/dim-statement.md)

- [<span data-ttu-id="c2383-133">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="c2383-133">Enum Statement</span></span>](../statements/enum-statement.md)

- [<span data-ttu-id="c2383-134">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="c2383-134">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="c2383-135">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="c2383-135">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="c2383-136">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="c2383-136">Interface Statement</span></span>](../statements/interface-statement.md)

- [<span data-ttu-id="c2383-137">Property Statement</span><span class="sxs-lookup"><span data-stu-id="c2383-137">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="c2383-138">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="c2383-138">Structure Statement</span></span>](../statements/structure-statement.md)

- [<span data-ttu-id="c2383-139">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="c2383-139">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="c2383-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2383-140">See also</span></span>

- [<span data-ttu-id="c2383-141">Condivisa</span><span class="sxs-lookup"><span data-stu-id="c2383-141">Shared</span></span>](shared.md)
- [<span data-ttu-id="c2383-142">Statico</span><span class="sxs-lookup"><span data-stu-id="c2383-142">Static</span></span>](static.md)
- [<span data-ttu-id="c2383-143">Privata</span><span class="sxs-lookup"><span data-stu-id="c2383-143">Private</span></span>](private.md)
- [<span data-ttu-id="c2383-144">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="c2383-144">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="c2383-145">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="c2383-145">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="c2383-146">MustOverride</span><span class="sxs-lookup"><span data-stu-id="c2383-146">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="c2383-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="c2383-147">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="c2383-148">Overload</span><span class="sxs-lookup"><span data-stu-id="c2383-148">Overloads</span></span>](overloads.md)
- [<span data-ttu-id="c2383-149">Overridable</span><span class="sxs-lookup"><span data-stu-id="c2383-149">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="c2383-150">Override</span><span class="sxs-lookup"><span data-stu-id="c2383-150">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="c2383-151">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c2383-151">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
