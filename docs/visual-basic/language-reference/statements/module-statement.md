---
title: Istruzione Module
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 51f8fd063449c072a69cdffd9f6ce2a96cc3f68c
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="module-statement"></a><span data-ttu-id="8ccae-102">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="8ccae-102">Module Statement</span></span>
<span data-ttu-id="8ccae-103">Dichiara il nome di un modulo e introduce la definizione di variabili, proprietà, eventi ed procedure che comprende il modulo.</span><span class="sxs-lookup"><span data-stu-id="8ccae-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ccae-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ccae-104">Syntax</span></span>  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a><span data-ttu-id="8ccae-105">Parti</span><span class="sxs-lookup"><span data-stu-id="8ccae-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="8ccae-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8ccae-106">Optional.</span></span> <span data-ttu-id="8ccae-107">Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="8ccae-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="8ccae-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8ccae-108">Optional.</span></span> <span data-ttu-id="8ccae-109">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ccae-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="8ccae-110">Public</span><span class="sxs-lookup"><span data-stu-id="8ccae-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [<span data-ttu-id="8ccae-111">Friend</span><span class="sxs-lookup"><span data-stu-id="8ccae-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 <span data-ttu-id="8ccae-112">Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8ccae-112">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `name`  
 <span data-ttu-id="8ccae-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8ccae-113">Required.</span></span> <span data-ttu-id="8ccae-114">Nome di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="8ccae-114">Name of this module.</span></span> <span data-ttu-id="8ccae-115">Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="8ccae-115">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `statements`  
 <span data-ttu-id="8ccae-116">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8ccae-116">Optional.</span></span> <span data-ttu-id="8ccae-117">Istruzioni che definiscono le variabili, proprietà, eventi, procedure e tipi annidati di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="8ccae-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>  
  
 `End Module`  
 <span data-ttu-id="8ccae-118">Termina il `Module` definizione.</span><span class="sxs-lookup"><span data-stu-id="8ccae-118">Terminates the `Module` definition.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ccae-119">Note</span><span class="sxs-lookup"><span data-stu-id="8ccae-119">Remarks</span></span>  
 <span data-ttu-id="8ccae-120">Oggetto `Module` istruzione definisce un tipo di riferimento disponibile in tutto lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8ccae-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="8ccae-121">A *modulo* (detto anche un *modulo standard*) è simile a una classe, ma con alcune differenze importanti.</span><span class="sxs-lookup"><span data-stu-id="8ccae-121">A *module* (sometimes called a *standard module*)is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="8ccae-122">Ogni modulo ha esattamente un'istanza e non devono essere creati o assegnati a una variabile.</span><span class="sxs-lookup"><span data-stu-id="8ccae-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="8ccae-123">I moduli non supportano l'ereditarietà o implementare interfacce.</span><span class="sxs-lookup"><span data-stu-id="8ccae-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="8ccae-124">Si noti che un modulo non è un *tipo* nel senso che è una classe o struttura, è possibile dichiarare un elemento di programmazione per il tipo di dati di un modulo.</span><span class="sxs-lookup"><span data-stu-id="8ccae-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>  
  
 <span data-ttu-id="8ccae-125">È possibile utilizzare `Module` solo a livello di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8ccae-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="8ccae-126">Ciò significa che il *contesto della dichiarazione* per un modulo deve essere un file di origine o di spazio dei nomi e non può essere una classe, struttura, modulo, interfaccia, routine o blocco.</span><span class="sxs-lookup"><span data-stu-id="8ccae-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="8ccae-127">È possibile nidificare un modulo all'interno di un altro modulo o all'interno di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="8ccae-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="8ccae-128">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8ccae-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="8ccae-129">Un modulo con la stessa durata del programma.</span><span class="sxs-lookup"><span data-stu-id="8ccae-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="8ccae-130">Poiché i relativi membri sono tutti `Shared`, hanno anche una durata uguale a quella del programma.</span><span class="sxs-lookup"><span data-stu-id="8ccae-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>  
  
 <span data-ttu-id="8ccae-131">Per impostazione predefinita i moduli [Friend](../../../visual-basic/language-reference/modifiers/friend.md) accesso.</span><span class="sxs-lookup"><span data-stu-id="8ccae-131">Modules default to [Friend](../../../visual-basic/language-reference/modifiers/friend.md) access.</span></span> <span data-ttu-id="8ccae-132">È possibile regolare i livelli di accesso con i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="8ccae-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="8ccae-133">Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8ccae-133">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="8ccae-134">Tutti i membri di un modulo sono implicitamente `Shared`.</span><span class="sxs-lookup"><span data-stu-id="8ccae-134">All members of a module are implicitly `Shared`.</span></span>  
  
