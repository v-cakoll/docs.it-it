---
title: Istruzione Imports - Namespace .NET e il tipo (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
ms.openlocfilehash: 93b299ffd8d2be1b1fabfd752e75d18ef87714b2
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974380"
---
# <a name="imports-statement-net-namespace-and-type"></a><span data-ttu-id="204fd-102">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="204fd-102">Imports Statement (.NET Namespace and Type)</span></span>
<span data-ttu-id="204fd-103">Consente di digitare i nomi a cui fare riferimento senza qualifica dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="204fd-103">Enables type names to be referenced without namespace qualification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="204fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="204fd-104">Syntax</span></span>  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a><span data-ttu-id="204fd-105">Parti</span><span class="sxs-lookup"><span data-stu-id="204fd-105">Parts</span></span>  
  
|<span data-ttu-id="204fd-106">Termine</span><span class="sxs-lookup"><span data-stu-id="204fd-106">Term</span></span>|<span data-ttu-id="204fd-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="204fd-107">Definition</span></span>|  
|---|---|  
|`aliasname`|<span data-ttu-id="204fd-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="204fd-108">Optional.</span></span> <span data-ttu-id="204fd-109">Un' *alias di importazione* o il nome mediante il quale il codice può fare riferimento a `namespace` anziché la stringa di qualificazione completo.</span><span class="sxs-lookup"><span data-stu-id="204fd-109">An *import alias* or name by which code can refer to `namespace` instead of the full qualification string.</span></span> <span data-ttu-id="204fd-110">Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="204fd-110">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`namespace`|<span data-ttu-id="204fd-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="204fd-111">Required.</span></span> <span data-ttu-id="204fd-112">Il nome completo dello spazio dei nomi da importare.</span><span class="sxs-lookup"><span data-stu-id="204fd-112">The fully qualified name of the namespace being imported.</span></span> <span data-ttu-id="204fd-113">Può essere una stringa di spazi dei nomi annidata a qualsiasi livello.</span><span class="sxs-lookup"><span data-stu-id="204fd-113">Can be a string of namespaces nested to any level.</span></span>|  
|`element`|<span data-ttu-id="204fd-114">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="204fd-114">Optional.</span></span> <span data-ttu-id="204fd-115">Il nome di un elemento di programmazione è dichiarato nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="204fd-115">The name of a programming element declared in the namespace.</span></span> <span data-ttu-id="204fd-116">Può essere qualsiasi elemento del contenitore.</span><span class="sxs-lookup"><span data-stu-id="204fd-116">Can be any container element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="204fd-117">Note</span><span class="sxs-lookup"><span data-stu-id="204fd-117">Remarks</span></span>  
 <span data-ttu-id="204fd-118">Il `Imports` istruzione consente i tipi che sono contenuti in un determinato spazio dei nomi a cui fare riferimento direttamente.</span><span class="sxs-lookup"><span data-stu-id="204fd-118">The `Imports`  statement enables types that are contained in a given namespace to be referenced directly.</span></span>  
  
 <span data-ttu-id="204fd-119">È possibile fornire un nome singolo spazio dei nomi o una stringa di spazi dei nomi annidati.</span><span class="sxs-lookup"><span data-stu-id="204fd-119">You can supply a single namespace name or a string of nested namespaces.</span></span> <span data-ttu-id="204fd-120">Ogni spazio dei nomi annidato è delimitato da spazio dei nomi di livello superiore successivo da un punto (`.`), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="204fd-120">Each nested namespace is separated from the next higher level namespace by a period (`.`), as the following example illustrates.</span></span>  
  
 `Imports System.Collections.Generic`  
  
 <span data-ttu-id="204fd-121">Ogni file di origine può contenere un numero qualsiasi di `Imports` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="204fd-121">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="204fd-122">Questi devono seguire le dichiarazioni di opzione, ad esempio la `Option Strict` istruzione che devono precedere qualsiasi dichiarazione di elemento di programmazione, ad esempio `Module` o `Class` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="204fd-122">These must follow any option declarations, such as the `Option Strict` statement, and they must precede any programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
 <span data-ttu-id="204fd-123">È possibile usare `Imports` solo a livello di file.</span><span class="sxs-lookup"><span data-stu-id="204fd-123">You can use `Imports` only at file level.</span></span> <span data-ttu-id="204fd-124">Ciò significa che il contesto della dichiarazione per l'importazione deve essere un file di origine e non può essere un spazio dei nomi, classe, struttura, modulo, interfaccia, routine o blocco.</span><span class="sxs-lookup"><span data-stu-id="204fd-124">This means the declaration context for importation must be a source file, and cannot be a namespace, class, structure, module, interface, procedure, or block.</span></span>  
  
 <span data-ttu-id="204fd-125">Si noti che il `Imports` istruzione non rende disponibili elementi di altri progetti e assembly al progetto.</span><span class="sxs-lookup"><span data-stu-id="204fd-125">Note that the `Imports` statement does not make elements from other projects and assemblies available to your project.</span></span> <span data-ttu-id="204fd-126">Importazione non è un'alternativa all'impostazione di un riferimento.</span><span class="sxs-lookup"><span data-stu-id="204fd-126">Importing does not take the place of setting a reference.</span></span> <span data-ttu-id="204fd-127">Rimuove solo la necessità per qualificare i nomi che sono già disponibili per il progetto.</span><span class="sxs-lookup"><span data-stu-id="204fd-127">It only removes the need to qualify names that are already available to your project.</span></span> <span data-ttu-id="204fd-128">Per altre informazioni, vedere "Importazione di elementi contenitore" nella [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="204fd-128">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="204fd-129">È possibile definire implicita `Imports` istruzioni utilizzando il [riferimenti (pagina), creazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="204fd-129">You can define implicit `Imports` statements by using the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span> <span data-ttu-id="204fd-130">Per altre informazioni, vedere [Procedura: Aggiungere o rimuovere spazi dei nomi importati (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="204fd-130">For more information, see [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
## <a name="import-aliases"></a><span data-ttu-id="204fd-131">Alias di importazione</span><span class="sxs-lookup"><span data-stu-id="204fd-131">Import Aliases</span></span>  
 <span data-ttu-id="204fd-132">Un' *alias di importazione* definisce l'alias per un tipo o dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="204fd-132">An *import alias* defines the alias for a namespace or type.</span></span> <span data-ttu-id="204fd-133">Gli alias di importazione sono utili quando è necessario usare gli elementi con lo stesso nome che vengono dichiarati in uno o più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="204fd-133">Import aliases are useful when you need to use items with the same name that are declared in one or more namespaces.</span></span> <span data-ttu-id="204fd-134">Per altre informazioni e un esempio, vedere "Qualificare un nome di un elemento" nella [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="204fd-134">For more information and an example, see "Qualifying an Element Name" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="204fd-135">Non è necessario dichiarare un membro al livello di modulo con lo stesso nome `aliasname`.</span><span class="sxs-lookup"><span data-stu-id="204fd-135">You should not declare a member at module level with the same name as `aliasname`.</span></span> <span data-ttu-id="204fd-136">Se non lo, il compilatore Visual Basic utilizza `aliasname` solo per il membro dichiarato e non sarà più lo riconosce come un alias di importazione.</span><span class="sxs-lookup"><span data-stu-id="204fd-136">If you do, the Visual Basic compiler uses `aliasname` only for the declared member and no longer recognizes it as an import alias.</span></span>  
  
 <span data-ttu-id="204fd-137">Sebbene la sintassi usata per dichiarare un alias di importazione è uguale a quella utilizzata per l'importazione di un prefisso dello spazio dei nomi XML, i risultati sono diversi.</span><span class="sxs-lookup"><span data-stu-id="204fd-137">Although the syntax used for declaring an import alias is like that used for importing an XML namespace prefix, the results are different.</span></span> <span data-ttu-id="204fd-138">Un alias di importazione è utilizzabile come espressione nel codice, mentre un prefisso dello spazio dei nomi XML può essere utilizzato solo in valori letterali XML o proprietà axis XML come prefisso per un elemento completo o il nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="204fd-138">An import alias can be used as an expression in your code, whereas an XML namespace prefix can be used only in XML literals or XML axis properties as the prefix for a qualified element or attribute name.</span></span>  
  
### <a name="element-names"></a><span data-ttu-id="204fd-139">Nomi di elementi</span><span class="sxs-lookup"><span data-stu-id="204fd-139">Element Names</span></span>  
 <span data-ttu-id="204fd-140">Se si specificano `element`, dovrà rappresentare un *elemento contenitore*, vale a dire un elemento di programmazione che può contenere altri elementi.</span><span class="sxs-lookup"><span data-stu-id="204fd-140">If you supply `element`, it must represent a *container element*, that is, a programming element that can contain other elements.</span></span> <span data-ttu-id="204fd-141">Elementi contenitore includono classi, strutture, moduli, interfacce ed enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="204fd-141">Container elements include classes, structures, modules, interfaces, and enumerations.</span></span>  
  
 <span data-ttu-id="204fd-142">L'ambito degli elementi messe a disposizione da un `Imports` istruzione dipende dal fatto che vengano specificati `element`.</span><span class="sxs-lookup"><span data-stu-id="204fd-142">The scope of the elements made available by an `Imports` statement depends on whether you specify `element`.</span></span> <span data-ttu-id="204fd-143">Se si specifica solo `namespace`, tutto in modo univoco denominate membri dello spazio dei nomi e i membri degli elementi contenitore all'interno di tale spazio dei nomi, sono disponibili senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="204fd-143">If you specify only `namespace`, all uniquely named members of that namespace, and members of container elements within that namespace, are available without qualification.</span></span> <span data-ttu-id="204fd-144">Se si specificano entrambe `namespace` e `element`, solo i membri di tale elemento sono disponibili senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="204fd-144">If you specify both `namespace` and `element`, only the members of that element are available without qualification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="204fd-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="204fd-145">Example</span></span>  
 <span data-ttu-id="204fd-146">Nell'esempio seguente restituisce tutte le cartelle nella directory c:\. utilizzando il <xref:System.IO.DirectoryInfo> classe.</span><span class="sxs-lookup"><span data-stu-id="204fd-146">The following example returns all the folders in the C:\ directory by using the <xref:System.IO.DirectoryInfo> class.</span></span>  
  
 <span data-ttu-id="204fd-147">Il codice non ha alcun `Imports` istruzioni all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="204fd-147">The code has no `Imports` statements at the top of the file.</span></span> <span data-ttu-id="204fd-148">Pertanto, il `DirectoryInfo`, <xref:System.Text.StringBuilder>, e <xref:Microsoft.VisualBasic.ControlChars.CrLf> riferimenti sono tutte completamente qualificati con gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="204fd-148">Therefore, the `DirectoryInfo`, <xref:System.Text.StringBuilder>, and <xref:Microsoft.VisualBasic.ControlChars.CrLf> references are all fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a><span data-ttu-id="204fd-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="204fd-149">Example</span></span>  
 <span data-ttu-id="204fd-150">L'esempio seguente include `Imports` istruzioni per gli spazi dei nomi cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="204fd-150">The following example includes `Imports` statements for the referenced namespaces.</span></span> <span data-ttu-id="204fd-151">Di conseguenza, i tipi non sono necessario essere completo con gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="204fd-151">Therefore, the types do not have to be fully qualified with the namespaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a><span data-ttu-id="204fd-152">Esempio</span><span class="sxs-lookup"><span data-stu-id="204fd-152">Example</span></span>  
 <span data-ttu-id="204fd-153">L'esempio seguente include `Imports` istruzioni che creano gli alias per gli spazi dei nomi cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="204fd-153">The following example includes `Imports` statements that create aliases for the referenced namespaces.</span></span> <span data-ttu-id="204fd-154">I tipi sono qualificati con gli alias.</span><span class="sxs-lookup"><span data-stu-id="204fd-154">The types are qualified with the aliases.</span></span>  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a><span data-ttu-id="204fd-155">Esempio</span><span class="sxs-lookup"><span data-stu-id="204fd-155">Example</span></span>  
 <span data-ttu-id="204fd-156">L'esempio seguente include `Imports` istruzioni che creano gli alias dei tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="204fd-156">The following example includes `Imports` statements that create aliases for the referenced types.</span></span> <span data-ttu-id="204fd-157">Gli alias vengono utilizzati per specificare i tipi.</span><span class="sxs-lookup"><span data-stu-id="204fd-157">Aliases are used to specify the types.</span></span>  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a><span data-ttu-id="204fd-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="204fd-158">See also</span></span>
- [<span data-ttu-id="204fd-159">Istruzione Namespace</span><span class="sxs-lookup"><span data-stu-id="204fd-159">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="204fd-160">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="204fd-160">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="204fd-161">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="204fd-161">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="204fd-162">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="204fd-162">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="204fd-163">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="204fd-163">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
