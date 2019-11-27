---
title: Parziale
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: df85571b757fd54496677bad1195fab9690b79cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351352"
---
# <a name="partial-visual-basic"></a><span data-ttu-id="448bd-102">Partial (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="448bd-102">Partial (Visual Basic)</span></span>
<span data-ttu-id="448bd-103">Indica che una dichiarazione di tipo è una definizione parziale del tipo.</span><span class="sxs-lookup"><span data-stu-id="448bd-103">Indicates that a type declaration is a partial definition of the type.</span></span>  
  
 <span data-ttu-id="448bd-104">Si può dividere la definizione di un tipo tra più dichiarazioni mediante la parola chiave `Partial`.</span><span class="sxs-lookup"><span data-stu-id="448bd-104">You can divide the definition of a type among several declarations by using the `Partial` keyword.</span></span> <span data-ttu-id="448bd-105">Si può usare il numero di dichiarazioni parziali desiderato, in un numero qualsiasi di file di origine differenti.</span><span class="sxs-lookup"><span data-stu-id="448bd-105">You can use as many partial declarations as you want, in as many different source files as you want.</span></span> <span data-ttu-id="448bd-106">Tutte le dichiarazioni, tuttavia, devono trovarsi nello stesso assembly e nello stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="448bd-106">However, all the declarations must be in the same assembly and the same namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="448bd-107">Visual Basic supporta i *metodi parziali*, che in genere sono implementati nelle classi parziali.</span><span class="sxs-lookup"><span data-stu-id="448bd-107">Visual Basic supports *partial methods*, which are typically implemented in partial classes.</span></span> <span data-ttu-id="448bd-108">Per altre informazioni, vedere [metodi parziali](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) e [istruzione secondaria](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="448bd-108">For more information, see [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) and [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="448bd-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="448bd-109">Syntax</span></span>  
  
```vb  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a><span data-ttu-id="448bd-110">Parti</span><span class="sxs-lookup"><span data-stu-id="448bd-110">Parts</span></span>  
  
|<span data-ttu-id="448bd-111">Termine</span><span class="sxs-lookup"><span data-stu-id="448bd-111">Term</span></span>|<span data-ttu-id="448bd-112">Definizione</span><span class="sxs-lookup"><span data-stu-id="448bd-112">Definition</span></span>|  
|---|---|  
|`attrlist`|<span data-ttu-id="448bd-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="448bd-113">Optional.</span></span> <span data-ttu-id="448bd-114">Elenco degli attributi applicabili al tipo.</span><span class="sxs-lookup"><span data-stu-id="448bd-114">List of attributes that apply to this type.</span></span> <span data-ttu-id="448bd-115">È necessario racchiudere l' [elenco degli attributi](../../../visual-basic/language-reference/statements/attribute-list.md) tra parentesi angolari (`< >`).</span><span class="sxs-lookup"><span data-stu-id="448bd-115">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets (`< >`).</span></span>|  
|`accessmodifier`|<span data-ttu-id="448bd-116">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="448bd-116">Optional.</span></span> <span data-ttu-id="448bd-117">Specifica il tipo di codice che può accedere al tipo.</span><span class="sxs-lookup"><span data-stu-id="448bd-117">Specifies what code can access this type.</span></span> <span data-ttu-id="448bd-118">Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="448bd-118">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`Shadows`|<span data-ttu-id="448bd-119">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="448bd-119">Optional.</span></span> <span data-ttu-id="448bd-120">Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="448bd-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>|  
|`MustInherit`|<span data-ttu-id="448bd-121">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="448bd-121">Optional.</span></span> <span data-ttu-id="448bd-122">Vedere [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="448bd-122">See [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>|  
|`NotInheritable`|<span data-ttu-id="448bd-123">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="448bd-123">Optional.</span></span> <span data-ttu-id="448bd-124">Vedere [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span><span class="sxs-lookup"><span data-stu-id="448bd-124">See [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span></span>|  
|`name`|<span data-ttu-id="448bd-125">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="448bd-125">Required.</span></span> <span data-ttu-id="448bd-126">Nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="448bd-126">Name of this type.</span></span> <span data-ttu-id="448bd-127">Deve corrispondere al nome definito in tutte le altre dichiarazioni parziali dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="448bd-127">Must match the name defined in all other partial declarations of the same type.</span></span>|  
|`Of`|<span data-ttu-id="448bd-128">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="448bd-128">Optional.</span></span> <span data-ttu-id="448bd-129">Specifica che si tratta di un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="448bd-129">Specifies that this is a generic type.</span></span> <span data-ttu-id="448bd-130">Vedere [tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="448bd-130">See [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>|  
|`typelist`|<span data-ttu-id="448bd-131">Obbligatorio se [si usa.](../../../visual-basic/language-reference/statements/of-clause.md)</span><span class="sxs-lookup"><span data-stu-id="448bd-131">Required if you use [Of](../../../visual-basic/language-reference/statements/of-clause.md).</span></span> <span data-ttu-id="448bd-132">Vedere [elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="448bd-132">See [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>|  
|`Inherits`|<span data-ttu-id="448bd-133">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="448bd-133">Optional.</span></span> <span data-ttu-id="448bd-134">Vedere [istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).</span><span class="sxs-lookup"><span data-stu-id="448bd-134">See [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md).</span></span>|  
|`classname`|<span data-ttu-id="448bd-135">Obbligatorio se si usa `Inherits`.</span><span class="sxs-lookup"><span data-stu-id="448bd-135">Required if you use `Inherits`.</span></span> <span data-ttu-id="448bd-136">Nome della classe o dell'interfaccia da cui deriva la classe.</span><span class="sxs-lookup"><span data-stu-id="448bd-136">The name of the class or interface from which this class derives.</span></span>|  
|`Implements`|<span data-ttu-id="448bd-137">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="448bd-137">Optional.</span></span> <span data-ttu-id="448bd-138">Vedere [istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="448bd-138">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>|  
|`interfacenames`|<span data-ttu-id="448bd-139">Obbligatorio se si usa `Implements`.</span><span class="sxs-lookup"><span data-stu-id="448bd-139">Required if you use `Implements`.</span></span> <span data-ttu-id="448bd-140">Nomi delle interfacce implementate dal tipo.</span><span class="sxs-lookup"><span data-stu-id="448bd-140">The names of the interfaces this type implements.</span></span>|  
|`variabledeclarations`|<span data-ttu-id="448bd-141">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="448bd-141">Optional.</span></span> <span data-ttu-id="448bd-142">Istruzioni che dichiarano variabili ed eventi aggiuntivi per il tipo.</span><span class="sxs-lookup"><span data-stu-id="448bd-142">Statements which declare additional variables and events for the type.</span></span>|  
|`proceduredeclarations`|<span data-ttu-id="448bd-143">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="448bd-143">Optional.</span></span> <span data-ttu-id="448bd-144">Istruzioni che dichiarano e definiscono routine aggiuntive per il tipo.</span><span class="sxs-lookup"><span data-stu-id="448bd-144">Statements which declare and define additional procedures for the type.</span></span>|  
|<span data-ttu-id="448bd-145">`End Class` o `End Structure`</span><span class="sxs-lookup"><span data-stu-id="448bd-145">`End Class` or `End Structure`</span></span>|<span data-ttu-id="448bd-146">Termina questa definizione `Class` o `Structure` parziale.</span><span class="sxs-lookup"><span data-stu-id="448bd-146">Ends this partial `Class` or `Structure` definition.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="448bd-147">Note</span><span class="sxs-lookup"><span data-stu-id="448bd-147">Remarks</span></span>  
 <span data-ttu-id="448bd-148">Visual Basic usa definizioni di classi parziali per separare il codice generato dal codice creato dall'utente in file di origine distinti.</span><span class="sxs-lookup"><span data-stu-id="448bd-148">Visual Basic uses partial-class definitions to separate generated code from user-authored code in separate source files.</span></span> <span data-ttu-id="448bd-149">Ad esempio, **Progettazione Windows Form** definisce classi parziali per controlli come <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="448bd-149">For example, the **Windows Form Designer** defines partial classes for controls such as <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="448bd-150">In questi controlli il codice generato non deve essere modificato.</span><span class="sxs-lookup"><span data-stu-id="448bd-150">You should not modify the generated code in these controls.</span></span>  
  
 <span data-ttu-id="448bd-151">Durante la creazione di un tipo parziale vengono applicate tutte le regole per la creazione delle classi, delle strutture, delle interfacce e dei moduli, ad esempio quelle relative all'uso dei modificatori e all'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="448bd-151">All the rules for class, structure, interface, and module creation, such as those for modifier usage and inheritance, apply when creating a partial type.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="448bd-152">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="448bd-152">Best Practices</span></span>  
  
- <span data-ttu-id="448bd-153">In condizioni normali, non è consigliabile suddividere lo sviluppo di un singolo tipo in due o più dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="448bd-153">Under normal circumstances, you should not split the development of a single type across two or more declarations.</span></span> <span data-ttu-id="448bd-154">Pertanto, nella maggior parte dei casi non occorre specificare la parola chiave `Partial`.</span><span class="sxs-lookup"><span data-stu-id="448bd-154">Therefore, in most cases you do not need the `Partial` keyword.</span></span>  
  
- <span data-ttu-id="448bd-155">Per migliorare la leggibilità, ogni dichiarazione parziale di un tipo deve includere la parola chiave `Partial`.</span><span class="sxs-lookup"><span data-stu-id="448bd-155">For readability, every partial declaration of a type should include the `Partial` keyword.</span></span> <span data-ttu-id="448bd-156">Il compilatore consente che la parola chiave venga omessa al massimo in una dichiarazione parziale. Se viene omessa in due o più dichiarazioni, viene segnalato un errore.</span><span class="sxs-lookup"><span data-stu-id="448bd-156">The compiler allows at most one partial declaration to omit the keyword; if two or more omit it the compiler signals an error.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="448bd-157">Comportamento</span><span class="sxs-lookup"><span data-stu-id="448bd-157">Behavior</span></span>  
  
- <span data-ttu-id="448bd-158">**Unione di dichiarazioni.**</span><span class="sxs-lookup"><span data-stu-id="448bd-158">**Union of Declarations.**</span></span> <span data-ttu-id="448bd-159">Il compilatore considera il tipo come l'unione di tutte le relative dichiarazioni parziali.</span><span class="sxs-lookup"><span data-stu-id="448bd-159">The compiler treats the type as the union of all its partial declarations.</span></span> <span data-ttu-id="448bd-160">Ogni modificatore di ciascuna definizione parziale si applica all'intero tipo e ogni membro di ciascuna definizione parziale è disponibile per l'intero tipo.</span><span class="sxs-lookup"><span data-stu-id="448bd-160">Every modifier from every partial definition applies to the entire type, and every member from every partial definition is available to the entire type.</span></span>  
  
- <span data-ttu-id="448bd-161">**Promozione del tipo non consentita per i tipi parziali nei moduli.**</span><span class="sxs-lookup"><span data-stu-id="448bd-161">**Type Promotion Not Allowed For Partial Types in Modules.**</span></span> <span data-ttu-id="448bd-162">Se una definizione parziale si trova all'interno di un modulo, l'effetto della promozione tipo di tale tipo viene automaticamente annullato.</span><span class="sxs-lookup"><span data-stu-id="448bd-162">If a partial definition is inside a module, type promotion of that type is automatically defeated.</span></span> <span data-ttu-id="448bd-163">In questo caso, un set di definizioni parziali può generare risultati imprevisti e persino errori del compilatore.</span><span class="sxs-lookup"><span data-stu-id="448bd-163">In such a case, a set of partial definitions can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="448bd-164">Per ulteriori informazioni, vedere [promozione del tipo](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="448bd-164">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
     <span data-ttu-id="448bd-165">Il compilatore unisce le definizioni parziali solo se i relativi percorsi completi sono identici.</span><span class="sxs-lookup"><span data-stu-id="448bd-165">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
 <span data-ttu-id="448bd-166">È possibile usare la parola chiave `Partial` nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="448bd-166">The `Partial` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="448bd-167">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="448bd-167">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="448bd-168">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="448bd-168">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## <a name="example"></a><span data-ttu-id="448bd-169">Esempio</span><span class="sxs-lookup"><span data-stu-id="448bd-169">Example</span></span>  
 <span data-ttu-id="448bd-170">L'esempio seguente suddivide la definizione della classe `sampleClass` in due dichiarazioni, ognuna delle quali definisce una routine `Sub` differente.</span><span class="sxs-lookup"><span data-stu-id="448bd-170">The following example splits the definition of class `sampleClass` into two declarations, each of which defines a different `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 <span data-ttu-id="448bd-171">Le due definizioni parziali nell'esempio precedente possono trovarsi nello stesso file di origine o in due file di origine differenti.</span><span class="sxs-lookup"><span data-stu-id="448bd-171">The two partial definitions in the preceding example could be in the same source file or in two different source files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="448bd-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="448bd-172">See also</span></span>

- [<span data-ttu-id="448bd-173">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="448bd-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="448bd-174">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="448bd-174">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="448bd-175">Promozione tipo</span><span class="sxs-lookup"><span data-stu-id="448bd-175">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
- [<span data-ttu-id="448bd-176">Shadows</span><span class="sxs-lookup"><span data-stu-id="448bd-176">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="448bd-177">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="448bd-177">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="448bd-178">Metodi parziali</span><span class="sxs-lookup"><span data-stu-id="448bd-178">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