## <a name="classes-and-modules"></a><span data-ttu-id="8ccae-135">Classi e moduli</span><span class="sxs-lookup"><span data-stu-id="8ccae-135">Classes and Modules</span></span>  
 <span data-ttu-id="8ccae-136">Questi elementi presentano molte analogie, ma esistono alcune importanti differenze.</span><span class="sxs-lookup"><span data-stu-id="8ccae-136">These elements have many similarities, but there are some important differences as well.</span></span>  
  
-   <span data-ttu-id="8ccae-137">**Terminologia.**</span><span class="sxs-lookup"><span data-stu-id="8ccae-137">**Terminology.**</span></span> <span data-ttu-id="8ccae-138">Due tipi di moduli di riconoscere le versioni precedenti di Visual Basic: *moduli di classe* (file CLS) e *moduli standard* (file BAS).</span><span class="sxs-lookup"><span data-stu-id="8ccae-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="8ccae-139">La versione corrente chiama questi *classi* e *moduli*, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="8ccae-139">The current version calls these *classes* and *modules*, respectively.</span></span>  
  
-   <span data-ttu-id="8ccae-140">**Membri condivisi.**</span><span class="sxs-lookup"><span data-stu-id="8ccae-140">**Shared Members.**</span></span> <span data-ttu-id="8ccae-141">È possibile controllare se è un oggetto condiviso di un membro di una classe o membro di istanza.</span><span class="sxs-lookup"><span data-stu-id="8ccae-141">You can control whether a member of a class is a shared or instance member.</span></span>  
  
