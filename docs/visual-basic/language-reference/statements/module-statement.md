---
title: Istruzione Module
ms.date: 07/20/2015
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
ms.openlocfilehash: 24a27ba41f5ac889f2f2725a2852368a4292a6fb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404455"
---
# <a name="module-statement"></a><span data-ttu-id="63fff-102">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="63fff-102">Module Statement</span></span>

<span data-ttu-id="63fff-103">Dichiara il nome di un modulo e introduce la definizione di variabili, proprietà, eventi e procedure inclusi nel modulo.</span><span class="sxs-lookup"><span data-stu-id="63fff-103">Declares the name of a module and introduces the definition of the variables, properties, events, and procedures that the module comprises.</span></span>

## <a name="syntax"></a><span data-ttu-id="63fff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63fff-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  Module name
    [ statements ]
End Module
```

## <a name="parts"></a><span data-ttu-id="63fff-105">Parti</span><span class="sxs-lookup"><span data-stu-id="63fff-105">Parts</span></span>

`attributelist`  
<span data-ttu-id="63fff-106">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="63fff-106">Optional.</span></span> <span data-ttu-id="63fff-107">Vedere [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="63fff-107">See [Attribute List](attribute-list.md).</span></span>

`accessmodifier`  
<span data-ttu-id="63fff-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="63fff-108">Optional.</span></span> <span data-ttu-id="63fff-109">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="63fff-109">Can be one of the following:</span></span>

- [<span data-ttu-id="63fff-110">Pubblica</span><span class="sxs-lookup"><span data-stu-id="63fff-110">Public</span></span>](../modifiers/public.md)

- [<span data-ttu-id="63fff-111">Amico</span><span class="sxs-lookup"><span data-stu-id="63fff-111">Friend</span></span>](../modifiers/friend.md)

<span data-ttu-id="63fff-112">Vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="63fff-112">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

`name`  
<span data-ttu-id="63fff-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="63fff-113">Required.</span></span> <span data-ttu-id="63fff-114">Nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="63fff-114">Name of this module.</span></span> <span data-ttu-id="63fff-115">Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="63fff-115">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

`statements`  
<span data-ttu-id="63fff-116">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="63fff-116">Optional.</span></span> <span data-ttu-id="63fff-117">Istruzioni che definiscono le variabili, le proprietà, gli eventi, le procedure e i tipi annidati di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="63fff-117">Statements which define the variables, properties, events, procedures, and nested types of this module.</span></span>

`End Module`  
<span data-ttu-id="63fff-118">Termina la `Module` definizione.</span><span class="sxs-lookup"><span data-stu-id="63fff-118">Terminates the `Module` definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="63fff-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="63fff-119">Remarks</span></span>

<span data-ttu-id="63fff-120">Un' `Module` istruzione definisce un tipo di riferimento disponibile in tutto il relativo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="63fff-120">A `Module` statement defines a reference type available throughout its namespace.</span></span> <span data-ttu-id="63fff-121">Un *modulo* (talvolta denominato *modulo standard*) è simile a una classe ma con alcune importanti differenze.</span><span class="sxs-lookup"><span data-stu-id="63fff-121">A *module* (sometimes called a *standard module*) is similar to a class but with some important distinctions.</span></span> <span data-ttu-id="63fff-122">Ogni modulo dispone esattamente di un'istanza e non è necessario crearlo o assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="63fff-122">Every module has exactly one instance and does not need to be created or assigned to a variable.</span></span> <span data-ttu-id="63fff-123">I moduli non supportano l'ereditarietà né implementano le interfacce.</span><span class="sxs-lookup"><span data-stu-id="63fff-123">Modules do not support inheritance or implement interfaces.</span></span> <span data-ttu-id="63fff-124">Si noti che un modulo non è un *tipo* nel senso che una classe o una struttura è: non è possibile dichiarare un elemento di programmazione per avere il tipo di dati di un modulo.</span><span class="sxs-lookup"><span data-stu-id="63fff-124">Notice that a module is not a *type* in the sense that a class or structure is — you cannot declare a programming element to have the data type of a module.</span></span>

<span data-ttu-id="63fff-125">È possibile usare `Module` solo a livello di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="63fff-125">You can use `Module` only at namespace level.</span></span> <span data-ttu-id="63fff-126">Ciò significa che il *contesto di dichiarazione* per un modulo deve essere un file di origine o uno spazio dei nomi e non può essere una classe, una struttura, un modulo, un'interfaccia, una routine o un blocco.</span><span class="sxs-lookup"><span data-stu-id="63fff-126">This means the *declaration context* for a module must be a source file or namespace, and cannot be a class, structure, module, interface, procedure, or block.</span></span> <span data-ttu-id="63fff-127">Non è possibile annidare un modulo all'interno di un altro modulo o all'interno di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="63fff-127">You cannot nest a module within another module, or within any type.</span></span> <span data-ttu-id="63fff-128">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="63fff-128">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="63fff-129">Un modulo ha la stessa durata del programma.</span><span class="sxs-lookup"><span data-stu-id="63fff-129">A module has the same lifetime as your program.</span></span> <span data-ttu-id="63fff-130">Poiché i relativi membri sono tutti `Shared` , hanno anche durate uguali a quelle del programma.</span><span class="sxs-lookup"><span data-stu-id="63fff-130">Because its members are all `Shared`, they also have lifetimes equal to that of the program.</span></span>

<span data-ttu-id="63fff-131">Per impostazione predefinita, i moduli sono con accesso [Friend](../modifiers/friend.md) .</span><span class="sxs-lookup"><span data-stu-id="63fff-131">Modules default to [Friend](../modifiers/friend.md) access.</span></span> <span data-ttu-id="63fff-132">È possibile modificare i livelli di accesso con i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="63fff-132">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="63fff-133">Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="63fff-133">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="63fff-134">Tutti i membri di un modulo sono implicitamente `Shared` .</span><span class="sxs-lookup"><span data-stu-id="63fff-134">All members of a module are implicitly `Shared`.</span></span>

## <a name="classes-and-modules"></a><span data-ttu-id="63fff-135">Classi e moduli</span><span class="sxs-lookup"><span data-stu-id="63fff-135">Classes and Modules</span></span>

<span data-ttu-id="63fff-136">Questi elementi presentano molte analogie, ma esistono anche alcune differenze importanti.</span><span class="sxs-lookup"><span data-stu-id="63fff-136">These elements have many similarities, but there are some important differences as well.</span></span>

- <span data-ttu-id="63fff-137">**Terminologia.**</span><span class="sxs-lookup"><span data-stu-id="63fff-137">**Terminology.**</span></span> <span data-ttu-id="63fff-138">Le versioni precedenti di Visual Basic riconoscono due tipi di moduli: *moduli di classe* (file con estensione CLS) e *moduli standard* (file con estensione BAS).</span><span class="sxs-lookup"><span data-stu-id="63fff-138">Previous versions of Visual Basic recognize two types of modules: *class modules* (.cls files) and *standard modules* (.bas files).</span></span> <span data-ttu-id="63fff-139">La versione corrente chiama queste *classi* e *moduli*, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="63fff-139">The current version calls these *classes* and *modules*, respectively.</span></span>

- <span data-ttu-id="63fff-140">**Membri condivisi.**</span><span class="sxs-lookup"><span data-stu-id="63fff-140">**Shared Members.**</span></span> <span data-ttu-id="63fff-141">È possibile controllare se un membro di una classe è un membro condiviso o di istanza.</span><span class="sxs-lookup"><span data-stu-id="63fff-141">You can control whether a member of a class is a shared or instance member.</span></span>

- <span data-ttu-id="63fff-142">**Orientamento dell'oggetto.**</span><span class="sxs-lookup"><span data-stu-id="63fff-142">**Object Orientation.**</span></span> <span data-ttu-id="63fff-143">Le classi sono orientate agli oggetti, ma i moduli non lo sono.</span><span class="sxs-lookup"><span data-stu-id="63fff-143">Classes are object-oriented, but modules are not.</span></span> <span data-ttu-id="63fff-144">È quindi possibile creare un'istanza di solo classi come oggetti.</span><span class="sxs-lookup"><span data-stu-id="63fff-144">So only classes can be instantiated as objects.</span></span> <span data-ttu-id="63fff-145">Per altre informazioni, vedere [oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="63fff-145">For more information, see [Objects and Classes](../../programming-guide/language-features/objects-and-classes/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="63fff-146">Regole</span><span class="sxs-lookup"><span data-stu-id="63fff-146">Rules</span></span>

- <span data-ttu-id="63fff-147">**Modificatori.**</span><span class="sxs-lookup"><span data-stu-id="63fff-147">**Modifiers.**</span></span> <span data-ttu-id="63fff-148">Tutti i membri del modulo sono [condivisi](../modifiers/shared.md)in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="63fff-148">All module members are implicitly [Shared](../modifiers/shared.md).</span></span> <span data-ttu-id="63fff-149">Non è possibile usare la `Shared` parola chiave quando si dichiara un membro e non è possibile modificare lo stato condiviso di un membro.</span><span class="sxs-lookup"><span data-stu-id="63fff-149">You cannot use the `Shared` keyword when declaring a member, and you cannot alter the shared status of any member.</span></span>

- <span data-ttu-id="63fff-150">**Ereditarietà.**</span><span class="sxs-lookup"><span data-stu-id="63fff-150">**Inheritance.**</span></span> <span data-ttu-id="63fff-151">Un modulo non può ereditare da un tipo diverso <xref:System.Object> da, da cui tutti i moduli ereditano.</span><span class="sxs-lookup"><span data-stu-id="63fff-151">A module cannot inherit from any type other than <xref:System.Object>, from which all modules inherit.</span></span> <span data-ttu-id="63fff-152">In particolare, un modulo non può ereditare da un altro modulo.</span><span class="sxs-lookup"><span data-stu-id="63fff-152">In particular, one module cannot inherit from another.</span></span>

  <span data-ttu-id="63fff-153">Non è possibile usare l' [istruzione Inherits](inherits-statement.md) in una definizione di modulo, anche per specificare <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="63fff-153">You cannot use the [Inherits Statement](inherits-statement.md) in a module definition, even to specify <xref:System.Object>.</span></span>

- <span data-ttu-id="63fff-154">**Proprietà predefinita.**</span><span class="sxs-lookup"><span data-stu-id="63fff-154">**Default Property.**</span></span> <span data-ttu-id="63fff-155">Non è possibile definire proprietà predefinite in un modulo.</span><span class="sxs-lookup"><span data-stu-id="63fff-155">You cannot define any default properties in a module.</span></span> <span data-ttu-id="63fff-156">Per ulteriori informazioni, vedere [default](../modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="63fff-156">For more information, see [Default](../modifiers/default.md).</span></span>

## <a name="behavior"></a><span data-ttu-id="63fff-157">Comportamento</span><span class="sxs-lookup"><span data-stu-id="63fff-157">Behavior</span></span>

- <span data-ttu-id="63fff-158">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="63fff-158">**Access Level.**</span></span> <span data-ttu-id="63fff-159">All'interno di un modulo, è possibile dichiarare ogni membro con il proprio livello di accesso.</span><span class="sxs-lookup"><span data-stu-id="63fff-159">Within a module, you can declare each member with its own access level.</span></span> <span data-ttu-id="63fff-160">Per impostazione predefinita, i membri del modulo hanno accesso [pubblico](../modifiers/public.md) , ad eccezione delle variabili e delle costanti, per impostazione predefinita l'accesso [privato](../modifiers/private.md) .</span><span class="sxs-lookup"><span data-stu-id="63fff-160">Module members default to [Public](../modifiers/public.md) access, except variables and constants, which default to [Private](../modifiers/private.md) access.</span></span> <span data-ttu-id="63fff-161">Quando un modulo dispone di un accesso più limitato di uno dei relativi membri, il livello di accesso del modulo specificato ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="63fff-161">When a module has more restricted access than one of its members, the specified module access level takes precedence.</span></span>

- <span data-ttu-id="63fff-162">**Ambito.**</span><span class="sxs-lookup"><span data-stu-id="63fff-162">**Scope.**</span></span> <span data-ttu-id="63fff-163">Un modulo è nell'ambito dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="63fff-163">A module is in scope throughout its namespace.</span></span>

  <span data-ttu-id="63fff-164">L'ambito di ogni membro del modulo è l'intero modulo.</span><span class="sxs-lookup"><span data-stu-id="63fff-164">The scope of every module member is the entire module.</span></span> <span data-ttu-id="63fff-165">Si noti che tutti i membri subiscono l' *innalzamento*di livello del tipo, che ne determina l'innalzamento di livello allo spazio dei nomi contenente il modulo.</span><span class="sxs-lookup"><span data-stu-id="63fff-165">Notice that all members undergo *type promotion*, which causes their scope to be promoted to the namespace containing the module.</span></span> <span data-ttu-id="63fff-166">Per ulteriori informazioni, vedere [promozione del tipo](../../programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="63fff-166">For more information, see [Type Promotion](../../programming-guide/language-features/declared-elements/type-promotion.md).</span></span>

- <span data-ttu-id="63fff-167">**Qualificazione.**</span><span class="sxs-lookup"><span data-stu-id="63fff-167">**Qualification.**</span></span> <span data-ttu-id="63fff-168">È possibile avere più moduli in un progetto ed è possibile dichiarare membri con lo stesso nome in due o più moduli.</span><span class="sxs-lookup"><span data-stu-id="63fff-168">You can have multiple modules in a project, and you can declare members with the same name in two or more modules.</span></span> <span data-ttu-id="63fff-169">Tuttavia, è necessario qualificare qualsiasi riferimento a tale membro con il nome del modulo appropriato se il riferimento è esterno al modulo.</span><span class="sxs-lookup"><span data-stu-id="63fff-169">However, you must qualify any reference to such a member with the appropriate module name if the reference is from outside that module.</span></span> <span data-ttu-id="63fff-170">Per altre informazioni, vedere [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="63fff-170">For more information, see [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

## <a name="example"></a><span data-ttu-id="63fff-171">Esempio</span><span class="sxs-lookup"><span data-stu-id="63fff-171">Example</span></span>

[!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]

## <a name="see-also"></a><span data-ttu-id="63fff-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63fff-172">See also</span></span>

- [<span data-ttu-id="63fff-173">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="63fff-173">Class Statement</span></span>](class-statement.md)
- [<span data-ttu-id="63fff-174">Istruzione Namespace</span><span class="sxs-lookup"><span data-stu-id="63fff-174">Namespace Statement</span></span>](namespace-statement.md)
- [<span data-ttu-id="63fff-175">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="63fff-175">Structure Statement</span></span>](structure-statement.md)
- [<span data-ttu-id="63fff-176">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="63fff-176">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="63fff-177">Property Statement</span><span class="sxs-lookup"><span data-stu-id="63fff-177">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="63fff-178">Promozione tipo</span><span class="sxs-lookup"><span data-stu-id="63fff-178">Type Promotion</span></span>](../../programming-guide/language-features/declared-elements/type-promotion.md)
