---
title: Shadows (Visual Basic)
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
ms.openlocfilehash: 4ca4ec48ee63b71447056a2c5cb68e8948f27ad0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604653"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="1b553-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b553-102">Shadows (Visual Basic)</span></span>
<span data-ttu-id="1b553-103">Specifica che un elemento di programmazione dichiarato ridichiara e nasconde un elemento con nome identico, o un set di elementi in overload di una classe di base.</span><span class="sxs-lookup"><span data-stu-id="1b553-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b553-104">Note</span><span class="sxs-lookup"><span data-stu-id="1b553-104">Remarks</span></span>  
 <span data-ttu-id="1b553-105">Lo scopo principale di shadowing (anche noto come *occultamento nome*) consiste nel conservare la definizione dei membri della classe.</span><span class="sxs-lookup"><span data-stu-id="1b553-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="1b553-106">La classe di base può essere sottoposto a una modifica che crea un elemento con lo stesso nome già definito.</span><span class="sxs-lookup"><span data-stu-id="1b553-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="1b553-107">In questo caso, il `Shadows` modificatore impone che fa riferimento tramite la classe deve essere risolto per il membro è definito, anziché il nuovo elemento della classe base.</span><span class="sxs-lookup"><span data-stu-id="1b553-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
 <span data-ttu-id="1b553-108">Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali.</span><span class="sxs-lookup"><span data-stu-id="1b553-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="1b553-109">Per ulteriori informazioni, vedere [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="1b553-109">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="1b553-110">Regole</span><span class="sxs-lookup"><span data-stu-id="1b553-110">Rules</span></span>  
  
-   <span data-ttu-id="1b553-111">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="1b553-111">**Declaration Context.**</span></span> <span data-ttu-id="1b553-112">È possibile utilizzare `Shadows` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="1b553-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="1b553-113">Ciò significa che il contesto della dichiarazione per un `Shadows` elemento deve essere una classe e non può essere un file di origine, lo spazio dei nomi, interfaccia, modulo, struttura o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="1b553-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
     <span data-ttu-id="1b553-114">È possibile dichiarare un solo elemento di shadowing in una singola istruzione di dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="1b553-114">You can declare only one shadowing element in a single declaration statement.</span></span>  
  
-   <span data-ttu-id="1b553-115">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="1b553-115">**Combined Modifiers.**</span></span> <span data-ttu-id="1b553-116">Non è possibile specificare `Shadows` con `Overloads`, `Overrides`, o `Static` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="1b553-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>  
  
-   <span data-ttu-id="1b553-117">**Tipi di elemento.**</span><span class="sxs-lookup"><span data-stu-id="1b553-117">**Element Types.**</span></span> <span data-ttu-id="1b553-118">È possibile nascondere qualsiasi tipo di elemento dichiarato con qualsiasi altro tipo.</span><span class="sxs-lookup"><span data-stu-id="1b553-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="1b553-119">Se si nasconde una proprietà o routine con un'altra proprietà o routine, i parametri e il tipo restituito non è affinché corrispondano a quelle nella proprietà di classe di base o della routine.</span><span class="sxs-lookup"><span data-stu-id="1b553-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>  
  
-   <span data-ttu-id="1b553-120">**L'accesso.**</span><span class="sxs-lookup"><span data-stu-id="1b553-120">**Accessing.**</span></span> <span data-ttu-id="1b553-121">L'elemento nascosto nella classe base è generalmente disponibile all'interno della classe derivata che lo nasconde.</span><span class="sxs-lookup"><span data-stu-id="1b553-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="1b553-122">Tuttavia, si applicano le considerazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1b553-122">However, the following considerations apply.</span></span>  
  
    -   <span data-ttu-id="1b553-123">Se l'elemento di shadowing non è accessibile dal codice che fa riferimento a esso, il riferimento viene risolto l'elemento nascosto.</span><span class="sxs-lookup"><span data-stu-id="1b553-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="1b553-124">Ad esempio, se un `Private` elemento nasconde un elemento della classe base, il codice che non dispone dell'autorizzazione per accedere il `Private` elemento accede invece all'elemento della classe base.</span><span class="sxs-lookup"><span data-stu-id="1b553-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>  
  
    -   <span data-ttu-id="1b553-125">Se si nasconde un elemento, è comunque possibile accedere all'elemento nascosto tramite un oggetto dichiarato con il tipo della classe di base.</span><span class="sxs-lookup"><span data-stu-id="1b553-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="1b553-126">È anche possibile accedervi tramite `MyBase`.</span><span class="sxs-lookup"><span data-stu-id="1b553-126">You can also access it through `MyBase`.</span></span>  
  
 <span data-ttu-id="1b553-127">Il modificatore `Shadows` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b553-127">The `Shadows` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="1b553-128">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="1b553-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="1b553-129">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="1b553-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="1b553-130">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="1b553-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="1b553-131">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="1b553-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="1b553-132">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="1b553-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="1b553-133">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="1b553-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="1b553-134">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="1b553-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="1b553-135">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="1b553-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="1b553-136">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="1b553-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="1b553-137">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="1b553-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="1b553-138">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="1b553-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="1b553-139">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="1b553-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1b553-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b553-140">See Also</span></span>  
 [<span data-ttu-id="1b553-141">Shared</span><span class="sxs-lookup"><span data-stu-id="1b553-141">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="1b553-142">Static</span><span class="sxs-lookup"><span data-stu-id="1b553-142">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)  
 [<span data-ttu-id="1b553-143">Private</span><span class="sxs-lookup"><span data-stu-id="1b553-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="1b553-144">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="1b553-144">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="1b553-145">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="1b553-145">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="1b553-146">MustOverride</span><span class="sxs-lookup"><span data-stu-id="1b553-146">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="1b553-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="1b553-147">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [<span data-ttu-id="1b553-148">Overload</span><span class="sxs-lookup"><span data-stu-id="1b553-148">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="1b553-149">Overridable</span><span class="sxs-lookup"><span data-stu-id="1b553-149">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="1b553-150">Overrides</span><span class="sxs-lookup"><span data-stu-id="1b553-150">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="1b553-151">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b553-151">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