-   <span data-ttu-id="8ccae-142">**Orientamento agli oggetti.**</span><span class="sxs-lookup"><span data-stu-id="8ccae-142">**Object Orientation.**</span></span> <span data-ttu-id="8ccae-143">Classi sono orientata agli oggetti, ma non sono moduli.</span><span class="sxs-lookup"><span data-stu-id="8ccae-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="8ccae-144">Pertanto sola classi possono essere implementate come oggetti.</span><span class="sxs-lookup"><span data-stu-id="8ccae-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="8ccae-145">Per ulteriori informazioni, vedere [oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="8ccae-145">For more information, see [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8ccae-146">Regole</span><span class="sxs-lookup"><span data-stu-id="8ccae-146">Rules</span></span>  
  
-   <span data-ttu-id="8ccae-147">**Modificatori.**</span><span class="sxs-lookup"><span data-stu-id="8ccae-147">**Modifiers.**</span></span> <span data-ttu-id="8ccae-148">Tutti i membri del modulo sono implicitamente [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="8ccae-148">All module members are implicitly [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="8ccae-149">Non è possibile utilizzare il `Shared` (parola chiave) quando si dichiara un membro se non è possibile modificare lo stato condiviso tra i membri.</span><span class="sxs-lookup"><span data-stu-id="8ccae-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>  
  
-   <span data-ttu-id="8ccae-150">**Ereditarietà.**</span><span class="sxs-lookup"><span data-stu-id="8ccae-150">**Inheritance.**</span></span> <span data-ttu-id="8ccae-151">Un modulo non può ereditare da qualsiasi tipo diverso da <xref:System.Object>, ereditare da tutti i moduli.</span><span class="sxs-lookup"><span data-stu-id="8ccae-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="8ccae-152">In particolare, un modulo non può ereditare da un altro.</span><span class="sxs-lookup"><span data-stu-id="8ccae-152">In particular, one module cannot inherit from another.</span></span>  
  
     <span data-ttu-id="8ccae-153">Non è possibile utilizzare il [istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md) nella definizione di un modulo, anche per specificare <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="8ccae-153">You cannot use the [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>  
  
-   <span data-ttu-id="8ccae-154">**Proprietà predefinita.**</span><span class="sxs-lookup"><span data-stu-id="8ccae-154">**Default Property.**</span></span> <span data-ttu-id="8ccae-155">È possibile definire le proprietà predefinite in un modulo.</span><span class="sxs-lookup"><span data-stu-id="8ccae-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="8ccae-156">Per ulteriori informazioni, vedere [predefinito](../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="8ccae-156">For more information, see [Default](../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="8ccae-157">Comportamento</span><span class="sxs-lookup"><span data-stu-id="8ccae-157">Behavior</span></span>  
  
-   <span data-ttu-id="8ccae-158">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="8ccae-158">**Access Level.**</span></span> <span data-ttu-id="8ccae-159">All'interno di un modulo, è possibile dichiarare ogni membro con il proprio livello di accesso.</span><span class="sxs-lookup"><span data-stu-id="8ccae-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="8ccae-160">Per impostazione predefinita ai membri del modulo [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accedere, ad eccezione delle variabili e costanti, il valore predefinito per [privata](../../../visual-basic/language-reference/modifiers/private.md) accesso.</span><span class="sxs-lookup"><span data-stu-id="8ccae-160">Module members default to [Public](../../../visual-basic/language-reference/modifiers/public.md) access, except variables and constants, which default to [Private](../../../visual-basic/language-reference/modifiers/private.md) access.</span></span> <span data-ttu-id="8ccae-161">Quando un modulo ha più limitato l'accesso a uno dei relativi membri, il livello di accesso del modulo specificato ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="8ccae-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>  
  
-   <span data-ttu-id="8ccae-162">**Ambito.**</span><span class="sxs-lookup"><span data-stu-id="8ccae-162">**Scope.**</span></span> <span data-ttu-id="8ccae-163">Un modulo è incluso nell'ambito dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8ccae-163">A module is in scope throughout its namespace.</span></span>  
  
     <span data-ttu-id="8ccae-164">L'ambito di ogni membro di modulo è l'intero modulo.</span><span class="sxs-lookup"><span data-stu-id="8ccae-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="8ccae-165">Si noti che è possibile eseguire tutti i membri *promozione del tipo*, che comporta l'ambito da innalzare di livello allo spazio dei nomi che contiene il modulo.</span><span class="sxs-lookup"><span data-stu-id="8ccae-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="8ccae-166">Per ulteriori informazioni, vedere [promozione tipo](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="8ccae-166">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
-   <span data-ttu-id="8ccae-167">**Qualifica.**</span><span class="sxs-lookup"><span data-stu-id="8ccae-167">**Qualification.**</span></span> <span data-ttu-id="8ccae-168">È possibile più moduli in un progetto che è possibile dichiarare membri con lo stesso nome in due o più moduli.</span><span class="sxs-lookup"><span data-stu-id="8ccae-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="8ccae-169">Tuttavia, è necessario qualificare ogni riferimento a tale membro con il nome del modulo appropriato se il riferimento si trova all'esterno del modulo.</span><span class="sxs-lookup"><span data-stu-id="8ccae-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="8ccae-170">Per ulteriori informazioni, vedere [riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="8ccae-170">For more information, see [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ccae-171">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ccae-171">Example</span></span>  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8ccae-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ccae-172">See Also</span></span>  
 [<span data-ttu-id="8ccae-173">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="8ccae-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="8ccae-174">Istruzione Namespace</span><span class="sxs-lookup"><span data-stu-id="8ccae-174">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="8ccae-175">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="8ccae-175">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="8ccae-176">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="8ccae-176">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="8ccae-177">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="8ccae-177">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="8ccae-178">Promozione tipo</span><span class="sxs-lookup"><span data-stu-id="8ccae-178">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
